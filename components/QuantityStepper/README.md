# QuantityStepper

Aantal-kiezer met min en plus naast de gele koopknop, met daaronder wat het gekozen aantal kost.

## Gebruik
- Alleen bij een product met laatste voorraad tegen een eigen prijs (`LastStockBuyButton`, branch `feature/last-stock-price`, nog niet op main). Elders is de koopknop er zonder aantal; de winkelmand (Rails) gebruikt een gewoon getalveld `.c-field w-16`.
- Rand 2px `color-neutral-200`, `radius-md`; knoppen 44px breed, teken 24px in `color-neutral-500`, hover `color-brand`. Min is uit bij 1 (opacity .4). Maximum 999.
- De regel eronder (`text-sm color-neutral-500`): "N stuks: a × prijs + b × prijs = **totaal** (excl. btw)", totaal in `color-neutral-800`, excl. in `color-neutral-400`.
- Hij deelt het aantal met de prijsrijen erboven (LastStockPrice): de rij die het aantal raakt licht op.

## Wat de gebruiker levert
Het product (sku, prijzen, limited_price). De stepper houdt zelf het aantal.

## Let op
- De excl.-btw-tekst in `color-neutral-400` haalt 2,6:1 (bron).
