# TP — Rendu livrable

1. **Le bouton « Réserver » était un `<div>`.**
   Impact : impossible de réserver au clavier, et le lecteur d'écran l'annonce comme du simple texte.
   Correction : vrai `<button>`.
   Vérification : Tab atteint « Réserver Après l’aube » et Entrée ouvre la fenêtre. DevTools > Accessibilité : rôle `button`.

2. **La fenêtre n'avait ni rôle ni nom.**
   Impact : l'ouverture n'est pas annoncée et l'utilisateur ne sait pas où il se trouve.
   Correction : `<dialog>` natif, avec `aria-labelledby` qui pointe vers le titre.
   Vérification : DevTools > Accessibilité : rôle `dialog`, nom « Réserver Après l’aube ».

3. **Le focus restait sur la page derrière la fenêtre.**
   Impact : avec Tab, on parcourt les films cachés derrière la fenêtre.
   Correction : ouverture avec `showModal()`, qui place le focus dans la fenêtre et rend le reste de la page inerte.
   Vérification : à l'ouverture, le focus est sur « Fermer ». Tab ne passe que par « Fermer » et « Revenir aux films ».