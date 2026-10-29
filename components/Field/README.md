# Field

Invoer: het zoekveld in de header met zijn resultatenlijst, en de gewone velden van formulieren.

## Gebruik
- Zoekveld: 2px `color-brand`-rand, `radius-md`, min. 300px, vergrootglas 20px links in `color-neutral-500` (draait als spinner tijdens zoeken). Resultaten: `color-surface`, rand, `shadow-2xl`, rijen met thumbnail 48px, naam `text-sm` medium en "merk · sku" `text-xs color-neutral-400`; de geselecteerde rij (pijltjestoetsen) `color-brand-tint`.
- Veld: 1px `color-neutral-300`, `radius-md`, `py-2.5 px-3`, 16px. Focus: rand en ring 2px `color-violet-500`. Label erboven `text-sm` semibold.
- Fout: rand `color-red-500` met ring `color-red-100` (Rails `.c-field-has-error`: ring-4 red-200), melding `text-sm color-red-700` met `role="alert"`.
- Op de Rails-pagina's heet het veld `.c-field` (min-hoogte 40px, `shadow-inner`, focus `violet-800`) met `shop-field-border` als rand; onder 640px 16px tekst zodat iOS niet inzoomt.

## Let op
- `is-meta` in `color-neutral-400`: 2,6:1 (bron).
