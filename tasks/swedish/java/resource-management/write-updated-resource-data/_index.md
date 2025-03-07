---
title: Skriv uppdaterad resursdata i Aspose.Tasks
linktitle: Skriv uppdaterad resursdata i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du enkelt uppdaterar resursdata i MS Project-filer med Aspose.Tasks för Java.
weight: 21
url: /sv/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skriv uppdaterad resursdata i Aspose.Tasks

## Introduktion
I den här självstudien guidar vi dig genom att uppdatera Microsoft Project-resursdata med Aspose.Tasks för Java. Aspose.Tasks är ett kraftfullt Java API som låter dig manipulera Microsoft Project-filer utan att Microsoft Project behöver installeras på ditt system.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Tasks för Java-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
3. Grundläggande kunskaper i Java-programmering.

## Importera paket

Först måste du importera de nödvändiga paketen för att arbeta med Aspose.Tasks i din Java-kod. Lägg till följande importsatser till din Java-fil:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Steg 1: Konfigurera din datakatalog

Definiera katalogen där dina datafiler finns:

```java
String dataDir = "Your Data Directory";
```

## Steg 2: Ange in- och utdatafiler

Definiera sökvägarna för den ingående MS Project-filen och den resulterande uppdaterade filen:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Testfil med en rsc att uppdatera
String resultFile = dataDir + "OutputMPP.mpp"; // Fil för att skriva testprojekt
```

## Steg 3: Ladda projektet

 Ladda MS Project-filen i en`Project` objekt:

```java
Project project = new Project(file);
```

## Steg 4: Lägg till en resurs och ställ in attribut

Lägg till en ny resurs till projektet och ställ in dess attribut som standardpris, övertidspris och grupp:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Steg 5: Spara projektet

Spara det uppdaterade projektet med de modifierade resursdata:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Slutsats

I den här handledningen har vi visat hur man uppdaterar MS Project-resursdata med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt manipulera resursinformation i dina MS Project-filer programmatiskt.

## FAQ's

### F1: Kan jag uppdatera flera resurser i samma projekt med Aspose.Tasks för Java?

S1: Ja, du kan uppdatera flera resurser genom att iterera igenom dem och ställa in deras attribut därefter.

### F2: Stöder Aspose.Tasks andra filformat än MS Project?

S2: Ja, Aspose.Tasks stöder olika filformat inklusive XML, MPP och mer.

### F3: Är Aspose.Tasks kompatibel med olika versioner av Java?

S3: Aspose.Tasks är kompatibel med Java version 6 och högre.

### F4: Kan jag utföra andra operationer på MS Project-filer med Aspose.Tasks?

S4: Ja, du kan utföra ett brett utbud av operationer som att läsa, skriva och manipulera uppgifter, resurser och kalendrar.

### F5: Var kan jag hitta ytterligare hjälp eller support för Aspose.Tasks?

 A5: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för all hjälp eller frågor.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
