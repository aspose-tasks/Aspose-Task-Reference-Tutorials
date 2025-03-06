---
title: Hantera varaktigheterna för uppgifter i Aspose.Tasks
linktitle: Hantera varaktigheterna för uppgifter i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Utforska Aspose.Tasks för Java och lär dig hantera uppgiftens varaktighet utan ansträngning. Följ vår steg-för-steg-guide för effektiv projektplanering och genomförande.
weight: 20
url: /sv/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera varaktigheterna för uppgifter i Aspose.Tasks

## Introduktion
Aspose.Tasks för Java tillhandahåller en robust lösning för att effektivt hantera projektuppgifter och varaktighet. I den här handledningen kommer vi att utforska hur du hanterar varaktigheterna för uppgifter med Aspose.Tasks, och guidar dig genom varje steg. Oavsett om du är en erfaren utvecklare eller nybörjare, hjälper den här guiden dig att förstå det väsentliga i att arbeta med uppgiftens varaktighet i dina projekt.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Java Development Kit (JDK): Se till att du har Java installerat på din maskin. Du kan ladda ner den[här](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: Ladda ner och inkludera Aspose.Tasks-biblioteket i ditt projekt. Du hittar biblioteket[här](https://releases.aspose.com/tasks/java/).
## Importera paket
I ditt Java-projekt, importera de nödvändiga paketen för att arbeta med Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Steg 1: Konfigurera ditt projekt
```java
// Skapa ett nytt projekt
Project project = new Project();
```
## Steg 2: Lägg till en ny uppgift
```java
// Lägg till en ny uppgift till projektet
Task task = project.getRootTask().getChildren().add("Task");
```
## Steg 3: Hämta och konvertera uppgiftens varaktighet
```java
// Få uppgiftens varaktighet i dagar (standardtidsenhet)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Konvertera varaktighet till timmar tidsenhet
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Steg 4: Uppdatera uppgiftens varaktighet till 1 vecka
```java
// Öka uppgiftens varaktighet till 1 vecka
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Steg 5: Minska uppgiftens varaktighet
```java
// Minska uppgiftens varaktighet
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Genom att följa dessa steg har du framgångsrikt hanterat varaktigheterna för uppgifterna i ditt Aspose.Tasks for Java-projekt.
## Slutsats
I den här handledningen har vi täckt grunderna för att hantera uppgiftens varaktighet med Aspose.Tasks för Java. Nu kan du med säkerhet införliva dessa tekniker i dina projekt för effektiv hantering av uppgiftens varaktighet.
## Vanliga frågor
### Är Aspose.Tasks kompatibel med alla Java-versioner?
Aspose.Tasks är kompatibel med Java 6 och senare versioner.
### Kan jag använda Aspose.Tasks för kommersiella projekt?
 Ja, du kan använda Aspose.Tasks för både personliga och kommersiella projekt. Besök[här](https://purchase.aspose.com/buy) för licensinformation.
### Var kan jag hitta ytterligare support och resurser?
 Besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd och diskussioner.
### Hur kan jag få en tillfällig licens för teständamål?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.
### Finns det en gratis testversion tillgänglig för Aspose.Tasks?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/) att utforska Aspose.Tasks innan du gör ett köp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
