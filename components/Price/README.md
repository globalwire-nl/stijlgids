# Price

Prijsweergave: incl. btw groot en bold, excl. btw klein eronder. De winkel noemt beide, want de klanten zijn bedrijven en particulieren.

## Gebruik
- Tegel: `price-tile` (24px, leading 16px, bold, `color-neutral-800`) met `price-excl` "… excl. BTW" in `color-neutral-400`.
- Productpagina: `price-hero` (48px vanaf md, 30px eronder) in `color-brand`, "… excl. btw" in `color-neutral-500`, en de voorraad-pil ernaast.
- Compact (rij-tegel, winkelmand): 16px bold.
- Notatie uit `formatPrice`: `189,95` zonder valuta op tegels; `€ 189,95` (formatPriceWithCurrency) in zinnen en totalen. Duizendtallen met punt.
- Het EU-energielabel staat altijd direct bij de prijs (NVWA): zie ProductCard.

## Let op
- `price-excl` op tegels in `color-neutral-400` is 2,6:1 in licht, onder 4,5:1 (bron). Op de productpagina is het `color-neutral-500` (4,7:1).
