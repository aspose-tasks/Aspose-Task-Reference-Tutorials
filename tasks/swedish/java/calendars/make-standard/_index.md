---
date: 2026-08-13
description: Lär dig hur du skapar en standard‑MS Project‑kalender i Java med Aspose.Tasks.
  Denna steg‑för‑steg‑guide visar hur du skapar en standard‑MS Project‑kalender, lägger
  till den som standard och sparar filen.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Skapa standardkalender i Aspose.Tasks
og_description: Hur man skapar kalender i Java med Aspose.Tasks. Lär dig att bygga
  en standard‑MS Project‑kalender, sätta den som standard och spara projektfilen på
  några minuter.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Hur man skapar kalender – skapa standardkalender i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Hur man skapar kalender – skapa standardkalender i Aspose.Tasks
url: /sv/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar kalender – skapa standardkalender i Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig **hur man skapar kalender**‑objekt för Microsoft Project‑filer genom att använda Aspose.Tasks för Java‑biblioteket. Vi går igenom hur man skapar en standard‑MS‑Project‑kalender, gör den till standard‑kalender och sparar projektfilen. I slutet av guiden kan du integrera kalender‑skapande i vilken Java‑baserad projekt‑hanteringslösning som helst.

## Snabba svar
- **Vad betyder “standardkalender”?** Det är den förvalda arbetstidsdefinitionen som tillämpas på uppgifter som inte har en anpassad kalender tilldelad.  
- **Vilket bibliotek krävs?** Aspose.Tasks för Java – ett rent Java‑API som fungerar utan att Microsoft Project är installerat.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktionsmiljöer.  
- **Vilket filformat genereras?** En XML‑baserad Microsoft Project‑fil (`.xml`).  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för en grundläggande kalenderinställning.

## Vad är en standardkalender i Microsoft Project?
En standardkalender definierar de förvalda arbetsdagarna och arbetstiderna för ett projekt, vanligtvis måndag till fredag, 08.00‑17.00. När du lägger till en standardkalender ärver varje uppgift som inte har en anpassad kalender dessa arbetstider, vilket säkerställer enhetlig schemaläggning i hela projektet.

## Varför använda Aspose.Tasks för att skapa en kalender?
Aspose.Tasks för Java stöder **50+ in‑ och utdataformat** och kan bearbeta projekt med upp till **10 000 uppgifter** utan att läsa in hela filen i minnet. Detta rena Java‑bibliotek låter dig automatisera skapandet av Project‑filer på servrar, CI‑pipelines eller i vilken Java‑applikation som helst, utan behov av en licensierad Microsoft Project‑installation.

## Förutsättningar
Innan du börjar, se till att följande är på plats:

### Installation av Java Development Kit (JDK)
Installera den senaste JDK:n från Oracles webbplats eller en OpenJDK‑distribution.

### Aspose.Tasks för Java‑biblioteket
Ladda ner biblioteket från [nedladdningssidan](https://releases.aspose.com/tasks/java/). Lägg till JAR‑filen i ditt projekts classpath.

## Importera paket
Vi behöver bara en import för den här handledningen:

```java
import com.aspose.tasks.*;
```

## Steg‑för‑steg‑guide

### Steg 1: konfigurera datakatalogen
Definiera var den genererade projektfilen ska sparas.

```java
String dataDir = "Your Data Directory";
```

Byt ut `"Your Data Directory"` mot den absoluta sökvägen på din maskin (t.ex. `C:/Projects/Output/`).

### Steg 2: skapa ett projekt‑instans
`Project` är Aspose.Tasks översta objekt som representerar en enda Microsoft Project‑fil i minnet. Att instansiera den ger dig en behållare för kalendrar, uppgifter, resurser och annan projektdata.

```java
Project project = new Project();
```

### Steg 3: definiera och gör kalendern till standard
`Calendar` är klassen som modellerar ett arbetstidschema. Genom att lägga till en ny kalender med namnet **“My Cal”** och anropa `makeStandardCalendar` gör du den till standardkalender för hela projektet.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Pro tip:** Metoden `makeStandardCalendar` markerar automatiskt den angivna kalendern som standard för projektet, vilket är exakt vad du behöver när du vill **lägga till standardkalender**‑funktionalitet.

### Steg 4: spara projektet
SaveFileFormat är en uppräkning som specificerar vilket filformat som ska användas när ett projekt sparas.  
Spara projektet (inklusive den nya kalendern) till en XML‑fil.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Du kan ändra filnamnet eller formatet (`SaveFileFormat.Pp`) om du föredrar en annan Project‑version.

### Steg 5: visa slutförandemeddelande
Ge dig själv en visuell indikation på att processen avslutades utan fel.

```java
System.out.println("Process completed Successfully");
```

## Vanliga problem & lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| **Filen hittades inte** | `dataDir` pekar på en icke‑existerande mapp | Skapa mappen eller använd en absolut sökväg |
| **Licensundantag** | Kör utan en giltig Aspose.Tasks‑licens i produktion | Använd en licensfil via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Tom kalender** | Glömt att lägga till arbetstidsdefinitioner | Använd `cal1.getWeekDays().add(WeekDay.DayType.Monday)` osv., om du behöver anpassade timmar |

## Vanliga frågor

**Q: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?**  
A: Ja, Aspose.Tasks stöder ett brett spektrum av Microsoft Project‑versioner, från 2000 upp till de senaste utgåvorna.

**Q: Kan jag anpassa kalenderinställningarna ytterligare?**  
A: Absolut! Du kan ändra arbetsdagar, lägga till undantag och definiera specifika arbetstider med klasserna `WeekDay` och `WorkingTime`.

**Q: Är Aspose.Tasks lämplig för företagsnivå‑applikationer?**  
A: Självklart. Biblioteket är designat för högpresterande, skalbara miljöer och erbjuder omfattande stöd för stora Project‑filer.

**Q: Erbjuder Aspose.Tasks teknisk support för utvecklare?**  
A: Ja, Aspose tillhandahåller dedikerade forum, ärendebaserad support och omfattande dokumentation för att hjälpa dig lösa problem snabbt.

**Q: Kan jag prova Aspose.Tasks innan jag köper?**  
A: Ja, du kan utforska en gratis provversion som finns på [webbplatsen](https://purchase.aspose.com/buy), så att du kan utvärdera alla funktioner innan du bestämmer dig.

---

**Senast uppdaterad:** 2026-08-13  
**Testad med:** Aspose.Tasks för Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Lägg till kalender i projekt med Aspose.Tasks för Java](/tasks/java/calendars/create/)
- [Hur man ställer in projektkalender Java med Aspose.Tasks](/tasks/java/calendars/properties/)
- [Skapa anpassade kalenderexceptioner med Aspose.Tasks för Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}