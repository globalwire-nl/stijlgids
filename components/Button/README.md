# Button

Knoppen van de winkel: geel voor elke actie die iets koopt of verstuurt, en een paar rustige varianten daaromheen.

## Gebruik
- `dd-btn dd-btn-buy`: elke koop- of verstuuractie (Afrekenen, Naar betaling, Aanmelden, Geef me een seintje). `color-yellow-500` met label in `color-violet-900`, hover `color-yellow-400`, `radius-md`, bold. Bron: `bg-yellow-500 hover:bg-yellow-400 text-violet-900 font-bold rounded-md px-5 py-2.5`.
- `dd-btn-buy-lg`: de volle-breedte koopknop op de productpagina (`py-3 text-lg w-full`), met het `cart`-icoon ervoor.
- `dd-btn-banner`: de grote knop in donkere banners (Tweedekans, Xelion): `color-yellow-400`, hover `color-yellow-300`, `px-8 py-3`.
- `dd-btn-pill`: snelkoppelingen in de hero, `radius-full`. Naast de gele pillen één omlijnde pil op violet: `dd-btn-pill-ghost` (`ring-1 ring-white/40`).
- `dd-btn-outline`: secundaire actie onder de koopknop (verlanglijst): tekst `color-sky-500`, rand `color-neutral-200`, hover-rand `color-brand`.
- `dd-btn-quiet` en `dd-btn-disabled` komen van de Rails-pagina's (kortingscode toepassen, Afrekenen zonder leverbare regels).

## Wat de gebruiker levert
Een `<a>` of `<button>` met de tekst; een icoon is een 24px Tabler-icoon in `currentColor` vóór de tekst.

## Niet doen
- Geen gele knop voor iets dat niet koopt of verstuurt; geen tweede gele knop naast de eerste.
- Geen witte tekst op geel. Het label is altijd `color-violet-900` (5,8:1).
- `dd-btn-outline` gebruikt `color-sky-500` als tekst: 2,7:1 in licht, onder de norm (zo in de bron).
