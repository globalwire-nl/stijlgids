DectDirect is een webwinkel in telefonie, headsets, netwerk en de rest van de werkplek, voor bedrijven en particulieren in de Benelux. De winkel is helder en praktisch: wit met één diep violet, geel voor alles wat koopt, en veel productfoto's op wit. Dit systeem beschrijft de nieuwe winkel (Next.js, live 8 december 2026) en de Rails-pagina's die erbij horen (winkelmand, afrekenen, account).

## Toon en tekst

- Schrijf in het Nederlands, met **je** en **jouw**, nooit u: "Heb je vragen?", "Hoe mogen we je aanspreken?", "Alles voor jouw perfecte werkplek." (Een oude merktekst over Jabra gebruikt nog "u"; neem dat niet over.)
- Koppen zijn korte uitspraken die op een punt eindigen: "Geliefd.", "Speciaal voor jou.", "Alleen de beste merken.", "Op ons kun je rekenen.", "Tweedekans, eerste keus." Een vraag mag: "Vergeet je niet een van deze?", "Niets missen?"
- Maak in een belofte het ene woord dat telt **bold**: "Verzending binnen EU en **gratis** binnen Benelux", "Kopen **op rekening** voor de zakelijke markt", "Altijd minimaal **2 jaar garantie**", "Klantbeoordeling **9.2/10**".
- Uitroepteken alleen in de vaste USP-regel en de metatekst ("Gratis verzending binnen de Benelux!"). Geen emoji.
- Gewone zinshoofdletters, geen Title Case. Productnamen zoals de fabrikant ze schrijft ("Jabra Evolve2 65 Flex UC Stereo").
- Voorraad en prijs feitelijk: "Nog maar 3 op voorraad", "Nog 2 voor deze prijs · meer leverbaar voor 189,95". Laatste voorraad is beschikbaarheid tegen een prijs, nooit "korting" of "actie".
- Prijzen: incl. btw groot, excl. btw eronder. `189,95` zonder teken op tegels, `€ 189,95` in zinnen en totalen. Schrijf "excl. btw" (de tegels zeggen nog "excl. BTW"; de rest van de winkel kleine letters).
- Knoppen zeggen wat er gebeurt: "Toevoegen aan winkelwagen" (op een telefoon "In winkelwagen"), "Afrekenen", "Naar betaling", "Aanmelden", "Geef me een seintje".

## Kleur

De winkel gebruikt het Tailwind v4-palet met vier eigen tokens. De namen hier zijn de CSS-variabelen van de storefront (`--color-brand` enz.), zodat code en systeem hetzelfde zeggen.

- **Pagina en vlakken.** `color-page` onder alles, `color-surface` voor wat erop ligt (header, kaarten, menu's). In licht zijn beide wit.
- **Tekst.** Lopende tekst `color-neutral-800`; productnamen `color-neutral-700`; secundair (kruimelpad, voorraadregel, byline) `color-neutral-500`. Randen zonder kleur zijn `color-neutral-200`.
- **Violet, twee rollen.** `color-brand` is het violet als *tekst of rand* (prijs op de productpagina, koppen in dialogen, hover-ring, zoekveld) en wordt in donker lichtviolet. `color-violet-900` is het violet als *vlak* (USP-balk, hero, badges, gekozen keuze) en blijft in beide thema's gelijk; wit erop, iconen erop `color-yellow-500`. Zet nooit wit op `color-brand`.
- **Geel = kopen.** `color-yellow-500` met label `color-violet-900` voor elke actie die iets koopt of verstuurt, en voor de infobalk. Hover `color-yellow-400`. In donkere banners begint de knop op `color-yellow-400` (hover `color-yellow-300`). Eén gele knop per blok.
- **Links.** In de storefront `color-sky-500` (hover van footer-, menu- en kruimelpadlinks, "Bekijk alle merken", paginering, links in artikelen). Op de Rails-pagina's `shop-link`.
- **Status.** Voorraad `color-green-500`, geen voorraad `color-rose-600`, fouten `color-red-700`/`color-red-500`, succes `color-green-700`. Status heeft altijd ook een woord of icoon, nooit alleen kleur.
- **Verlopen.** Precies drie, alle uit de bron: de nieuwsbrief-band `color-violet-900` → `color-sky-500`; de donkere banners `color-slate-900` → `color-slate-600`; koptekst in een verloop op die banners (`color-green-500` → `color-lime-200` voor Tweedekans, `color-sky-500` → `color-violet-500` voor Xelion). Geen nieuwe verlopen.
- `logo-*` en `icon-violet` zijn de kleuren die in de logo- en icoonbestanden staan; gebruik ze niet in UI-CSS.

## Licht en donker

Licht is de standaard. Donker volgt de systeeminstelling, tenzij `<html data-theme="light|dark">` (de keuze uit de schakelaar in de footer, in localStorage `theme`). In donker krijgen `color-page`, `color-surface`, `color-brand`, `color-brand-tint` andere waarden en draait de grijsschaal om (`color-neutral-50` is dan het donkerst), zodat `color-neutral-700` gewoon blijft werken. Ook de getinte uiteinden van groen, rood, sky en geel (meldingen) draaien mee. Violet-vlakken en de gele knoppen blijven gelijk.

Productfoto's hebben een eigen witte achtergrond: het fotovlak van product- en merktegels en de blauwe categorietegel blijven licht in donker (`theme-light`). In donker wisselt het logo naar `logo-white.svg`, en de betaalmethode-logo's krijgen samen een wit plaatje.

## Typografie

Eén familie: **Barlow** (Google Fonts, gewichten 400, 500, 600, 700; de storefront host hem zelf via next/font, de Rails-pagina's laden hem van bunny.net). Koppen en prijzen zijn bold (700); semibold (600) alleen voor labels en de footer-contactregels; medium (500) voor de voorraad-pil en zoekresultaten.

- Koppen: `hero` (48px) op de homepage, `page-title` (36px) voor artikelen, `heading-section` (30px) voor secties, `heading-banner` (24px) in banners en dialogen, `heading-card` (20px), `heading-small` (18px).
- Tekst: `body` 16px, `body-lg` 18px voor de korte productomschrijving, `small` 14px, `caption` 12px voor de USP-balk.
- Het hoofdmenu (`nav`) staat in hoofdletters op 13px met 0.05em spatiëring.
- Prijzen: `price-hero`, `price-tile`, `price-row` met `tabular-nums` in rijen en totalen, `price-excl` eronder.

## Ruimte, vorm en schaduw

- Raster van 4px (Tailwind-stappen; `spacing-4` = 16px). Inhoud tot `container-max` (1280px) met `spacing-4` marge, vanaf xl `spacing-10`. Secties `spacing-6` boven en onder; productrasters `spacing-2` tussenruimte op een telefoon, `spacing-5` vanaf md.
- Hoeken: `radius-md` (6px) is de standaard voor knoppen, tegels, velden en menu's. `radius-full` voor pillen (Bestseller, voorraad, snelkoppelingen, teller). `radius-xl` (12px) voor de grote vlakken: hero, banners, de Rails-kaart.
- Tegels hebben geen schaduw maar een ring: 1px `color-neutral-200`, bij hover 2px `color-brand`. Schaduw alleen voor wat zweeft of plakt: `shadow-sm` (sticky header, badges op de foto), `shadow-md` (tooltip), `shadow-xl` (megamenu), `shadow-2xl` (zoek-dropdown), `shadow-buy-bar` (sticky koopbalk).
- Focus: de bron gebruikt een ring van 2px, in wisselende kleuren (`color-violet-900` bij de galerij, `color-yellow-400` bij het productlabel, `color-violet-500` bij velden, de Rails-pagina's `violet-800`). Kies bij iets nieuws ring 2px `color-violet-500` met 2px tussenruimte in `color-page`, zoals de keuzeknoppen in het afrekenen.
- Beweging is klein: `fadeIn` 0.3s (4px omhoog) voor de teller en de toast, `slideIn` 0.2s voor panelen, `shimmer` 1.5s voor laadskeletten, kleurovergangen op hover.

## Beeld

- Productfoto's: altijd op wit, `object-contain`, nooit bijgesneden. Op de categorietegel wordt de foto met `mix-blend-mode: multiply` op `color-sky-50` gelegd.
- Sfeerbeelden (`assets/Beeld/brand-*.jpg`) naast het USP-blok op de homepage; merkbanners (`index-brand-*.png`) op de merkkaarten.
- De twee donkere banners (Tweedekans, Xelion) zijn het enige donkere beeld in de lichte winkel.

## Iconografie

- UI-iconen zijn **Tabler Icons** (v3.46.0, MIT): omlijnd met lijndikte 2 op een raster van 24, of gevuld (sterren). Ze staan in `assets/Iconen/tabler/` met de namen die de storefront gebruikt (`cart`, `heart`, `chat`, `truck`, …). In de winkel tekenen ze in `currentColor`; de bestanden hier hebben inkt `#262626` (`color-neutral-800`) omdat een `<img>` geen kleur erft.
- Groottes: 24px in de header en op knoppen, 20px compact, 16px in de USP-balk, 12px bij de voorraadregel.
- De categorieën hebben eigen iconen: een violette schijf met wit symbool (`assets/Categorie-iconen`, 40–50px in het menu, 32px op de homepage).
- Eigen accenten in de huisstijlkleuren: gele vinkjes (`check.svg`), het avondverzending-busje bij de levertijd, Instagram en LinkedIn in de footer.
- Geen emoji als icoon.

## Logo

- `logo.svg`: beeldmerk (de D in een verloop van violet naar blauw) plus woordmerk "dect" violet en "direct" blauw met gele punt. Vanaf lg, 40px hoog.
- `logo-without-mark.svg`: alleen het woordmerk, voor de smalle header (32px).
- `-white`-varianten voor donker: "dect" wit, de rest gelijk.
- `mark.svg` is het losse beeldmerk (favicon en app-icoon).

## Rails-pagina's (winkelmand, afrekenen, account)

Deze pagina's horen bij dezelfde winkel en volgen hetzelfde thema, met een eigen set `shop-*`-kleuren: in licht is de pagina `shop-page` (slate-50) in plaats van wit, de grijzen zijn Tailwinds slate, links `shop-link` (sky-600) en velden hebben `shop-field-border`. Donker heeft exact de storefront-waarden. De inhoud staat in een witte kaart (`radius-xl`, `shadow-sm`). Violet-vlakken en gele knoppen zijn gelijk aan de storefront.

## Verschil met het Lightspeed-thema

Het oude thema (Lightspeed C-series, Tailwind v3) bevestigt de basis: Barlow, het violet als hoofdkleur, gele koopknoppen met violet label, `sky-500` links, dezelfde producttegel en dezelfde logobestanden. De nieuwe winkel wint waar ze verschillen:
- Violet-900 is in Tailwind v4 `oklch(38% 0.189 293.745)` (≈ #4d179a); Lightspeed en de Rails-pagina's gebruiken v3 `#4c1d95`. Zelfde rol, net iets andere waarde.
- Iconen: Lightspeed gebruikte Heroicons (lijndikte 1.5); de nieuwe winkel Tabler (lijndikte 2).
- Lightspeed had geen donker thema, geen `color-brand`/`color-brand-tint`-tokens en staffelprijzen ("Prijs bij 5 stuks") waar de nieuwe winkel de laatste-voorraadrijen heeft.
- Het hoofdmenu, de USP-balk, de nieuwsbrief-band en de categorie-iconen zijn zo overgenomen.

## Bekende contrastproblemen (bron, niet aangepast)

Deze paren komen zo uit de code en halen 4,5:1 (of 3:1 voor iconen) niet. Ze staan ook bij hun tokens.
- `color-sky-500` als linktekst op wit: 2,7:1 (licht). Dekt alle storefront-links en de verlanglijst-knop.
- `color-neutral-400` (excl. btw op tegels, SKU in zoekresultaten): 2,6:1 op wit, 2,4:1 op `color-brand-tint`.
- `color-green-500`: "Op voorraad" als tekst 2,2:1 en wit op de groene voorraad-pil en de "toegevoegd"-knop 2,2:1.
- Laatste voorraad, donker: witte teller op `color-brand` (#c4b5fd) 1,85:1.
- `color-neutral-500` op `color-neutral-100` of `color-brand-tint`: 4,3:1.
- Wit op het lichte einde van de nieuwsbrief-band (`color-sky-500`): 2,7:1.
- Rails: `shop-link` 4,1:1 op wit, `shop-400` 2,6:1, amber-600 ("Prijs gewijzigd") 3,2:1.

## Niet opgenomen

Het Tailwind-palet staat er alleen in voor zover de winkel het gebruikt. Niet als component: de Xelion-calculator, de fotogalerij en lightbox, filters en sorteren, productspecificaties en tabbladen, reviews, dialogen, de winkelwagen-toast, de chatknop en de oranje ShopNotice. Productfoto's komen uit de productfeed en zitten niet in het systeem. De componenten zijn statische weergaven (HTML met `components/bundle.css`), met de klassen nagebouwd uit de React-componenten van de storefront; er is geen bundel gebouwd.
