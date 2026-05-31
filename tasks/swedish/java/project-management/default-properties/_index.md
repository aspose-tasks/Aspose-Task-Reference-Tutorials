---
date: 2026-05-31
description: Lär dig hur du läser in en MPP-fil i Java och hanterar projektets egenskaper
  med Aspose.Tasks, inklusive att ställa in standardegenskaper och konvertera format.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Hantera standardprojektets egenskaper i Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Läs in MPP-fil i Java – Hantera projektets egenskaper med Aspose.Tasks
url: /sv/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs in MPP-fil Java – Hantera projekt egenskaper med Aspose.Tasks

## Introduktion
Om du behöver **load MPP file Java** projekt och programatiskt hantera standardprojekt egenskaper, gör Aspose.Tasks for Java det enkelt. I den här handledningen går vi igenom hela processen—från att läsa in en befintlig Microsoft Project-fil till att anpassa standarduppgifter och resurser, och slutligen spara det uppdaterade projektet. I slutet har du ett tydligt, återanvändbart mönster som du kan använda i vilken Java‑baserad projekt‑hanteringslösning som helst.

## Snabba svar
- **Vad betyder “load MPP file Java”?** Det betyder att läsa en Microsoft Project (.mpp)-fil med Java‑kod via Aspose.Tasks.  
- **Vilket bibliotek hanterar detta?** Aspose.Tasks for Java tillhandahåller ett fullständigt API för projektmanipulation.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktionsanvändning.  
- **Kan jag ändra standarduppgiftens startdatum?** Ja—använd `Prj.DEFAULT_START_TIME` och relaterade egenskaper för att ställa in standardvärden.  
- **Vilka utdataformat stöds?** Förutom native MPP kan du spara till XML, PDF, HTML och över 20 andra format.

## Vad är “load MPP file Java”?
Att läsa in en MPP-fil i Java innebär att använda ett bibliotek för att tolka det binära Microsoft Project-formatet och exponera dess objekt (uppgifter, resurser, kalendrar) som Java‑klasser. Detta gör att du kan läsa, ändra och spara projektdata utan att någonsin öppna Microsoft Project.

## Varför använda Aspose.Tasks för Java?
Aspose.Tasks låter dig hantera projekt egenskaper utan en Microsoft Project‑installation, stöder **50+ in‑ och utdataformat**, och kan bearbeta projekt med **upp till 10 000 uppgifter** samtidigt som minnesanvändningen hålls under 200 MB. Det körs på alla operativsystem som stödjer en JDK, vilket gör det idealiskt för server‑sidig automatisering.

## Förutsättningar
Innan vi dyker ner, se till att du har följande:

### 1. Java Development Kit (JDK)
- Installera JDK 11 eller senare.  
- Du kan ladda ner det från [här](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### 2. Aspose.Tasks for Java Library
- Ladda ner den senaste Aspose.Tasks JAR‑filen och lägg till den i ditt projekts classpath.  
- Hämta den från [webbplatsen](https://releases.aspose.com/tasks/java/).

## Importera paket
Import‑satserna tar med de väsentliga Aspose.Tasks‑klasserna i din Java‑källkod.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Hur laddar man MPP file Java och sätter standardegenskaper?
`Project`‑klassen representerar en Microsoft Project‑fil och ger åtkomst till dess uppgifter, resurser och inställningar. Ladda projektet, inspektera dess standardvärden, ändra dem och spara resultatet—allt i några enkla rader. Detta tillvägagångssätt ger dig full kontroll över schemastandarder, kalendersättningar och kostnadsackumuleringsregler, så att du kan upprätthålla konsekventa projektstandarder i alla genererade filer.

### Steg 1: Ladda projektfil
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Steg 2: Visa standardegenskaper
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Steg 3: Sätt standardegenskaper
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Steg 4: Spara projekt i XML‑format
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Steg 5: Visa resultat
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

Genom att följa dessa steg har du framgångsrikt **läst in en MPP-fil i Java**, inspekterat dess standardinställningar, anpassat dem och sparat det uppdaterade projektet.

## Vanliga problem & tips
- **File not found** – Verifiera att `dataDir` slutar med en sökvägsavgränsare (`/` eller `\\`).  
- **License not applied** – Om du ser ett provvattenstämpel, lägg till din licensfil innan du laddar projektet: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Date handling** – Använd `java.util.Calendar` eller den nyare `java.time`‑API:n (konvertera till `java.util.Date` innan du tilldelar).

## Vanliga frågor
**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks finns också tillgängligt för .NET, Python och andra plattformar.

**Q: Är Aspose.Tasks lämpligt för både personligt och företagsanvändning?**  
A: Absolut! Det skalar från små personliga projekt till stora företagsportföljer.

**Q: Erbjuder Aspose.Tasks kundsupport?**  
A: Ja, du kan hitta hjälp och community‑support på [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Kan jag prova Aspose.Tasks innan jag köper?**  
A: Självklart! Du kan få en gratis provversion från [webbplatsen](https://releases.aspose.com/).

**Q: Hur kan jag få en tillfällig licens för Aspose.Tasks?**  
A: Du kan få en tillfällig licens från [köpsidan](https://purchase.aspose.com/temporary-license/) för test‑ och utvärderingsändamål.

## Slutsats
I den här handledningen gick vi igenom hur man **load MPP file Java** projekt, läser och ändrar deras standardegenskaper, och sparar ändringarna med Aspose.Tasks for Java. Att införliva dessa tekniker i dina applikationer hjälper dig att automatisera projekt‑hanteringsuppgifter, upprätthålla konsekventa standardvärden och minska manuellt arbete.

---

**Senast uppdaterad:** 2026-05-31  
**Testad med:** Aspose.Tasks for Java 24.12 (senaste vid skrivandet)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Ställ in projektets startdatum i MS Project med Aspose.Tasks för Java](/tasks/java/project-properties/write-project-info/)
- [Hur man ställer in projektkalender med Aspose.Tasks för Java](/tasks/java/calendars/properties/)
- [Hur man skapar MPP-fil – Skapa och spara tomt projekt i MPP-format med Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}