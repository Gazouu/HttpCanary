### HTTP

#### 1. Le format du message HTTP

HTTP est la forme abrégée de Hypertext Transfer Protocol, qui est basé sur le protocole TCP de la couche transport.

Tout d'abord, vous devez apprendre le format du message HTTP, voici un exemple pour une demande et une réponse HTTP simple.

Requête:
```
GET /index.html HTTP/1.1
Host: www.httpcanary.com
```
La première ligne est la ligne de demande, la deuxième ligne est l'en-tête de la demande (une demande HTTP peut avoir plus d'un en-tête de demande). Si la méthode de requête est POST, il y aura également un corps de requête.

Message de réponse :
```
HTTP/1.1 200 OK
Server: Apache
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8
Content-Length: 12

Hello World!
```
La première ligne est la ligne de réponse, les deuxième à quatrième lignes sont les en-têtes de réponse, la dernière ligne est le corps de réponse.

Dans la pratique, le format du HTTP est beaucoup plus complexe que cet exemple. Vous pouvez obtenir plus de détails à partir de ce [lien](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview).


#### 2. Visionneuses HTTP

HttpCanary prend en charge l'analyse des paquets HTTP dans différentes versions, y compris HTTP/1.0, HTTP/1.1 et HTTP/2, et fournit une variété de vues d'opération.

Dans la page de contenu du paquet, vous pouvez glisser vers la gauche ou vers la droite pour passer de la requête HTTP à la réponse. Ensuite, vous pouvez cliquer sur les balises ci-dessous pour passer d'un affichage à l'autre.

##### 2.1 Vue d'ensemble

Voici un aperçu du contenu d'une demande et d'une réponse dont le protocole est HTTP/1.1:

![](/assets/http_overview.png)

La page d'aperçu affiche les propriétés de base d'une requête HTTP, notamment l'URL, les informations sur le serveur, le contenu, l'heure, la taille de la requête, etc.

##### 2.2 Visionneuse raw

Le Raw Viewer affiche les données brutes d'une requête HTTP (les données dans HTTP/2 seront automatiquement transformées en HTTP/1.x). Vous pouvez faire une longue pression sur le contenu pour le copier.

![](/assets/http_raw.png)

##### 2.3 Headers Viewer

La visionneuse d'en-têtes affiche les en-têtes des demandes et des réponses. Vous pouvez taper sur les éléments de l'en-tête pour effectuer d'autres opérations.

![](/assets/http_headers.png)

##### 2.4 Visionneuse HEX

HttpCanary fournit le visualiseur HEX qui affiche le corps de la requête et de la réponse en hexadécimal. Cette vue peut aider les développeurs à analyser le format de données des paquets. 

![](/assets/http_hex.png)

##### 2.5 Visionneuse de texte

La visionneuse de texte affiche le corps de la demande et le corps de la réponse au format texte. Le contenu des paquets sera automatiquement décodé en texte. Il prend en charge les formats tels que gzip, chunked, Brotli, etc.

![](/assets/http_text.png)

Remarque : Le contenu non textuel sera affiché dans un code désordonné.

##### 2.6 Visionneuse

HttpCanary prend en charge le formatage et la prévisualisation des données de certains formats de données, tels que json, images, audio et vidéo.

Par exemple, le contenu json sera formaté automatiquement :

![](/assets/http_preview.png)

##### 2.7 Visionneuse de JSON

Bien que l'aperçu prenne déjà en charge le formatage du contenu json, HttpCanary fournit toujours un visualiseur JSON professionnel et coloré, auquel on peut accéder en tapant sur le contenu de l'aperçu. La vue JSON prend en charge la fermeture et l'expansion des nœuds JSON, et vous pouvez cliquer sur les nœuds pour plus d'opérations.


![](/assets/http_json.png)

##### 2.8 Visionneuse d'images

HttpCanary permet de prévisualiser le contenu de l'image. Vous pouvez taper sur l'image dans la page de contenu pour entrer dans le mode de prévisualisation de l'image, utiliser le geste pour faire un zoom avant et arrière, et taper sur le coin supérieur droit pour enregistrer.

![](/assets/http_image.png)

La vue des images prend en charge non seulement les images animées (format .gif, .webp, etc.), mais aussi les images statiques (format .jpg et .png, etc.).

##### 2.9 Visionneuse audio

HttpCanary supporte la lecture de contenu audio, y compris les formats audio standard tels que mp3, wav, aac, ogg ect...

![](/assets/http_audio.png)

##### 2.10 Visionneuse vidéo

HttpCanary prend également en charge la lecture de contenus vidéo, y compris les formats vidéo standard tels que mp4, wav, etc.

![](/assets/http_video.png)

##### 2.11 Visionneuse d'URL

Certaines URL peuvent contenir une quantité de paramètres, vous pouvez appuyer sur l'URL et accéder au visualiseur d'URL. Dans cette visionneuse, vous pouvez prévisualiser les paramètres fractionnés et effectuer des opérations sur ceux-ci.

![](/assets/http_url.png)

##### 2.12 Visualisation des cookies

Les cookies sont des données couramment utilisées dans les pages web. HttpCanary a conçu un visualiseur de cookies correspondant qui affiche le contenu des cookies et le contenu des sets de cookies.

![](/assets/http_set-cookie.png)
![](/assets/http_cookie.png)

<br>

#### 3. Sauvegarder et partager les paquets HTTP

##### 3.1 Sauvegarde

Dans la page de contenu du paquet, cliquez sur le bouton de sauvegarde dans le coin supérieur droit pour sauvegarder les données du paquet capturées. Le répertoire cible est le répertoire HttpCanary/download dans sdcard. Deux fichiers sont enregistrés, l'un est un paquet de données original au format .hcy, et l'autre est le contenu du corps de la demande ou du corps de la réponse.


![](/assets/http_save.png)

En outre, le format .hcy peut être ouvert à nouveau avec HttpCanary dans le gestionnaire de fichiers.

##### 3.2 Partager

Pour le partage HTTP, vous pouvez choisir de partager la demande ou la réponse séparément, ou choisir de partager ensemble. Certaines applications ne permettent pas de partager ensemble, comme WeChat et QQ.

![](/assets/http_share.png)



