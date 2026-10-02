# Classeur Pokémon

Un classeur de cartes Pokémon virtuel, en **un seul fichier HTML** : tu choisis une extension, tu feuillettes les pages comme un vrai classeur et tu coches les cartes que tu possèdes. Sans compte, sans serveur, sans installation.

Les cartes, images et prix viennent de l'API ouverte [TCGdex](https://tcgdex.dev).

## Fonctionnalités

**Collection**
- Toutes les séries et extensions TCGdex, en **français** ou en **anglais**.
- Un clic sur un emplacement pour marquer la carte comme possédée. Les cartes manquantes sont en noir et blanc.
- Progression de l'extension (nombre de cartes et pourcentage) et **valeur possédée / valeur totale**.
- Deux modes :
  - **Normal** : une carte par numéro du set officiel (sans les cartes secrètes), en version de base.
  - **Master set** : chaque carte avec toutes ses versions (normale, reverse, holo, 1re édition).
- Recherche « **Où est cette carte ?** » : tape un nom de Pokémon et le classeur ouvre la bonne page, avec la carte surlignée.

**Affichage**
- Pages de 2×2, 3×3, 4×3 ou 4×4 cartes, avec option « Ajuster à l'écran ».
- Effets holo (arc-en-ciel) et reverse (reflet argenté) qui suivent le pointeur.
- Badges de version (N, R, H, 1) et symboles de rareté (●, ◆, ★).
- Prix Cardmarket (€), TCGplayer ($) ou masqués.
- Mode **plein écran** et thème clair ou sombre automatique.

**Navigation**
- Animation de tourne-page avec **curseur de réglage** : désactivée, ou de très lente à très rapide.
- Choix du côté de la **première page** : à droite (comme un livre) ou à gauche.
- ⏮ / ⏭ pour la première et la dernière page, champ « Aller à la page » et barre de défilement pour parcourir tout le classeur.
- Raccourcis clavier :

| Touche | Action |
|---|---|
| `←` / `→` | Page précédente / suivante |
| `Début` / `Fin` | Première / dernière page |
| `Page préc.` / `Page suiv.` | Reculer / avancer de 5 doubles pages |
| `Échap` | Quitter le plein écran |

**Profils et sauvegarde**
- Plusieurs **profils** (un simple pseudo, aucune donnée personnelle), chacun avec sa propre collection.
- **Export / import** de toute la collection, en fichier `.json` ou en code compressé à copier-coller, pour passer d'un appareil à l'autre.
- À l'import, un profil de même pseudo est fusionné sans retirer aucune carte.

## Utilisation

### En local
Télécharge le fichier HTML et ouvre-le dans ton navigateur. Une connexion internet est nécessaire pour charger les données et les images depuis TCGdex.

### Avec GitHub Pages
1. Renomme le fichier en `index.html`.
2. Dans **Settings → Pages**, choisis la branche `main` et le dossier `/ (root)`.
3. Le classeur est disponible à l'adresse `https://<ton-pseudo>.github.io/<nom-du-repo>/`.

## Où sont stockées mes données ?

Tout reste dans le **`localStorage` de ton navigateur** : profils, cartes possédées, réglages d'animation et de première page. Rien n'est envoyé à un serveur.

Les versions et les prix de chaque extension sont mis en cache pendant la journée pour éviter de recharger toutes les cartes à chaque ouverture.

⚠️ Si tu vides les données du site ou changes de navigateur, ta collection disparaît. **Pense à exporter régulièrement** une sauvegarde (bouton « 👤 Profil »).

## Stack technique

- HTML, CSS et JavaScript « vanilla », dans un seul fichier, sans dépendance ni étape de build.
- API REST [TCGdex v2](https://api.tcgdex.net/v2/) (séries, extensions, cartes, prix).
- Animation du tourne-page en CSS 3D ; compression du code de sauvegarde avec l'API native `CompressionStream`.

## Limites connues

- Les prix proviennent de TCGdex (tendance Cardmarket ou prix du marché TCGplayer). Ils sont mis à jour une fois par jour et peuvent manquer pour certaines cartes.
- Sur petit écran (moins de 820 px), les deux pages s'empilent et l'animation de tourne-page est désactivée.
- Il n'y a pas de synchronisation automatique entre appareils : la sauvegarde passe par l'export manuel.

## Crédits et mentions légales

- Données et images : [TCGdex](https://tcgdex.dev).
- Projet de fan, non officiel : il n'est ni affilié à, ni approuvé par Nintendo, Creatures, GAME FREAK ou The Pokémon Company. Pokémon et les noms de cartes sont des marques de leurs détenteurs respectifs.

## Licence

Code sous licence MIT (ajoute un fichier `LICENSE` à la racine du dépôt). Les images et données de cartes restent la propriété de leurs ayants droit.
