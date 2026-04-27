# AI Learning Coach — Drop-in Kit

Een AI-gestuurde studiecoach voor Azure certificeringen en tech learning paths.
Oorspronkelijk gebouwd voor AI-102 prep, maar werkt voor elke certificering.

## Wat zit erin?

| File | Wat doet het |
|------|-------------|
| `COACH.md` | System prompt — laad dit in je AI tool als instructies |
| `study-plan-template.md` | Studieplan framework met quiz systeem en fases |

## Gebruik met GitHub Copilot Chat

1. Open je repo/workspace in VS Code
2. Kopieer `COACH.md` en `study-plan-template.md` naar je workspace root
3. In Copilot Chat, verwijs naar het bestand:
   - `@workspace /explain #file:COACH.md` om Copilot de instructies te laten lezen
   - Of plak de inhoud van `COACH.md` als eerste bericht in een nieuwe chat

**Tip:** In GitHub Copilot kun je `COACH.md` toevoegen als custom instruction via
`.github/copilot-instructions.md` — dan heeft elke chat automatisch de coach context.

## Gebruik met Microsoft Copilot (copilot.microsoft.com)

1. Start een nieuwe chat
2. Plak de inhoud van `COACH.md` als eerste bericht
3. Volg op met: "Hier is mijn studieplan:" + de inhoud van `study-plan-template.md`
4. Begin met studeren!

## Hoe werkt het?

- **Intake quiz**: elke nieuwe topic begint met 5-10 vragen om je niveau te peilen
- **Adaptief tempo**: score bepaalt of je versneld, normaal of extra diep gaat
- **Hands-on focus**: theorie → quiz → lab, niet alleen lezen
- **Voortgang tracking**: quiz scores worden bijgehouden om groei te meten

## GitHub Pages Reference Guide

Een belangrijk onderdeel van deze aanpak: na elke studiesessie wordt een **reference guide** bijgewerkt en gepubliceerd via GitHub Pages. Dit geeft je:

- Een levende samenvatting die meegroeit met je studie
- Een doorzoekbare referentie tijdens het examen (open book prep)
- Zichtbare voortgang

De repo zelf dient als zowel studieplan áls gepubliceerde guide. Zet GitHub Pages aan op je repo (Settings → Pages → Deploy from branch: `main`).

## Aanpassen

- Pas het studieplan aan voor jouw certificering (fases, topics, tijdlijn)
- De coach werkt voor elke Azure cert (AZ-104, AZ-305, AI-102, DP-100, etc.)
- Voeg je eigen resources toe (MS Learn paths, YouTube, labs)
- Pas de HTML template aan naar je eigen stijl
