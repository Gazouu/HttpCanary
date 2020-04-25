### Installation

####  1. Configuration du VPN（Nécessaire）

HttpCanary utilise le VPN comme un MITM (Man in the Middle) pour capturer les paquets du réseau, vous devez donc d'abord configurer le VPN.

![](/assets/install_vpn.png)

<br>

####  2. Installer le certificat root（Necessary）

**En raison des limitations du système Android, vous devez dessiner le verrouillage de l'écran de votre téléphone ou entrer le mot de passe du téléphone lors de l'installation du certificat. Si vous ne les avez pas définis, vous devez d'abord définir un verrou d'écran ou un mot de passe.**

HttpCanary utilise la technologie MITM (Man in the Middle) pour capturer les paquets de réseau ou pour décrypter les paquets de réseau qui ont été cryptés avec TLS/SSL dans les requêtes des protocoles HTTPS, WSS, etc. Vous devez donc d'abord installer le certificat racine de HttpCanary. Pendant l'installation, cliquez sur OK par défaut. Ne modifiez pas la configuration.

![](/assets/install_user_cetificate.png)

<br>

####  3. Mettre à niveau le certificat en certificat de système（7.0+ Fortement recommandé）

**Cette étape nécessite un dispositif Root. Il est fortement recommandé de faire cette configuration pour les systèmes avec Android 7.0 et plus. Sauter cette étape pour les systèmes 5.0-6.0.**

Depuis Android 7.0(Android N), Google a modifié la politique de sécurité du réseau. Par défaut, le certificat de l'autorité de certification installé par l'utilisateur ne sera pas pris en compte par la connexion TLS/SSL. Cela signifie que HttpCanary peut ne pas capturer les paquets qui sont cryptés avec TLS/SSL et ne peut pas se connecter au réseau pendant la capture des paquets. Par conséquent, vous devez mettre à niveau le certificat installé à la dernière étape vers le certificat de l'autorité de certification du système.

##### 3.1 Première méthode：Mise à jour en un clic dans HttpCanary 

![](/assets/install_system_cetificate.png)

Cette méthode peut échouer. Si elle échoue, veuillez vous référer aux autres méthodes ci-dessous.

##### 3.2 Deuxième méthode：Importation manuelle(Root nécessaire)

Tout d'abord, exportez le fichier de certificat qui a été installé à l'étape 2. Vous le trouverez dans le répertoire /data/misc/user/0/cacerts-added/ (vous devez faire la distinction par l'attribut temporel du fichier s'il y a plusieurs fichiers). Vous pouvez également l'exporter sur une carte SD dans les paramètres du certificat racine de HttpCanary.

![](/assets/cetificate_export.png)

Copiez le fichier .0 (ne modifiez pas son nom) dans le répertoire CA du système : /system/etc/security/cacerts/.

Il existe plusieurs moyens :

- Utilisez les commandes adb pour copier,

Cette méthode nécessite l'installation d'outils adb, elle convient donc aux développeurs Android. Si les outils adb ne sont pas installés, veuillez vous référer à d'autres méthodes.

```shell
# 87bc3517.0 est un exemple, vous devez le remplacer par le vrai nom du fichier
adb root
adb shell
mount -o rw,remount /system
cp -f /sdcard/HttpCanary/87bc3517.0 /system/etc/security/cacerts
```

- Utilisation d'applications pouvant fonctionner sur des fichiers système pour effectuer des opérations de copie et de modification, telles que le gestionnaire MT 2.

Utilisez le gestionnaire MT 2 pour importer le fichier de certificat, et copiez le fichier de certificat au format .0 dans le répertoire /system/etc/security/cacerts directement (il faut monter la partition système avec le statut de lecture et d'écriture).

![](/assets/cetificate_move.png)

##### 3.3 Vérifier après une mise à niveau réussie

Après une mise à niveau réussie, vous pouvez trouver le certificat HttpCanary correspondant sous Paramètres -> Chiffrement et références
-> Références de confiance -> Système.

![](/assets/cetificate_trust.png)

##### 3.4 Attention

- Cette opération doit être effectuée sur des appareils ayant un privilège de base
- Il n'est pas nécessaire de le configurer pour les appareils sous Android 7.0
- La mise à niveau/le redémarrage du système Android peut supprimer ou réinitialiser le fichier de certificat du système. Veuillez vérifier et réimporter
- Après avoir mis à niveau le certificat du système, ne pas désinstaller le certificat d'utilisateur qui a été installé à l'étape 2

<br>

####  4. Ajouter un certificat à Mozilla Firefox

Mozilla Firefox est adapté pour capturer les paquets de pages web, mais il utilise un certificat CA non système pour authentication，So ; le certificat système de HttpCanary ne fonctionne pas. Vous devez ajouter le certificat à Firefox manuellement.

![](/assets/cetificate_firefox1.png)

Ouvrez la page d'installation du certificat Firefox de HttpCanary, cliquez sur "Installer" et choisissez Firefox. Sélectionnez toutes les options dans la boîte de dialogue d'installation du certificat Firefox qui s'ouvre automatiquement et cliquez sur "Confirmer" (**Veuillez sélectionner toutes les options**).

![](/assets/cetificate_firefox2.png)

<br>

####  5. Installer un espace parallèle (fortement recommandé pour les versions 7.0 - 9.0 d'Android qui ne sont pas des périphériques racine)

Pour les utilisateurs non root, dont la version du système est Android 7.0 ou supérieure, il est fortement recommandé d'installer un espace parallèle pour faciliter la capture de paquets. Les appareils équipés d'Android 5.0-6.0 et 10.0+ peuvent ignorer cette étape.

**Attention：L'espace parallèle ne prend pas en charge la version Q d'Android**

Des dispositifs root sont nécessaires pour mettre à niveau le certificat en certificat de système. Par conséquent, les utilisateurs qui ne peuvent pas utiliser le périphérique racine peuvent utiliser l'espace parallèle pour faciliter la capture de paquets, ce qui peut résoudre le problème de l'impossibilité de se connecter au réseau pendant la capture de paquets dans certaines applications.

##### 5.1 Installation

Après avoir initialisé HttpCanary, trouvez l'entrée pour installer l'espace parallèle dans les paramètres de HttpCanary. S'il s'agit d'un appareil 64 bits, deux options d'installation d'espace parallèle seront affichées. Veuillez les installer une par une. Les téléphones mobiles avec Android 8.0 et plus restreindront la source d'installation pendant l'installation. Veuillez choisir "Autoriser l'installation" (vous pouvez désactiver les autorisations après avoir terminé l'installation).


![](/assets/install_paralle_space.png)

**Attention : Vous devez utiliser la version intégrée de l'espace parallèle de HttpCanary, et la capture de paquets sera invalide dans la version supérieure de l'espace parallèle**


##### 5.2 L'utilisation de l'espace parallèle

Pour certaines applications qui ne peuvent pas se connecter au réseau pendant la capture de paquets, vous pouvez utiliser l'espace parallèle pour l'ouvrir (ouvrir l'application cible, pas HttpCanary).


![](/assets/paralle_space_capture.png)

Utilisez HttpCanary pour capturer les paquets de l'espace parallèle, puis vous pouvez capturer les paquets de l'application cible.

---

#### Summary

- Pour les téléphones mobiles dont la version d'Android est inférieure à Android 7.0, la mise à niveau vers le certificat système n'est pas nécessaire et l'installation d'un espace parallèle n'est pas non plus nécessaire. Il est très convivial de capturer des paquets.

- Pour les téléphones mobiles dont la version du système est 7.0 et supérieure, mettre à jour le certificat si le système est enraciné, installer un espace parallèle si le système n'est pas enraciné.

**C'est la fin du tutoriel d'installation ! Commencez à utiliser HttpCanary avec plaisir !**






