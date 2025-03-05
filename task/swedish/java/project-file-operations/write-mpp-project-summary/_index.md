---
title: Skriv MPP-projektsammanfattning i Aspose.Tasks
linktitle: Skriv MPP-projektsammanfattning i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du skriver MPP-projektsammanfattningar i Java med Aspose.Tasks. Ställ in och hämta projektinformation utan ansträngning.
type: docs
weight: 27
url: /sv/java/project-file-operations/write-mpp-project-summary/
---
## Introduktion
I den här handledningen kommer vi att lära oss hur man använder Aspose.Tasks för Java för att skriva MPP-projektsammanfattningar. Aspose.Tasks är ett kraftfullt Java-bibliotek för att arbeta med Microsoft Project-filer. Genom att följa stegen som beskrivs nedan kommer du att kunna ställa in och hämta olika sammanfattningsinformation om ett projekt med hjälp av detta bibliotek.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Tasks for Java: Ladda ner och installera Aspose.Tasks for Java-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Välj din föredragna IDE för Java-utveckling, såsom IntelliJ IDEA, Eclipse eller NetBeans.

## Importera paket
Importera först de nödvändiga paketen till din Java-klass:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Steg 1: Konfigurera projekt och definiera sammanfattningsinformation
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Data Directory";
//Initiera ett nytt projektobjekt med sökvägen till din projektfil
Project project = new Project(dataDir + "project.mpp");
// Ange sammanfattande information om projektet
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Ange skapelsedatum för projektet
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Ställ in nyckelord för projektet
project.set(Prj.KEYWORDS, "MPP Aspose");
// Ange senast utskrivna datum för projektet
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Steg 2: Spara projektsammanfattningsinformation
```java
// Spara projektet tillbaka i MPP-format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Visa ett framgångsmeddelande
System.out.println("Process completed Successfully");
```
## Steg 3: Läs projektsammanfattningsinformation
```java
// Läser projektsammanfattningsinformation
project = new Project(dataDir + "MppAspose.xml");
// Print författare till projektet
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Skriv ut sista författaren till projektet
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Skriv ut revisionsnummer för projektet
System.out.println("Revision: " + project.get(Prj.REVISION));
// Skriv ut nyckelord för projektet
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Skriv ut kommentarer om projektet
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Skriv ut skapandedatum för projektet
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Skriv ut nyckelord för projektet (igen)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Skriv ut sista utskrivna datum för projektet
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Slutsats
den här handledningen har vi täckt hur man skriver MPP-projektsammanfattningar med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt ställa in och hämta olika sammanfattningsinformation om dina projektfiler. Aspose.Tasks förenklar processen att arbeta med Microsoft Project-filer i Java-applikationer, och erbjuder robust funktionalitet och enkel användning.
## FAQ's
### F: Kan jag använda Aspose.Tasks för Java med andra Java-bibliotek?
S: Ja, Aspose.Tasks för Java kan sömlöst integreras med andra Java-bibliotek för att förbättra dina projekthanteringsmöjligheter.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### F: Hur ofta uppdateras Aspose.Tasks för Java?
S: Aspose.Tasks för Java uppdateras regelbundet för att säkerställa kompatibilitet med de senaste versionerna av Java- och Microsoft Project-filer.
### F: Kan jag anpassa projektsammanfattningsinformationen ytterligare?
S: Absolut, Aspose.Tasks för Java erbjuder omfattande alternativ för att anpassa projektsammanfattningsinformation enligt dina specifika krav.
### F: Var kan jag få support för Aspose.Tasks för Java?
S: Du kan få stöd från Aspose.Tasks communityforum[här](https://forum.aspose.com/c/tasks/15).