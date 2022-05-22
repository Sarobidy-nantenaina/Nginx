# INSTALLATION ET CONFIGURATION DU SERVEUR  NGINX  

### INSTALLATION :
 * commande :
    * sudo apt update -y
    * sudo apt install nginx -y

#### Lorsque l'installation est effectuée, on peut regarder quelle version est installée à l'aide de la commande suivante (similaire à celle d'Apache ou d'autres paquets) :
  * sudo nginx -v
#### Suite à l'installation, le serveur Nginx est déjà démarré, on peut le vérifier avec la commande ci-dessous. Cela permettra de voir qu'il est bien actif:
  * sudo systemctl status nginx  
  ![Nginx Sarobidy-nantenaina](https://www.it-connect.fr/wp-content-itc/uploads/2021/06/install-nginx-debian-01.png)  
#### Pour que notre serveur Web Nginx démarre automatiquement lorsque la machine Linux démarre ou redémarre, on doit exécuter la commande suivante :
 * sudo systemctl enable nginx
#### Dès à présent, on peut accéder à la page par défaut du serveur Web à partir d'un navigateur. Si votre machine où est installé Nginx dispose d'une interface graphique, on peut y accéder en local :
 * http://127.0.0.1
#### À partir d'une machine distante, utilisez l'adresse IP de votre serveur Web plutôt que l'adresse de loopback (127.0.0.1). Voici la page qui doit s'afficher :  

 ![Nginx Sarobidy-nantenaina](https://www.it-connect.fr/wp-content-itc/uploads/2021/06/install-nginx-debian-02.png)  

#### Le contenu de cette page Web correspond au fichier suivant :
  * /var/www/html/index.nginx-debian.html  
#### En fait, le site par défaut de Nginx est déclaré dans le fichier de configuration suivant :
  * /etc/nginx/sites-enabled/default

  ![Nginx Sarobidy-nantenaina](https://www.it-connect.fr/wp-content-itc/uploads/2021/06/nginx-default-website.jpg)  

#### La racine de ce site est :  
  * /var/www/html
#### On peut le vérifier grâce à la directive suivante :
  * root /var/www/html;

  ------------------------------------------------------------------------------------------

 ### CONFIGURATION DU SERVEUR Nginx :

 #### Le fichier de configuration global de Nginx est :
 * /etc/nginx/nginx.conf
 #### Le dossier qui contient les fichiers de configuration des sites disponibles est :
 * /etc/nginx/sites-available/
 #### Le dossier qui contient les fichiers de configuration des sites actifs est :
 * /etc/nginx/sites-enabled/

 ##### Lorsque l'on crée la configuration d'un nouveau site, on crée le fichier dans "sites-available" et ensuite lorsque le site est prêt à être activé, on crée un lien symbolique vers "sites-enabled". Cela tombe bien, nous allons créer notre premier site Web dans Nginx : l'occasion de voir ce mécanisme, identique à Apache.