# Simulateur de devis : mise à jour du 19/11/2026

Page : gangofbordeaux.com/exempledevistraiteur (bloc Code du simulateur)

## Ce qui change
1. **Four mobile et camion frigorifique offerts en dessous de 20 convives.** Ils s'affichent « Offert » et ne sont plus facturés. À partir de 20 convives, rien ne change.
2. **La Table du Chef passe à 130 €/convive, tout compris :** chef, service, champagne, vins, eaux et vaisselle complète. La vaisselle n'est plus en option pour cette formule.

## Étape 1 : remplacer le script
Dans le bloc Code, remplacez tout le `<script> … </script>` final (celui qui commence par `(function () { var host = document.getElementById("gob-devis");`) par le contenu de `script-simulateur.html`.
Ne touchez pas au reste du bloc (le `<div id="gob-devis">` et le `<template id="gob-devis-tpl">`).

## Étape 2 : trois textes à modifier dans le même bloc Code

**a) Paragraphe « S'ajoutent selon la formule… »**
Remplacer :
> S’ajoutent selon la formule la vaisselle, les boissons, les fours mobiles (au moins un, puis un de plus par tranche de 40 convives), le camion frigorifique et le déplacement au-delà de 30 km.

par :
> S’ajoutent selon la formule la vaisselle, les boissons, les fours mobiles (au moins un, puis un de plus par tranche de 40 convives), le camion frigorifique et le déplacement au-delà de 30 km. En dessous de 20 convives, le four mobile et le camion frigorifique sont offerts.

**b) FAQ sur le camion**
Remplacer la question :
> Pourquoi un camion frigorifique est-il inclus ?

par :
> Pourquoi un camion frigorifique ?

Et sa réponse :
> Il garde les produits à la bonne température jusqu’au moment du service, même dans un lieu sans chambre froide. Nous l’incluons dans chaque prestation pour garantir la sécurité alimentaire, sauf pour les repas à la villa Montgolfière, équipée sur place. Il est en option pour Le Brunch posé et Le Buffet Essentiel.

par :
> Il garde les produits à la bonne température jusqu’au moment du service, même dans un lieu sans chambre froide. Il est prévu à partir de 20 convives et offert en dessous, comme le four mobile. Il n’est pas nécessaire pour les repas à la villa Montgolfière, équipée sur place, et il est en option pour Le Brunch posé et Le Buffet Essentiel.

**c) Tableau des prix (texte de départ, lu par Google avant que le script ne le recalcule)**
Remplacer `105 €<span class="fn">La Table du Chef</span>` par `130 €<span class="fn">La Table du Chef</span>`.

## Étape 3 : injection de code de l'en-tête de la page
La page contient aussi, dans l'en-tête (Paramètres de la page > Avancé > Injection de code), un bloc `FAQPage` qui reprend l'ancienne réponse sur le camion. Remplacez-y la question et la réponse comme au point b).

## Vérifié
Le nouveau script a été testé dans un navigateur sur une copie de la page.
- Déjeuner servi, 15 convives : four et camion « Offert ». Total 953 € avec la vaisselle.
- Déjeuner servi, 25 convives : four et camion facturés comme avant.
- Table du Chef, 12 convives : 1 560 € (130 € par convive), vins et vaisselle « Inclus ».
- Mariages : aucun changement (minimum 30 à 40 convives).
