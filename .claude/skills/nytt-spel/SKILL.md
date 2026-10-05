---
name: nytt-spel
description: Checklista för att skapa ett nytt minispel i webgame-samlingen och lägga in det på startsidan. Använd när användaren vill göra ett nytt spel eller lägga till ett befintligt spel i samlingen.
---

# Nytt spel i samlingen

Följ konventionerna i `AGENTS.md`. Steg för steg:

1. **Idé.** Kolla vad användaren vill ha. Fråga bara om något verkligen är oklart och välj annars ett rimligt standardval.
   Användaren gillar spel som är lite svåra, sladdriga och överdrivna.
2. **Filnamn.** Använd `<spelnamn>.html` i gemener utan mellanslag i roten, t.ex. `slirpong.html`.
3. **Grundstomme** (titta gärna på `slirpong.html` som mall):
   - `<!doctype html>`, `lang="sv"`, viewport-meta med `viewport-fit=cover`.
   - Google Fonts med Anton och Archivo (eller ett eget typsnitt som passar spelet).
   - Färgtokens på `:root`, mörk bakgrund och `[hidden]{display:none!important}`.
   - Canvas för spelet (eller three.js från cdnjs för 3D) och HTML-overlays för meny, paus och slutskärm.
   - Länken `<a class="back" href="index.html">← Alla spel</a>`.
4. **Spelloop:** `requestAnimationFrame` med `dt` begränsat till högst ~0,033 s, och tillstånd som `menu`, `play`, `paused` och `over`.
   Pausa med P/Esc och när fliken döljs (`visibilitychange`).
5. **Styrning:** tangentbord och touch. Om två spelare går, stöd W/S mot piltangenterna.
6. **Juice:** skärmskak, partiklar och korta WebAudio-pip. Ljud ska inte låta i menyn.
7. **Startsidan:** lägg till ett objekt i `GAMES` i `index.html` (`file`, `title`, `art`, `artName`, `desc`, `tags`)
   och en CSS-klass `.art.<namn>` under kommentaren "Spelbilder".
8. **Uppdatera `AGENTS.md`:** lägg till en rad i speltabellen.
9. **Testa:** öppna med `Start-Process <fil>.html` i PowerShell. Node och Python finns inte, så säg ärligt vad som inte är testat.
10. Committa inte förrän användaren ber om det.
