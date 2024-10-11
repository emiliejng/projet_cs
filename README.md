Projet Emilie JIANG

Ce projet permet de contrôler une LED et de lire les valeurs d'un potentiomètre via une interface web, en utilisant un ESP32 comme serveur WebSocket. On peut accéder en haut à droite à 3 pages (LED, POTENTIOMETER, SWITCH) via mon site:
J'ai donc 3 différents code HTML en plus de "style_site.css" que j'ai créé pour la partie esthétique de mon site et du code HTML de la page principale de mon site "site.html".


Fichiers créés 

- `led.html` : interface pour le contrôle de la LED
- `potentiometer.html` : interface pour visualiser les valeurs du potentiomètre + permet de contrôler l'intensité de la LED
- `style_site.css` : feuille de style pour l'apparence du site.
- `site.html` : site "principal"
- `images/` : contient les images pour l'interface (Hello Kitty, LOGO LinkedIn, etc.).
- Le code Arduino pour gérer les WebSockets et contrôler le matériel.


- "led.html": sert à allumer ou éteindre la LED à distance.
- "potentiometer.html" : sert afficher en temps réel la valeur lue par le potentiomètre mais permet également de contrôler la l'intensité de la LED sur la breadboard.


Le projet est divisé en deux parties :
1. Une interface web pour envoyer des commandes et lire les données.
2. Un microcontrôleur ESP32 pour recevoir les commandes via WebSocket et exécuter les actions correspondantes.


Matériel que j'ai utilisé

- ESP32 (modèle utilisé : Adafruit QT Py ESP32-C3)
- LED avec résistance de 120Ω
- Potentiomètre
- Câblage de base (fils de connexion, breadboard)


Installation

J'ai commencé par connecter la LED avec une résistance de 120Ω au GPIO 8 de l'ESP32.
Je me suis ensuite connecter le potentiomètre au GPIO 0 pour la lecture analogique.
   
- J'ai utilisé l'IDE Arduino avec la bibliothèque WebSockets installée.
- J'ai modifié le fichier Arduino pour y inclure vos identifiants Wi-Fi :
     ```cpp
    const char* ssid = "PoleDeVinci_IFT";
    const char* password = "*c.r4UV@VfPn_0";

     ```
- Finalelent j'ai sélectionné la carte ESP32 et téléverser le code.

--> démarrage du serveur WebSocket** :
   
   - Une fois que le code est "téléversé", l'ESP32 s'est connecté au Wi-Fi et a lancé le serveur WebSocket.
   - L'IP du serveur s'est'affichée dans le moniteur série.



LED

- On commence par se rendre sur le site (site.html) et on appuie sur "LED".
- Nous avons deux boutons : "Turn LED On" et "Turn LED OFF" qui servent respectivement à allumer et éteindre la LED. 


Potentiomètre

1. Accédez à `potentiometer.html` pour visualiser la valeur actuelle du potentiomètre.
2. La valeur du potentiomètre est mise à jour en temps réel.



Problèmes rencontrés 

- Délai de mise à jour : Un petit délai dans la réponse de la LED ou de la lecture du potentiomètre peut être dû à la latence du réseau ou au délai programmé dans le code.


demo LED : https://youtube.com/shorts/1KDXcCYTI-I?feature=share

demo potentiomètre : https://youtube.com/shorts/OiS3O_y36lI?si=UCZo8YOwirU1KfvI

demo PUSH : https://youtube.com/shorts/ite0CF_G5eA?si=iyyBnj-L_NNrXcb9





