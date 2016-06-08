---
layout: post
title:  "[PHP] Une extension déclarée en trop en empêche une autre d'être déclarée..."
date:   2015-03-11 21:27:45
categories: php
---
Petit problème sur un nouveau serveur. Je souhaite installer xcache, paquet installé, php parse le .ini de xcache, mais l'extension n'est pas présente dans le PHPinfo, mis à part dans le pied de page avant le "PHP Credits". Je commençais à virer maboule alors je me suis dit que j'allais corriger une vieille erreur sur le serveur :

```
[11-Mar-2015 19:39:01 America/New_York] PHP Warning:  Module 'xdebug' already loaded in Unknown on line 0
```

Je savais pas trop d'ou ça pouvait venir, mon install étant plutôt récente et sans bidouille. Mais apparemment j'avais un fichier de trop dans le conf.d/ de PHP, qui redéclarait Xdebug. Je le retire, redémarre php-fpm, et nous voilà reparti comme en 14, ou comme en 40 selon les goûts.
