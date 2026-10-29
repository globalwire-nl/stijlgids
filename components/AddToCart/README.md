# AddToCart

De gele "In winkelwagen"-knop in zijn vier gedaanten: icoonknop op de tegel, compact, de volle knop op de productpagina en de sticky balk op een telefoon.

## Gebruik
- Tegel: `dd-cart-icon-btn` (p-2, `color-yellow-500`, icoon `color-violet-800`, 4,8:1). Compact (`is-compact`, p-1) in de rij-tegel.
- Na een geslaagde toevoeging krijgt de knop 2 seconden `dd-is-added` (`color-green-500`, wit icoon) en de teller in de header speelt zijn pop opnieuw. Een geweigerde toevoeging toont de melding in de winkelwagen-toast, niet in de knop.
- Productpagina: `dd-btn-buy-lg` met "Toevoegen aan winkelwagen". Bij laatste voorraad: zie QuantityStepper.
- Op een telefoon verschijnt `dd-buy-bar` onderaan zodra de echte knop boven uit beeld is: prijs in `color-brand` links, knop rechts, `shadow-buy-bar`.
- Is bestellen gesloten (`html[data-ordering="closed"]`), dan verdwijnt elke knop met `data-order-action` en toont de pagina "Bestellen is op dit moment niet mogelijk".

## Wat de gebruiker levert
SKU en aantal (het formulier post naar `/cart/items`, werkt ook zonder JS), en een `srLabel` voor schermlezers.

## Let op
- `dd-is-added` zet wit op `color-green-500`: 2,2:1, onder de 3:1 voor iconen (bron).
