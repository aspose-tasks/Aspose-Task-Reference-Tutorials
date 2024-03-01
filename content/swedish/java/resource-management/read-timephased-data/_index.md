---
title: Läs Timephased Data for Resources i Aspose.Tasks
linktitle: Läs Timephased Data for Resources i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du extraherar tidsfasdata från MS Project-resurser med Aspose.Tasks för Java. Steg-för-steg handledning.
type: docs
weight: 15
url: /sv/java/resource-management/read-timephased-data/
---
## Introduktion
I den här handledningen guidar vi dig genom processen att läsa tidsfasad data för MS Project-resurser med Aspose.Tasks för Java. Det här biblioteket tillhandahåller kraftfulla funktioner för att hantera Microsoft Project-filer programmatiskt.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner den från[hemsida](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) och följ installationsanvisningarna.
2.  Aspose.Tasks for Java Library: Ladda ner Aspose.Tasks for Java-biblioteket från[nedladdningssida](https://releases.aspose.com/tasks/java/) och följ installationsinstruktionerna i dokumentationen.

## Importera paket
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Steg 1: Konfigurera datakatalog
Först definierar du katalogen där din MS Project-fil finns.
```java
String dataDir = "Your Data Directory";
```
## Steg 2: Läs MS Project Template File
Ange namnet på din MS Project-mallfil.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Steg 3: Läs indatafil som projekt
Läs indatafilen med Aspose.Tasks och ladda den som ett projektobjekt.
```java
Project project = new Project(dataDir + fileName);
```
## Steg 4: Hämta resurs efter ID
Hämta den önskade resursen från projektet med dess unika identifierare (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Steg 5: Skriv ut tidsfasdata för resursarbete
Skriv ut tidsfasdata för resursarbete.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Steg 6: Skriv ut tidsfasdata för resurskostnad
Skriv ut tidsfasdata för resurskostnad.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Slutsats
I den här handledningen har vi lärt oss hur man läser tidsfasdata för MS Project-resurser med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt extrahera värdefull information från dina projektfiler programmatiskt.
## FAQ's
### Kan Aspose.Tasks hantera andra typer av projektfiler förutom Microsoft Project?
Ja, Aspose.Tasks stöder olika filformat, inklusive MPP, XML och CSV.
### Är Aspose.Tasks kompatibel med olika Java-utvecklingsmiljöer?
Ja, Aspose.Tasks är kompatibel med alla större Java IDE:er och ramverk.
### Kan jag manipulera projektdata med Aspose.Tasks?
Absolut, Aspose.Tasks tillhandahåller omfattande API:er för att skapa, modifiera och analysera projektdata.
### Är Aspose.Tasks lämpligt för projekt på företagsnivå?
Ja, Aspose.Tasks används ofta i företagsmiljöer på grund av dess tillförlitlighet och skalbarhet.
### Var kan jag hitta support om jag stöter på problem när jag använder Aspose.Tasks?
 Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för hjälp från samhället och supportteamet.