# PaymentMethods

Betaalkeuze in het afrekenen (Rails): de rij betaalmethode-logo's onder de bestelknop, de keuze particulier/zakelijk en de betaalwijze voor klanten op rekening.

## Gebruik
- Logo's: Mollie's eigen iconen uit `assets/Betaalmethoden`, elk met een eigen hoogte zodat ze even groot ogen (iDEAL 28px, Creditcard en PayPal 24px, Apple Pay en in3 20px, Bancontact 16px, Klarna en overboeking 14px). Voorafgegaan door "Betalen met" (`text-xs`). In donker krijgen ze samen een wit plaatje (`radius-md`), want een paar zijn zwart op transparant.
- "Ik bestel als": twee keuzeknoppen met icoon; gekozen = `color-violet-900` vlak met wit, anders rand 2px `color-neutral-300`. Focus: ring 2px `color-violet-500` met 2px tussenruimte.
- Betaalwijze verschijnt alleen voor klanten met krediet: "Online betalen" of "Koop op rekening", met de termijn en het beschikbare krediet in `color-neutral-500`. Past de bestelling niet in het krediet, dan blijft de optie zichtbaar maar uit (`color-neutral-400`) met de reden.
- Op de productpagina staat een regel "Veilig achteraf betalen via Klarna of Billink" met beide woordmerken in `currentColor`.

## Wat de gebruiker levert
De lijst methodes die het afrekenen aanbiedt (`storefront_payment_methods`), en voor de rekening-optie krediet en termijn.

## Let op
- De Rails-pagina's tekenen met de `shop-*`-kleuren (slate in licht). Dit voorbeeld gebruikt de storefront-tokens.
