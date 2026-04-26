# LFIAGtube — Preview repo (Netflix UI v1)

**Repo de test alternatif.** Ne pas merger sur main avant validation visuelle.

## Déploiement GitHub Pages

1. Push sur un repo GitHub (ex: `lfiagselect/lfiagtube-preview`).
2. Settings → Pages → Source: `main` branch, root.
3. Attendre 1-2 min, ouvrir l'URL gh-pages.

## Stack

- Statique pur (HTML/CSS/JS vanilla). Pas de build.
- Vignettes: `images/categories-v2/` (16:9) + `images/categories-v2-poster/` (2:3).
- Polices: Google Fonts (Inter, Anton, Bebas Neue).
- Pas d'auth réelle dans cette preview — utilise mock data + lecture localStorage `lfiag_videos_cache` si dispo (même origine que prod uniquement).

## Limites preview

- Pas de connexion Drive directe (preview = vue UI uniquement).
- Routes Documentaires/Concerts: si cache prod détecté → vrais noms ; sinon mock.
- Pas de player Drive (boutons play = visuels seulement).

## Validation avant merge main

- [ ] Splash TUDUM lisible mobile + desktop
- [ ] Billboard rotation 9s + preview vidéo OK
- [ ] Top 10 posters portrait + chiffres géants
- [ ] Hover card-expand desktop (≥1024px hover devices)
- [ ] Routes nav: Séries (5), Documentaires, Concerts, Ma liste
- [ ] Mobile responsive 360-768px
- [ ] Tablet 768-1024px
- [ ] TV / 4K 1920+

## Si OK → merge main

```bash
# Sur le repo principal lfiagselect.github.io
cp index.html ../lfiagselect.github.io/   # avec adaptation auth
cp -r images/categories-v2{,-poster} ../lfiagselect.github.io/images/
```
