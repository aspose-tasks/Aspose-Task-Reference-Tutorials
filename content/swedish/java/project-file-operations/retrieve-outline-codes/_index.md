---
title: Hämta MS Project Outline-koder i Aspose.Tasks
linktitle: Hämta dispositionskoder i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du hämtar Microsoft Project-konturkoder programmatiskt med Aspose.Tasks för Java. Förbättra dina projektledningsmöjligheter.
type: docs
weight: 15
url: /sv/java/project-file-operations/retrieve-outline-codes/
---
## Introduktion
den här handledningen kommer vi att lära oss hur du hämtar Microsoft Project-konturkoder med Aspose.Tasks för Java. Dispositionskoder i MS Project ger ett strukturerat sätt att kategorisera och organisera projektuppgifter, resurser och uppdrag. Aspose.Tasks är ett kraftfullt Java-bibliotek som tillåter utvecklare att manipulera och hantera Microsoft Project-filer programmatiskt.
## Förutsättningar
Innan vi börjar, se till att du har ställt in följande förutsättningar:
### 1. Java utvecklingsmiljö
Se till att du har Java Development Kit (JDK) installerat på ditt system. Du kan ladda ner och installera JDK från Oracles webbplats.
### 2. Aspose.Tasks Library
 Ladda ner och inkludera Aspose.Tasks-biblioteket i ditt Java-projekt. Du kan ladda ner biblioteket från[Aspose.Tasks för Java Nedladdningssida](https://releases.aspose.com/tasks/java/).
## Importera paket
Importera först de nödvändiga paketen från Aspose.Tasks i din Java-kod:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Låt oss nu dela upp den medföljande exempelkoden i flera steg:
## Steg 1: Ladda projektet
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 I det här steget laddar vi Microsoft Project-filen till en`Project` objekt med det angivna filnamnet.
## Steg 2: Hämta dispositionskoder
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Vi itererar igenom varje dispositionskoddefinition i projektet.
## Steg 3: Åtkomst till Outline Code Properties
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Vi hämtar och skriver ut olika egenskaper för dispositionskoddefinitionen som Alias, Fält-ID och Fältnamn.
## Steg 4: Kontrollera Enterprise Custom Code
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Vi kontrollerar om dispositionskoden är en företagsanpassad kod och skriver ut resultatet därefter.
## Steg 5: Visa konturkodmasker
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Vi itererar igenom varje mask som är associerad med konturkoden och skriver ut dess nivå och maskvärde.
## Steg 6: Visa dispositionskodvärden
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Vi itererar genom varje dispositionskodvärde och skriver ut dess beskrivning, värde-ID, värde och typ.
## Slutsats
I den här handledningen har vi lärt oss hur man hämtar MS Project-konturkoder med Aspose.Tasks för Java. Genom att följa de medföljande stegen kan du effektivt komma åt och manipulera dispositionskoder i dina Java-applikationer, vilket möjliggör avancerade projekthanteringsfunktioner.
## FAQ's
### F1: Kan jag använda Aspose.Tasks för Java för att ändra dispositionskoder i en projektfil?
S: Ja, Aspose.Tasks för Java tillhandahåller API:er för att modifiera dispositionskoder i MS Project-filer programmatiskt.
### F2: Finns det en testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan ladda ner en gratis testversion av Aspose.Tasks för Java från[Aspose.Tasks webbplats](https://releases.aspose.com/).
### F3: Hur kan jag få teknisk support för Aspose.Tasks för Java?
 S: Du kan få teknisk support genom att besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) och skicka dina frågor där.
### F4: Kan jag köpa en tillfällig licens för Aspose.Tasks för Java?
 S: Ja, du kan köpa en tillfällig licens för Aspose.Tasks för Java från[köpsidan](https://purchase.aspose.com/temporary-license/).
### F5: Var kan jag hitta den fullständiga dokumentationen för Aspose.Tasks för Java?
 S: Du kan hänvisa till[dokumentation](https://reference.aspose.com/tasks/java/) för detaljerad information om hur du använder Aspose.Tasks för Java.