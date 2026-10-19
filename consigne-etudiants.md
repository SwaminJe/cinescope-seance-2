# TP — Réparer la fenêtre modale

Durée : 55 minutes — travail en binôme. Inversez pilote et observateur après 25 minutes.

## Objectif

Corriger l’ouverture et la fermeture de la réservation afin que le dialogue
soit compréhensible et utilisable uniquement au clavier.

Vous retrouvez le corrigé de la séance 1 avec ses affiches, sa recherche,
ses favoris et ses informations pratiques. Conservez ces acquis et cette
présentation. Le travail porte sur la nouvelle commande « Réserver » et la
fenêtre qu’elle ouvre.

## Scénario de vérification

Sans utiliser la souris :

1. atteindre le film « Après l’aube » ;
2. ouvrir la réservation ;
3. identifier le nom de la fenêtre ;
4. parcourir ses commandes ;
5. fermer avec `Escape` ;
6. vérifier la position du focus ;
7. recommencer avec le bouton de fermeture.

Refaites le scénario avec un deuxième film. Vérifiez que le focus revient au
bouton du film réellement demandé. Pour identifier le nom calculé, utilisez le
panneau Accessibilité des DevTools ; aucun lecteur d’écran n’est à installer
pour ce TP. Le clavier seul ne permet pas de lire ce nom calculé.

## Travail demandé

Corrigez au minimum les points suivants :

- l’action qui ouvre la réservation doit utiliser un élément HTML natif ;
- la fenêtre doit avoir un rôle et un nom accessibles ;
- le focus doit entrer dans la fenêtre à l’ouverture ;
- la fermeture doit être possible au clavier et son bouton doit être nommé ;
- après la fermeture, le focus doit revenir au déclencheur ;
- le contenu derrière la fenêtre ne doit pas participer au parcours pendant
  son ouverture.

## Contraintes

- aucun `tabIndex` positif ;
- privilégier les éléments HTML natifs ;
- ne pas supprimer l’indicateur de focus ;
- le parcours doit rester compréhensible à 200 % de zoom.

## Priorités si vous manquez de temps

1. déclencheur clavier et fenêtre nommée ;
2. entrée du focus dans le dialogue ;
3. fermeture au clavier ;
4. retour du focus.

## Livrable

Le code corrigé et une note courte indiquant :

- trois problèmes rencontrés ;
- leur impact utilisateur ;
- la méthode utilisée pour vérifier chaque correction.

## Vérifications avec les DevTools

Réutilisez la fiche `atelier-devtools-lecteur-ecran.md` : relevez le rôle et
le nom calculés du déclencheur et du dialogue, puis le focus avant, pendant
et après fermeture. Testez deux films. Les manipulations dans Elements sont
temporaires : reportez la correction dans les sources React.

La démonstration de lecteur d’écran de dix minutes est réalisée par
l’enseignant avant le TP. Elle complète les essais clavier et l’inspection ;
aucune installation n’est demandée sur les postes étudiants.

Pour aller plus loin pendant le temps de TP : ateliers 2 (ordre du focus) et
4 (retour au mauvais film), dans le dossier `ateliers`.

## Bonus pour les binômes ayant terminé le socle

- Extraire un `BookingDialog` typé sans perdre le nom du dialogue ni le cycle du focus.
- Ajouter une confirmation explicite pour les séances disponibles, distincte d’une simple fermeture.
- Afficher le résultat (film et horaire) dans une région `role="status"` déjà présente ; vérifier son annonce avec l’enseignant sans déplacer le focus sur le message.
- Vérifier les annulations, une séance complète et deux confirmations successives du même film.

Le scénario reste une simulation sans billet réel. Le détail et les critères
sont dans `bonus-corrige.md`. Ces bonus et les ateliers 2/4 sont des alternatives
selon votre progression, pas des tâches toutes obligatoires dans les 55 minutes.
