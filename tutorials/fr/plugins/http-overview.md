### Aperçu HTTP

Ce plugin est utilisé pour rassembler les statistiques des paquets HTTP et générer le rapport dans des fichiers Excel. Ces fichiers sont enregistrés sous /HttpCanary/plugins/StatsOverview .

**Pour une version gratuite de HttpCanary, ce plugin est disponible pendant la période d'essai.

Voici les statistiques en aperçu :
- url
- serveur ip
- version du protocole
- méthode de demande
- code de réponse
- Horodatage de la demande de départ
- l'horodatage du début de la réponse
- l'heure de la réponse finale
- taille des données de la demande
- taille des données de la réponse
- la durée entre le début de la demande et le début de la réponse
- le délai entre le début de la demande et la fin de la réponse

**Remarque**
- L'horodatage du début de la réponse est le point qui a reçu le code de réponse, l'horodatage de la fin de la réponse est le point qui a reçu toutes les données de la réponse.

Voici un exemple de fichier Excel qui contient les statistiques.

[Fichier de démonstration](https://raw.githubusercontent.com/MegatronKing/HttpCanary/master/plugins/HttpOverview/http-overview.xls)