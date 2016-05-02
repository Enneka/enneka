---
layout: post
title:  "Modem/routeur Archer D2, firewall et telephone IP"
date:   2016-05-01 10:27:45
categories: 
---
J'ai acheté un modem/routeur TP-Link Archer D2 pour remplacer le vieux modem moisi fourni par Acanac. Il me semblait qu'il avait de bonnes reviews.

L'installation était facile. Jusqu'à maintenant il a bien fonctionné (Ouais... Ça fait juste 2 mois). Néanmoins, il y avait un gros souci.

Le téléphone IP fourni par ma boite n'arrêtait pas de recevoir des appels fantômes, d'un numéro allant de 1 à 2000, auxquels je ne pouvais pas répondre, juste ignorer/rejeter.

Une recherche sur internet ("Ghost calls" ou "Phantom calls" en anglais) m'informe que ce sont des probes SIP faites par des scripts pour tenter d'infiltrer des téléphones IP.

Maintenant... C'est le genre de trucs qu'un firewall bloque automatiquement right? RIGHT?

Voilà la triste réalité : le firewall n'est pas actif par défaut o_O o_O o_O

Maintenant... Il suffit de l'activer, right? RIGHT?

Oui, il faut juste bien mettre les bonnes rêgles : Deny par défaut et juste autoriser le trafic sortant, en prenant soin d'ajouter à l'avance le range d'IPs que cela concerne.

Ça devrait être suffisant pour empêcher ces appels fantômes right? RIGHT?

Non... Ça continuait. Comment font-il pour passer à travers le pare-feu, qui bloque toute connection entrante?

Encore un peu de fouille sur internet me signale que les routeurs peuvent avoir des [ALG (Application-Level Gateway)](https://en.wikipedia.org/wiki/Application-level_gateway) qui servent à faciliter les réglages de pare-feu pour certaines applications, pour éviter les casse-têtes...

Bien entendu la moitié de ces ALG sont de la daube qui ne fonctionnent pas, comme c'est le cas ici. Pour le désactiver, dans le menu du routeur, aller dans "Network", "ALG Settings" et désactiver "SIP ALG". C'est fini je pense.
