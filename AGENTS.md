# Webgame – spelsamling

Små webbläsarspel samlade bakom en startsida. Läs den här filen innan du ändrar något i repot,
och uppdatera den när du lär dig något nytt om hur vi vill ha det (se skillen `kom-ihag`).

## Spelen

| Fil | Spel | Kort om det |
|---|---|---|
| `index.html` | Startsidan | Kort för varje spel. Nya spel läggs in i `GAMES`-listan, och spelbilden är en CSS-klass under "Spelbilder". |
| `Dorza_Horizon_6.html` | Dorza Horizon 6 | 3D-racing i Japan (three.js r128 från cdnjs). Välj första bil och samla bilar i Autoshow. Har egna typsnitt (Kanit/Michroma). |
| `2big4you.html` | 2Big4You | Gymspel: tio dagar på dig att bli jacked. Handla protein, töm kylskåpet, sov. |
| `slirpong.html` | Slirpong | Pong på is: racketen glider, bollen skruvar och blir snabbare, racketar krymper under långa rallyn. 1P mot dator (Lätt/Normal/Brutal) eller 2P lokalt. Ratten för känslan finns överst i skriptet (`FRICTION`, `ACC`, `MAXV`). |

## Hur vi gör spelen

- **En fil per spel.** Allt i en självständig `.html` i roten: CSS i `<style>`, JS i `<script>`. Inget byggsteg, ingen npm.
- **Externa bibliotek** bara via CDN (helst cdnjs), t.ex. three.js. Typsnitt via Google Fonts.
- **Svenska** i allt användaren ser (menyer, knappar, texter) och gärna i kodkommentarer.
- **Stil:** mörkt tema med färgtokens på `:root`. Samlingens typsnitt är Anton (rubriker) och Archivo (brödtext), om spelet inte har en egen tydlig stil.
- **Upplägg i spelet:** en startmeny som overlay, paus (P/Esc och när fliken döljs), en slutskärm med "Spela igen" och "Meny", och en länk tillbaka till `index.html` ("← Alla spel").
- **Fungera på mobil:** touchstyrning där det går, `viewport-fit=cover` och safe-area-insets.
- **Känsla:** lite överdrivet och lekfullt, med skärmskak, partiklar, enkla WebAudio-ljud och en svårighet som ökar under spelets gång.
- **Nytt spel = nytt kort på startsidan.** Lägg alltid till det i `GAMES` i `index.html` med en egen spelbild i CSS.

## Arbetssätt

- Användaren skriver på svenska. Svara på svenska.
- Committa bara när användaren ber om det.
- Maskinen har **varken Node eller Python**. Använd Edit/Write för filändringar och öppna spelet i webbläsaren med
  `Start-Process <fil>.html` (PowerShell) för att testa. Säg ärligt att något inte är testat om du inte kunnat köra det.
- Skills för det här repot ligger i `.claude/skills/`:
  - `nytt-spel` – checklista för att lägga till ett nytt spel i samlingen.
  - `kom-ihag` – spara lärdomar här eller gör en ny skill av ett återkommande arbetsflöde.

## Lärdomar

<!-- Lägg till korta punkter här när något visar sig viktigt. Datera dem (ÅÅÅÅ-MM-DD). -->
- 2026-10-05: Slirpong lades till. Användaren vill att spelen gärna är "sladdriga och svåra" snarare än snälla.
