---
date: 2026-02-05
description: Lär dig hur du bestämmer arbetsdagar och beräknar uppgiftens varaktighet
  genom att extrahera arbetstimmar från MS Project‑kalendrar med Aspose.Tasks för
  Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Bestäm arbetsdagar och arbetstimmar med Aspose.Tasks
url: /sv/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestäm arbetsdagar och arbetstimmar med Aspose.Tasks

## Introduktion
Att hantera projektkalendrar är en grundläggande del av framgångsrik projektplanering. I den här handledningen kommer du att **bestämma arbetsdagar** för vilken uppgift som helst och **extrahera arbetstimmar** från en MS Project-kalender med hjälp av Aspose.Tasks för Java. I slutet av guiden kommer du att kunna **beräkna uppgiftens varaktighet**, anpassa arbetstimmar och på ett pålitligt sätt **ladda en MPP-fil** för att hämta den data du behöver. Du kommer också att se hur du **läser MS Project**-filer utan att ha Microsoft Project installerat, vilket gör automatisering möjlig på vilken plattform som helst.

## Snabba svar
- **Vad betyder “determine working days”?** Det betyder att identifiera vilka kalenderdatum som betraktas som arbetsdagar för en given uppgift.  
- **Vilket bibliotek ska jag använda?** Aspose.Tasks för Java erbjuder ett fullständigt API för att arbeta med MS Project-filer.  
- **Hur lång tid tar implementeringen?** Vanligtvis 10–15 minuter för en grundläggande extraktion.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktionsanvändning.  
- **Kan jag anpassa arbetstimmar?** Ja – du kan modifiera kalendrar, lägga till helgdagar och ange anpassade arbetstidsintervall.  

## Vad är “determine working days”?
När en uppgift schemaläggs definierar projektkalendern vilka dagar som är arbetsdagar och vilka som är icke‑arbetsdagar (helger, helgdagar). Att bestämma arbetsdagar innebär att fråga kalendern för att exakt veta när arbete kan utföras, vilket är avgörande för korrekta **calculate task duration**-beräkningar.

## Varför använda Aspose.Tasks för att hämta arbetstimmar?
- **Ingen Microsoft Project krävs** – du kan läsa MS Project-filer direkt från Java-kod.  
- **Full kalenderstöd** – inkluderar standard-, resurs- och uppgiftskalendrar.  
- **Hög prestanda** – bearbeta stora projekt snabbt.  
- **Omfattande dokumentation** – exempel och API-referens finns lättillgängliga.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK)** – version 8 eller högre.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR-filen från [here](https://releases.aspose.com/tasks/java/).  
3. Grundläggande kunskaper i Java-programmering.  

## Importera paket
Först, importera det centrala Aspose.Tasks-namnområdet:

```java
import com.aspose.tasks.*;
```

## Hur laddar man en MPP-fil med Aspose.Tasks?
Att ladda projektfilen är det första steget mot all kalenderanalys. API:et låter dig **ladda en MPP-fil** i en enda kodrad, utan att behöva MS Project-användargränssnittet.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Hämta uppgift- och kalenderinformation
Välj den uppgift du vill analysera och hämta dess associerade kalender. Här **hämtar vi arbetstimmar** för uppgiften:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definiera start- och slutdatum
Ställ in tidsfönstret för vilket du vill **bestämma arbetsdagar**. Genom att använda uppgiftens start- och slutdatum säkerställer du att du bara utvärderar den relevanta perioden.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterera genom datum
Loopa genom varje datum i uppgiftens varaktighet. Denna loop hjälper oss att senare **anpassa arbetstimmar** om det behövs:

```java
java.util.Calendar tempDate = calStartDate;
```

## Beräkna varaktighet
Under iterationen kontrollerar vi om varje dag är en arbetsdag, summerar arbetstimmarna och beräknar slutligen uppgiftens varaktighet i minuter, timmar och dagar. Detta steg visar hur man **calculate working days** och **calculate task duration** programatiskt.

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
Aspose.Tasks låter dig ändra kalenderns arbetstidsintervall och lägga till undantag såsom helgdagar. Du kan anropa `taskCalendar.addWorkingTime()` eller `taskCalendar.addException()` för att anpassa schemat efter din organisations policy. Detta är användbart när standardtiden 9‑5 inte stämmer med verkligheten.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Uppgift returnerar `null` för kalender** | Se till att uppgiften faktiskt har en kalender tilldelad; annars ärver den projektets standardkalender. |
| **Felaktig varaktighet på grund av helgdagar** | Verifiera att helgdagar är definierade i uppgiftens kalender eller i projektets baskalender. |
| **Tidszonsfel** | Använd `java.util.TimeZone` för att justera kalenderns tidszon med ditt system om det behövs. |

## Vanliga frågor
### Q: Kan Aspose.Tasks för Java hantera komplexa projektstrukturer?
A: Ja, Aspose.Tasks för Java erbjuder omfattande stöd för att hantera komplexa projektstrukturer, inklusive uppgifter, resurser och kalendrar.

### Q: Är Aspose.Tasks för Java kompatibel med olika versioner av MS Project?
A: Absolut, Aspose.Tasks för Java stödjer olika versioner av MS Project, vilket säkerställer kompatibilitet i olika miljöer.

### Q: Kan jag anpassa arbetstimmar och helgdagar i projektkalendrar?
A: Ja, du kan enkelt anpassa arbetstimmar och helgdagar enligt dina projektkrav med hjälp av Aspose.Tasks för Java API:er.

### Q: Erbjuder Aspose.Tasks för Java support och dokumentation?
A: Ja, Aspose.Tasks för Java tillhandahåller omfattande dokumentation och dedikerade supportforum för att hjälpa utvecklare att använda dess funktioner effektivt.

### Q: Finns en provversion tillgänglig för Aspose.Tasks för Java?
A: Ja, du kan få åtkomst till en gratis provversion av Aspose.Tasks för Java från [here](https://releases.aspose.com/).

## Slutsats
I den här guiden demonstrerade vi hur man **bestämmer arbetsdagar**, **hämtar arbetstimmar** och **beräknar uppgiftens varaktighet** från en MS Project-kalender med Aspose.Tasks för Java. Genom att följa stegen ovan kan du automatisera schemalägesanalys, anpassa kalendrar och hålla dina projektplaner korrekta och uppdaterade. Du har nu verktygen för att **läsa MS Project**-data, **ladda en MPP-fil** och utföra precisa varaktighetsberäkningar utan att behöva Microsoft Project själv.

---

**Last Updated:** 2026-02-05  
**Testad med:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}