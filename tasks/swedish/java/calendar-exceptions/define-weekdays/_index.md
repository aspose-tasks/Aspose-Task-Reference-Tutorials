---
date: 2026-07-29
description: Lär dig hur du schemalägger icke-arbetsdagar genom att skapa en projektkalender
  med Aspose.Tasks för Java, definiera veckodagsundantag och hantera semesterplaner.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Schemalägg icke-arbetsdagar – Skapa projektkalender Aspose
og_description: Schemalägg icke-arbetsdagar med Aspose.Tasks för Java. Lär dig att
  definiera veckodagar, lägga till kalenderexceptioner och hantera semesterplaner
  effektivt.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Schemalägg icke-arbetsdagar – Skapa projektkalender Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Schemalägg icke-arbetsdagar – Skapa projektkalender Aspose
url: /sv/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Schemalägg icke‑arbetsdagar – Skapa projektkalender Aspose

### Introduktion
När du behöver **schemalägga icke‑arbetsdagar** för ett projekt måste du kunna modellera helgdagar, speciella skift eller tillfälliga stängningar direkt i projektplanen. Aspose.Tasks for Java ger dig full kontroll över kalenderdefinitioner och låter dig lägga till undantag som speglar verkliga scheman. I den här handledningen går vi igenom de exakta stegen för att definiera veckodagar för kalenderundantag, så att dina projekttidslinjer förblir korrekta och pålitliga. I slutet kommer du också att se hur detta passar in i en bredare **icke‑arbetsdagsschema**‑strategi för alla företagsprojekt.

## Snabba svar
- **Vad betyder “schemalägga icke‑arbetsdagar”?**  
  Det betyder att använda Aspose.Tasks för att skapa en kalender som markerar specifika datum som icke‑arbetsdagar, vilket automatiskt påverkar uppgiftsdatum.  
- **Behöver jag en licens för att köra exemplet?**  
  En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilka IDE:er stöds?**  
  IntelliJ IDEA, Eclipse, NetBeans, eller någon IDE som stödjer Java 8+.  
- **Kan jag lägga till flera undantag i samma kalender?**  
  Ja – du kan lägga till så många `CalendarException`‑objekt som behövs.  
- **Vilka filformat kan jag spara projektet i?**  
  XML, MPP och flera andra format som stöds av Aspose.Tasks.  

## Vad är en projektkalender i Aspose.Tasks?
Den **projektkalender** är Aspose.Tasks översta objekt som definierar arbetsdagar och -timmar för ett projekt. Den påverkar direkt uppgiftens start-/slutdatum, resursallokering och övergripande schemaläggningsberäkningar. Genom att anpassa en kalender säkerställer du att schemat respekterar verkliga begränsningar som företagshelgdagar eller helgarbetsregler.

## Varför definiera veckodagar för kalenderundantag?
Att definiera veckodagsundantag säkerställer att projektmotorn behandlar dessa dagar som icke‑arbetsdagar, vilket förhindrar att uppgifter automatiskt schemaläggs på dem och håller tidslinjen i linje med verkliga begränsningar såsom helgdagar, underhållsfönster eller speciella skiftmönster i hela organisationen.

- **Exakta tidslinjer:** Uppgifter placeras inte på helgdagar eller avstängningsperioder.  
- **Resursplanering:** Resurser tilldelas endast på giltiga arbetsdagar, vilket förhindrar överbelastning.  
- **Efterlevnad:** Scheman följer automatiskt organisationspolicyer eller lagstadgade helgdagskalendrar.  

## Icke‑arbetsdagsschema med kalenderundantag
När du underhåller ett **icke‑arbetsdagsschema** har du vanligtvis en huvudlista över helgdagar, underhållsfönster eller andra avstängningsperioder. Att lägga till dessa datum som `CalendarException`‑objekt garanterar att varje beräkning – oavsett om det är kritisk‑vägs‑analys eller resursutjämning – automatiskt respekterar dessa begränsningar. Detta tillvägagångssätt eliminerar manuella datumjusteringar och minskar risken för schemaläggningsavvikelser.

## Förutsättningar
1. **Java Development Kit (JDK)** – version 8 eller senare.  
2. **Aspose.Tasks for Java** – ladda ner från den officiella [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **En IDE** – IntelliJ IDEA, Eclipse, NetBeans eller någon Java‑kompatibel editor.  

## Hur man schemalägger icke‑arbetsdagar med kalenderundantag
Läs in ditt projekt, skapa en anpassad kalender och lägg till `CalendarException`‑objekt som markerar önskade veckodagar som icke‑arbetsdagar. Denna hela process kan genomföras i några enkla steg, och den resulterande kalendern kommer automatiskt att påverka all uppgiftsschemaläggningslogik.

### Steg‑för‑steg‑guide

### Steg 1: Importera nödvändiga paket
Vi behöver de grundläggande Aspose.Tasks‑klasserna och Javas `GregorianCalendar` för datumhantering.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Steg 2: Definiera datakatalogen
Ange var den genererade projektfilen ska sparas.

```java
String dataDir = "Your Data Directory";
```

### Steg 3: Skapa en projektinstans
`Project` är huvudobjektet som innehåller all projektdata, inklusive uppgifter, resurser och kalendrar.

```java
Project project = new Project();
```

### Steg 4: Definiera en kalender
`Calendar` representerar ett schema för arbets‑ och icke‑arbetstider inom ett projekt.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Steg 5: Definiera veckodagsundantag
`CalendarException` representerar en period som markeras som icke‑arbetsdag i en kalender.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Steg 6: Spara projektet
Spara projektet, inklusive den anpassade kalendern och dess undantag, till en XML‑fil.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Undantagsdatum tillämpas inte** | Se till att `setEnteredByOccurrences(false)` och korrekta `FromDate/ToDate`‑värden används. |
| **Sparad fil är tom** | Verifiera att `dataDir` pekar på en skrivbar mapp och att filnamnet slutar med `.xml`. |
| **Kalendern återspeglas inte i uppgiftsschemaläggning** | Tilldela kalendern till uppgifter eller resurser med `task.setCalendar(cal)` eller `resource.setCalendar(cal)`. |

## Vanliga frågor

**Q: Kan jag definiera flera undantag för olika veckodagar inom samma kalender?**  
A: Ja. Lägg till ytterligare `CalendarException`‑objekt till `cal.getExceptions()` för varje distinkt period eller regel.

**Q: Är Aspose.Tasks for Java kompatibel med olika Java‑IDE:er?**  
A: Absolut. Biblioteket fungerar med IntelliJ IDEA, Eclipse, NetBeans och alla IDE:er som stödjer standard‑Java‑projekt.

**Q: Kan jag anpassa undantagstyper förutom dagliga undantag?**  
A: Ja. Använd `CalendarExceptionType.Weekly`, `Monthly` eller `Yearly` för att passa dina schemaläggningsbehov.

**Q: Hur kan jag hantera undantag dynamiskt baserat på projektkrav?**  
A: Bygg undantagsobjekten programatiskt – t.ex. läs in helgdagar från en databas eller konfigurationsfil och skapa `CalendarException`‑instanser i en loop.

**Q: Finns det en provversion av Aspose.Tasks for Java?**  
A: Ja, du kan ladda ner en gratis provversion från [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Slutsats
Genom att följa dessa steg vet du nu hur du **schemalägger icke‑arbetsdagar** genom att skapa en projektkalender och definiera veckodagsundantag som exakt återspeglar helgdagar eller speciella icke‑arbetsperioder. Korrekt kalenderkonfiguration är avgörande för realistiska scheman, resursallokering och projektets övergripande framgång. Utforska vidare genom att koppla den anpassade kalendern till uppgifter eller resurser och experimentera med andra undantagstyper för att bygga ett omfattande **icke‑arbetsdagsschema** för vilket projekt som helst.

---

**Senast uppdaterad:** 2026-07-29  
**Testad med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose

## Relaterade handledningar

- [Lägg till kalender i projekt med Aspose.Tasks för Java](/tasks/java/calendars/create/)
- [Skapa kalenderundantag Aspose för Java](/tasks/java/calendar-exceptions/add-remove/)
- [Hur man ställer in kalender och definierar veckodagar i MS Project med Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}