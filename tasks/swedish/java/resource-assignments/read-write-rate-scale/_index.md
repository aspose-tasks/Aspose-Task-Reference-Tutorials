---
title: Läs- och skrivhastighetsskala för resurstilldelningar i Aspose.Tasks
linktitle: Läs- och skrivhastighetsskala för resurstilldelningar i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du hanterar resurstilldelningar effektivt i Aspose.Tasks för Java med denna omfattande handledning.
weight: 20
url: /sv/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs- och skrivhastighetsskala för resurstilldelningar i Aspose.Tasks

## Introduktion
I den här handledningen kommer vi att fördjupa oss i hantering av resurstilldelningshastighetsskala med Aspose.Tasks för Java, ett robust bibliotek för att arbeta med Microsoft Project-filer programmatiskt. Genom att följa dessa steg kommer du att effektivt kunna manipulera inställningar för hastighetsskala för resurstilldelningar i dina Java-applikationer.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Environment: Se till att du har Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Tasks for Java Library: Ladda ner och installera Aspose.Tasks for Java-biblioteket från[här](https://releases.aspose.com/tasks/java/).

## Importera paket
Först måste du importera de nödvändiga paketen för att arbeta med Aspose.Tasks-funktioner. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Steg 1: Konfigurera ditt projekt
Börja med att ställa in ditt Java-projekt och inkludera Aspose.Tasks-biblioteket i dina beroenden.
## Steg 2: Ladda projektfilen
Ladda projektfilen du vill arbeta med i din Java-applikation.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Steg 3: Lägg till en uppgift
Lägg till en ny uppgift till ditt projekt.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Steg 4: Definiera resurser
Definiera materiella och icke-materiella resurser och specificera deras typer.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Steg 5: Tilldela resurser till uppgift
Tilldela de tidigare definierade resurserna till uppgiften tillsammans med deras hastighetsskaltyper.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Steg 6: Spara projektet
Spara projektet med de ändrade resurstilldelningarna.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Steg 7: Hämta resurstilldelningar
Ladda om det sparade projektet och hämta resurstilldelningar för att verifiera inställningarna för hastighetsskala.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Slutsats
Hantering av resurstilldelningar i Aspose.Tasks för Java är avgörande för effektiv projektledning. Genom att följa denna steg-för-steg-guide kan du sömlöst manipulera hastighetsskalningsinställningar för resurstilldelningar i dina Java-applikationer.
## FAQ's
### F1: Kan jag använda Aspose.Tasks för Java med vilken Java IDE som helst?
S: Ja, Aspose.Tasks för Java är kompatibel med alla större Java IDE, inklusive IntelliJ IDEA, Eclipse och NetBeans.
### F2: Stöder Aspose.Tasks andra filformat förutom MPP?
S: Ja, Aspose.Tasks stöder olika filformat, inklusive MPP, XML och HTML.
### F3: Är Aspose.Tasks lämplig för projektledning på företagsnivå?
S: Absolut, Aspose.Tasks erbjuder omfattande funktioner för att hantera projekt av alla skala, vilket gör det lämpligt för projektledning på företagsnivå.
### F4: Kan jag anpassa resurstilldelningar längre än frekvensskala?
S: Ja, Aspose.Tasks tillhandahåller omfattande möjligheter för att anpassa resurstilldelningar, inklusive justeringar av kostnader, arbete och varaktighet.
### F5: Finns det ett communityforum för Aspose.Tasks-support?
 S: Ja, du kan hitta support och interagera med andra användare på Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
