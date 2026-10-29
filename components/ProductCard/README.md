# ProductCard

De producttegel van elk productraster: foto, naam, voorraad, energielabel en prijs met de gele icoonknop.

## Gebruik
- Rasters: 2 kolommen op telefoon (`gap-2`), 4 vanaf lg (`md:gap-5`). Tegel `radius-md`, padding 12px, vanaf md 16px.
- Foto: vierkant, altijd wit (ook in donker, `theme-light`), `object-contain p-2`, rand eronder. Zonder foto: `color-neutral-100` vlak met het `photoOff`-icoon.
- Badges linksboven op de foto: Bestseller (top 50 verkoop over 30 dagen) en het backoffice-label, beide `dd-badge`.
- Naam: bold, `color-neutral-700`, max. 2 regels (min-hoogte 2.5rem). De hele tegel is de link: ring 1px `color-neutral-200`, hover 2px `color-brand` en de naam wordt `color-brand`.
- Regel eronder: StockBadge klein + SKU (SKU verborgen onder sm).
- Energielabel en prijs staan onderaan, op één lijn over de tegels (`mt-auto`). Het energielabel hoort bij de prijs (NVWA).
- De icoonknop staat er alleen bij voorraad > 0 en een SKU.

## Wat de gebruiker levert
Een product uit de feed: `full_name`, `slug`, `sku`, `stock`, `shop_price_incl_vat`/`excl`, `image_url`, `labels`, `energy_label`, `sales_rank_30d`.

## Let op
- In deze voorbeelden staat de lege-fotostaat: productfoto's komen uit de feed en zitten niet in het systeem.
- `Op voorraad` in `color-green-500` is 2,2:1 en de excl.-btw-prijs 2,6:1 in licht (bron).
