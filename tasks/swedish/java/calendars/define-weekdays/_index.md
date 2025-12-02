---
date: 2025-12-02
description: Lär dig hur du ställer in kalender, definierar veckodagar i MS Project
  och anger anpassade arbetsdagar med Aspose.Tasks för Java. Spara projektet som XML
  med bara några rader kod.
language: sv
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man ställer in kalender och definierar veckodagar i MS Project med Aspose.Tasks
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så ställer du in kalender och definierar veckodagar i MS Project med Aspose.Tasks

## Introduktion
I den här handledningen kommer du att upptäcka **hur man ställer in kalender**‑inställningar programatiskt och definiera veckodagar i en Microsoft Project‑fil med hjälp av Aspose.Tasks‑biblioteket för Java. Oavsett om du behöver skapa en standardarbetsvecka, lägga till arbetsdagar på helgen eller konfigurera ett kort fredags‑schema, guidar den här artikeln dig genom varje steg – från projektets skapande till att spara filen som XML.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Tasks för Java  
- **Kan jag lägga till arbetsdagar på helgen?** Ja – lägg bara till lördag och söndag som arbetsdagar.  
- **Hur sparar jag projektet?** Använd `prj.save(..., SaveFileFormat.Xml)`.  
- **Behöver jag en licens?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.  
- **Vilken Java‑version krävs?** Java 8 eller högre.

## Vad betyder “hur man ställer in kalender” i MS Project‑sammanhang?
Att ställa in en kalender i MS Project innebär att definiera vilka dagar som är arbetsdagar, de dagliga arbetstimmarna samt eventuella undantag som helgdagar. Denna kalender styr uppgiftsschemaläggning, resursallokering och hela projektets tidslinjer.

## Varför använda Aspose.Tasks för kalenderhantering?
- **Full kontroll** – skapa, ändra eller ta bort kalendrar programatiskt utan att öppna UI.  
- **Plattformsoberoende** – fungerar på alla OS som stödjer Java.  
- **Stöder alla filformat** – MPP, MPT och XML, så du kan *spara projekt som XML* för enkel integration med andra system.  
- **Inga COM‑beroenden** – till skillnad från Microsoft Project Interop‑biblioteket.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK) 8+** – ladda ner från [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks för Java** – hämta den senaste JAR‑filen från [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. En IDE eller byggverktyg (Maven/Gradle) för att lägga till Aspose.Tasks JAR i ditt projekts classpath.

## Importera paket
Först importerar du de klasser du behöver. Dessa importeringar ger dig åtkomst till projekt‑, kalender‑ och arbetstid‑objekt.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Steg‑för‑steg‑guide

### Steg 1: Skapa en projektinstans
Skapa ett nytt `Project`‑objekt. Detta objekt representerar den MS Project‑fil du kommer att redigera.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Steg 2: Definiera en ny kalender
Lägg till en ny kalender i projektet. Att ge den ett tydligt namn underlättar när du har flera kalendrar.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Steg 3: Lägg till standardarbetsdagar (måndag‑torsdag)
Använd den inbyggda hjälpfunktionen `WeekDay.createDefaultWorkingDay` för att sätta standardtiden 9 – 17 för kärnarbetsveckan.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Steg 4: Lägg till arbetsdagar på helgen
Om ditt projekt körs på helgerna, lägg bara till lördag och söndag som vanliga arbetsdagar. Detta demonstrerar **lägga till arbetsdagar på helgen**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Steg 5: Ställ in en anpassad kort arbetsdag (fredag)
Här **ställer vi in anpassade arbetsdagar** för fredag: ett morgonskift (9 – 12) och ett eftermiddagsskift (13 – 16).

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

### Steg 6: Spara projektet som XML
Till sist, spara ändringarna. Alternativet `SaveFileFormat.Xml` låter dig **spara projekt som XML**, vilket är användbart för integration med andra verktyg.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Vanliga problem & lösningar
| Problem | Lösning |
|-------|----------|
| **Arbetstider tillämpas inte** | Se till att `setDayWorking(true)` anropas på den anpassade `WeekDay`. |
| **Filen hittas inte vid sparning** | Verifiera att `dataDir` pekar på en befintlig mapp och att din applikation har skrivrättigheter. |
| **Kalendern återspeglas inte i uppgifter** | Tilldela den nyss skapade kalendern till resurser eller uppgifter med `task.setCalendar(cal)`. |

## Vanliga frågor

**Q: Kan jag definiera anpassade icke‑arbetsdagar med Aspose.Tasks för Java?**  
A: Ja. Sätt `DayWorking`‑egenskapen till `false` för vilken `WeekDay` du vill behandla som en icke‑arbetsdag.

**Q: Hur kan jag lägga till helgdagar eller företagsspecifika undantag?**  
A: Skapa `CalendarException`‑objekt, ange undantagsdatumen och lägg till dem i `cal.getExceptions()`.

**Q: Är biblioteket kompatibelt med äldre MS Project‑versioner?**  
A: Absolut. Aspose.Tasks stöder MPP‑, MPT‑ och XML‑format över flera Project‑versioner.

**Q: Kan jag ändra en befintlig kalender i ett importerat projekt?**  
A: Ladda projektet med `new Project("existing.mpp")`, hämta den önskade kalendern, gör ändringar och spara.

**Q: Hanterar Aspose.Tasks återkommande uppgifter också?**  
A: Ja, du kan skapa och redigera återkommande uppgifter med klassen `RecurringTask`.

## Slutsats
Du vet nu **hur man ställer in kalender**‑inställningar, **definierar veckodagar i MS Project**, lägger till arbetsdagar på helgen och skapar ett kort fredags‑schema – allt med Aspose.Tasks för Java. Spara resultatet som XML och integrera kalenderlogiken i vilken Java‑baserad projektstyrningslösning som helst.

---

**Senast uppdaterad:** 2025-12-02  
**Testad med:** Aspose.Tasks för Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}