# Méthode de travail

> Comment on produit une vidéo, de l'idée au fichier final.
> Ce fichier décrit le processus ; l'avancement se note dans `SUIVI.md`,
> les choix visuels dans `DA.md`.

## 1. Repérage des moments (pendant / après le live)
- Pendant le live : noter l'heure des moments forts (marqueur de stream,
  commande du chat ou simple note).
- Après : revoir les passages notés et garder les meilleurs.
- Un bon clip : une réaction forte, un fail, une course-poursuite, un moment
  drôle ou une découverte dans GTA 6, **compréhensible sans contexte**.
- Noter chaque moment dans le tableau « Clips » de `SUIVI.md`
  (horodatage début / fin).

## 2. Choix du format
| Type                | Format        | Durée cible | Plateforme              |
| ------------------- | ------------- | ----------- | ----------------------- |
| Clip court          | 9:16 vertical | 15–45 s     | TikTok, Shorts, Reels   |
| Extrait de live     | 16:9          | 1–5 min     | YouTube                 |
| Compilation         | 16:9          | 8–15 min    | YouTube                 |

## 3. Structure d'un clip court
| Temps     | Rôle        | Contenu                                         |
| --------- | ----------- | ----------------------------------------------- |
| 0–1 s     | Hook        | Titre néon + le moment le plus fort ou sa promesse |
| 1–25 s    | Action      | Le moment, coupé serré, sous-titres mot par mot |
| Fin       | Chute       | Réaction / punchline, puis rappel de la chaîne  |

Le titre doit donner envie en 5 mots maximum (« IL A VOLÉ LE MAUVAIS YACHT »).

## 4. Préparation des ressources
- Exporter le passage du live (VOD) : gameplay + facecam séparés si possible.
- Fichiers dans `public/clips/<date>_<nom>/`.
- Transcription automatique pour les sous-titres (`@remotion/captions`,
  Whisper), puis corriger les erreurs.
- Respecter la palette et la typo de `DA.md`.

## 5. Montage dans Remotion
- Un modèle de composition réutilisable par format (`ClipVertical`,
  `ExtraitLive`) : on ne change que les props (vidéo, début/fin, titre,
  sous-titres) pour chaque nouveau clip.
- Vidéo via `<OffthreadVideo>` avec `trimBefore` / `trimAfter` pour couper.
- Facecam et gameplay recadrés depuis la même source si le live est en un
  seul fichier.
- Les couleurs, polices et durées viennent d'un fichier de constantes
  unique (reflet de `DA.md`), jamais en dur dans les scènes.
- Animations avec `interpolate()` / `spring()` à partir de `useCurrentFrame()`.
- Prévisualiser dans Remotion Studio : `bunx remotion studio`.

## 6. Relecture
- [ ] Orthographe et textes
- [ ] Hook visible dans la première seconde
- [ ] Rythme : pas de temps mort, sous-titres lisibles
- [ ] Cohérence avec la DA
- [ ] Son : voix au-dessus de la musique et du jeu, pas de saturation sur les cris
- [ ] Zones de sécurité respectées (interface des réseaux sociaux)

## 7. Rendu et publication
```bash
bunx remotion render <id-composition> --output out/<nom>.mp4
bunx remotion still <id-composition> --output out/<nom>.png   # miniature
```
- Nommage : `AAAA-MM-JJ_gta6_<nom-du-clip>_<9x16|16x9>_vN.mp4`
- Miniature (16:9) : capture du moment fort + titre néon + visage expressif.
- Description : titre + hashtags (`#GTA6 #GTAVI #ViceCity #gaming #clip`).
- Noter la publication (date, plateforme, lien) dans `SUIVI.md`.

## Règles générales
- Une modification = une note dans le journal de `SUIVI.md`.
- Toute décision visuelle durable est reportée dans `DA.md`.
- On valide la sélection des moments avant de monter.
- Mieux vaut un clip court et fort qu'un long et moyen.
