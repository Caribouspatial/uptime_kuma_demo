# Prérequis

- VM kali linux de sécurité des réseaux
- docker
- docker compose
- git
- avoir les ports : 8080 et 3001 libres

### Instalation du code

git clone https://github.com/Caribouspatial/uptime_kuma_demo.git

### Notification

Aller dans paramètre serveur -> intégration -> webhooks
 
Ajouter un webhook et copier son lien (n'oubliez pas d'enregistrer les modifications)

Dans le répertoire Gatus :
"nano config.yaml"

À la ligne 7 remplacer "WEBHOOK_ICI" par votre webhook.

### Lancement

"Docker compose up -d" à la racine du dossier clonné.

Vérifier avec "docker ps" que les dockers sont bien en fonctionnement et que Uptime-Kuma a fini de charger.

### Vérification:

Ouvrez un navigateur et 2 onglets et aller sur les sites http://localhost:3001 et http://localhost:8080

Pour Gatus, sa configuration fixe est déjà faite.

Pour Uptime-Kuma créer vous un compte qui se sauvegarde sur votre navigateur.

Ensuite cliquer sur ajouter une sonde.
Garder le type HTTP(s), mettez un nom d'affichage aux choix, URL: http://demo-web,
une interval de 20 sec minimum, puis sauvegarder.

Ensuite ajouter une notification pour la sonde, choisissez discord et un lien webhook (le même que Gatus peut être utilisé)

### Test 
Faite un "docker stop demo-web"

Normalement, vous recevrez deux notifications discord.

Exercisse terminé