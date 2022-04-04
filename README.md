## Installation de laravel avec Docker

Pour se faire il a fallu dans un premier temps installer WSL2 et une distribution Linux (Debian dans mon cas).
Une fois Debian installé, il faut l'activer sous Docker et relancer le service.

Il faut ensuite lancer debian et éxécuter la commande : 

  ```curl -s "https://laravel.build/minimalist-blog-laravel" | bash```
  
  
Une fois l'éxcution fini éxécuter les commandes suivantes : 

  ```cd minimalist-blog-laravel
 
  ./vendor/bin/sail up -d```
