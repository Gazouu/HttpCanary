### Protocole WebSocket

#### 1. Le format du protocole WebSocket

WebSocket est un protocole de communication full-duplex sur une seule connexion TCP. Pour établir une connexion WebSocket, le client doit d'abord envoyer une requête HTTP au serveur. Cette requête est différente de la requête HTTP commune, elle contient quelques en-têtes supplémentaires. L'en-tête supplémentaire "Upgrade : WebSocket" indique qu'il s'agit d'une requête HTTP qui s'applique à la mise à niveau du protocole. Le serveur analyse ces en-têtes supplémentaires et génère un message de réponse au client, et la connexion WebSocket entre le client et le serveur est établie. Les deux parties peuvent alors transmettre librement des informations par ce canal de connexion. La connexion existera jusqu'à ce que le client ou le serveur la ferme activement.


Voici le processus d'interaction du protocole Websocket :

![](/assets/websockets_diagram.png)

#### 2. Visionneuse de protocole WebSocket

HttpCanary prend en charge l'analyse du protocole WebSocket, et affiche l'interaction des données entre le client et le serveur sous forme de dialogue.

![](/assets/websockets_overview.png)







