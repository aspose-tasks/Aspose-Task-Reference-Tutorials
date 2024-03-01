---
title: Övervaka övertid, återstående kostnader och arbete i Aspose.Tasks
linktitle: Övervaka övertid, återstående kostnader och arbete i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du övervakar övertid, återstående kostnader och arbetar i Java-projekt med Aspose.Tasks. Enkla steg för effektiv projektledning.
type: docs
weight: 18
url: /sv/java/resource-assignments/overtime-remaining-costs-work/
---
## Introduktion
I den här handledningen kommer vi att lära oss hur du använder Aspose.Tasks för Java för att övervaka övertid, återstående kostnader och arbete i ett projekt. Detta kan vara ovärderligt för projektledare och gruppledare för att säkerställa att projekt håller sig på rätt spår och inom budget.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK): Aspose.Tasks för Java kräver Java SE 6 eller senare.
2.  Aspose.Tasks för Java Library: Ladda ner och installera biblioteket från[här](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Alla Java IDE som Eclipse, IntelliJ IDEA eller NetBeans.

## Importera paket
Börja med att importera de nödvändiga paketen i din Java-fil:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Steg 1: Konfigurera datakatalogen
Definiera katalogen där din projektfil finns:
```java
String dataDir = "Your Data Directory";
```
 Byta ut`"Your Data Directory"` med sökvägen till din projektfil.
## Steg 2: Ladda projektet
 Instantiera en`Project` objekt och ladda projektfilen:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Byta ut`"ResourceAssignmentOvertimes.mpp"` med namnet på din projektfil.
## Steg 3: Iterera genom resurstilldelningar
Gå igenom varje resurstilldelning i projektet:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Steg 4: Skriv ut övertidskostnader och arbete
Hämta och skriv ut övertidskostnader och arbete för varje resursuppdrag:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Steg 5: Skriv ut återstående kostnader och arbete
Hämta och skriv ut återstående kostnader och arbete för varje resursuppdrag:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Steg 6: Skriv ut återstående övertidskostnader och arbete
Hämta och skriv ut återstående övertidskostnader och arbete för varje resursuppdrag:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Slutsats
Att övervaka övertid, återstående kostnader och arbete i ett projekt är avgörande för framgångsrik projektledning. Med Aspose.Tasks för Java kan du enkelt komma åt och spåra denna information, vilket säkerställer att dina projekt håller schemat och inom budget.
## FAQ's
### Kan jag använda Aspose.Tasks för Java med andra Java-bibliotek?
Ja, Aspose.Tasks för Java är kompatibelt med andra Java-bibliotek och ramverk.
### Stöder Aspose.Tasks olika projektfilformat?
Ja, Aspose.Tasks stöder olika projektfilformat inklusive MPP, XML och mer.
### Finns det en testversion tillgänglig?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### Var kan jag hitta support om jag stöter på problem?
 Du kan besöka Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15) för support.
### Hur kan jag köpa en licens för Aspose.Tasks?
 Du kan köpa en licens från[här](https://purchase.aspose.com/buy).