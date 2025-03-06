---
title: Bestäm MS Project-version med Aspose.Tasks
linktitle: Bestäm projektversionen med Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du bestämmer versionen av MS Project-filer programmatiskt med Aspose.Tasks för Java. Steg-för-steg guide med kodexempel.
weight: 12
url: /sv/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bestäm MS Project-version med Aspose.Tasks

## Introduktion
Denna handledning guidar dig genom att använda Aspose.Tasks för Java för att bestämma versionen av en MS Project-fil steg för steg. Aspose.Tasks är ett kraftfullt Java API som tillåter utvecklare att manipulera Microsoft Project-filer utan att Microsoft Project behöver installeras.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Tasks for Java JAR-fil: Ladda ner Aspose.Tasks for Java-biblioteket från[hemsida](https://releases.aspose.com/tasks/java/) och lägg till det i ditt Java-projekt.
3. MS Project File: Förbered en MS Project-fil (XML-format) för testning.

## Importera paket
Innan vi dyker in i koden, låt oss importera de nödvändiga paketen:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Steg 1: Konfigurera projektet
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"` med sökvägen till katalogen som innehåller din MS Project-fil.
## Steg 2: Ladda projektet
```java
Project project = new Project(dataDir + "input.xml");
```
 Byta ut`"input.xml"` med namnet på din MS Project-fil.
## Steg 3: Bestäm projektversionen
```java
//Visa egendom för projektversion
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Detta kodavsnitt hämtar och skriver ut versionen och det senaste sparade datumet för MS Project-filen.
## Steg 4: Visa resultat
```java
//Visa resultatet av konvertering.
System.out.println("Process completed Successfully");
```
Denna rad indikerar slutförandet av processen.

## Slutsats
I den här handledningen lärde du dig hur du bestämmer versionen av en MS Project-fil med Aspose.Tasks för Java. Genom att följa steg-för-steg-guiden kan du effektivt arbeta med MS Project-filer i dina Java-applikationer utan krångel.

## FAQ's
### F: Kan jag använda Aspose.Tasks med andra programmeringsspråk?
S: Ja, Aspose.Tasks stöder flera programmeringsspråk inklusive .NET, Java och C++.
### F: Är Aspose.Tasks lämpligt för storskaliga projekt?
S: Absolut, Aspose.Tasks är designat för att hantera projekt av alla storlekar med lätthet.
### F: Kan jag anpassa projektdata med Aspose.Tasks?
S: Ja, du kan manipulera projektdata, ändra uppgifter, resurser och mycket mer med Aspose.Tasks.
### F: Kräver Aspose.Tasks installation av Microsoft Project?
S: Nej, Aspose.Tasks fungerar självständigt och kräver inte att Microsoft Project installeras.
### F: Finns teknisk support tillgänglig för Aspose.Tasks?
 S: Ja, du kan få teknisk support från Aspose.Tasks-forumet på[här](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
