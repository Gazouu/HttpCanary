### Protocole TCP/UDP

#### 1. Format du protocole TCP/UDP

Le TCP et l'UDP sont deux protocoles de la couche transport. La couche transport de la plupart des protocoles de réseau est basée sur ces deux protocoles, tels que HTTP, XMPP, MQTT, RTSP, etc. HttpCanary prend en charge l'analyse du protocole TCP/UDP. Si la couche application utilise le protocole HTTP, elle sera automatiquement analysée au format HTTP. Si la couche application utilise un protocole inconnu, elle sera affichée dans le format de données original de TCP/UDP.

#### 2. Visionneuse de protocole TCP/UDP

Comme les paquets réseau originaux de TCP/UDP sont presque en format binaire, HttpCanary sera déformé lorsqu'il sera affiché sous forme de texte. La flèche gauche indique que ce paquet de données est un paquet envoyé du client au serveur et la flèche droite indique que ce paquet de données est un paquet envoyé du serveur au client.

![](/assets/tcp_udp_text.png)

Il est recommandé d'utiliser le visualiseur HEX lors de l'analyse des paquets TCP/UDP. En analysant le format des données binaires, vous pouvez spéculer sur le protocole de la couche application des paquets. Comme HttpCanary ne prend en charge que certaines parties du protocole de la couche application, l'identification et l'analyse des autres protocoles de la couche application doivent être effectuées par vous-même.

![](/assets/tcp_udp_hex.png)

Dans le menu "plus", il y a quelques opérations telles que la sauvegarde, le partage, la copie et le changement d'affichage du contenu du protocole.

![](/assets/tcp_udp_more.png)






