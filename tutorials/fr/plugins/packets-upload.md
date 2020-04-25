### Téléchargement de paquets

Ce plugin peut empaqueter et télécharger les fichiers par paquets vers le serveur spécifié. Si le téléphone mobile et l'ordinateur se trouvent dans le même réseau local, vous pouvez utiliser l'ordinateur comme serveur local, les fichiers de paquets de données du téléphone mobile peuvent alors être synchronisés automatiquement avec l'ordinateur. Vous pouvez également configurer le téléchargement vers un serveur distant. En outre, le téléchargement de paquets de données est déclenché chaque fois que la capture de paquets est arrêtée.


**Ce plugin est disponible en version premium**

Le but de ce tutoriel est d'expliquer comment configurer un serveur local sur votre ordinateur, puis de télécharger les paquets réseau capturés par HttpCanary sur votre ordinateur.

#### Configurer le fichier du plugin HttpCanary 

Configurez l'adresse IP et le port de l'ordinateur dans /HttpCanary/plugins/PacketsUpload/config.json, par exemple, 192.168.1.4:9090. Nous pouvons également configurer un en-tête personnalisé (facultatif).

```json
{
  "hello": "ok",
  "server": "http://192.168.1.4:9090"
}
```

#### Configure local server

Dans ce tutoriel, nous utilisons Nodejs pour construire rapidement le serveur. Vous pouvez utiliser d'autres frameworks à la place. Le code Nodejs pour le serveur a été fourni sur github et peut être exécuté directement,
[Cliquez ici](https://github.com/MegatronKing/HttpCanary/tree/master/plugins/PacketsUpload)。

##### 1. Installer nodejs

Vous devez d'abord installer nodejs. Vous pouvez le télécharger à partir du[site officiel] (https://nodejs.org) ou vous pouvez utiliser le gestionnaire de paquets qui est fourni avec votre ordinateur.

##### 2. Configurer le code du serveur

Téléchargez les deux fichiers ci-dessus, app.js et package.json, et mettez-les dans le même répertoire :
```
    .
    ├── app.js
    └── package.json
```

Exécutez la commande npm pour installer les dépendances :
```
npm install
```

##### 3. Démarrer le serveur

Exécutez la commande suivante pour démarrer le serveur :
```
node app.js
```

Faites des opérations sur votre téléphone portable. Après avoir terminé la capture de paquets, vous pouvez voir le fichier de paquets synchronisés dans le dossier du serveur ! Le format du fichier de paquets de données est le format binaire hcy. Il n'y a pas de logiciel correspondant du côté du PC pour l'ouvrir directement, mais vous pouvez utiliser les fichiers HEX et autres pour l'analyse.


##### 4. Attentions

**Pour votre confidentialité, veuillez ne pas configurer les adresses de serveurs provenant de sources inconnues**