---
date: 2026-08-03
description: Lär dig hur du skapar ms project-kalender, lägger till en kalender i
  ett projekt och sparar projektet som XML med Aspose.Tasks for Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Lägg till kalender i projekt med Aspose.Tasks
og_description: Skapa ms project-kalender programatiskt med Aspose.Tasks for Java.
  Lägg till kalendrar, anpassa scheman och exportera till XML på några minuter.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Skapa ms project-kalender med Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Skapa ms project-kalender med Aspose.Tasks for Java
url: /sv/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa ms project-kalender med Aspose.Tasks för Java

## Introduktion
I moderna projekt‑hanteringsarbetsflöden kan förmågan att **create ms project calendar** programatiskt spara timmar av manuellt redigering. Aspose.Tasks för Java ger dig ett rent, typ‑säkert API för att manipulera Microsoft Project‑filer utan att någonsin öppna skrivbordsklienten. I den här handledningen lär du dig hur du lägger till en kalender, hur du skapar en MS Project‑kalender och hur du sparar projektet som XML — allt med bara några rader Java‑kod.

## Snabba svar
- **Vad betyder “create ms project calendar”?**  
  Det betyder att infoga en ny definition av arbetstid (kalender) i en Microsoft Project‑fil via kod.  
- **Vilket bibliotek hanterar detta?**  
  Aspose.Tasks för Java tillhandahåller `Calendar`‑klassen och `Project`‑behållaren för att hantera kalendrar.  
- **Behöver jag en licens?**  
  En tillfällig utvärderingslicens fungerar för testning; en full licens krävs för produktionsanvändning.  
- **Kan jag spara filen som XML?**  
  Ja — använd `SaveFileFormat.Xml` för att exportera projektet som en XML‑fil.  
- **Vad är förutsättningarna?**  
  Java JDK 8+ och Aspose.Tasks för Java‑JAR‑filen på din klassökväg.

## Vad är create ms project calendar?
Att skapa en MS Project‑kalender innebär att programatiskt lägga till en ny kalenderdefinition i en projektfil, ange arbetsdagar, undantag och dagliga arbetstimmar, och sedan tilldela den kalendern till uppgifter, resurser eller hela projektet så att schemaläggningsberäkningarna följer den definierade arbetstiden.

## Varför använda Aspose.Tasks för Java för att lägga till kalender i projektet?
Du bör använda Aspose.Tasks för Java eftersom det erbjuder ett helt typ‑säkert API som fungerar utan att Microsoft Project är installerat, stöder alla större Project‑versioner (2007‑2021, över 5 utgåvor), och kan exportera till XML, MPP och **10+** andra format, vilket möjliggör automatiserad massproduktion av kalendrar på vilken server som helst.

## Förutsättningar
- **Java Development Kit (JDK) 8 eller nyare** installerat och konfigurerat.  
- **Aspose.Tasks för Java**‑biblioteket – ladda ner från den [officiella webbplatsen](https://releases.aspose.com/tasks/java/) och lägg till JAR‑filen i ditt projekts klassökväg.  
- En IDE eller byggverktyg (Maven/Gradle) efter eget val.

## Steg‑för‑steg‑guide

### Steg 1: importera det erforderliga Aspose.Tasks‑paketet
Först, importera Aspose.Tasks‑klasserna så att du kan arbeta med projekt och kalendrar.

```java
import com.aspose.tasks.*;
```

### Steg 2: ange sökvägen till datakatalogen
Definiera var den genererade projektfilen ska skrivas. Ersätt platshållaren med en absolut eller relativ sökväg på din maskin.

```java
String dataDir = "Your Data Directory";
```

### Steg 3: skapa en ny Project‑instans
`Project` är kärnklassen som representerar en Microsoft Project‑fil i minnet.

```java
Project prj = new Project();
```

### Steg 4: definiera de kalendrar du vill lägga till
`Calendar` definierar ett schema med arbetsdagar, undantag och arbetstider för ett projekt.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Proffstips:** Efter att ha lagt till en kalender kan du anpassa dess arbetsdagar med `cal1.getWeekDays().add(...)` och sätta dagliga arbetstimmar med `cal1.getBaseCalendar().setWorkingTime(...)`.

### Steg 5: spara projektet (spara projekt som XML)
`SaveFileFormat.Xml` instruerar Aspose.Tasks att skriva projektet i XML‑format.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Steg 6: visa ett slutförande‑meddelande
Låt användaren veta att operationen har avslutats framgångsrikt.

```java
System.out.println("Process completed Successfully");
```

Genom att följa dessa sex koncisa steg har du framgångsrikt **added a calendar to a project** och sparat resultatet som en XML‑fil.

## Vanliga problem och lösningar
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Projektobjektet är inte korrekt initierat. | Se till att `new Project()` anropas innan du får åtkomst till kalendrar. |
| **Fil ej hittad vid sparning** | `dataDir` pekar på en icke‑existerande mapp. | Skapa katalogen först eller använd en absolut sökväg. |
| **Kalendernamn visas som “no info”** | Platshållarnamn användes i exemplet. | Ersätt med meningsfulla namn som återspeglar schemat (t.ex. “US Holiday Calendar”). |
| **Sparad XML kan inte öppnas i MS Project** | Använder en föråldrad version av Aspose.Tasks. | Uppdatera till den senaste Aspose.Tasks för Java‑utgåvan. |

## Vanliga frågor

**Q: Kan Aspose.Tasks hantera komplexa kalendrar med flera undantag?**  
A: Ja – efter att ha lagt till en kalender kan du definiera undantag, arbetstimmar och icke‑arbetsdagar med hjälp av `WeekDay`‑ och `Exception`‑klasserna.

**Q: Är det möjligt att tilldela den nya kalendern till specifika uppgifter?**  
A: Absolut. Hämta en uppgift via `prj.getRootTask().getChildren().add("Task Name")` och sätt `task.set(Tsk.CALENDAR, cal3);`.

**Q: Stöder biblioteket att spara i andra format som MPP?**  
A: Ja. Ersätt `SaveFileFormat.Xml` med `SaveFileFormat.Mpp` eller `SaveFileFormat.P6` vid behov; Aspose.Tasks stöder **12** utdataformat.

**Q: Behöver jag en licens för utvecklingsbyggen?**  
A: En tillfällig utvärderingslicens räcker för testning; en full licens krävs för produktionsdistributioner.

**Q: Var kan jag få hjälp om jag stöter på problem?**  
A: Aspose.Tasks‑community‑forumet är en utmärkt resurs: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Senast uppdaterad:** 2026-08-03  
**Testat med:** Aspose.Tasks för Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man definierar veckodagar i MS Project‑kalendrar – Aspose.Tasks Java](/tasks/java/calendars/)
- [Hur man ställer in projektkalender i Java med Aspose.Tasks](/tasks/java/calendars/properties/)
- [Skapa anpassade kalenderundantag med Aspose.Tasks för Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}