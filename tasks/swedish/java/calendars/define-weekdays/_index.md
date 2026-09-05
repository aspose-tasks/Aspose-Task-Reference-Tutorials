---
date: 2026-08-08
description: Lär dig hur du ställer in kalender i MS Project, anger dagliga arbetstimmar
  och lägger till arbetsdagar på helgen med Aspose.Tasks för Java. Spara projektet
  som XML med bara några rader kod.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Hur man ställer in kalender i MS Project och definierar veckodagar
og_description: Ställ in kalender i MS Project, definiera veckodagar och lägg till
  arbetsdagar på helgen med Aspose.Tasks för Java. Följ denna steg-för-steg-handledning
  och spara som XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Ställ in kalender i MS Project med Aspose.Tasks – Java-guide
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Hur man ställer in kalender i MS Project och definierar veckodagar
url: /sv/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in kalender ms project och definierar veckodagar

I den här handledningen kommer du att lära dig **hur man ställer in kalender ms project** programatiskt, definiera veckodagar och konfigurera anpassade arbetsdagar med Aspose.Tasks‑biblioteket för Java. Oavsett om du bygger en schemaläggningsmotor, integrerar med ERP‑system eller bara behöver generera en projektplan utan att öppna Microsoft Project, visar stegen nedan hur du skapar en kalender, anger dagliga arbetstimmar och lägger till helgdagar som arbetsdagar på några få kodrader.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Tasks för Java.  
- **Kan jag lägga till helgdagar som arbetsdagar?** Ja – markera bara lördag och söndag som arbetsdagar.  
- **Hur sparar jag projektet?** Anropa `prj.save(..., SaveFileFormat.Xml)`.  
- **Behövs en licens?** En gratis provversion fungerar för utvärdering; en licens krävs för produktionsanvändning.  
- **Vilken Java‑version stöds?** Java 8 eller högre.

## Vad är set calendar ms project?
Att ställa in kalendern i MS Project bestämmer vilka dagar som räknas som arbetsdagar, antalet arbetstimmar per dag samt eventuella undantag som helgdagar eller företagsstängningar. Denna information styr uppgiftsschemaläggning, resursallokering och hela projektets tidslinjer, så att beräkningarna följer organisationens faktiska arbetsmönster.

## Varför använda Aspose.Tasks för kalenderhantering?
Aspose.Tasks ger dig programmatisk kontroll över kalendrar utan att starta Microsoft Project‑gränssnittet. Det körs på alla operativsystem som stöder Java, hanterar mer än 50 in‑ och utdataformat och kan bearbeta projekt med hundratals sidor utan att ladda hela filen i minnet, vilket gör det idealiskt för server‑sidig automatisering.

## Förutsättningar
- **Java Development Kit (JDK) 8+** – ladda ner från [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks för Java** – hämta den senaste JAR‑filen från [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- En IDE eller byggverktyg (Maven/Gradle) för att lägga till Aspose.Tasks‑JAR‑filen i din classpath.

## Importera paket
Importera de klasser som ger åtkomst till projekt, kalendrar och arbetstid‑objekt.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Steg‑för‑steg guide

### Steg 1: skapa ett projektinstans
Instansiera ett `Project`‑objekt, som representerar den MS Project‑fil du kommer att manipulera.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Steg 2: definiera en ny kalender
`Calendar` representerar en uppsättning arbetstider, undantag och helgdagar för ett projekt.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Steg 3: lägg till standardarbetsdagar (måndag‑torsdag)
`WeekDay` definierar arbetstiden för en specifik veckodag.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Steg 4: lägg till helgdagar som arbetsdagar
Om ditt projekt körs på helger, lägg till lördag och söndag som vanliga arbetsdagar. Detta demonstrerar **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Steg 5: ställ in en anpassad kort arbetsdag (fredag)
Konfigurera fredagen med ett morgonskift (09:00‑12:00) och ett eftermiddagsskift (13:00‑16:00) för att illustrera **set daily working hours** och en anpassad kort arbetsdag.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Steg 6: spara projektet som XML
`SaveFileFormat` listar de filformat som stöds vid sparning av ett projekt, såsom XML eller MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Vanliga problem & lösningar
| Problem | Lösning |
|---------|----------|
| **Arbetstider tillämpas inte** | Se till att `setDayWorking(true)` anropas för varje anpassad `WeekDay`. |
| **Filen hittades inte vid sparning** | Verifiera att `dataDir` pekar på en befintlig mapp och att applikationen har skrivbehörighet. |
| **Kalendern återspeglas inte i uppgifter** | Tilldela den nyss skapade kalendern till resurser eller uppgifter med `task.setCalendar(cal)`. |

## Vanliga frågor

**Q: Kan jag definiera anpassade icke‑arbetsdagar med Aspose.Tasks för Java?**  
A: Ja. Ställ in egenskapen `DayWorking` till `false` för varje `WeekDay` du vill behandla som en icke‑arbetsdag.

**Q: Hur kan jag lägga till helgdagar eller företagsspecifika undantag?**  
A: Skapa `CalendarException`‑objekt, ange undantagsdatumen och lägg till dem i `cal.getExceptions()`.

**Q: Är biblioteket kompatibelt med äldre MS Project‑versioner?**  
A: Absolut. Aspose.Tasks stöder MPP, MPT och XML‑format över flera Project‑versioner.

**Q: Kan jag ändra en befintlig kalender i ett importerat projekt?**  
A: Läs in projektet med `new Project("existing.mpp")`, hämta den önskade kalendern, gör ändringar och spara.

**Q: Hanterar Aspose.Tasks återkommande uppgifter också?**  
A: Ja, du kan skapa och redigera återkommande uppgifter med hjälp av `RecurringTask`‑klassen.

## Slutsats
Du vet nu **hur man ställer in kalender ms project**, definiera veckodagar, lägga till helgdagar som arbetsdagar och konfigurera ett kort fredagschema – allt med Aspose.Tasks för Java. Spara resultatet som XML och integrera kalenderlogiken i vilken Java‑baserad projekt‑hanteringslösning som helst.

---

**Senast uppdaterad:** 2026-08-08  
**Testad med:** Aspose.Tasks för Java 24.11  
**Författare:** Aspose

## Relaterade handledningar

- [Lägg till kalender i projekt med Aspose.Tasks för Java](/tasks/java/calendars/create/)
- [Bestäm arbetsdagar & arbetstimmar med Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Lägg till helgdagar i kalender och spara som MPP med Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}