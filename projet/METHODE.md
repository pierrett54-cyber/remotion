# Méthode de travail

> Comment on produit une vidéo, de l'idée au fichier final.
> Ce fichier décrit le processus ; l'avancement se note dans `SUIVI.md`,
> les choix visuels dans `DA.md`.

## 1. Brief
- Objectif de la vidéo : _informer, vendre, annoncer…_
- Public visé : _…_
- Plateforme de diffusion et format : _YouTube 16:9, Reels/TikTok 9:16, carré 1:1…_
- Durée cible : _…_
- Message clé en une phrase : _…_

## 2. Script et storyboard
1. Écrire le texte / la voix off scène par scène.
2. Découper en scènes avec une durée pour chacune.
3. Pour chaque scène : ce qu'on voit, ce qu'on entend, l'animation principale.

| # | Durée | Visuel | Texte / voix | Animation |
| - | ----- | ------ | ------------ | --------- |
| 1 | 3 s   | _…_    | _…_          | _…_       |

## 3. Préparation des ressources
- Images, vidéos, logos, polices et sons dans `public/`.
- Vérifier droits d'utilisation et qualité (résolution ≥ format final).
- Respecter la palette et la typo de `DA.md`.

## 4. Animation dans Remotion
- Une composition par format (`<Composition>` dans `Root.tsx`).
- Une scène = un composant, placée dans une `<Sequence>`.
- Les couleurs, polices et durées viennent d'un fichier de constantes
  unique (reflet de `DA.md`), jamais en dur dans les scènes.
- Animations avec `interpolate()` / `spring()` à partir de `useCurrentFrame()`.
- Prévisualiser dans Remotion Studio : `bunx remotion studio`.

## 5. Relecture
- [ ] Orthographe et textes
- [ ] Rythme : rien de trop rapide pour être lu
- [ ] Cohérence avec la DA
- [ ] Son : niveaux, pas de coupure
- [ ] Zones de sécurité respectées (interface des réseaux sociaux)

## 6. Rendu et livraison
```bash
bunx remotion render <id-composition> --output out/<nom>.mp4
bunx remotion still <id-composition> --output out/<nom>.png   # miniature
```
- Nommage : `AAAA-MM-JJ_projet_format_vN.mp4`
- Noter le rendu (date, version) dans `SUIVI.md`.

## Règles générales
- Une modification = une note dans le journal de `SUIVI.md`.
- Toute décision visuelle durable est reportée dans `DA.md`.
- On valide le storyboard avant d'animer.
