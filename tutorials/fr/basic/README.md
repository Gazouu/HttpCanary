### Usage de base

HttpCanary permet de capturer les paquets qui utilisent TCP ou UDP dans la couche transport, mais ne peut analyser que les paquets dont le protocole de la couche application est HTTP ou WebSocket. Les paquets avec d'autres protocoles de la couche application seront affichés en tant que données brutes et marqués comme TCP ou UDP.

![](/assets/main_page.png)

L'image ci-dessus montre les enregistrements dans différents protocoles : 1er - HTTP, 2e - TCP, 3e - UDP, 4e - Websocket.

Voyons le format des données des protocoles suivants. 

- [Protocole HTTP](/basic/http.md)
- [Protocole WebSocket](/basic/websocket.md)
- [Protocoles basés sur TCP/UDP](/basic/tcp-udp.md)