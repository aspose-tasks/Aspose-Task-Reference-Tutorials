---
date: 2026-09-20
description: Lär dig hur du extraherar valutasymbol mpp och uppdaterar projektegenskaper
  med Aspose.Tasks för Java. Ändra och hämta symbolen på bara några kodrader.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Extrahera valutasymbol mpp med Aspose.Tasks för Java
og_description: Lär dig hur du extraherar valutasymbol mpp och uppdaterar projektegenskaper
  med Aspose.Tasks för Java. Snabbt, pålitligt och redo för produktion.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Hur man extraherar valutasymbol mpp med Aspose.Tasks för Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Hur man extraherar valutasymbol mpp med Aspose.Tasks för Java
url: /sv/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahera valutasymbol mpp med Aspose.Tasks för Java

## Introduktion
I den här handledningen kommer du att lära dig hur du arbetar med **java project properties**—specifikt hur du **extract currency symbol mpp** från en Microsoft Project (MPP)-fil och hur du **change currency symbol java** eller **retrieve currency symbol java** med hjälp av Aspose.Tasks-biblioteket. Oavsett om du bygger ett verktyg för finansiell rapportering, integrerar Project-data i ett ERP‑system, eller helt enkelt behöver visa rätt valutasymbol i ditt UI, så kommer behärskning av denna lilla men viktiga uppgift att göra dina Java‑applikationer mer robusta och användarvänliga.

## Snabba svar
- **What does “extract currency symbol mpp” mean?** Det betyder att läsa av valutasymbolen som lagras i en MPP (Microsoft Project)-fil.  
- **Which library handles this?** Vilket bibliotek hanterar detta? Aspose.Tasks for Java tillhandahåller ett enkelt API för uppgiften.  
- **Do I need a license?** Behöver jag en licens? En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **How long does it take?** Hur lång tid tar det? Med koden nedan kan du få symbolen på under en minut.  
- **Can I also change the symbol?** Kan jag också ändra symbolen? Ja – du kan sätta ett nytt värde med samma `Prj.CURRENCY_SYMBOL`-egenskap.

## Vad är “extract currency symbol mpp”?
Att extrahera valutasymbolen från en MPP‑fil betyder att läsa den enkla tecknet som Microsoft Project lagrar i filens huvud för att representera projektets monetära enhet. Denna operation låter dig visa rätt symbol (t.ex. $, €, £) i dina egna applikationer utan att hårdkoda ett värde.

## Varför uppdatera valutasymbol i java project properties?
Att uppdatera valutasymbolen låter dig lokalisera rapporter, fakturor och instrumentpaneler i realtid. Företag som driver projekt över flera regioner kan byta symbol i ett enda steg, vilket undviker behovet av att duplicera hela projektfilen. Aspose.Tasks kan ändra egenskapen i minnet och spara tillbaka filen, och stödjer projekt med upp till 2 000 uppgifter utan märkbar prestandapåverkan.

## Förutsättningar
Innan vi dyker ner, se till att du har:

1. **Java Development Kit (JDK)** – version 8 eller högre.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR-filen från [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. En giltig **project.mpp**-fil placerad i en mapp som du kan referera till från din kod.

## Importera paket
Först, importera de klasser vi behöver för att arbeta med Project‑filer.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Steg 1: definiera datakatalogen
Berätta för applikationen var din *.mpp*-fil finns.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Använd `System.getProperty("user.dir")` för att bygga en absolut sökväg som fungerar på vilken maskin som helst.

## Steg 2: läs in MS Project‑filen
`Project` är Aspose.Tasks översta objekt som representerar en enskild Microsoft Project‑fil i minnet. Att skapa detta objekt läser in filstrukturen utan att Microsoft Project behöver vara installerat.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Steg 3: hämta (och eventuellt ändra) valutasymbolen
`Prj.CURRENCY_SYMBOL` är egenskapsnyckeln som lagrar valutasymbolen. Att läsa den returnerar den aktuella symbolen; att tilldela en ny sträng uppdaterar projektets valutadefinition.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println`‑anropet skriver ut symbolen (t.ex. `$`) till konsolen, vilket bekräftar att extraktionen lyckades.

## Vanliga problem & hur man åtgärdar dem
| Symptom | Trolig orsak | Lösning |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | Fel filväg eller filen hittades inte | Verifiera `dataDir` och filnamnet; använd `new File(dataDir).exists()` för felsökning |
| Unexpected symbol (e.g., `?`) | Projekt skapat med en icke‑standardiserad lokalkod | Säkerställ att käll-MPP-filen faktiskt definierar en valutasymbol; du kan sätta en programatiskt som visat ovan |
| License error | Använder provversion utan en giltig licensfil | Läs in din licens med `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` innan du skapar `Project`‑objektet |

## Vanliga frågor

**Q: Kan jag manipulera andra projektattribut förutom valutasymboler med Aspose.Tasks?**  
A: Ja, Aspose.Tasks låter dig redigera uppgifter, resurser, tilldelningar, kalendrar och många fler projektegenskaper.

**Q: Är Aspose.Tasks kompatibel med olika versioner av MS Project‑filer?**  
A: Absolut. Det stödjer MPP-, MPT- och XML‑format från Project 98 upp till de senaste versionerna.

**Q: Erbjuder Aspose.Tasks dokumentation och support för utvecklare?**  
A: Omfattande API‑dokumentation, kodexempel och ett dedikerat supportforum finns tillgängligt på Aspose.Tasks‑webbplatsen.

**Q: Kan jag prova Aspose.Tasks innan jag köper det?**  
A: Ja – en fullt funktionell gratis provversion kan laddas ner från [Aspose website](https://purchase.aspose.com/buy).

**Q: Hur kan jag få en tillfällig licens för Aspose.Tasks?**  
A: Tillfälliga licenser tillhandahålls på [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) för utvärderingsändamål.

---

**Senast uppdaterad:** 2026-09-20  
**Testat med:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Författare:** Aspose

## Relaterade handledningar

- [Projektegenskaper Java – Läs metadata med Aspose.Tasks](/tasks/java/project-properties/)
- [Hur man hämtar valuta från MS Project med Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Ställ in projektets startdatum i MS Project med Aspose.Tasks för Java](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}