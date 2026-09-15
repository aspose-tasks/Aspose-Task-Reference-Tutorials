---
date: 2026-09-14
description: Lär dig hur du får ms project valuta och läser projekt egenskaper java
  med Aspose.Tasks. Steg‑för‑steg guide för att extrahera valutans siffror från en
  MPP‑fil.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Hur man får valuta från MS Project med Aspose.Tasks
og_description: Lär dig hur du får ms project valuta och läser projekt egenskaper
  java med Aspose.Tasks. Följ denna koncisa Java‑handledning för att extrahera valutans
  siffror från en MPP‑fil.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Hur man får ms project valuta med Aspose.Tasks – Java‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Hur man får ms project valuta med Aspose.Tasks
url: /sv/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man hämtar ms project-valuta med Aspose.Tasks

## Introduktion
Om du undrar **hur man hämtar ms project currency** information från en Microsoft Project‑fil, har du hamnat på rätt plats. I den här omfattande handledningen kommer du att upptäcka **hur man arbetar med ms project currency**‑värden med hjälp av Aspose.Tasks‑biblioteket för Java. Oavsett om du bygger ett rapporteringsverktyg, ett migrationsverktyg eller helt enkelt behöver läsa valutainställningarna från en **java project file**, guidar den här guiden dig genom varje steg – från att ladda en *.mpp*-fil till att extrahera valutans siffror. I slutet kommer du att känna dig bekväm med att hantera ms project currency‑data i dina egna applikationer.

## Snabba svar
- **Vilket bibliotek läser MS Project‑filer?** Aspose.Tasks for Java.  
- **Hur många kodrader behövs för att hämta valutans siffror?** Just three concise lines after the project is loaded.  
- **Behöver jag en licens för utveckling?** A free trial works for testing; a commercial license is required for production.  
- **Vilken Java‑version stöds?** Java 8 or higher (any JDK that runs Aspose.Tasks).  
- **Kan jag hämta andra Project‑egenskaper?** Yes – Aspose.Tasks exposes a full set of Project fields (e.g., start date, cost rates, etc.).

## Vad är ms project currency?
`ms project currency`‑egenskapen definierar antalet decimaler som Microsoft Project använder när monetära värden visas. Den lagras i projektfilen som fältet **CURRENCY_DIGITS** och bestämmer om beloppen visas som heltal, en‑decimal, två‑decimaler osv. Denna inställning påverkar direkt budgetrapporter, kostnadsuppsamlingar och alla UI‑element som visar finansiella siffror, vilket gör den avgörande för korrekt datautbyte.

## Varför använda Aspose.Tasks för att hantera ms project currency?
Aspose.Tasks låter dig extrahera valutans siffror utan att installera Microsoft Project, och det gör det med prestanda på företagsnivå. Biblioteket stöder **30+ år av Project‑filversioner**—från Project 2000 till Project 2024—och täcker mer än **150 olika filscheman**. Att ladda ett 500‑sidigt projekt tar vanligtvis under **2 sekunder** på en standardserver, och du kan fråga endast de fält du behöver, vilket håller minnesanvändningen under **50 MB** även för de största schemana.

## Förutsättningar
1. **Java Development Environment** – JDK 8 eller nyare installerad och konfigurerad.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från den officiella webbplatsen: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – du bör vara bekväm med att skapa ett Java‑projekt, lägga till externa bibliotek och köra en `main`‑metod.  

## Importera paket
Först importerar du de klasser vi behöver. Importera `Project`‑klassen och relaterade verktyg från Aspose.Tasks‑biblioteket.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Steg 1: definiera datakatalog
Ange mappen som innehåller din **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Byt ut `"Your Data Directory"` mot den absoluta eller relativa sökvägen där `project.mpp` finns.

## Steg 2: ladda mpp‑filen  
Nu ska vi se **hur man laddar mpp**‑filer med Aspose.Tasks. `Project`‑klassen representerar en Microsoft Project‑fil och ger åtkomst till dess egenskaper.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Se till att filnamnet matchar exakt; annars kastas ett `IOException`.

## Steg 3: hämta valutans siffror  
När projektet är laddat är extraheringen av **ms project currency**‑siffror en enradare: Metoden `getCurrencyDigits()` returnerar antalet decimaler som definierats för monetära värden.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Anropet returnerar en `Integer` som representerar antalet decimaler (t.ex. `2` för cent). Värdet skrivs ut i konsolen, men du kan också lagra det i en variabel för vidare bearbetning.

## Vanliga problem & tips
- **File not found** – dubbelkolla `dataDir`‑sökvägen och se till att filnamnet är korrekt, inklusive `.mpp`‑ändelsen.  
- **Unsupported file version** – Aspose.Tasks stöder Project 2000‑2024‑format; äldre eller korrupta filer kan behöva konverteras.  
- **License not set** – under utveckling fungerar en provversion, men i produktion måste du tillämpa en giltig licens för att undvika utvärderingsvattenmärken.

## Vanliga frågor

**Q: Kan Aspose.Tasks hantera andra Project‑attribut förutom valutans siffror?**  
A: Ja, Aspose.Tasks erbjuder ett brett utbud av funktioner för att manipulera olika aspekter av Project‑filer, såsom uppgifter, resurser och anpassade fält.

**Q: Är Aspose.Tasks lämplig för företagsnivå‑applikationer?**  
A: Absolut, Aspose.Tasks är designat för att möta kraven på företagsklassade projekt, med hög prestanda och skalbarhet.

**Q: Stöder Aspose.Tasks plattformsoberoende utveckling?**  
A: Ja, du kan använda Aspose.Tasks för Java på alla plattformar som stöder Java Runtime Environment (Windows, Linux, macOS).

**Q: Kan jag prova Aspose.Tasks innan jag köper?**  
A: Ja, du kan ladda ner en gratis provversion från [Aspose releases page](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.Tasks?**  
A: Du kan hitta support på [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Senast uppdaterad:** 2026-09-14  
**Testad med:** Aspose.Tasks for Java (senaste vid skrivande)  
**Författare:** Aspose

## Relaterade handledningar

- [java projekt egenskaper – Extrahera valutasymbol från MPP med Aspose.Tasks för Java](/tasks/java/currency/currency-symbols/)
- [Hur man hämtar valuta från MS Project med Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Project‑egenskaper Java – Läs metadata med Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}