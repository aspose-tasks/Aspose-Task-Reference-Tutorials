---
date: 2025-12-07
description: Lär dig hur du **skapar testprojekt** och **lägger till ett anpassat
  fält** när du manipulerar Microsoft Project-filer med Aspose.Tasks för Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Skapa testprojekt och använd formler med Aspose.Tasks för Java
url: /sv/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa testprojekt och använd formler med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att **skapa testprojekt**‑filer, lägga till ett anpassat fält och arbeta med MS Project‑formler med hjälp av Aspose.Tasks‑biblioteket för Java. Aspose.Tasks gör det enkelt att **manipulera Microsoft Project**‑data programmässigt—oavsett om du behöver generera scheman, beräkna datum eller automatisera rapportering. I slutet av guiden har du ett körbart exempel som definierar ett utökat attribut, sätter en deadline för en uppgift och sparar projektet som en MPP‑fil.

## Snabba svar
- **Vad täcker handledningen?** Skapa ett testprojekt, lägga till ett anpassat fält, definiera ett utökat attribut och sätta en uppgiftsdeadline med en formel.  
- **Vilket bibliotek krävs?** Aspose.Tasks för Java (senaste versionen).  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en licens krävs för produktion.  
- **Vilken IDE kan jag använda?** Vilken Java‑IDE som helst (IntelliJ IDEA, Eclipse, VS Code) som stödjer JDK 8+.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för att kopiera koden och köra den.

## Vad är ett “testprojekt” i Aspose.Tasks?
Ett **testprojekt** är en lättviktig Microsoft Project‑fil som skapas programmässigt för att demonstrera eller validera funktionalitet. Det innehåller en minimal uppsättning uppgifter, resurser och anpassade fält som du kan manipulera utan att påverka riktiga projektdata.

## Varför använda Aspose.Tasks för att manipulera Microsoft Project?
- **Full API‑täckning** – åtkomst till varje Project-, Task- och Resource‑egenskap.  
- **Ingen Office‑installation krävs** – fungerar på servrar, CI‑pipelines och Docker‑containrar.  
- **Plattformsoberoende** – körs på Windows, Linux och macOS med samma Java‑kod.  
- **Robust formelmotor** – beräkna datum, varaktigheter och anpassade fält direkt i projektfilen.

## Förutsättningar
Innan du börjar, se till att du har följande:

- **Java Development Kit (JDK) 8+** – ladda ner från Oracles webbplats eller adoptera OpenJDK.  
- **Aspose.Tasks for Java** – hämta den senaste JAR‑filen från [Aspose.Tasks för Java nedladdningssida](https://releases.aspose.com/tasks/java/) och lägg till den i ditt projekts classpath eller Maven/Gradle‑beroenden.

## Importera paket
Först, importera de klasser vi behöver:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Steg‑för‑steg‑guide

### Steg 1: Skapa ett testprojekt med ett anpassat fält
Vi börjar med att **skapa testprojekt** och lägga till ett anpassat fält som senare kommer att hålla vårt formelresultat.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` är en hjälpfunktion som bygger ett minimalt schema och registrerar ett utökat attribut redo för formeltilldelning.

### Steg 2: Definiera ett utökat attribut (lägg till anpassat fält)
Därefter **definierar vi ett utökat attribut** – i princip det anpassade fältet – och ger det ett vänligt alias. Här lägger vi till logiken för **att lägga till anpassat fält**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** gör fältet läsbart i Project.  
- **Formel** beräknar antalet dagar mellan en uppgifts *Finish*-datum och dess *Deadline*.

### Steg 3: Sätt deadline för en uppgift (lägg till deadline‑uppgift & sätt uppgiftsdeadline)
Nu **lägger vi till deadline‑uppgifts**‑data genom att sätta *Deadline*-egenskapen på en specifik uppgift.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar`‑instansen definierar den exakta deadline‑tidpunkten.  
- `set(Tsk.DEADLINE, …)` **sätter uppgiftsdeadline** för den valda uppgiften.

### Steg 4: Spara projektet (manipulera Microsoft Project‑fil)
Till sist **manipulerar vi Microsoft Project** genom att spara ändringarna till en MPP‑fil.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Du kan öppna `SaveFile.mpp` i Microsoft Project för att se det anpassade fältet, formelresultatet och deadlinen reflekterade i schemat.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Formeln utvärderas inte** | Se till att attributets `Formula`‑sträng använder korrekta fältnamn (t.ex. `[Deadline]`, `[Finish]`). |
| **Uppgift ej hittad** | Verifiera att uppgifts‑ID (`1` i exemplet) finns; använd `project.getRootTask().getChildren().size()` för felsökning. |
| **Licensundantag** | Applicera en giltig Aspose.Tasks‑licens innan du anropar några API‑metoder (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks tillhandahåller API:er för .NET, Java och andra plattformar, vilket gör att du kan **manipulera Microsoft Project**‑filer i det språk du föredrar.

**Q: Finns det en gratis provversion av Aspose.Tasks?**  
A: Absolut. Ladda ner en fullt funktionell provversion från [Aspose.Tasks nedladdningssida](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks?**  
A: Den officiella dokumentationen finns på [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Hur kan jag få support för Aspose.Tasks?**  
A: Besök [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för att ställa frågor och dela erfarenheter med communityn.

**Q: Behöver jag en tillfällig licens för utvärdering?**  
A: En tillfällig licens finns tillgänglig för korttids‑testning; du kan begära en [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2025-12-07  
**Testat med:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}