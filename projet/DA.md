# Direction artistique — Clips GTA 6

> Ambiance « Vice City / Leonida » : couchers de soleil, néons, chaleur de
> Floride, énergie de live. Inspiré de l'univers GTA 6, **sans reprendre le
> logo ni les visuels officiels de Rockstar** (on évoque, on ne copie pas).

## Identité en quelques mots
- Ambiance : coucher de soleil sur Vice City, néons, rétro années 80 modernisé.
- Trois mots-clés : **chaud**, **néon**, **punchy**.
- Contenu : clips courts et extraits de live sur GTA 6.
- Ce qu'on évite : couleurs ternes, fonds blancs, textes longs, logo officiel
  GTA VI utilisé comme si c'était le nôtre.

## Couleurs

Palette « sunset Leonida » : dégradé violet → rose → orange, relevé par un
cyan néon.

| Rôle               | Nom              | Hex       | Usage                                       |
| ------------------ | ---------------- | --------- | ------------------------------------------- |
| Principale         | Rose néon        | `#FF3D8B` | Titres, mot surligné dans les sous-titres   |
| Secondaire         | Orange sunset    | `#FF8A3D` | Accents, barres, compteurs                  |
| Lumière            | Jaune soleil     | `#FFC94A` | Chiffres clés, « moments forts »            |
| Contraste froid    | Cyan Vice        | `#2EE6D6` | Contours, détails, réactions chat           |
| Profondeur         | Violet crépuscule| `#5B2A86` | Dégradés, ombres colorées                   |
| Fond               | Nuit Leonida     | `#120A24` | Arrière-plans, bandeaux                     |
| Texte              | Blanc chaud      | `#FFF6EC` | Texte courant, sous-titres                  |

**Dégradé signature** (fonds, bandeaux, transitions) :
```css
linear-gradient(180deg, #5B2A86 0%, #FF3D8B 55%, #FF8A3D 85%, #FFC94A 100%)
```

**Lueur néon** (titres) :
```css
text-shadow: 0 0 12px #FF3D8B, 0 0 32px rgba(255, 61, 139, 0.6);
```

Règle de lisibilité : texte blanc avec contour noir (6–8 px) ou ombre
portée, toujours lisible par-dessus le gameplay.

## Typographie

| Usage              | Police                         | Graisse | Taille (9:16, 1080 px) |
| ------------------ | ------------------------------ | ------- | ---------------------- |
| Titre / hook       | **Anton** (ou Bebas Neue)      | 400     | 110–140 px             |
| Accent rétro       | **Yellowtail** (script néon)   | 400     | 80–100 px              |
| Sous-titres        | **Montserrat**                 | 800     | 64–72 px               |
| Infos (pseudo, date)| Montserrat                    | 600     | 36–40 px               |

- Toutes disponibles via `@remotion/google-fonts`.
- Titres et sous-titres en **MAJUSCULES**.
- Option « GTA classique » : la police Pricedown (vérifier la licence avant
  un usage commercial).

## Mise en page

### Clip vertical 9:16 (TikTok, Shorts, Reels) — format principal
```
┌──────────────────────┐
│  zone libre ~250 px  │  ← interface des applis
│  HOOK (titre néon)   │
├──────────────────────┤
│                      │
│      FACECAM         │  ~35 % de la hauteur
│                      │
├──────────────────────┤  ← trait dégradé rose→orange 8 px
│                      │
│      GAMEPLAY        │  ~65 %, recadré au centre de l'action
│   SOUS-TITRES ici    │
│                      │
│  zone libre ~300 px  │  ← boutons like / commentaires
└──────────────────────┘
```
- 1080×1920, 30 ou 60 FPS (60 si le live est en 60).
- Marges latérales : 60 px minimum.
- Sous-titres centrés, au tiers inférieur du gameplay, 2 lignes max.

### Extrait 16:9 (YouTube, compilations)
- 1920×1080, gameplay plein écran, facecam en incrustation coin bas droit,
  bordure néon rose 4 px, coins arrondis 24 px.

## Mouvement
- Rythme : **rapide et punchy**, montage serré, pas de temps mort.
- Hook : le titre arrive dans les **0,5 premières secondes** (zoom 120 % → 100 %
  avec `spring`, léger tremblement).
- Sous-titres : mot par mot, le mot prononcé passe en **rose néon** et grossit
  légèrement (scale 1 → 1,1).
- Moments forts : zoom rapide sur le gameplay, flash orange 3 images, texte
  jaune (« WTF », « 5 ÉTOILES », etc.).
- Transitions : glissement + flou de mouvement ou balayage du dégradé
  signature (8–10 images).
- Courbe par défaut : `spring({ damping: 14, stiffness: 180 })` pour les
  entrées, fondu 6 images pour les sorties.

## Éléments graphiques
- Bandeau « LIVE » rouge/rose avec point clignotant pour les extraits de live.
- Étoiles de recherche (★) comme gimmick pour noter l'intensité d'un moment.
- Soleil couchant / palmiers en silhouette pour intro / outro.
- Grain léger + vignettage pour l'effet ciné.
- Pseudo de la chaîne : coin haut gauche, discret, Montserrat 600.
- Messages du chat : bulles fond `#120A24`, bord cyan, pseudo en rose.

## Son
- Musique : synthwave / retrowave ou trap chill, à **−20 dB** sous la voix.
- Garder les cris et réactions du live : c'est le contenu.
- Effets : « whoosh » sur les transitions, « bass boom » sur les moments forts,
  avec parcimonie.

## Références
- Bandes-annonces et visuels officiels de GTA 6 (ambiance seulement)
- Esthétique Miami / Vice City des années 80, synthwave
- _Ajouter ici tes captures d'inspiration et chaînes de référence_
