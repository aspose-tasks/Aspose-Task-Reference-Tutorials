---
date: 2026-02-13
description: Lär dig hur du beräknar dagar mellan datum, skapar ett testprojekt och
  lägger till ett anpassat fält när du manipulerar Microsoft Project‑filer med Aspose.Tasks
  för Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Beräkna dagar mellan datum med Aspose.Tasks för Java
url: /sv/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beräkna dagar mellan datum med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att **beräkna dagar mellan datum** genom att skapa ett testprojekt, lägga till ett anpassat fält och använda Microsoft Project‑formler via Aspose.Tasks‑biblioteket för Java. Oavsett om du behöver generera tidplaner, beräkna deadlines eller automatisera rapportering, låter Aspose.Tasks dig manipulera Project‑data programatiskt utan någon skrivbordsinstallation. I slutet av guiden har du ett körbart exempel som definierar ett utökat attribut, sätter en deadline för en uppgift och sparar projektet som en MPP‑fil.

## Snabba svar
- **Vad täcker handledningen?** Skapa ett testprojekt, lägga till ett anpassat fält, definiera ett utökat attribut och sätta en uppgiftsdeadline med en formel för att beräkna dagar mellan datum.  
- **Vilket bibliotek krävs?** Aspose.Tasks för Java (senaste version).  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **Vilken IDE kan jag använda?** Vilken Java‑IDE som helst (IntelliJ IDEA, Eclipse, VS Code) som stödjer JDK 8+.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för att kopiera koden och köra den.

## Vad är “calculate days between dates” i Aspose.Tasks?
Att beräkna dagar mellan datum innebär att använda en Project‑formel som subtraherar ett datumfält (t.ex. **Finish**) från ett annat (t.ex. **Deadline**) och returnerar det numeriska skillnaden i dagar. Detta är användbart för att följa upp schemaavvikelser, mäta bufferttid eller generera anpassade rapporter.

## Varför använda Aspose.Tasks för att beräkna dagar mellan datum?
- **Full API‑täckning** – åtkomst till alla Project-, Task‑ och Resource‑egenskaper.  
- **Ingen Office‑installation krävs** – fungerar på servrar, CI‑pipelines och Docker‑containrar.  
- **Cross‑platform** – körs på Windows, Linux och macOS med samma Java‑kod.  
- **Robust formelmotor** – låter dig definiera beräkningar som `[Deadline] - [Finish]` direkt i projektfilen.

## Hur man anger deadline för en uppgift
Att sätta en deadline är första steget innan du kan beräkna intervallet. Deadline lagras i fältet `Tsk.DEADLINE` för en uppgift och kan tilldelas med en `java.util.Calendar`‑instans.

## Hur man definierar ett utökat attribut
Ett utökat attribut är det anpassade fält som kommer att hålla resultatet av din formel. Du definierar det en gång, ger det ett alias för läsbarhet och kopplar sedan en formel som utför datumsubtraktionen.

## Förutsättningar
Innan du börjar, se till att du har följande:

- **Java Development Kit (JDK) 8+** – ladda ner från Oracles webbplats eller adoptera OpenJDK.  
- **Aspose.Tasks för Java** – hämta den senaste JAR‑filen från [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) och lägg till den i ditt projekts classpath eller Maven/Gradle‑beroenden.

## Importera paket
Först importerar vi de klasser vi kommer att behöva:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Steg‑för‑steg guide

### Steg 1: Skapa ett testprojekt med ett anpassat fält
Vi börjar med att **skapa ett testprojekt** och lägga till ett anpassat fält som senare kommer att hålla vårt formelresultat.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` är en hjälpfunktion som bygger ett minimalt schema och registrerar ett utökat attribut redo för formeltilldelning.

### Steg 2: Definiera ett utökat attribut (lägg till anpassat fält)
Därefter **definierar vi ett utökat attribut** – i praktiken det anpassade fältet – och ger det ett vänligt alias. Här lägger vi till logiken för det anpassade fältet.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** gör fältet läsbart i Project.  
- **Formel** beräknar antalet dagar mellan en uppgifts *Finish*-datum och dess *Deadline* – kärnan i *calculate days between dates*.

### Steg 3: Ange deadline för en uppgift (lägg till deadline‑uppgift & ange uppgiftsdeadline)
Nu **lägger vi till deadline‑uppgiftsdata** genom att sätta *Deadline*-egenskapen på en specifik uppgift.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar`‑instansen definierar den exakta deadline‑tidpunkten.  
- `set(Tsk.DEADLINE, …)` **sätter uppgiftsdeadline** för den valda uppgiften.

### Steg 4: Spara projektet (manipulera Microsoft Project‑filen)
Slutligen **manipulerar vi Microsoft Project** genom att persistera ändringarna till en MPP‑fil.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Du kan öppna `SaveFile.mpp` i Microsoft Project för att se det anpassade fältet, formelresultatet och deadline reflekterade i tidplanen.

## Vanliga problem och lösningar
| Problem | Lösning |
|---------|----------|
| **Formeln utvärderas inte** | Säkerställ att attributets `Formula`‑sträng använder korrekta fältnamn (t.ex. `[Deadline]`, `[Finish]`). |
| **Uppgift hittades inte** | Verifiera att uppgifts‑ID (`1` i exemplet) finns; använd `project.getRootTask().getChildren().size()` för felsökning. |
| **Licensundantag** | Applicera en giltig Aspose.Tasks‑licens innan du anropar några API‑metoder (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks erbjuder API:er för .NET, Java och andra plattformar, så att du kan **manipulera Microsoft Project**‑filer i det språk du föredrar.

**Q: Finns det en gratis provversion av Aspose.Tasks?**  
A: Absolut. Ladda ner en fullt funktionell provversion från [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks?**  
A: Den officiella dokumentationen finns på [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Hur kan jag få support för Aspose.Tasks?**  
A: Besök [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för att ställa frågor och dela erfarenheter med communityn.

**Q: Behöver jag en tillfällig licens för utvärdering?**  
A: En tillfällig licens finns tillgänglig för korttids‑testning; du kan begära en [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-02-13  
**Testad med:** Aspose.Tasks för Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}