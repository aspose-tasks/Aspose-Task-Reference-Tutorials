---
date: 2026-08-13
description: Lär dig hur du lägger till helgdagar i en kalender, tilldelar kalendern
  till ett projekt och sparar MS Project-filen som MPP med Aspose.Tasks för Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Uppdatera kalender till MPP-format i Aspose.Tasks
og_description: Lägg till helgdagar i kalendern, tilldela den till ett projekt och
  konvertera schedule till MPP med Aspose.Tasks för Java. Lär dig steg‑för‑steg automation.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Lägg till helgdagar i kalendern och spara som MPP med Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Lägg till helgdagar i kalendern och spara som MPP med Aspose.Tasks
url: /sv/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till helgdagar i kalendern och spara som MPP med Aspose.Tasks

## Introduktion

I modern projektledning behöver du ofta **add holidays to calendar**‑filer, skapa en **MS Project calendar** och sedan dela schemat i det inhemska MPP‑formatet. Oavsett om du konsoliderar tidslinjer från flera källor eller migrerar äldre data, eliminerar generering av en kalender programatiskt manuella fel och snabbar upp leveransen. Denna handledning guidar dig genom hela processen att skapa en kalender i MS Project, anpassa den med helgdagar, **assign calendar to project**, och slutligen **convert project to MPP** med Aspose.Tasks Java‑API.

## Snabba svar
- **What does this tutorial cover?** Lägga till helgdagar i en kalender, tilldela den till ett projekt och spara resultatet som en MPP‑fil med Aspose.Tasks för Java.  
- **Do I need a license?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Which Java version is required?** Java 8 eller högre (JDK 8+).  
- **Can I customize the calendar?** Ja – du kan lägga till arbetstider, undantag och helgdagar.  
- **How long does implementation take?** Ungefär 10‑15 minuter för en grundläggande kalender.  

## Vad är “create calendar MS Project”?

Att skapa en calendar MS Project innebär att definiera arbetsdagar, timmar och undantag som styr uppgiftsschemaläggning i en Microsoft Project‑fil. Med Aspose.Tasks kan du programatiskt bygga denna kalender, ange helgdagar och bädda in den i ett projekt utan att öppna MS Project‑gränssnittet.

## Varför använda Aspose.Tasks för denna uppgift?

Du bör använda Aspose.Tasks eftersom det erbjuder full Java‑kompatibilitet, ingen Microsoft Office‑installation behövs, och du kan generera och spara inhemska MPP‑filer direkt från kod. Biblioteket stöder alla kalenderfunktioner, fungerar i alla servermiljöer och bearbetar projekt med upp till 10 000 uppgifter på under en sekund.

## Förutsättningar

1. **Java Development Kit (JDK) 8+** – se till att `java -version` visar 1.8 eller nyare.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse eller någon annan editor du föredrar.  
4. **Basic Java knowledge** – bekantskap med klasser, metoder och fil‑I/O.

## Hur man lägger till helgdagar i kalendern

För att lägga till helgdagar skapar du ett nytt `Calendar`‑objekt, hämtar dess `Exceptions`‑samling och lägger till `DateException`‑poster för varje helgdag. `DateException` representerar ett enskilt icke‑arbetsdatum eller ett intervall i en kalender. Aspose.Tasks behandlar sedan dessa datum som icke‑arbetsdagar, vilket säkerställer att uppgifter schemaläggs runt de definierade helgdagarna.

### Steg 1: importera nödvändiga paket

Först, importera Aspose.Tasks‑klasserna och Java‑verktygen.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Steg 2: konfigurera datakatalogen

Definiera var dina inmatningsmallar och utdatafiler ska lagras. Ersätt platshållaren med den faktiska sökvägen på din maskin.

```java
String dataDir = "Your Data Directory";
```

### Steg 3: definiera namn på in- och utdatafiler

Vi kommer att läsa in en befintlig MPP‑fil (eller ett tomt projekt) och skriva resultatet till en ny fil.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Steg 4: läs in projektet och lägg till en ny kalender

`Project`‑klassen representerar en MS Project‑fil i minnet och ger åtkomst till dess kalendrar, uppgifter och resurser.

Skapa en `Project`‑instans från källfilen och lägg till en kalender med namnet **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Steg 5: anpassa kalendern (valfritt)

`Calendar`‑objektet definierar arbetsdagar, timmar och undantag för ett projekts schema.

Om du behöver specifika arbetstider, helgdagar eller undantag, anropa din egen hjälpfunktion. Exemplet använder `GetTestCalendar` som en platshållare.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Proffstips:** Du kan direkt manipulera `cal1.getWeekDays()` för att ange arbetstimmar för varje veckodag, eller använda `cal1.getExceptions()` för att **add holidays to calendar**.

### Steg 6: tilldela kalendern till projektet

Berätta för projektet att använda den nyss skapade kalendern för alla sina schemaläggningsberäkningar.

```java
project.set(Prj.CALENDAR, cal1);
```

### Steg 7: spara projektet som MPP

`SaveFileFormat`‑enumerationen specificerar utdataformatet, där `Mpp` indikerar det inhemska Microsoft Project‑formatet.

Nu **convert project to MPP** genom att spara det med `SaveFileFormat.Mpp`‑alternativet.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Steg 8: bekräfta lyckad slutförande

Ett enkelt konsolmeddelande visar att processen avslutades utan fel.

```java
System.out.println("Process completed Successfully");
```

## Vanliga användningsfall

- **Automated schedule generation** för återkommande projekt (t.ex. veckovisa sprintar).  
- **Migrating legacy CSV or Excel calendars** till en fullt utrustad MS Project‑fil.  
- **Server‑side reporting** där en webbtjänst returnerar en MPP‑fil på begäran.  

## Felsökning & vanliga fallgropar

| Problem | Orsak | Lösning |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` pekar på en icke‑existerande mapp | Se till att katalogen finns eller skapa den programatiskt. |
| Kalendern tillämpas inte på uppgifter | Uppgifter refererar fortfarande standardkalendern | Efter att ha satt `Prj.CALENDAR`, uppdatera även varje uppgifts `Task.CALENDAR` om de tidigare har överskrivits. |
| Utdatafilen är 0 KB | Saknade skrivbehörigheter | Kör JVM med lämpliga filsystembehörigheter eller välj en skrivbar sökväg. |

## Vanliga frågor

**Q: Är Aspose.Tasks för Java kompatibel med olika versioner av MS Project?**  
A: Ja, Aspose.Tasks stöder alla Microsoft Project‑filformat från Project 2007 till Project 2024, vilket täcker mer än 10 versioner.

**Q: Kan jag anpassa kalendrar enligt specifika projektkrav?**  
A: Absolut. Du kan definiera arbetsdagar, ange anpassade arbetsveckor, lägga till helgdagar och till och med skapa flera kalendrar i en enda projektfil.

**Q: Erbjuder Aspose.Tasks för Java support för felsökning och hjälp?**  
A: Ja, du kan få hjälp via Aspose.Tasks‑community‑forumet [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Finns det en gratis provversion av Aspose.Tasks för Java?**  
A: Ja, en fullt funktionell gratis provversion finns tillgänglig [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Tasks för Java?**  
A: Tillfälliga licenser kan begäras via Aspose‑webbplatsen [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---
**Senast uppdaterad:** 2026-08-13  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Lägg till kalender i projekt med Aspose.Tasks för Java](/tasks/java/calendars/create/)
- [Hur man definierar veckodagar i MS Project‑kalendrar – Aspose.Tasks Java](/tasks/java/calendars/)
- [Skapa anpassade kalenderundantag med Aspose.Tasks för Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}