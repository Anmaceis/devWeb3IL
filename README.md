## Installation de laravel avec Docker

Pour se faire il a fallu dans un premier temps installer WSL2 et une distribution Linux (Debian dans mon cas).
Une fois Debian installé, il faut l'activer sous Docker et relancer le service.

Il faut ensuite lancer debian et éxécuter la commande : 

  ```curl -s "https://laravel.build/minimalist-blog-laravel" | bash```
  
  
Une fois l'éxcution fini éxécuter les commandes suivantes : 

  ```cd minimalist-blog-laravel```
  ```./vendor/bin/sail up -d```
  
  
 
## Erreur avec composer

Dans le cas ou composer ne se lancerais pas pour des problèmes de droit taper la commande suivante :

```chmod -R 666 ../minimalist-blog-laravel```


## Bien compiler l'application

Après de grosse modification sur le code du site, il faut bien penser à relancer la commande :

```npm run dev```

Cette commande aura pour effet de recompiler le code et d'appliquer les modifications


## Rappel GIT

Après des modifications il faut bien penser à effectuer plusieurs étapes :

Récupérer le code du dépot distant au cas où des choses ont étés modifiés ou ajouté : 

```git pull```

Une fois le code récupéré, récupérer tout les éléments modifiés : 

```git add *```

Donner la nature du commit :

```git commit -m "Fix bug of \App\Models\Post" ```


Pousser le tout sur le dépôt distant :

```git push```
