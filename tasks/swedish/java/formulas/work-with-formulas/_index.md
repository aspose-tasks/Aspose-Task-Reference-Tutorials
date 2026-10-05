---
date: 2026-10-05
description: Lär dig hur du skapar testprojekt och beräknar dagar mellan datum med
  Aspose.Tasks för Java, lägger till ett custom field och hanterar MPP-filer effektivt.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Arbeta med formler i Aspose.Tasks
og_description: Skapa testprojekt och beräkna dagar mellan datum med Aspose.Tasks
  för Java. Denna guide visar hur du lägger till ett custom field, sätter task deadlines
  och sparar projektet som en MPP-fil.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Skapa testprojekt och beräkna dagar mellan datum
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Skapa testprojekt och beräkna dagar mellan datum
url: /sv/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa testprojekt och beräkna dagar mellan datum

I den här handledningen kommer du att **skapa testprojekt** och **beräkna dagar mellan datum** genom att lägga till ett anpassat fält, definiera ett utökat attribut och tillämpa en Microsoft Project-formel via Aspose.Tasks-biblioteket för Java. Oavsett om du behöver generera scheman, beräkna deadlines eller automatisera rapportering, låter Aspose.Tasks dig manipulera Project-data programatiskt utan en skrivbordsinstallation, med stöd för över 50 in- och utdataformat och hanterar filer med flera hundra sidor i minnes‑effektiv läge.

## Snabba svar
- **Vad täcker handledningen?** Den visar hur man skapar ett testprojekt, definierar ett utökat attribut, sätter en uppgiftdeadline och använder en formel för att beräkna dagar mellan datum.  
- **Vilket bibliotek krävs?** Aspose.Tasks for Java (latest version).  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktionsanvändning.  
- **Vilken IDE kan jag använda?** Valfri Java‑IDE (IntelliJ IDEA, Eclipse, VS Code) som stödjer JDK 8+.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för att kopiera koden och köra den.

## Vad är “calculate days between dates” i Aspose.Tasks?
I Aspose.Tasks är en formel en sträng som kan referera till uppgiftsfält och utföra beräkningar. `[Deadline] - [Finish]` är den formelsyntax som Aspose.Tasks använder för att returnera det numeriska skillnaden i dagar mellan två datumfält. Resultatet lagras som ett numeriskt värde som representerar hela dagar, vilket du kan visa i ett anpassat fält eller använda i vidare beräkningar.

## Varför använda Aspose.Tasks för att beräkna dagar mellan datum?
Aspose.Tasks erbjuder **full API-täckning** för varje Project-, Task- och Resource‑egenskap, körs på Windows, Linux och macOS, och **kräver inte Microsoft Project eller Office** för installation. Motorn kan bearbeta projekt med **500+ uppgifter** på under en sekund på vanlig serverhårdvara, vilket gör den idealisk för CI‑pipelines, Docker‑behållare och högvolym batch‑bearbetning.

## Hur man sätter deadline för en uppgift
`java.util.Calendar` är en Java‑klass som representerar ett specifikt ögonblick i tiden. Du sätter en deadline genom att tilldela ett `java.util.Calendar`‑värde till fältet `Tsk.DEADLINE` för en uppgift. Efter att ha skapat Calendar‑instansen, sätt dess år, månad och dag till önskad deadline, och anropa sedan `task.set(Tsk.DEADLINE, calendar);`. Deadline lagras i projektfilen och kan användas i formler såsom `[Deadline] - [Finish]`.

## Hur man definierar ett utökat attribut
Ett utökat attribut är ett anpassat fält som lagrar resultatet av din formel. Du skapar det en gång, ger det ett vänligt alias och bifogar uttrycket `[Deadline] - [Finish]` så att varje uppgift automatiskt kan beräkna intervallet. Skapa det genom att instansiera `ExtendedAttribute`, sätta dess Alias, tilldela formeln och lägga till det i projektets samling.

## Förutsättningar
- **Java Development Kit (JDK) 8+** – ladda ner från Oracles webbplats eller adoptera OpenJDK.  
- **Aspose.Tasks for Java** – hämta den senaste JAR‑filen från [Aspose.Tasks för Java nedladdningssida](https://releases.aspose.com/tasks/java/) och lägg till den i ditt projekts classpath eller Maven/Gradle‑beroenden.

## Importera paket
First, import the classes we’ll need:

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
Därefter **definierar vi ett utökat attribut** – i princip det anpassade fältet – och ger det ett vänligt alias. Detta är där vi **lägger till anpassat fält** logik.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** gör fältet läsbart i Project.  
- **Formula** beräknar antalet dagar mellan en uppgifts *Finish*-datum och dess *Deadline* – kärnan i *calculate days between dates*.

### Steg 3: Sätt deadline för en uppgift (lägg till deadline‑uppgift & sätt uppgiftsdeadline)
Nu **lägger vi till deadline‑uppgift**-data genom att sätta *Deadline*-egenskapen på en specifik uppgift.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar`‑instansen definierar det exakta deadline‑ögonblicket.  
- `set(Tsk.DEADLINE, …)` **sätter uppgiftsdeadline** för den valda uppgiften.

### Steg 4: Spara projektet (manipulera Microsoft Project‑fil)
Slutligen **manipulerar vi Microsoft Project** genom att spara ändringarna till en MPP‑fil.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Du kan öppna `SaveFile.mpp` i Microsoft Project för att se det anpassade fältet, formelresultatet och deadline reflekterade i schemat.

## Vanliga problem och lösningar
| Issue | Solution |
|-------|----------|
| **Formeln utvärderas inte** | Se till att attributets `Formula`‑sträng använder korrekta fältnamn (t.ex. `[Deadline]`, `[Finish]`). |
| **Uppgift ej hittad** | Verifiera att uppgifts‑ID (`1` i exemplet) finns; använd `project.getRootTask().getChildren().size()` för felsökning. |
| **Licensundantag** | Applicera en giltig Aspose.Tasks‑licens innan du anropar några API‑metoder (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks tillhandahåller API:er för .NET, Java och andra plattformar, vilket gör att du kan manipulera Microsoft Project‑filer i det språk du föredrar.

**Q: Finns det en gratis provversion av Aspose.Tasks?**  
A: Absolut. Ladda ner en fullt funktionell provversion från [Aspose.Tasks nedladdningssida](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.Tasks?**  
A: Den officiella dokumentationen finns på [Aspose.Tasks Java API‑referens](https://reference.aspose.com/tasks/java/).

**Q: Hur kan jag få support för Aspose.Tasks?**  
A: Besök [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för att ställa frågor och dela erfarenheter med communityn.

**Q: Behöver jag en tillfällig licens för utvärdering?**  
A: En tillfällig licens finns tillgänglig för korttids‑testning; du kan begära en från [sidan för begäran av tillfällig licens](https://purchase.aspose.com/temporary-license/).

**Senast uppdaterad:** 2026-10-05  
**Testad med:** Aspose.Tasks for Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar MPP‑fil – Skapa och spara tomt projekt i MPP‑format med Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Ställ in projektets startdatum i MS Project med Aspose.Tasks för Java](/tasks/java/project-properties/write-project-info/)
- [Hur man skapar utökat attribut i Java med Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}