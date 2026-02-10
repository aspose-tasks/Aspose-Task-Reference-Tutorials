---
date: 2026-02-10
description: Lär dig hur du hämtar valutavärden, läser MS Project‑fil och konverterar
  projektfil till Java med Aspose.Tasks. Steg‑för‑steg‑guide för att extrahera valutasiffror.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hur man hämtar valuta från MS Project med Aspose.Tasks
url: /sv/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man hämtar valuta från MS Project med Aspose.Tasks

## Introduction
Om du undrar **hur man får valuta** information från en Microsoft Project‑fil, har du hamnat på rätt ställe. I den här omfattande handledningen kommer du att upptäcka **hur man arbetar med ms project currency**‑värden med hjälp av Aspose.Tasks‑biblioteket för Java. Oavsett om du bygger ett rapporteringsverktyg, ett migrationsverktyg eller helt enkelt behöver läsa valutainställningarna från en **java project file**, guidar den här guiden dig genom varje steg – från att ladda en *.mpp*-fil till att extrahera valutans siffror. I slutet kommer du att känna dig bekväm med att hantera ms project currency‑data i dina egna applikationer.

## Quick Answers
- **Vilket bibliotek läser MS Project‑filer?** Aspose.Tasks for Java.  
- **Hur många kodrader behövs för att hämta valutans siffror?** Endast tre koncisa rader efter att projektet har laddats.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version stöds?** Java 8 eller högre (vilken JDK som helst som kör Aspose.Tasks).  
- **Kan jag hämta andra projekt‑egenskaper?** Ja – Aspose.Tasks exponerar en komplett uppsättning projektfält (t.ex. startdatum, kostnadsräntor osv.).

## What is ms project currency?
`ms project currency` avser den numeriska precisionen (antal decimaler) som Microsoft Project använder när monetära värden visas. Den lagras i projektfilen som egenskapen **CURRENCY_DIGITS** och bestämmer om beloppen visas som heltal, en‑decimal, två‑decimaler osv.

## Why use Aspose.Tasks for handling ms project currency?
- **Ingen Microsoft Project‑installation krävs** – arbeta direkt med *.mpp*-filer på vilken plattform som helst som stöder Java.  
- **Stark typ‑säkerhet** – API‑et returnerar starkt typade värden, vilket minskar parsningsfel.  
- **Prestandaoptimerad** – ladda stora projekt snabbt och extrahera endast de fält du behöver.  
- **Cross‑platform** – kör på Windows, Linux eller macOS utan modifiering.

## Prerequisites
Innan du börjar, se till att du har följande:

1. **Java‑utvecklingsmiljö** – JDK 8 eller nyare installerad och konfigurerad.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från den officiella webbplatsen: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Grundläggande Java‑kunskaper** – du bör vara bekväm med att skapa ett Java‑projekt, lägga till externa bibliotek och köra en `main`‑metod.  

## Import Packages
Först, importera de klasser vi behöver.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Define Data Directory
Ange mappen som innehåller din **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Byt ut `"Your Data Directory"` mot den absoluta eller relativa sökvägen där `project.mpp` finns.

## Step 2: Load the MPP File  
Nu ska vi se **hur man laddar mpp**‑filer med Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Se till att filnamnet matchar exakt; annars kastas ett `IOException`.

## Step 3: Retrieve Currency Digits  
När projektet är laddat är extrahering av **ms project currency**‑siffror en enradare:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Anropet returnerar en `Integer` som representerar antalet decimaler (t.ex. `2` för cent). Värdet skrivs ut till konsolen, men du kan också lagra det i en variabel för vidare bearbetning.

## Common Issues & Tips
- **Fil ej hittad** – dubbelkolla `dataDir`‑sökvägen och säkerställ att filnamnet är korrekt, inklusive `.mpp`‑ändelsen.  
- **Ej stöd för filversion** – Aspose.Tasks stöder Project 2000‑2024‑format; äldre eller korrupta filer kan behöva konverteras.  
- **Licens ej satt** – under utveckling fungerar en provversion, men för produktion måste du tillämpa en giltig licens för att undvika utvärderingsvattenstämplar.

## Frequently Asked Questions

**Q: Kan Aspose.Tasks hantera andra projektattribut förutom valutans siffror?**  
A: Ja, Aspose.Tasks erbjuder ett brett spektrum av funktioner för att manipulera olika aspekter av projektfiler, såsom uppgifter, resurser och anpassade fält.

**Q: Är Aspose.Tasks lämpligt för företags‑nivå applikationer?**  
A: Absolut, Aspose.Tasks är designat för att möta kraven hos företagsklassade projekt, med hög prestanda och skalbarhet.

**Q: Stöder Aspose.Tasks cross‑platform‑utveckling?**  
A: Ja, du kan använda Aspose.Tasks för Java på vilken plattform som helst som stöder Java Runtime Environment (Windows, Linux, macOS).

**Q: Kan jag prova Aspose.Tasks innan jag köper?**  
A: Ja, du kan ladda ner en gratis provversion från [here](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.Tasks?**  
A: Du kan hitta support på [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Du vet nu **hur man får valuta**‑siffror från en MS Project‑fil med Aspose.Tasks för Java. Processen är enkel: ladda projektet, anropa `project.get(Prj.CURRENCY_DIGITS)`, och använd resultatet i din applikation. Känn dig fri att utforska andra projekt‑egenskaper med samma mönster och integrera denna logik i större rapporterings‑ eller migrationslösningar.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}