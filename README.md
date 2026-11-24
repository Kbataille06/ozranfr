# OZRAN — thème Shopify (ozran.fr)

Base : **Horizon 4.5.0**, récupéré depuis le thème live `#212010369363`
(boutique `rcyeua-n9.myshopify.com`). Les fichiers du thème sont à la racine,
c'est obligatoire pour l'intégration GitHub de Shopify.

## Fichiers modifiés par l'éditeur de thème (customizer)

Ces fichiers sont réécrits par Shopify à chaque enregistrement dans l'éditeur
et commités sur la branche connectée par le bot `shopify` :

- `config/settings_data.json` (réglages globaux)
- `templates/*.json` (contenu et ordre des sections de chaque page)
- `sections/*-group.json` (header, footer…)
- `locales/*.json` (textes modifiés dans l'admin)

## Règles

1. **`git pull` avant toute modif** pour récupérer les commits du bot `shopify`.
2. On ne touche aux JSON ci-dessus que volontairement. En cas de conflit, la version
   live (celle du bot) gagne par défaut.
3. Dev local : `shopify theme dev --store rcyeua-n9.myshopify.com` sur une branche de feature,
   puis merge dans `main`.
4. Jamais de merge à l'aveugle des JSON d'une branche de test vers `main`.
5. Pas de protection de branche qui bloquerait les commits du bot sur `main`.
6. CLI : toujours `--nodelete`, et `--only` / `--ignore` pour limiter les envois.
   Ne jamais pousser `config/settings_data.json` sans l'avoir tiré juste avant.
7. Nos ajouts sont préfixés `ozran-` (sections, snippets, blocks, assets) pour garder
   les futures montées de version d'Horizon faciles à fusionner.
8. Pas de build `src/` → `dist/` à la racine : CSS/JS livrés tels quels dans `assets/`.
9. Dupliquer le thème live dans l'admin avant toute publication.
