---
title: Lägg till utökade attribut till uppgifter i Aspose.Tasks
linktitle: Lägg till utökade attribut till uppgifter i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Utforska kraften i Aspose.Tasks Java för att anpassa Microsoft Project-filer med utökade attribut. Förbättra dina projektledningsmöjligheter utan ansträngning.
weight: 11
url: /sv/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till utökade attribut till uppgifter i Aspose.Tasks

## Introduktion
Att förbättra dina projektledningsmöjligheter är avgörande för effektiv uppgiftsspårning och resurshantering. Aspose.Tasks för Java tillhandahåller en kraftfull lösning för Java-utvecklare att manipulera Microsoft Project-filer sömlöst. I den här handledningen kommer vi att utforska hur du lägger till utökade attribut till uppgifter med Aspose.Tasks för Java, så att du kan anpassa och organisera dina projektdata enligt dina specifika krav.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
- Grundläggande kunskaper i Java-programmering.
-  Aspose.Tasks för Java-biblioteket installerat. Du kan ladda ner den från[hemsida](https://releases.aspose.com/tasks/java/).
- En Java Integrated Development Environment (IDE) installerad på ditt system.
## Importera paket
I ditt Java-projekt, importera de nödvändiga paketen för att komma åt Aspose.Tasks-funktioner:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Låt oss nu dela upp varje exempel i flera steg:
## 1. Lägga till attribut för vanlig text
1. Ställ in sökvägen till dokumentkatalogen:
```java
String dataDir = "Your Document Directory";
```
2. Skapa ett nytt projekt:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Skapa en utökad attributdefinition av typen Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Lägg till definitionen i projektets samling av utökade attribut:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Lägg till en uppgift till projektet:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Skapa ett utökat attribut från attributdefinitionen:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Tilldela ett värde till det genererade utökade attributet:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Lägg till det utökade attributet till uppgiften:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Spara projektet:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Lägga till textattribut med uppslagsalternativ
Följ samma steg som ovan, ersätt Text1 med Text2 och anpassa uppslagsvärden.
## 3. Lägga till Duration Attribut med Lookup Option
Följ samma steg som ovan, ersätt Text1 med Duration2 och anpassa uppslagsvärden.
## Slutsats
Genom att följa denna steg-för-steg-guide har du lärt dig hur du använder Aspose.Tasks för Java för att lägga till utökade attribut till uppgifter i dina Microsoft Project-filer. Denna anpassning låter dig skräddarsy din projektledningsmetod, vilket ökar flexibiliteten och effektiviteten.
## Vanliga frågor
### F: Kan jag använda Aspose.Tasks för Java med andra Java-bibliotek?
S: Ja, Aspose.Tasks för Java kan sömlöst integreras i dina Java-projekt, och det fungerar bra med andra Java-bibliotek.
### F: Är Aspose.Tasks för Java lämpligt för storskaliga projektledningsapplikationer?
S: Absolut, Aspose.Tasks för Java är designat för att hantera projekt av varierande storlek, inklusive storskaliga applikationer.
### F: Finns det några licensöverväganden för att använda Aspose.Tasks för Java i ett kommersiellt projekt?
 S: Ja, se till att granska licensinformationen som finns på[Aspose.Tasks webbplats](https://purchase.aspose.com/buy).
### F: Hur kan jag få support eller hjälp med Aspose.Tasks för Java?
 A: Besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd och diskussioner.
### F: Kan jag prova Aspose.Tasks för Java innan jag köper?
 S: Ja, du kan få tillgång till en gratis testversion[här](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
