+++
title = "Guide pas à pas"
author = "Jester Bamboo"
+++
# Todo

- il faut voir comment faire pour que les images soit en petit dans le guide, mais qu'il soit possible de cliquer dessus pour agrandir l'image et voir mieux le détails. il faut donc que les images soit redimensionner dynamiquement par hugo ou par le css.
lorsque l'on clique sur la photo, est-ce que ça l'ouvre tout seul et il faut revenir en arrière ou ça l'ouvre dans une modale? il est essentiel que le site soit fonctionnel sous tor. et aussi, il faut qu'il soit fonctionnel sans javascript. Il est possible d'imaginer que les deux comportements existes. s'il y a du javascript, ça fait une modale, s'il n'y en a pas ça ouvre l'image dans l'onglet actuelle. c'est un comportement acceptable pour un utilisateur qui décide de désactiver le javascript. dans un premier temps, il est plus facile et rapide de faire la méthode sans javascript, et la méthode avec javascript viendra dans un deuxième temps.

tuto pour implémenter le zoom in pour les images: https://codeconvey.com/html-image-zoom-on-click/

Ce guide pas à pas se veut minimaliste sur l'aspect théorique et se concentre sur la fabrication de l'émetteur FM. Pour plus de détails théoriques, je vous invite à allez jeter un oeil à la section [détails techniques](/techniques).

# Principe de base

## Schéma électronique
Note: La compréhension du schéma électronique n'est pas requise pour arrivé à faire fonctionner l'émetteur radio.

![Schéma électronique](/schema-electronique.png)    


# Matériel nécessaire

## Composants électroniques

- Résistances
    - 1 x 470 ohm (jaune-violet-marron)
    - 1 x 10k ohm (marron-noir-orange)
    - 1 x 27k ohm (rouge-violet-orange)

    <a href="/composants/resistance-470.jpg"><img class="small" src="/composants/resistance-470.jpg" alt="Résistance 470 ohm"/></a>
    <a href="/composants/resistance-10k.jpg"><img class="small" src="/composants/resistance-10k.jpg" alt="Résistance 10k ohm"/></a>
    <a href="/composants/resistance-27k.jpg"><img class="small" src="/composants/resistance-27k.jpg" alt="Résistance 27k ohm"/></a>

- Condensateurs
    - 1 x 10 picofarad (pF)
    - 2 x 10 nanofarad (nF) (équivalent à 0.01 uF)
    - 1 x 1 microfarad (uF) polarisé     
    - 1 x condensateur variable entre 1 et 22 picofarad (pF)

    <a href="/composants/condensateur-10pF.jpg"><img class="small" src="/composants/condensateur-10pF.jpg" alt="Condensateur 10 picofarad"/></a>
    <a href="/composants/condensateur-10nF.jpg"><img class="small" src="/composants/condensateur-10nF.jpg" alt="Condensateur 10 nanofarad"/></a>
    <a href="/composants/condensateur-1uF.jpg"><img class="small" src="/composants/condensateur-1uF.jpg" alt="Condensateur 1 microfarad"/></a>
    <a href="/composants/condensateur-variable.jpg"><img class="small" src="/composants/condensateur-variable.jpg" alt="Condensateur variablem"/></a>

- 1 x transistor NPN - 2N2222A
- 10cm de fil de cuivre émaillé 0.8mm (pour fabriquer une bobine)
- Plaque en époxy simple face, 8mm d'épaisseur, recouvert d'une couche de cuivre

    <a href="/composants/transistor-2N2222A.jpg"><img class="small" src="/composants/transistor-2N2222A.jpg" alt="Transistor 2N2222A"/></a>
    <a href="/composants/fil-emaille.jpg"><img class="small" src="/composants/fil-emaille.jpg" alt="Fil émaillé"/></a>
    <a href="/composants/plaque-epoxy.jpg"><img class="small" src="/composants/plaque-epoxy.jpg" alt="Plaque époxy"/></a>

- 1 x fiche jack femelle mono "3,5mm"
- 1 x connecteur à pression pour pile 9V
- 1 x pile 9V

    <a href="/composants/jack-femelle.jpg"><img class="small" src="/composants/jack-femelle.jpg" alt="Jack femelle"/></a>
    <a href="/composants/connecteur-9V.jpg"><img class="small" src="/composants/connecteur-9V.jpg" alt="Connecteur pile 9V"/></a>
    <a href="/composants/pile-9V.jpg"><img class="small" src="/composants/pile-9V.jpg" alt="Pile 9V"/></a>

## Où acheter les composants?

- Un revendeur d’électronique :
Si vous avez de la chance un magasin d’électronique existe proche de chez vous. Vous pouvez lui apporter la liste ci-dessus et il aura probablement la plupart du matériel en stock ou des équivalents. S’il n’a pas l’intégralité de la commande en stock, il y a de bonnes probabilités qu’il puisse les commander.

- Sur internet :
Je n’ai pas une liste exhaustive de site à recommander. Pour ma part, je commande sur gotronic.fr. Le coût n’est pas le moins chère de la toile, mais les délais de livraison sont de quelques jours (si vous résidez en France) et l’ergonomie du site agréable.

Voici un exemple de panier chez gotronic.fr pour la fabrication d'un seul émetteur.
![Panier Gotronic 1](/panier-gotronic-1.png)

On remarque que le coût est assez élevé pour un seul émetteur. On est à 20€, et il nous restera des composants en surplus.

Si l’on fait la même commande dans l’idée de fabriquer dix émetteurs. On tombe à un coût de 5€ par émetteur. Il est préférable de faire une commande groupé en vu d’en fabriquer plusieurs. Notamment car le fil émaillé coûte assez chère. La bobine fait 22m alors que nous allons nous servir de quelques centimètres pour chaque montage.

Voici un exemple de panier pour la fabrication de 10 émetteurs.
![Panier Gotronic 10](/panier-gotronic-10.png)

## Outils
- Un fer à souder et de l'étain
- Une scie à métaux
- De la colle super glue
- Une pince coupante
- Un cutter (ou pince à dénuder)
- Un petit tournevis plat
- Des fils électroniques rouges et des fils noirs
- Un cable jack-jack
- Un récepteur radio FM

# Assemblage de l'émetteur

## Quelques conseils de soudures :
- Les pattes des composants sont souvent trop grandes. Vous pouvez les couper pour faciliter la positionnement. Ne les coupez pas trop courts non plus. 1cm pour chaque patte devrait être suffisant.
- Plier les pattes selon un angle de 90° à la moitié de leur longueur. Ceci facilitera la mise en place du composant et l’organisation visuel du circuit.
- Faites fondre un peu d'étain sur le pattes du composants pour faciliter son installation.
- Les résistances, les petits condensateurs céramiques et la bobine n’ont pas de sens d’installation.
- Attention, le condensateur radial est polarisé. Il doit être installé dans un sens défini. Sur le schéma le ‘+’ et le ‘-‘ sont indiqués. Sur le condensateur seulement le ‘-‘ est indiqué. Il faut que le ‘-‘ du condensateur soit placé sur le ‘-’ du circuit.
- Il n’y a pas d’ordre obligatoire de soudure. Mais il est recommandé de commencer par les composants du centre et ceux nécessitant une attention particulière.
- Il est possible qu’en faisant fondre l’étain sur un potentiel, cela amène à dé-souder un autre composant déjà installé. Parfois, il faut faire preuve d’un peu de dextérité pour tenir plusieurs composants en même temps avec les doigts et le fer à souder.

## Le montage en 14 étapes
1. À l’aide la pince à métaux, découpez un carré de 50cm*50cm dans la plaque d’époxy. On appellera ce carré « la masse »

2. Découpez 5 carrés de 10mm*5mm dans la plaque coupé précédemment. On appellera ses petits carrés « les potentiels »

3. Avec la colle super glu, collez les potentiels sur la masse selon la disposition suivante :

4. Faites fondre de l’étain sur chaque potentiel à l’aide du fer à souder

<a href="/assemblage/1-potentiels-masses"><img class="medium" src="/assemblage/1-potentiels-masses.jpg" alt="Potentiels et masses 1"/></a>
<a href="/assemblage/2-potentiels-colles.jpg"><img class="medium" src="/assemblage/2-potentiels-colles.jpg" alt="Potentiels et masses 2"/></a>

5. Soudez le transistor
    - selon le type de transistor que vous avez, plusieurs montage son possible. Dans le cas le plus simple où vous avez le 2N2222A dans un boitier TO92, il vous suffit de suivre la photo suivante

    - si vous avez un autre transistor, il vous faut allez vérifier sur internet son sens de montage en fonction des broches base, émetteur et collecteur dans la datasheet.

    <a href="/assemblage/3-2N2222A.jpg"><img class="medium" src="/assemblage/3-2N2222A.jpg" alt="Datasheet 2N2222A"/></a>
    <a href="/assemblage/4-transistor.jpg"><img class="medium" src="/assemblage/4-transistor.jpg" alt="Montage transistor"/></a>

6. Soudez le petit condensateur de 10pF entre les pattes émetteur et collecteur du transistor.(attention, les photos montrent un ordre de montage un peu différent avec le condensateur 10pf qui est monté après le condensateur variable. J'ai depuis changé ma façon de faire et je recommande de souder le 10pf avant le variable.)

7. Soudez le condensateur variable. Le condensateur variable a trois pattes. Il faut mettre une des pattes sur le potentiel indiqué sur le schéma et les deux autres pattes à la masse. Sur l’image ci-dessous, on voit les trois pattes du condensateurs. Les broches entourés d’un cercle rouge doivent-être reliées à la masse (donc soudé sur la plaque de cuivre). La patte composé de plusieurs petites languettes entourée d'un cercle bleu doit être reliée au potentiel indiqué sur le schéma.

<a href="/assemblage/5-condensateur-variable-schema.jpg"><img class="medium" src="/assemblage/5-condensateur-variable-schema.jpg" alt="Schéma condensateur variable"/></a>
<a href="/assemblage/6-condensateur-variable.jpg"><img class="medium" src="/assemblage/6-condensateur-variable.jpg" alt="Montage condensateur variable"/></a>

8. Fabriquez la bobine

        - Coupez un morceau de fil émaillé d’environ 8cm
        - À l’aide d’un tournevis, ou d’une vis de diamètre 5mm, faites 4 tour de fil autour du support.
        - Faites des petites pattes au bout de la bobine
        - Enlevez le vernis présent sur les pattes de la bobine à l’aide du cutter en grattant la fine couche de surface.

9. Soudez la bobine

10. Soudez le condensateur polarisé en faisant attention au sens indiqué sur le condensateur et le schéma.

<a href="/assemblage/7-bobine.jpg"><img class="medium" src="/assemblage/7-bobine.jpg" alt="Montage bobine"/></a>
<a href="/assemblage/8-condensateur-radial.jpg"><img class="medium" src="/assemblage/8-condensateur-radial.jpg" alt="Montage condensateur radial"/></a>

11. Vous pouvez souder les autres composants dans l’ordre désiré. Je recommande de souder les composants les plus au centre en premier.

        - Deux condensateur 10nF (ceux écrit 103 dessus)
        - La résistance 27k ohm (rouge-violet-orange)
        - La résistance 10k ohm (marron-noir-orange)
        - La résistance 470 ohm (jaune-violet-marron)
        - Le connecteur de la pile 9V


<a href="/assemblage/10-condensateur-10pf.jpg"><img class="medium" src="/assemblage/10-condensateur-10pf.jpg" alt="Montage condensateur 10pf"/></a>
<a href="/assemblage/9-condensateur-10pf.jpg"><img class="medium" src="/assemblage/9-condensateur-10pf.jpg" alt="Montage condensateur 10pf"/></a>
<a href="/assemblage/11-resistances.jpg"><img class="medium" src="/assemblage/11-resistances.jpg" alt="Montage résistances"/></a>
<a href="/assemblage/12-resistance-470ohm.jpg"><img class="medium" src="/assemblage/12-resistance-470ohm.jpg" alt="Montage résistance 470 ohm"/></a>

12. Assemblez l'entrée jack

Si vous avez acheté une prise jack sans fil, vous devez lui en souder. Pour celà, il faut faire attention à quelques éléments. Sur une prise jack stéréo, il y a un point gauche, un point droite et une masse. Dans notre cas, puisque l’entrée de l’émetteur est mono, nous connecterons les pattes gauche et droites ensemble de la prise jack. Pour faciliter la suite, il est préférable d’utiliser un fil noir pour la masse et un fil rouge pour le fil relient les pattes gauche/droite au potentiel.

<a href="/assemblage/13-jack-femelle-soudure.jpg"><img class="medium" src="/assemblage/13-jack-femelle-soudure.jpg" alt="Jack femelle soudures"/></a>

13. Fin du montage.

Voici à quoi devrait (environ) ressembler votre émetteur FM

<a href="/assemblage/14-vueensemble.jpg"><img class="medium" src="/assemblage/14-vueensemble.jpg" alt="Vue d'ensemble"/></a>
# Réglage de l'émetteur
