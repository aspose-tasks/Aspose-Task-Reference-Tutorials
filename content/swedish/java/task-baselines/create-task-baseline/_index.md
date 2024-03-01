---
title: Skapa MS Project Task Baseline i Aspose.Tasks
linktitle: Skapa en Task Baseline i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du skapar en Microsoft Project-uppgiftsbaslinje i Java med Aspose.Tasks, ett kraftfullt bibliotek för att hantera projektdata utan ansträngning.
type: docs
weight: 11
url: /sv/java/task-baselines/create-task-baseline/
---
## Introduktion
den här handledningen kommer vi att fördjupa oss i processen att skapa en Microsoft Project-uppgiftsbaslinje med Aspose.Tasks för Java. Aspose.Tasks är ett kraftfullt Java-bibliotek som gör det möjligt för utvecklare att arbeta med Microsoft Project-filer utan att Microsoft Project behöver installeras. Med Aspose.Tasks kan du enkelt manipulera projektdata, inklusive uppgifter, resurser och kalendrar, för att effektivisera projektledningsuppgifter.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Aspose.Tasks för Java kräver JDK installerat på ditt system. Du kan ladda ner och installera JDK från Oracles webbplats.
2.  Aspose.Tasks for Java Library: Ladda ner Aspose.Tasks for Java-biblioteket från[nedladdningslänk](https://releases.aspose.com/tasks/java/) försedd.

## Importera paket
För att börja arbeta med Aspose.Tasks i ditt Java-projekt, importera de nödvändiga paketen:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Steg 1: Skapa ett projektobjekt
```java
Project project = new Project();
```
 Skapa först en ny`Project` objekt. Det här objektet representerar Microsoft Project-filen du kommer att arbeta med.
## Steg 2: Lägg till en uppgift till projektet
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Använda`getRootTask()` metod, gå till rotuppgiften för projektet och lägg sedan till en ny uppgift till den med hjälp av`add()` metod. Ange ett namn för uppgiften inom parentes.
## Steg 3: Ställ in baslinje för specificerade uppgifter
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
För att ställa in en baslinje för specifika uppgifter, skapa en lista med uppgifter (`myList` i det här fallet) och fyll den med de uppgifter som du vill ställa in baslinjen för. Använd sedan`setBaseline()` metod, som anger baslinjetypen och listan med uppgifter.
## Steg 4: Ställ in baslinje för hela projektet
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternativt kan du ställa in en baslinje för hela projektet genom att helt enkelt ringa`setBaseline()` metod med den angivna baslinjetypen.

## Slutsats
I den här handledningen har vi utforskat hur man skapar en Microsoft Project-uppgiftsbaslinje med Aspose.Tasks för Java. Genom att följa stegen som beskrivs ovan kan du effektivt hantera projektdata och effektivisera projektledningsuppgifter med lätthet.
## FAQ's
### Kan jag använda Aspose.Tasks för Java utan Microsoft Project installerat?
Ja, Aspose.Tasks för Java låter dig arbeta med Microsoft Project-filer utan att Microsoft Project behöver installeras på ditt system.
### Är Aspose.Tasks för Java kompatibelt med olika versioner av Microsoft Project?
Ja, Aspose.Tasks för Java stöder olika versioner av Microsoft Project, vilket säkerställer kompatibilitet mellan olika miljöer.
### Kan jag manipulera projektresurser med Aspose.Tasks för Java?
Absolut, Aspose.Tasks för Java tillhandahåller robusta funktioner för att manipulera projektresurser, inklusive att lägga till, uppdatera och ta bort resurser efter behov.
### Har Aspose.Tasks för Java stöd för att ställa in uppgiftsberoende?
Ja, du kan enkelt ställa in uppgiftsberoenden med Aspose.Tasks för Java, vilket gör att du kan fastställa sekvensen av uppgifter i ditt projekt.
### Finns teknisk support tillgänglig för Aspose.Tasks för Java?
 Ja, du kan få tillgång till teknisk support för Aspose.Tasks för Java via[supportforum](https://forum.aspose.com/c/tasks/15), där du kan ställa frågor och söka hjälp från samhället och Asposes supportpersonal.