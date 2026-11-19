# Zwazo Péi

La chasse aux oiseaux et aux témoignages de La Réunion. Zwazo Péi propose une série de mini-jeux sur les oiseaux de l'île : on parcourt une carte en étapes, on capture des oiseaux dans un « Zwazodex », on gagne de l'XP et des badges, et on part recueillir les souvenirs et les histoires des habitants (les gramouns) sur les oiseaux.

## Ce qui existe

- **Accueil** : présentation du jeu et de la chasse aux témoignages.
- **Carte** : 6 étapes, de l'étang de Saint-Paul à la Roche Écrite, qui se débloquent l'une après l'autre.
- **Mini-jeux** : *Qui suis-je ?* (indices), *Œil de lynx* (réflexes), *Vrai ou faux ?* (connaissances).
- **Zwazodex** : 8 oiseaux illustrés (tec-tec, papangue, tuit-tuit, pétrel de Barau…) avec fiches.
- **Badges & progression** : niveaux, titres, 8 badges.
- **Témoignages** : quêtes, récits publiés, formulaire de partage.

## Technologies

- TanStack Start (React 19, TanStack Router), Vite, TypeScript
- Tailwind CSS 4 et composants shadcn/ui
- Netlify (hébergement, Image CDN pour les illustrations)

## Lancer en local

```bash
pnpm install
netlify dev   # ou : pnpm dev
```

## Suite du projet

Les données de jeu sont pour l'instant dans `src/data/fixtures.ts` et la progression reste sur l'appareil. Les prochains jalons (voir [PLAN.md](PLAN.md)) ajoutent la base de données, l'enregistrement et la modération des témoignages (avec audio et photos), les comptes joueurs, de nouveaux mini-jeux et un mode terrain géolocalisé.
