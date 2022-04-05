## Erreur au lancement de Docker

Si vous avez une erreur mentionnant le port 3306 lors de votre lancement de Docker, c'est surement que un processus mysql tourne déjà en fond.
Pour le trouver ouvrer un terminal est tapé :

```netstat -nao```

Cherchez dans la liste la ligne mentionnant le port, par exemple : 

![image](https://user-images.githubusercontent.com/61062487/161768608-01f1709e-7062-4bf8-861a-36b39b58a100.png)

Tout à droite de cette ligne vous trouvez un ID, ici 5060. 
Ouvrez le moniteur de ressource et dans processeur cherchez qu'elle processus possède le PID 5060 et une fois trouvez faites clique droit et _Terminer l'arborescence du processus_

## Installation de laravel avec Docker

[Lien vers la doc Laravel](https://laravel.com/docs/9.x)

Pour se faire il a fallu dans un premier temps installer [WSL2](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi) et une distribution Linux ([Debian](https://www.microsoft.com/fr-fr/p/debian/9msvkqc78pk6?activetab=pivot:overviewtab) dans mon cas).
Une fois Debian installé, il faut l'activer sous Docker (comme sur l'image ci-dessous) et relancer le service.

![image](https://user-images.githubusercontent.com/61062487/161767507-2bb60ebc-d9ae-4e86-8e7f-538e85a0b9fd.png)

Il faut ensuite lancer debian et éxécuter la commande : 

  ```curl -s "https://laravel.build/minimalist-blog-laravel" | bash```
  
Une fois l'éxcution fini éxécuter les commandes suivantes : 

  ```cd minimalist-blog-laravel```
  ```./vendor/bin/sail up -d```
  
## Erreur avec la commande php

Si lorsque vous utilisez la commande php vous avez une erreur vous inqiquant que vous n'utilisez pas la bonne version de php, pas de panique il y a une solution.
En effet grâce a Laravel vous pouvez utilisez la commande [sail](https://laravel.com/docs/9.x/sail) pour éxécuter votre commande php.
Pour se faire vous devez dans un premier temps saisir dans votre terminal : 

```alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'```

Par la suite vous pouvez utilisez vos commandes php tranquillement par exemple : 

```sail php artisan migrate```
 
## Erreur avec composer

Dans le cas ou composer ne se lancerais pas pour des problèmes de droit taper la commande suivante :

```chmod -R 666 ../minimalist-blog-laravel```

Dans le cas où la modification de droit ne fonctionnerais pas, il faudra utiliser le composer via un [conteneur docker ](https://hub.docker.com/_/composer)


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
