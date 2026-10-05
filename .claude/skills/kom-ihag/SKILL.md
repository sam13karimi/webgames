---
name: kom-ihag
description: Spara en lärdom om spelen eller användarens önskemål i AGENTS.md, eller skapa en ny skill av ett arbetsflöde som återkommer. Använd när användaren säger "kom ihåg", "från och med nu", "lär dig", eller när du märker att samma sak behöver göras eller förklaras flera gånger.
---

# Kom ihåg och lär dig

## Välj var det ska sparas

- **Ett faktum eller önskemål** (t.ex. "vi vill alltid ha highscore", eller att ett spel använder ett visst bibliotek):
  lägg det i `AGENTS.md`.
  - Gäller det hur spel ska byggas, lägg det under **Hur vi gör spelen**.
  - Gäller det ett visst spel, uppdatera dess rad i speltabellen.
  - Allt annat går under **Lärdomar** som en kort, daterad punkt (`- ÅÅÅÅ-MM-DD: ...`).
- **Ett arbetsflöde i flera steg som kommer tillbaka** (t.ex. "lägg till highscore i ett spel", "gör en mobilversion"):
  skapa en ny skill i `.claude/skills/<namn>/SKILL.md`.

## Regler

- Läs filen först. Uppdatera det som redan finns i stället för att skriva samma sak två gånger, och ta bort sådant som inte längre stämmer.
- Skriv kort och konkret och ta med *varför* om det inte är självklart.
- Spara inte sådant som redan syns i koden eller git-historiken.

## Ny skill – mall

```markdown
---
name: <kort-namn-med-bindestreck>
description: <Vad skillen gör och NÄR den ska användas. Det här är vad som avgör om den laddas.>
---

# <Rubrik>

<Konkreta steg. Hänvisa till filer i repot i stället för att kopiera kod.>
```

När en ny skill har skapats, lägg till den i listan under **Arbetssätt** i `AGENTS.md`.
Skillen går att använda med `/<namn>` från nästa session (eller direkt om sessionen läser in skills på nytt).
