# Adapteur grbl pour Geckodrive

La zenbot 1624 est piloté via un vieil ordinateur portable faisant tourner LinuxCNC.

Par confort d'utilisation, j'aurai préféré pouvoir utiliser mon Macbook pour piloter la machine.

On peut en fait programmer un Arduino Uno avec un pilote G-Code, il s'agit du projet [[https://github.com/grbl/grbl/wiki|grbl]]. L'Arduino fait alors office de proxy entre le port USB et le driver des moteurs pas à pas.

## Conception

Il suffit de fabriquer un adaptateur entre le port parallèle du Gecko 540 ([[http://www.geckodrive.com/geckodrive-step-motor-drives/g540.html]])

C'est ce que j'ai fait avec le circuit qui suit. Rien de compliquer, quelques strip wire pour s'affranchir d'un routage double couche.

![pcb](https://user-images.githubusercontent.com/65183668/84675448-8ac7e780-af2c-11ea-8893-f891776b7a24.png)

Sources Eagle: [sources.zip](https://github.com/echofab-communautique/echofab_durable/files/4781248/sources.zip)
## Réalisation

J'ai décidé d'utiliser la CNC disponible au Fablab du Pec ({{http://www.fablab.koumbit.org/wordpress/}}). J'ai pu voir leur pipeline menant d'un fichier eagle à un circuit terminé. Il suffit de:
  * exporter le png de eagle avec les bons calques en 500dpi
  * cisailler / tourner le circuit dans un logiciel de retouche graphique
  * envoyer le tout dans fabmodules ([[http://fabmodules.org/]]) pour obtenir le gcode
  * mettre le gcode dans l'ordinateur de controle et le tour est joué

<img width="1052" alt="fabmodules" src="https://user-images.githubusercontent.com/65183668/84675524-a9c67980-af2c-11ea-9283-cb348cc83364.png">

Remerciement à Raphaël et Laurent pour leur accueil.


## Bibliographie

  * [[http://www.ereplacementparts.com/hitachi-m12vc-214hp-variable-speed-fixed-base-router-parts-c-7927_13365_13369.html]]
  * [[https://www.amazon.com/Hitachi-301795-2-Inch-Collet-Plunge/dp/B000BSWP72?ie=UTF8&qid=1460084982&ref_=sr_1_1&refinements=p_89%3AHitachi&s=power-hand-tools&sr=1-1]]
  * [[http://oahumakerspace.com/w/images/1/1c/ZenBot_manual.pdf]]
  * [[http://wiki.lvl1.org/Zenbot_1216_CNC]]
  * [[http://www.instructables.com/id/Make-your-own-PCBs-on-an-inexpensive-desktop-CNC-m/]]
