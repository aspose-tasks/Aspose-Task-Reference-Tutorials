---
title: Läs Valutaegenskaper i Aspose.Tasks Projects
linktitle: Läs Valutaegenskaper i Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: Lär dig hur du extraherar valutainformation från MS Project-filer med Aspose.Tasks för Java. Steg-för-steg guide tillhandahålls.
weight: 10
url: /sv/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs Valutaegenskaper i Aspose.Tasks Projects

## Introduktion
den här handledningen kommer vi att lära oss hur man använder Aspose.Tasks för Java för att läsa valutaegenskaper från Microsoft Project-filer. Aspose.Tasks är ett kraftfullt Java API som gör det möjligt för utvecklare att manipulera Microsoft Project-dokument utan att Microsoft Project behöver installeras. Genom att följa stegen som beskrivs nedan kommer du att kunna extrahera valutarelaterad information utan ansträngning.
## Förutsättningar
Innan du fortsätter med den här handledningen, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system.
2.  Aspose.Tasks for Java JAR: Ladda ner Aspose.Tasks for Java-biblioteket från[här](https://releases.aspose.com/tasks/java/) och inkludera det i ditt Java-projekt.
## Importera paket
Börja med att importera de nödvändiga paketen till din Java-klass:
```java
import com.aspose.tasks.*;
```
## Steg 1: Konfigurera din projektkatalog
Ställ först in din projektkatalog där din Microsoft Project-fil finns. Du kan definiera denna katalogsökväg enligt följande:
```java
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"` med den faktiska sökvägen till din projektkatalog.
## Steg 2: Skapa en Project Reader-instans
 Instantiera en`Project` objekt genom att ange sökvägen till din Microsoft Project-fil:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Se till att byta ut`"project.mpp"` med namnet på din MS Project-fil.
## Steg 3: Visa valutaegenskaper
Hämta och visa valutaegenskaper från projektfilen:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Detta kodsegment hämtar information som valutakod, siffror, symbol och symbolposition från MS Project-filen och skriver ut dem till konsolen.
## Steg 4: Processen slutförd
Slutligen, skriv ut ett meddelande som indikerar framgångsrikt slutförande av processen:
```java
System.out.println("Process completed Successfully");
```
## Slutsats
I den här handledningen undersökte vi hur man läser valutaegenskaper från Microsoft Project-filer med Aspose.Tasks för Java. Genom att följa de skisserade stegen kan du enkelt extrahera valutarelaterad information från dina projektfiler programmatiskt, vilket möjliggör sömlös integrering i dina Java-applikationer.
## FAQ's
### F: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?
S: Aspose.Tasks stöder olika versioner av Microsoft Project, inklusive MPP-filer genererade av MS Project 2003-2021.
### F: Kan jag ändra valutaegenskaper med Aspose.Tasks?
S: Ja, Aspose.Tasks låter dig både läsa och ändra valutaegenskaper i MS Project-filer programmatiskt.
### F: Är Aspose.Tasks lämplig för kommersiellt bruk?
 S: Ja, Aspose.Tasks är ett kommersiellt bibliotek designat för professionellt bruk. Du kan köpa en licens[här](https://purchase.aspose.com/buy).
### F: Erbjuder Aspose.Tasks en gratis provperiod?
 S: Ja, du kan använda en gratis testversion av Aspose.Tasks från[här](https://releases.aspose.com/).
### F: Var kan jag söka hjälp eller stöd för Aspose.Tasks?
 S: Du kan besöka Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15) för all hjälp eller frågor.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
