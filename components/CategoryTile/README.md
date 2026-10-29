# CategoryTile

Ingangen naar een categorie: de lichtblauwe beeldtegel op categoriepagina's en de link met rond categorie-icoon op de homepage.

## Gebruik
- Beeldtegel (`components/category/blocks.js`): vierkant vlak `color-sky-50`, `radius-md`, de foto van de bestseller met `mix-blend-mode: multiply` zodat het wit van de foto in het blauw opgaat. Label eronder bold `color-brand`, onderstreept bij hover; hover-ring 1px `color-brand`. Het vlak blijft licht in donker (`theme-light`).
- Categorie-link (homepage onder lg, waar het menu achter de hamburger zit): ring `color-neutral-200`, hover 2px `color-brand`, icoon 32px uit `assets/Categorie-iconen`, label bold `color-neutral-800`. "Cloud telefonie" (Xelion) staat altijd als laatste, in `color-brand`.
- In dit voorbeeld staat het categorie-icoon op de plek van de productfoto: de winkel leent daar een productfoto uit de feed.

## Wat de gebruiker levert
`href`, `label` en een beeld (productfoto of categorie-icoon).
