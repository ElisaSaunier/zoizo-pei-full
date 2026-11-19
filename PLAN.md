# Zwazo Péi — Feuille de route

Zwazo Péi est une plateforme de mini-jeux sur les oiseaux de La Réunion : parcours en étapes sur une carte de l'île, captures façon collection, niveaux et badges, et pour finir une chasse aux témoignages qui recueille la mémoire collective sur les oiseaux.

Le produit avance par jalons courts, chacun utilisable dès qu'il est livré.

## 1. Surface du produit ✅ (livré)

- Page d'accueil illustrée (`/`).
- Carte de l'île avec 6 étapes qui se débloquent l'une après l'autre (`/carte`).
- Trois mini-jeux jouables : *Qui suis-je ?*, *Œil de lynx*, *Vrai ou faux ?* (`/jeu/$etapeId`).
- Zwazodex (8 oiseaux) avec fiches détaillées (`/zwazodex`, `/zwazodex/$birdId`).
- Niveaux, XP et 8 badges (`/badges`).
- Chasse aux témoignages : quêtes, récits, formulaire de partage (`/temoignages`).
- Toutes les données viennent de `src/data/fixtures.ts` ; la progression est gardée dans le navigateur (`src/lib/progress.tsx`).

## 2. Catalogue en base de données

- Schéma Netlify Database (Drizzle) pour oiseaux, zones, étapes, affirmations, badges, quêtes (`db/schema.ts`).
- Script de chargement initial à partir des fixtures actuelles.
- Lecture via des server functions TanStack Start ; les écrans gardent la même forme de données.

## 3. Témoignages persistés et modération

- Table `temoignages` (statut `en-attente` / `publie` / `refuse`, consentement horodaté).
- Envoi du formulaire vers une server function avec validation Zod et anti-spam.
- Pièces jointes : enregistrement audio et photo, stockés dans Netlify Blobs.
- Espace de modération réservé (rôle `moderateur`) pour relire, corriger et publier.

## 4. Comptes joueurs et sauvegarde

- Netlify Identity : inscription, connexion, profil, pseudo.
- Migration de la progression locale vers le compte à la première connexion.
- XP, captures, badges et étapes calculés et validés côté serveur.

## 5. Plus de jeu

- Nouveaux mini-jeux : *Qui chante ?* (chants d'oiseaux), *Silhouette*, *Mémory*.
- Davantage d'oiseaux (introduits compris : martin, bulbul orphée, cardinal…) et d'étapes.
- Saisons et événements (ex. « Nuits sans lumière » pour les pétrels).
- Classement par commune ou par classe.

## 6. Chasse aux témoignages sur le terrain (esprit « Pokémon GO »)

- Mode géolocalisé : quêtes déclenchées à proximité de lieux réels (avec respect des zones protégées).
- Parcours pour les écoles et associations (codes de classe, tableau de bord enseignant).
- Carte publique des témoignages publiés, filtrable par oiseau, commune et époque.
- Export des témoignages (CSV / archive) pour les partenaires patrimoniaux.

## 7. Finitions

- Version créole / français de l'interface.
- Mode hors ligne (PWA) pour les sentiers sans réseau.
- Accessibilité et performances auditées.
