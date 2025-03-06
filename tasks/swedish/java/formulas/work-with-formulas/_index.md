---
title: MS Project Formler med Aspose.Tasks för Java
linktitle: Arbeta med formler i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du manipulerar MS Project-filer i Java med Aspose.Tasks-biblioteket. Skapa, ändra och beräkna attribut med lätthet.
weight: 11
url: /sv/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Formler med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer vi att fördjupa oss i att arbeta med MS Project Formulas med Aspose.Tasks för Java. Aspose.Tasks är ett kraftfullt bibliotek som gör det möjligt för utvecklare att manipulera Microsoft Project-filer programmatiskt. Med dess omfattande funktioner kan du enkelt skapa, läsa, ändra och konvertera projektfiler i Java-applikationer.
## Förutsättningar
Innan vi börjar, se till att du har ställt in följande förutsättningar:
### Java utvecklingsmiljö
Se till att du har ett Java Development Kit (JDK) installerat på ditt system. Du kan ladda ner och installera den senaste JDK från Oracles webbplats.
### Aspose.Tasks bibliotek
Du måste ha Aspose.Tasks-biblioteket lagt till ditt Java-projekt. Du kan ladda ner biblioteket från[Aspose.Tasks för Java nedladdningssida](https://releases.aspose.com/tasks/java/) och inkludera det i ditt projekts beroenden.

## Importera paket
Innan du dyker in i exemplen, importera de nödvändiga paketen till din Java-kod:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Låt oss dela upp exemplet i flera steg:
## Steg 1: Skapa ett testprojekt med anpassat fält
```java
Project project = CreateTestProjectWithCustomField();
```
 Skapa först ett testprojekt med ett anpassat fält med hjälp av`CreateTestProjectWithCustomField()` metod. Denna metod returnerar ett projektobjekt som representerar det nyskapade projektet.
## Steg 2: Definiera en utökad attributdefinition
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Hämta den utökade attributdefinitionen från projektet och ställ in dess alias och formel. I det här exemplet definierar vi ett attribut för att beräkna antalet dagar från slutdatumet till deadline.
## Steg 3: Ställ in deadline för en uppgift
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Skapa ett kalenderobjekt och ställ in ett deadlinedatum. Hämta sedan en uppgift från projektet och ställ in dess deadline med hjälp av Calendar-objektet.
## Steg 4: Spara projektet
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Slutligen sparar du projektet till en fil med angivet namn och format. I det här fallet sparar vi den som en MPP-fil.

## Slutsats
I den här handledningen har vi lärt oss hur man arbetar med MS Project Formulas med Aspose.Tasks för Java. Genom att följa dessa steg kan du effektivt manipulera projektfiler programmatiskt, lägga till anpassade fält och beräkna attribut baserat på formler.

## FAQ's
### F: Kan jag använda Aspose.Tasks med andra programmeringsspråk?
S: Ja, Aspose.Tasks stöder olika programmeringsspråk inklusive Java, .NET och mer.
### F: Finns det en gratis testversion tillgänglig för Aspose.Tasks?
 S: Ja, du kan ladda ner en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).
### F: Var kan jag hitta dokumentation för Aspose.Tasks?
 S: Du kan hitta dokumentationen för Aspose.Tasks[här](https://reference.aspose.com/tasks/java/).
### F: Hur kan jag få support för Aspose.Tasks?
 S: För support kan du besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
### F: Behöver jag en tillfällig licens för att använda Aspose.Tasks?
S: Om du behöver ytterligare funktioner kan du få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
