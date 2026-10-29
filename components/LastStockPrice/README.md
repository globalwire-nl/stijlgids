# LastStockPrice

De prijs in twee rijen voor een product met laatste voorraad tegen een eigen prijs: "Laatste voorraad" en "Meer leverbaar", elk met hoeveel van het gekozen aantal erin valt.

## Gebruik
- Variant B van het ontwerp (Sem, 28-10-2026), `components/LastStockBuyBlock.js` op branch `feature/last-stock-price` (nog niet op main).
- Rij: 2px rand `color-neutral-200`, `radius-md`, `py-2.5 px-4`. Een rij waar het aantal in valt krijgt rand `color-brand` en vlak `color-brand-tint`, en een teller-pil "2×" in `color-brand`.
- Titel bold `color-neutral-800`, onderregel `text-sm color-neutral-500`, prijs `price-row` in `color-brand`, excl. btw `text-xs color-neutral-400`.
- Op de tegel: de laatste-voorraadprijs is de kopprijs, met eronder een gestippelde lijn en "Nog N voor deze prijs · meer leverbaar voor …".
- Altijd beschikbaarheid tegen een prijs, nooit als korting verwoorden. De winkelmand (Rails) rekent de prijs opnieuw live.

## Let op (contrast)
- De teller zet wit op `color-brand`: in licht 11:1, maar in donker is `color-brand` `#c4b5fd` en wit erop 1,85:1. Daar hoort donkere tekst (bijv. `color-page`) op; in de bron nog niet opgelost.
- `color-neutral-400` op `color-brand-tint`: 2,4:1; `color-neutral-500` op `color-brand-tint`: 4,3:1 (bron).
