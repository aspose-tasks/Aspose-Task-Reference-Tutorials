---
title: Konfigurera Gantt-diagramvy i Aspose.Tasks-projekt
linktitle: Konfigurera Gantt-diagramvy i Aspose.Tasks-projekt
second_title: Aspose.Tasks Java API
description: Lär dig hur du konfigurerar Gantt MS Project Chart View i Aspose.Tasks med Java. Anpassa projekt och visualisera dem i Gantt-diagrammet steg-för-steg.
type: docs
weight: 10
url: /sv/java/project-configuration/configure-gantt-chart/
---
## Introduktion
I den här handledningen kommer du att lära dig hur du konfigurerar Gantt MS Project Chart View i Aspose.Tasks-projekt med Java. Aspose.Tasks är ett kraftfullt Java API som låter dig arbeta med Microsoft Project-filer programmatiskt. Genom att följa dessa steg kommer du att kunna anpassa Gantt-diagramvyn enligt ditt projekts krav.
## Förutsättningar
Innan du börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har Java installerat på ditt system.
2.  Aspose.Tasks Library: Ladda ner och installera Aspose.Tasks-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Välj en IDE som du väljer. Den här handledningen använder IntelliJ IDEA, men du kan använda vilken IDE du är bekväm med.
## Importera paket
Först måste du importera de nödvändiga paketen för att arbeta med Aspose.Tasks i ditt Java-projekt. Lägg till följande importsatser till din Java-fil:
```java
import com.aspose.tasks.*;
```
Låt oss nu dela upp processen för att konfigurera Gantt MS Project Chart View i steg-för-steg-instruktioner:
## Steg 1: Ställ in datakatalog
```java
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"` med sökvägen till din projektdatakatalog.
## Steg 2: Ladda projektfilen
```java
Project project = new Project(dataDir + "project.mpp");
```
Ladda din projektfil (`project.mpp` i det här exemplet) med hjälp av`Project` klass från Aspose.Tasks.
## Steg 3: Lägg till ny aktivitet
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Skapa en ny uppgift i ditt projekt med hjälp av`Task` klass och lägg till den i rotuppgiftens barn.
## Steg 4: Definiera anpassat attribut
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Definiera ett nytt anpassat attribut med hjälp av`ExtendedAttributeDefinition`klass och lägg till den i projektets utökade attribut.
## Steg 5: Lägg till anpassat attribut till uppgift
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Lägg till det anpassade attributet till den skapade uppgiften med hjälp av`createExtendedAttribute` metod.
## Steg 6: Anpassa tabell
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Anpassa tabellen genom att lägga till textattributfältet med specificerad bredd, titel och justering.
## Steg 7: Spara projekt
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Spara projektet med den konfigurerade Gantt MS Project Chart View. Den resulterande filen kan öppnas i Microsoft Project 2010.
## Slutsats
Grattis! Du har framgångsrikt konfigurerat Gantt MS Project Chart View i Aspose.Tasks-projekt med Java. Du kan nu anpassa projektattribut och visualisera dem i Gantt-diagrammet enligt ditt projekts behov.
## FAQ's
### F: Kan jag använda Aspose.Tasks med andra programmeringsspråk?
S: Ja, Aspose.Tasks är tillgängligt för flera programmeringsspråk inklusive .NET, Java och C++.
### F: Finns det någon gratis testversion tillgänglig för Aspose.Tasks?
 S: Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### F: Var kan jag hitta support för Aspose.Tasks?
S: Du kan hitta support och ställa frågor på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
### F: Hur kan jag köpa en licens för Aspose.Tasks?
 S: Du kan köpa en licens från[här](https://purchase.aspose.com/buy).
### F: Behöver jag en tillfällig licens för teständamål?
 S: Ja, du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).