---
layout: post
title:  "VirtualBox, serveurs web et fichiers JS/CSS tronqués"
date:   2015-04-27 21:27:45
categories: VirtualBox nginx apache js css
---
En bossant ce soir, il m'est arrivé un truc chiant: le fichier JS que j'étais en train d'éditer finissait tronqué dans mon naviguateur. Au début je pensais à un caractère spécial dans mon fichier, mais celui-ci revenait toujours à la normale si j'annulais mes modifs...

J'essaie actuellement de mettre en place une machine virtuelle VirtualBox/Vagrant/Salt pour reproduire l'environnement de développement. Après une courte recherche sur ce qui pouvait causer un fichier JS tronqué je suis tombé sur le coupable!

Apparemment certains serveurs (que ce soit Apache ou Nginx dans ce cas) n'aiment pas trop qu'un fichier partagé entre une machine virtuelle et son hôte soit modifié.

Pour __nginx__ modifier la config :

	sendfile off;

Pour __Apache__ modifier la config :

	EnableSendFile Off 