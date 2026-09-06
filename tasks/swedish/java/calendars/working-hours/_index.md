---
date: 2026-08-24
description: Lär dig hur du lägger till en kalender för helgdagar, bestämmer arbetsdagar
  och beräknar uppgiftens varaktighet genom att extrahera arbetstimmar från MS Project‑kalendrar
  med Aspose.Tasks för Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Hur man lägger till en kalender för helgdagar och bestämmer arbetsdagar
og_description: Lär dig hur du lägger till en kalender för helgdagar, bestämmer arbetsdagar
  och beräknar uppgiftens varaktighet genom att extrahera arbetstimmar från MS Project‑kalendrar
  med Aspose.Tasks för Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Hur man lägger till en kalender för helgdagar och bestämmer arbetsdagar
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Hur man lägger till en kalender för helgdagar och bestämmer arbetsdagar
url: /sv/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till helgdagar i kalendern och bestämmer arbetsdagar

Att hantera projektkalendrar är en grundläggande del av framgångsrik projektplanering. I den här handledningen kommer du att **lägga till helgdagar i kalendern**, **bestämma arbetsdagar** för vilken uppgift som helst, och **extrahera arbetstimmar** från en MS Project‑kalender med Aspose.Tasks för Java. I slutet av guiden kommer du att kunna **beräkna uppgiftens varaktighet**, anpassa arbetstimmar och på ett pålitligt sätt **ladda en MPP‑fil** för att hämta de data du behöver — utan att installera Microsoft Project.

## Snabba svar
- **Vad betyder “determine working days”?** Det betyder att identifiera vilka kalenderdatum som betraktas som arbetsdagar för en given uppgift.  
- **Vilket bibliotek ska jag använda?** Aspose.Tasks för Java erbjuder ett fullständigt API för att arbeta med MS Project‑filer.  
- **Hur lång tid tar implementeringen?** Vanligtvis 10–15 minuter för en grundläggande extraktion.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktionsanvändning.  
- **Kan jag anpassa arbetstimmar?** Ja – du kan ändra kalendrar, lägga till helgdagar och ange anpassade arbetstidsintervall.  

## Vad är “determine working days”?
**Determine working days** betyder att fråga ett projektkalender för att ta reda på vilka datum som är markerade som arbetsdagar jämfört med icke‑arbetsdagar (helger, helgdagar eller anpassade undantag). Denna information är avgörande för exakt **calculate task duration** eftersom endast arbetsdagar bidrar till den förflutna tiden för en uppgift.

## Varför använda Aspose.Tasks för att hämta arbetstimmar?
Aspose.Tasks låter dig läsa MS Project‑filer utan att Microsoft Project är installerat, vilket möjliggör automatisering på vilken plattform som helst. Det erbjuder också högpresterande bearbetning, omfattande formatstöd och detaljerad dokumentation.  

- **Full kalenderstöd** – standard-, resurs- och uppgiftskalendrar är alla tillgängliga.  
- **Hög prestanda** – kan bearbeta projekt som innehåller **10 000+ uppgifter på under 2 sekunder** på en standard‑CPU på 2,5 GHz.  
- **Omfattande formatstöd** – stöder **50+ in‑ och utdataformat**, inklusive MPP, MPX, XML och Primavera.  
- **Omfattande dokumentation** – kodexempel, API‑referens och community‑forum finns tillgängliga.

## Förutsättningar
1. **Java Development Kit (JDK)** – version 8 eller högre.  
2. **Aspose.Tasks för Java** – ladda ner den senaste JAR‑filen från [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Grundläggande kunskaper i Java‑programmering.  

## Importera paket
`Project`‑klassen är Aspose.Tasks översta objekt som representerar en enskild MS Project‑fil i minnet. Importera det erforderliga namnutrymmet innan du börjar:

Importera paket

```java
import com.aspose.tasks.*;
```

## Hur man laddar en MPP‑fil med Aspose.Tasks?
`Project`‑klassen laddar en MS Project‑fil och ger åtkomst till dess data. Ladda projektfilen i en enda kodrad; ingen UI eller COM‑interop krävs. Detta enkla steg ger dig full åtkomst till kalendrar, uppgifter och resurser.

Laddar en MPP‑fil

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Hämta uppgifts‑ och kalenderinformation
`Task` representerar en projektuppgift, och `Calendar` definierar dess arbetstidsregler. Välj den uppgift du vill analysera och hämta dess associerade kalender. `Task`‑objektet tillhandahåller metoderna `getStart()` och `getFinish()`, medan `Calendar`‑objektet visar definitioner för arbetstid.

Hämtar uppgift och kalender

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definiera start‑ och slutdatum
`Date`‑objekt specificerar tidsfönstret för kalenderanalys. Ställ in tidsfönstret för vilket du vill **determine working days**. Genom att använda uppgiftens start‑ och slutdatum säkerställer du att du bara utvärderar den relevanta perioden.

Definierar datum

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterera genom datum
En `for`‑loop kan iterera över varje dag i datumintervallet. Loopa igenom varje datum i uppgiftens varaktighet. Denna loop låter dig senare **customize working hours** om det behövs och är grunden för att beräkna total arbetstid.

Itererar datum

```java
java.util.Calendar tempDate = calStartDate;
```

## Beräkna varaktighet
`Duration` samlar den totala arbetstiden som beräknas från iterationen. Under iterationen kontrollerar du om varje dag är en arbetsdag, summerar arbetstimmarna och beräknar slutligen uppgiftens varaktighet i minuter, timmar och dagar. Detta visar hur man **calculate working days** och **calculate task duration** programatiskt.

Beräknar varaktighet

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Hur man anpassar arbetstimmar och helgdagar
Du kan ändra kalenderns arbetstidsintervall och lägga till undantag såsom helgdagar. Använd `taskCalendar.addWorkingTime()` för att ange nya arbetsperioder och `taskCalendar.addException()` för att infoga en helgdag. Detta är användbart när standardtidsplanen 9‑5 inte stämmer överens med din organisations policy.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Uppgift returnerar `null` för kalender** | Se till att uppgiften faktiskt har en kalender tilldelad; annars ärver den projektets standardkalender. |
| **Felaktig varaktighet på grund av helgdagar** | Verifiera att helgdagar är definierade i uppgiftens kalender eller i projektets grundkalender. |
| **Tidszonskillnad** | Använd `java.util.TimeZone` för att justera kalenderns tidszon med ditt system om det behövs. |

## Vanliga frågor
### Q: Kan Aspose.Tasks för Java hantera komplexa projektstrukturer?
A: Ja, Aspose.Tasks för Java erbjuder omfattande stöd för att hantera komplexa projektstrukturer, inklusive uppgifter, resurser och kalendrar.

### Q: Är Aspose.Tasks för Java kompatibel med olika versioner av MS Project?
A: Absolut, Aspose.Tasks för Java stöder olika MS Project‑versioner, vilket säkerställer kompatibilitet över olika miljöer.

### Q: Kan jag anpassa arbetstimmar och helgdagar i projektkalendrar?
A: Ja, du kan enkelt anpassa arbetstimmar och helgdagar enligt dina projektkrav med hjälp av Aspose.Tasks för Java‑API:er.

### Q: Erbjuder Aspose.Tasks för Java support och dokumentation?
A: Ja, Aspose.Tasks för Java tillhandahåller omfattande dokumentation och dedikerade supportforum för att hjälpa utvecklare att effektivt använda dess funktioner.

### Q: Finns en provversion tillgänglig för Aspose.Tasks för Java?
A: Ja, du kan få tillgång till en gratis provversion av Aspose.Tasks för Java från [Aspose releases page](https://releases.aspose.com/).

## Slutsats
I den här guiden demonstrerade vi hur man **add holidays calendar**, **determine working days**, **retrieve working hours**, och **calculate task duration** från en MS Project‑kalender med Aspose.Tasks för Java. Genom att följa stegen ovan kan du automatisera schemaanalys, anpassa kalendrar och hålla dina projektplaner korrekta och uppdaterade. Du har nu verktygen för att **read MS Project**‑data, **load an MPP file**, och utföra precisa varaktighetsberäkningar utan att behöva Microsoft Project själv.

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Relaterade handledningar

- [Lägg till kalender i projekt med Aspose.Tasks för Java](/tasks/java/calendars/create/)
- [Lägg till helgdagar i kalender och spara som MPP med Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Skapa anpassade kalenderundantag med Aspose.Tasks för Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}