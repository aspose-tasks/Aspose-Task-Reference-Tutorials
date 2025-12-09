---
date: 2025-12-05
description: Lär dig hur du hanterar MS Project-valutaciffror effektivt med Aspose.Tasks
  för Java. Steg‑för‑steg‑guide som täcker Java‑projektfilhantering och hur du laddar
  MPP‑filer.
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hantera MS Project‑valutans siffror med Aspose.Tasks
url: /sv/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera ms project-valuta siffror med Aspose.Tasks

## Introduktion
I den här omfattande handledningen kommer du att upptäcka **hur man arbetar med ms project currency**-värden med hjälp av Aspose.Tasks‑biblioteket för Java. Oavsett om du bygger ett rapporteringsverktyg, ett migrationsverktyg eller helt enkelt behöver läsa valutainställningarna från en **java project file**, guidar den här guiden dig genom varje steg—från att ladda en *.mpp*‑fil till att extrahera valutans siffror. När du är klar kommer du att känna dig säker på att hantera ms project‑valutadata i dina egna applikationer.

## Snabba svar
- **Vilket bibliotek läser MS Project-filer?** Aspose.Tasks for Java.  
- **Hur många kodrader behövs för att hämta valuta-siffror?** Endast tre koncisa rader efter att projektet har laddats.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilken Java-version stöds?** Java 8 eller högre (valfri JDK som kör Aspose.Tasks).  
- **Kan jag hämta andra Project-egenskaper?** Ja – Aspose.Tasks exponerar en full uppsättning Project-fält (t.ex. startdatum, kostnadsnivåer, etc.).

## Vad är ms project-valuta?
`ms project currency` avser den numeriska precisionen (antal decimaler) som Microsoft Project använder när monetära värden visas. Den lagras i projektfilen som egenskapen **CURRENCY_DIGITS** och bestämmer om belopp visas som heltal, en‑decimal, två‑decimaler osv.

## Varför använda Aspose.Tasks för att hantera ms project-valuta?
- **Ingen Microsoft Project-installation krävs** – arbeta direkt med *.mpp* filer på vilken plattform som helst som stödjer Java.  
- **Stark typ‑säkerhet** – API:et returnerar starkt typade värden, vilket minskar parsningsfel.  
- **Prestandaoptimerad** – ladda stora projekt snabbt och extrahera endast de fält du behöver.  
- **Plattformsoberoende** – kör på Windows, Linux eller macOS utan ändringar.

## Förutsättningar
Innan du börjar, se till att du har följande:

1. **Java-utvecklingsmiljö** – JDK 8 eller nyare installerad och konfigurerad.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR-filen från den officiella webbplatsen: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Grundläggande Java-kunskaper** – du bör vara bekväm med att skapa ett Java-projekt, lägga till externa bibliotek och köra en `main`‑metod.  

## Importera paket
Först, importera de klasser vi behöver.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Steg 1: Definiera datakatalog
Ange mappen som innehåller din **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Byt ut `"Your Data Directory"` mot den absoluta eller relativa sökvägen där `project.mpp` finns.

## Steg 2: Ladda MPP-filen  
Nu ska vi se **hur man laddar mpp**‑filer med Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Se till att filnamnet matchar exakt; annars kastas ett `IOException`.

## Steg 3: Hämta valuta-siffror  
När projektet är laddat är extrahering av **ms project currency**‑siffror en enradare:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Anropet returnerar en `Integer` som representerar antalet decimaler (t.ex. `2` för cent). Värdet skrivs ut i konsolen, men du kan också lagra det i en variabel för vidare bearbetning.

## Vanliga problem & tips
- **Fil ej hittad** – dubbelkolla `dataDir`‑sökvägen och säkerställ att filnamnet är korrekt, inklusive `.mpp`‑ändelsen.  
- **Ej stöd för filversion** – Aspose.Tasks stödjer Project 2000‑2024-format; äldre eller korrupta filer kan behöva konverteras.  
- **Licens ej angiven** – under utveckling fungerar en provversion, men för produktion måste du tillämpa en giltig licens för att undvika utvärderingsvattenmärken.

## Vanliga frågor

**Q: Kan Aspose.Tasks hantera andra Project-attribut förutom valuta-siffror?**  
A: Ja, Aspose.Tasks erbjuder ett brett utbud av funktioner för att manipulera olika aspekter av Project-filer, såsom uppgifter, resurser och anpassade fält.

**Q: Är Aspose.Tasks lämplig för företagsnivåapplikationer?**  
A: Absolut, Aspose.Tasks är designad för att möta kraven på företagsklassade projekt, med hög prestanda och skalbarhet.

**Q: Stöder Aspose.Tasks plattformsoberoende utveckling?**  
A: Ja, du kan använda Aspose.Tasks för Java på vilken plattform som helst som stödjer Java Runtime Environment (Windows, Linux, macOS).

**Q: Kan jag prova Aspose.Tasks innan jag köper?**  
A: Ja, du kan ladda ner en gratis provversion från [here](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.Tasks?**  
A: Du kan hitta support på [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Senast uppdaterad:** 2025-12-05  
**Testad med:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}