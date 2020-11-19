+++
title = "Guide pas à pas"
author = "Jester Bamboo"
+++
##### mise à jour: novembre 2020

Ce guide pas à pas se veut minimaliste sur l'aspect théorique et se concentre sur la fabrication de l'émetteur FM. Pour plus de détails théoriques, je vous invite à allez jeter un oeil à la section [détails techniques](/techniques).

##### Note: Cliquez sur les images pour les agrandir

## Principe de base

### Schéma électronique
##### Note: La compréhension du schéma électronique n'est pas requise pour arrivé à faire fonctionner l'émetteur radio.

![Schéma électronique](/schema-electronique.png)    


## Matériel nécessaire

### Composants électroniques

- Résistances
    - 1 x 470 ohm (jaune-violet-marron)
    - 1 x 10k ohm (marron-noir-orange)
    - 1 x 27k ohm (rouge-violet-orange)

    {{< figure src="/composants/resistance-470.jpg" alt="Résistance de 470 ohms" class="small small-3">}}
    {{< figure src="/composants/resistance-10k.jpg" alt="Résistance de 10k ohms" class="small small-3">}}
    {{< figure src="/composants/resistance-27k.jpg" alt="Résistance de 27k ohms" class="small small-3">}}

<div style="clear:both"></div>

- Condensateurs
    - 1 x 10 picofarad (pF)
    - 2 x 10 nanofarad (nF) (équivalent à 0.01 uF)
    - 1 x 1 microfarad (uF) polarisé     
    - 1 x condensateur variable entre 1 et 22 picofarad (pF)

    {{< figure src="/composants/condensateur-10pF.jpg" alt="Condensateur 10 picofarad" class="small small-4">}}
    {{< figure src="/composants/condensateur-10nF.jpg" alt="Condensateur 10 nanofarad" class="small small-4">}}
    {{< figure src="/composants/condensateur-1uF.jpg" alt="Condensateur radial 1 microfarad" class="small small-4">}}
    {{< figure src="/composants/condensateur-variable.jpg" alt="Condensateur variable" class="small small-4">}}

<div style="clear:both"></div>


- 1 x transistor NPN - 2N2222A
- 10cm de fil de cuivre émaillé 0.8mm (pour fabriquer une bobine)
- Plaque en époxy simple face, 8mm d'épaisseur, recouvert d'une couche de cuivre

    {{< figure src="/composants/transistor-2N2222A.jpg" alt="Transistor 2N2222A" class="small small-3">}}
    {{< figure src="/composants/fil-emaille.jpg" alt="Fil émaillé" class="small small-3">}}
    {{< figure src="/composants/plaque-epoxy.jpg" alt="Plaque époxy" class="small small-3">}}

<div style="clear:both"></div>

- 1 x fiche jack femelle mono "3,5mm"
- 1 x connecteur à pression pour pile 9V
- 1 x pile 9V

    {{< figure src="/composants/jack-femelle.jpg" alt="Transistor 2N2222A" class="small small-3">}}
    {{< figure src="/composants/connecteur-9V.jpg" alt="Fil émaillé" class="small small-3">}}
    {{< figure src="/composants/pile-9V.jpg" alt="Plaque époxy" class="small small-3">}}

<div style="clear:both"></div>

### Où acheter les composants?

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
> 1. À l’aide la pince à métaux, découpez un carré de 50cm*50cm dans la plaque d’époxy. On appellera ce carré « la masse »

> 2. Découpez 5 carrés de 10mm*5mm dans la plaque coupé précédemment. On appellera ses petits carrés « les potentiels »

> 3. Avec la colle super glu, collez les potentiels sur la masse selon la disposition de la photo ci-dessous.

> 4. Faites fondre de l’étain sur chaque potentiel à l’aide du fer à souder

{{< figure src="/assemblage/1-potentiels-masses.jpg" alt="Potentiels et masses 1" class="medium">}}
{{< figure src="/assemblage/2-potentiels-colles.jpg" alt="Potentiels et masses 2" class="medium">}}

<div style="clear:both"></div>

> 5. Soudez le transistor
    <ul>
        <li>selon le type de transistor que vous avez, plusieurs montage son possible. Dans le cas le plus simple où vous avez le 2N2222A dans un boitier TO92, il vous suffit de suivre la photo suivante</li>
        <li>si vous avez un autre transistor, il vous faut allez vérifier sur internet son sens de montage en fonction des broches base, émetteur et collecteur dans la datasheet.</li>
    </ul>

{{< figure src="/assemblage/3-2N2222A-resized.jpg" alt="Datasheet 2N2222A" class="medium">}}
{{< figure src="/assemblage/4-transistor.jpg" alt="Montage transistor" class="medium">}}

<div style="clear:both"></div>

> 6. Soudez le petit condensateur de 10pF entre les pattes émetteur et collecteur du transistor.(attention, les photos montrent un ordre de montage un peu différent avec le condensateur 10pf qui est monté après le condensateur variable. J'ai depuis changé ma façon de faire et je recommande de souder le 10pf avant le variable.)

> 7. Soudez le condensateur variable. Le condensateur variable a trois pattes. Il faut mettre une des pattes sur le potentiel indiqué sur le schéma et les deux autres pattes à la masse. Sur l’image ci-dessous, on voit les trois pattes du condensateurs. Les broches entourés d’un cercle rouge doivent-être reliées à la masse (donc soudé sur la plaque de cuivre). La patte composé de plusieurs petites languettes entourée d'un cercle bleu doit être reliée au potentiel indiqué sur le schéma.

{{< figure src="/assemblage/5-condensateur-variable-schema.jpg" alt="Schéma condensateur variable" class="medium">}}
{{< figure src="/assemblage/6-condensateur-variable.jpg" alt="Montage condensateur variable" class="medium">}}

<div style="clear:both"></div>

> 8. Fabriquez la bobine
    <ul>
        <li>Coupez un morceau de fil émaillé d’environ 8cm</li>
        <li>À l’aide d’un tournevis, ou d’une vis de diamètre 5mm, faites 4 tour de fil autour du support.</li>
        <li>Faites des petites pattes au bout de la bobine</li>
        <li>Enlevez le vernis présent sur les pattes de la bobine à l’aide du cutter en grattant la fine couche de surface.</li>
    </ul>

> 9. Soudez la bobine

> 10. Soudez le condensateur polarisé en faisant attention au sens indiqué sur le condensateur et la photo ci-dessous.

{{< figure src="/assemblage/7-bobine.jpg" alt="Montage bobine" class="medium">}}
{{< figure src="/assemblage/8-condensateur-radial.jpg" alt="Montage condensateur radial" class="medium">}}

<div style="clear:both"></div>

> 11. Vous pouvez souder les autres composants dans l’ordre désiré. Je recommande de souder les composants les plus au centre en premier.
    <ul>
        <li>Deux condensateur 10nF (ceux écrit 103 dessus)</li>
        <li>La résistance 27k ohm (rouge-violet-orange)</li>
        <li>La résistance 10k ohm (marron-noir-orange)</li>
        <li>La résistance 470 ohm (jaune-violet-marron)</li>
        <li>Le connecteur de la pile 9V</li>
    </ul>

{{< figure src="/assemblage/9-condensateur-10pf.jpg" alt="Montage condensateur 10pf" class="medium medium-3">}}
{{< figure src="/assemblage/11-resistances.jpg" alt="Montage résistances" class="medium medium-3">}}
{{< figure src="/assemblage/12-resistance-470ohm.jpg" alt="Montage résistance 470 ohm radial" class="medium medium-3">}}

<div style="clear:both"></div>

> 12. Assemblez l'entrée jack. <br>
Si vous avez acheté une prise jack sans fil, vous devez lui en souder. Pour celà, il faut faire attention à quelques éléments. Sur une prise jack stéréo, il y a un point gauche, un point droite et une masse. Dans notre cas, puisque l’entrée de l’émetteur est mono, nous connecterons les pattes gauche et droites ensemble de la prise jack. Pour faciliter la suite, il est préférable d’utiliser un fil noir pour la masse et un fil rouge pour le fil relient les pattes gauche/droite au potentiel.

{{< figure src="/assemblage/13-jack-femelle-schema.jpg" alt="Montage résistances" class="medium">}}
{{< figure src="/assemblage/13-prisejack1-photo.jpg" alt="Montage résistance 470 ohm radial" class="medium">}}

<div style="clear:both"></div>

> 13. Fin du montage. <br>
Voici à quoi devrait (environ) ressembler votre émetteur FM

{{< figure src="/assemblage/14-vueensemble.jpg" alt="Vue d'ensemble" class="medium medium-1">}}

<div style="clear:both"></div>

## Réglage de l'émetteur

Maintenant que l’émetteur est construit, nous allons devoir le régler pour qu’il émette sur une fréquence choisi. Pour cela vous aurez besoin d’un récepteur radio FM qui permettra d’écouter en même temps ce que vous émettez.

> Les étapes du réglages:
    <ul>
        <li> Branchez la pile 9V à l’émetteur</li>
        <li> Allumer votre poste de radio récepteur sur n’importe quelle fréquence entre 88MHz et 107MHz</li>
        <li> À l’aide d’un petit tournevis, faites tourner la vitesse sur la condensateur variable. À chaque tour, vous devriez entendre un petit moment de blanc sur la radio. Il se peut que vous arrivez à trouver le fréquence blanche (silence total à la radio) lorsque vous avez le tournevis sur le condensateur et qu’elle disparaît lorsque vous relachez. Réglez le condesanteur variable un peu près autour de cette fréquence blanche.</li>
        <li> Maintenant, affiner la fréquence sur votre poste radio pour trouver le silence radio.</li>
        <li> Mettez le volume de votre source de son au minimum et augmentez doucement le volume. Si tout c’est bien passé, vous devriez entendre votre son à la radio.</li>
        <li> Brancher le fil jack-jack sur l’entrée jack de la radio et sur votre source de son.</li>
        <li>Mettez le volume de votre source de son au minimum et augmentez doucement le volume. Si tout c’est bien passé, vous devriez entendre votre son à la radio.</li>
    </ul>

## Dépannage

Dans le cas où vous n’arrivez pas à entendre votre son à la radio ou que la qualité du signal écouté n’est pas satisfaisante, nous allons devoir passer au dépannage pour identifier les différents problèmes présents.

Est-ce que lorsque vous tournez le condensateur variable, vous entendez un petit « saut » du son dans la radio ?

> Non, alors il est probable que le problème vienne de votre montage.
    <ul>
        <li> Est-ce que le transistor est bien monté ?</li>
        <li> Est-ce que le condensateur variable est dans le bon sens ?</li>
        <li> Est-ce que les résistances sont au bonne endroit ?</li>
    </ul>

> Oui, vous arrivez à trouver la fréquence blanche mais pas le son de votre source
    <ul>
        <li>Est-ce que le condensateur radial polarisé est dans le bon sens ? c’est le condensateur qui est relié à au fil rouge de la prise jack.</li>
        <li> Est-ce que la câble jack-jack est bon ?</li>
    </ul>

> Oui, vous entendez votre son mais la qualité est très mauvaise
    <ul>
        <li> Vérifier que le volume de votre source audio soit assez faible pour ne pas faire saturer l’amplificateur</li>
        <li> Vérifier que vous n’avez pas inverser le rouge et le noir de la prise jack</li>
    </ul>

{{< load-photoswipe >}}
