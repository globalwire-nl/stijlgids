# De site bouwen

De stijlgids is een statische site die GitHub Pages zo uit de root van `main`
serveert (geen Actions-workflow; `.nojekyll` zorgt dat de bestanden ongewijzigd
uitgeleverd worden). De pagina's zijn gegenereerd en staan in de repo.

## Wat is bron en wat is gegenereerd

- **Bron, zoals geëxporteerd, niet met de hand aanpassen:** `README.md` (het
  merkboek), `tokens.json`, `design-system.json`, `components/`, `assets/`.
- **Hand-geschreven:** `site.css` (stijl van de site), `fonts/` (Barlow),
  `bin/build`, dit bestand.
- **Gegenereerd door `bin/build`:** `index.html`, `tokens.html`, `beeld.html`,
  `tokens.css` en alles in `componenten/`.

## Opnieuw bouwen

Na een nieuwe export van het design system: kopieer de bronbestanden over de
oude heen en draai

```
bin/build
```

Alleen Python 3 met de standaardbibliotheek, geen packages. Het script maakt
`componenten/` leeg en schrijft alles opnieuw; dezelfde bron geeft
byte voor byte dezelfde site. Controleren of de site bij de bron past, zonder
iets te schrijven:

```
bin/build --check
```

Het script stopt met een fout als een `/_blob/<id>` in een voorbeeld niet via
de `assetGroups` in `design-system.json` naar een bestand in `assets/` leidt,
of als een tokenwaarde geen gewone kleur, lengte of CSS-waarde is.

Lokaal bekijken: `python3 -m http.server 8000` in deze map en open
<http://localhost:8000/>.

## Barlow

Barlow (400, 500, 600, 700; latin en latin-ext) staat in `fonts/`, uit
`@fontsource/barlow` 5.3.0 op npm, met de SIL Open Font License als
`fonts/OFL.txt`. `fonts/barlow.css` heeft de `@font-face`-regels. Er wordt
niets van Google Fonts of bunny.net geladen. Bijwerken:

```
curl -fLO https://registry.npmjs.org/@fontsource/barlow/-/barlow-5.3.0.tgz
tar xzf barlow-5.3.0.tgz package/files package/LICENSE
cp package/files/barlow-latin{,-ext}-{400,500,600,700}-normal.woff2 fonts/
cp package/LICENSE fonts/OFL.txt
```

## Niet geïndexeerd

Elke pagina heeft `<meta name="robots" content="noindex, nofollow">`; de site
wordt gedeeld met een link, niet gevonden. Geen analytics, geen externe
scripts of fonts.
