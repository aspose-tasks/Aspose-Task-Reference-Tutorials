---
date: 2026-02-20
description: Utforska hur du lägger till en uppgift i ett projekt och hanterar varaktigheter
  med Aspose.Tasks för Java. Lär dig hur du ställer in varaktighet och hur du enkelt
  konverterar varaktighet.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lägg till uppgift i projektet och hantera varaktigheter med Aspose.Tasks
url: /sv/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till uppgift i projekt och hantera varaktigheter med Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig **hur man lägger till en uppgift i ett projekt** och styr dess varaktighet med Aspose.Tasks för Java. Oavsett om du bygger ett nytt projektplaneringsverktyg eller utökar en befintlig lösning, är det viktigt att behärska hantering av uppgiftsvaraktigheter för exakt schemaläggning och rapportering.

## Snabba svar
- **Vad betyder “add task to project”?** Det skapar ett nytt task‑objekt under projektets rot eller en specifik sammanfattningsuppgift.  
- **Vilken klass representerar en varaktighet?** `com.aspose.tasks.Duration`.  
- **Hur sätter man varaktighet?** Använd `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Kan jag konvertera en varaktighet till en annan enhet?** Ja, anropa `duration.convert(TimeUnitType.Hour)` eller någon annan `TimeUnitType`.  
- **Behöver jag en licens för produktion?** En giltig Aspose.Tasks‑licens krävs för kommersiell användning.

## Vad är “add task to project”?
Att lägga till en uppgift i ett projekt innebär att skapa ett `Task`‑objekt och fästa det i projektets uppgiftshierarki. Denna operation är det första steget innan du kan definiera arbete, resurser eller varaktighet för den uppgiften.

## Varför hantera uppgiftsvaraktigheter?
Exakta varaktigheter driver realistiska tidslinjer, resursallokering och kritisk‑vägsanalys. Med Aspose.Tasks kan du programatiskt sätta, läsa, konvertera och justera varaktigheter, vilket ger dig full kontroll över projektscheman.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Java Development Kit (JDK): Se till att du har Java installerat på din maskin. Du kan ladda ner det [here](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: Ladda ner och inkludera Aspose.Tasks‑biblioteket i ditt projekt. Du kan hitta biblioteket [here](https://releases.aspose.com/tasks/java/).

## Importera paket
I ditt Java‑projekt, importera de nödvändiga paketen för att arbeta med Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Steg 1: Ställ in ditt projekt
```java
// Create a new project
Project project = new Project();
```

## Steg 2: Lägg till en ny uppgift (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Hur man sätter varaktighet
Nu när uppgiften finns kan du definiera dess längd. Som standard uttrycks varaktigheter i dagar.

## Steg 3: Hämta och konvertera uppgiftsvaraktighet
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Hur man konverterar varaktighet
`convert`‑metoden låter dig översätta en `Duration` från en `TimeUnitType` till en annan (t.ex. dagar → timmar, veckor → dagar).

## Steg 4: Uppdatera uppgiftsvaraktigheten till 1 vecka
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Steg 5: Minska uppgiftsvaraktigheten
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Genom att följa dessa steg har du framgångsrikt **lagt till en uppgift i ett projekt** och hanterat dess varaktighet med Aspose.Tasks för Java.

## Vanliga fallgropar och tips
- **Fallgrop:** Att glömma att konvertera varaktigheten innan aritmetiska operationer kan leda till felaktiga resultat. Verifiera alltid enheten med `duration.getTimeUnit()`.
- **Tips:** Använd `project.getDuration(value, TimeUnitType)` för att skapa varaktigheter i önskad enhet istället för att konvertera senare.
- **Fallgrop:** Att sätta en negativ varaktighet kommer att kasta ett undantag. Se till att validera inmatningsvärden.

## Slutsats
I den här guiden har vi gått igenom hur du **lägger till en uppgift i ett projekt**, läser dess standardvaraktighet, **sätter varaktighet** och **konverterar varaktighet** till olika tidsenheter. Du kan nu integrera dessa tekniker i större schemaläggningsapplikationer för exakt projektplanering.

## Vanliga frågor
### Är Aspose.Tasks kompatibel med alla Java‑versioner?
Aspose.Tasks är kompatibel med Java 6 och senare versioner.

### Kan jag använda Aspose.Tasks för kommersiella projekt?
Ja, du kan använda Aspose.Tasks för både personliga och kommersiella projekt. Besök [here](https://purchase.aspose.com/buy) för licensinformation.

### Var kan jag hitta ytterligare support och resurser?
Besök [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för community‑support och diskussioner.

### Hur kan jag få en temporär licens för teständamål?
Du kan få en temporär licens [here](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.

### Finns det en gratis provperiod för Aspose.Tasks?
Ja, du kan komma åt den gratis provperioden [here](https://releases.aspose.com/) för att utforska Aspose.Tasks innan du köper.

## Vanliga frågor och svar

**Q: Hur ändrar jag en uppgifts varaktighet efter att den har satts?**  
**A:** Hämta den aktuella varaktigheten med `task.get(Tsk.DURATION)`, modifiera den (t.ex. `add`, `subtract` eller `convert`), och sätt sedan tillbaka den med `task.set(Tsk.DURATION, newDuration)`.

**Q: Kan jag sätta en varaktighet i minuter?**  
**A:** Ja, använd `TimeUnitType.Minute` när du anropar `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Uppdaterar ändring av varaktigheten automatiskt uppgiftens start‑ och slutdatum?**  
**A:** Endast om projektets schemaläggningsläge är satt till automatiskt. Annars kan du behöva omberäkna schemat med `project.calculateCriticalPath()`.

**Q: Är det möjligt att hämta varaktigheten som ett råtal?**  
**A:** Anropa `duration.getTimeSpan()` för att få det numeriska värdet i den aktuella tidsenheten.

**Q: Vad händer om jag subtraherar mer än den aktuella varaktigheten?**  
**A:** API‑et kommer att kasta ett `ArgumentOutOfRangeException`. Validera alltid att den resulterande varaktigheten förblir positiv.

---

**Senast uppdaterad:** 2026-02-20  
**Testat med:** Aspose.Tasks för Java (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}