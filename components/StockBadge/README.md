# StockBadge

Voorraadstatus: klein met vinkje of kruisje op tegels, als pil naast de prijs op de productpagina.

## Gebruik
- Klein: `Op voorraad` in `color-green-500` met `check`-icoon 12px; `Geen voorraad` in `color-rose-600` met `x`-icoon.
- Groot: pil `radius-full`, `color-green-500` met witte tekst (medium). Aantal alleen waar het iets zegt (Ponck, maart 2026): onder 5 "Nog maar **N** op voorraad", 5 tot 10 "**N×** op voorraad", daarboven gewoon "Op voorraad". Uitverkocht: grijze pil `color-neutral-200` met `color-neutral-600` bold.
- Heeft het product een tweedekans-variant, dan staat er een omlijnde pil naast met het `recycle`-icoon in `color-green-800`.

## Let op (contrast)
- Groen en rood/roze zijn hier ook in woorden en icoon verschillend, dus niet alleen kleur.
- `color-green-500` als tekst op wit: 2,2:1; wit op `color-green-500`: 2,2:1. Beide halen 4,5:1 niet in licht (bron, ook al in Lightspeed). In donker is de kleine variant 8,5:1.
