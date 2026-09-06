---
date: 2026-08-13
description: Lär dig hur du läser arbetsveckor från en MS Project‑kalender med Aspose.Tasks
  för Java. Följ den step‑by‑step guide med code examples och troubleshooting tips.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Läs arbetsveckor från kalender med Aspose.Tasks
og_description: Hur man läser arbetsveckor från en MS Project‑kalender med Aspose.Tasks
  för Java. Följ den concise tutorial med setup steps, code snippets och troubleshooting
  tips.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Hur man läser arbetsveckor från MS‑kalender med Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Hur man läser arbetsveckor från MS‑kalender med Aspose.Tasks
url: /sv/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser arbetsveckor från MS-kalender med Aspose.Tasks

## Introduktion
I den här handledningen kommer du **lära dig att läsa arbetsveckor** från en Microsoft Project-kalender med hjälp av Aspose.Tasks-biblioteket för Java. Oavsett om du bygger en rapporteringsdashboard, synkroniserar scheman med ett ERP‑system eller automatiserar dataextraktion för analys, sparar programmatisk åtkomst till arbetsveksdefinitioner otaliga manuella timmar. Aspose.Tasks stödjer **50+ in‑ och utdataformat** och kan bearbeta projektfiler på flera hundra sidor utan att ladda hela filen i minnet, vilket ger både flexibilitet och prestanda.

## Snabba svar
- **Vad betyder “read workweeks”?** Det avser att extrahera arbetsveksdefinitioner (datum och dagliga arbetstidsregler) från en Project‑fil via Java‑kod.  
- **Vilket bibliotek krävs?** Aspose.Tasks for Java (gratis provversion tillgänglig).  
- **Behöver jag en licens för utveckling?** En provversion fungerar för testning; en kommersiell licens krävs för produktionsdistributioner.  
- **Vilka filformat stöds?** Både *.mpp* och Project XML‑filer hanteras, samt över 50 andra format för import/export.  
- **Hur lång tid tar implementeringen?** Vanligtvis under 10 minuter när biblioteket är installerat.

## Vad är en arbetsvecka i MS Project?
En arbetsvecka definierar kalenderreglerna som bestämmer när resurser är tillgängliga under en specifik period. Den inkluderar ett startdatum, ett slutdatum och dagliga arbetstidsintervall (t.ex. 09.00–17.00). I MS Project kan varje kalender innehålla flera arbetsveckor, vilket gör att du kan modellera helgdagar, skiftmönster eller säsongsplaner.

## Hur läser Aspose.Tasks arbetsveckor från en kalender?
Aspose.Tasks exponerar `WorkWeekCollection` för ett `Calendar`‑objekt. Genom att skapa en `Project`‑instans, välja önskad kalender (via UID eller namn) och iterera över dess `WorkWeekCollection` kan du hämta varje arbetsveckas etikett, giltiga datumintervall och de detaljerade dagliga arbetstidsluckorna. API‑et hanterar alla datum‑ och tidskonverteringar och respekterar automatiskt projektets tidszonsinställningar.

## Varför läsa arbetsveckor i Java från en Microsoft Project‑kalender?
Att läsa arbetsveckor programmässigt eliminerar manuellt kopierande, säkerställer att efterföljande system (ERP, HR, rapportering) använder exakt samma schemaläggningsregler och garanterar konsistens över flera projekt. Automation minskar också mänskliga fel och snabbar upp integrationspipelines, särskilt när du behöver bearbeta dussintals projektfiler varje natt.

## Förutsättningar
Innan vi dyker in i koden, se till att du har:

1. **Java Development Kit (JDK)** – version 8 eller senare installerad.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från den officiella webbplatsen: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. En **exempelfil för Project** (`ReadWorkWeeksInformation.mpp`) placerad i en känd mapp på din maskin.

## Importera paket
Först importerar du de klasser vi behöver för att interagera med kalendrar och arbetsveckor:

`Project` representerar en Microsoft Project‑fil, `Calendar` tillhandahåller dess kalendrar, `WorkWeek` definierar en arbetsvecka och `WeekDay` representerar en dag.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Steg 1: konfigurera din datakatalog
Definiera mappen som innehåller `.mpp`‑filen. Ersätt platshållaren med den faktiska sökvägen på din maskin:

```java
String dataDir = "Your Data Directory";
```

## Steg 2: skapa en Project‑instans och få åtkomst till kalendern
`Project`‑klassen representerar en Microsoft Project‑fil och ger åtkomst till dess datastrukturer, inklusive kalendrar, uppgifter och resurser.  
Instansiera ett `Project`‑objekt, välj den kalender du vill ha (via UID) och hämta dess `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Om du inte är säker på kalender‑UID:n, iterera genom `project.getCalendars()` och skriv ut varje kalenders namn och UID först.

## Steg 3: iterera genom arbetsveckor
`WorkWeek`‑klassen kapslar in en arbetsveckas definition, innehållande start-/slutdatum och dagliga arbetstidsinställningar.  
Loopa igenom varje `WorkWeek` för att visa dess namn, start-/slutdatum och de dagliga arbetstiderna:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Vad du kommer att se:** Konsolen skriver ut varje arbetsveckas etikett (t.ex. “Standard”), dess giltiga datumintervall, och du kan gå ner till de exakta arbetstimmarna för varje dag.

## Vanliga problem och lösningar
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` när du får åtkomst till `calendar` | Fel UID eller kalender finns inte | Verifiera UID:n med `project.getCalendars().size()` och lista tillgängliga kalendrar först. |
| Ingen utskrift för arbetsveckor | Den valda kalendern har inga anpassade arbetsveckor (använder standard) | Använd standardkalendern (`project.getDefaultCalendar()`) eller skapa en arbetsvecka programmässigt. |
| Datumformatet ser konstigt ut | `System.out.println` använder standardformatet för `java.util.Date` | Använd en `SimpleDateFormat` för att formatera datum efter behov. |

## Vanliga frågor
**Q: Kan jag ändra informationen om arbetsveckor med Aspose.Tasks för Java?**  
A: Ja. API‑et tillhandahåller `addWorkWeek()`, `removeWorkWeek()` och egenskaps‑setters för att ändra namn, datum och arbetstider.

**Q: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project‑filer?**  
A: Absolut. Det stödjer MPP‑filer från Project 98 upp till de senaste versionerna, samt Project XML‑filer.

**Q: Kan jag integrera Aspose.Tasks med andra Java‑ramverk?**  
A: Ja. Biblioteket är rent Java, så du kan använda det tillsammans med Spring, Jakarta EE eller något annat ramverk.

**Q: Finns det en provversion av Aspose.Tasks?**  
A: Ja, du kan ladda ner en gratis 30‑dagars provversion från den officiella webbplatsen: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Var kan jag hitta support för Aspose.Tasks?**  
A: Aspose‑community‑forumet är den bästa platsen: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Senast uppdaterad:** 2026-08-13  
**Testat med:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Lägg till kalender i projekt med Aspose.Tasks för Java](/tasks/java/calendars/create/)
- [Hämta kalenderundantag med Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Hur man ställer in kalender och definierar veckodagar i MS Project med Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}