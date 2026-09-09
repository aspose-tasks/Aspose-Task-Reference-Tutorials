---
date: 2026-09-09
description: Lär dig hur du ändrar valutasymbol i Aspose.Tasks Java‑projekt, ställer
  in valutakoder, justerar symboler och tillämpar anpassade format för Microsoft Project‑filer.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Ställ in valutainställningar i Aspose.Tasks‑projekt
og_description: Hur du ändrar valutasymbol i Aspose.Tasks med Java. Upptäck steg‑för‑steg‑instruktioner,
  förutsättningar och tips för att anpassa projektkostnadsformatering.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Hur du ändrar valutasymbol i Aspose.Tasks – Java‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Hur du ändrar valutasymbol i Aspose.Tasks-projekt – Java‑guide
url: /sv/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så ändrar du valutasymbol i Aspose.Tasks – Java‑guide

## Introduktion
I den här handledningen kommer du att lära dig **hur du ändrar valutasymbol** för en Microsoft Project‑fil med hjälp av Aspose.Tasks Java‑API. Oavsett om du förbereder rapporter för en utländsk kund, konsoliderar budgetar över flera regioner, eller helt enkelt behöver anpassa ditt företags redovisningsstandarder, så säkerställer justering av valutasymbolen att varje kostnadsrelaterat fält visar rätt monetära tecken. Handledningen går igenom varje steg, från att sätta upp utvecklingsmiljön till att spara ändringarna i en ny eller befintlig projektfil.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Tasks for Java.  
- **Kan jag ändra valutasymbolen?** Ja – sätt `Prj.CURRENCY_SYMBOL` och välj `CurrencySymbolPositionType`.  
- **Vilka filformat stöds?** XML, MPP och många andra via `SaveFileFormat`.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Hur lång tid tar implementeringen?** Cirka 5‑10 minuter för en grundläggande installation.

## Så ändrar du valutasymbol i Aspose.Tasks med Java?
Läs in målprojektet (eller skapa ett nytt), ställ in önskade valutainställningar och spara filen. Hela operationen består av tre API‑anrop: skapa eller läsa in ett `Project`‑objekt, tilldela valutakod, symbol och position, och sedan anropa `project.save`. Detta tillvägagångssätt fungerar både för nya projekt och befintliga filer utan att Microsoft Project behöver vara installerat.

## Varför använda Aspose.Tasks för att ändra valuta?
Aspose.Tasks erbjuder **full API‑täckning för 30+ valutarelaterade egenskaper**, vilket gör att du kan definiera kod, symbol, decimaler och positionering på ett ställe. Biblioteket bearbetar projektfiler på flera hundra sidor på under en sekund på vanlig serverhårdvara, och det fungerar på Windows, Linux och macOS utan några extra beroenden.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK) 8 eller högre** – API:et kräver minst JDK 8.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från [Aspose.Tasks nedladdningssida](https://releases.aspose.com/tasks/java/).  
3. **En IDE** – Eclipse, IntelliJ IDEA eller någon editor som stödjer Java.  
4. **En skrivbar mapp** – där den genererade projektfilen kommer att sparas.

## Importera paket
Följande klasser ger dig åtkomst till projektegenskaper, filhantering och valutainställningar.  

`Project` – representerar en Microsoft Project‑fil i minnet.  
`Prj` – innehåller konstanter för alla projekt‑nivå egenskaper, inklusive valutafält.  
`CurrencySymbolPositionType` – enumererar möjliga positioner för valutasymbolen (före eller efter beloppet).  

Dessa import måste göras innan någon kod kan manipulera ett projekt.

## Steg‑för‑steg guide

### Steg 1: Definiera datakatalogen
Välj en mapp som innehåller dina källfiler och där utdata ska skrivas. Se till att katalogen finns och att din Java‑process har skrivrättigheter.

### Steg 2: Skapa en ny projektinstans
`Project`‑klassen är Aspose.Tasks översta objekt som representerar en enskild projektfil i minnet. Att instansiera den skapar ett tomt projekt redo för konfiguration.

### Steg 3: Ställ in valutainställningar
Här konfigurerar du valutakod, antal decimaler, själva symbolen och symbolens position.

- **Valutakod** – en tresiffrig ISO‑4217‑kod som `AUD` eller `USD`.  
- **Decimaler** – vanligtvis 2 för de flesta valutor.  
- **Valutasymbol** – tecknet eller strängen som visas med beloppen, t.ex. `$` eller `€`.  
- **Symbolposition** – `CurrencySymbolPositionType.Before` placerar symbolen före siffran; `After` placerar den efter.

Dessa inställningar påverkar varje kostnadsrelaterat fält (resurspriser, uppgiftsbudgetar osv.) i projektet.

> **Proffstips:** Om du behöver ändra valutan för en befintlig fil, läs in den med `new Project("file.mpp")` innan du tillämpar ovanstående inställningar.

### Steg 4: Spara det uppdaterade projektet
Skriv projektet tillbaka till disk med önskat format. XML‑formatet är läsbart för människor, medan `SaveFileFormat.MPP` bevarar full kompatibilitet med Microsoft Project.

### Steg 5: Bekräfta framgång
Skriv ut ett kort meddelande eller loggpost så du vet att operationen slutfördes utan fel. Detta är särskilt användbart i automatiserade pipelines.

## Vanliga problem & lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| **`NullPointerException` på `project.save`** | `dataDir` är inte en giltig sökväg eller saknar skrivrättigheter. | Se till att katalogen finns och att din Java‑process har skrivrättigheter. |
| **Valutasymbol visas inte** | Symbolpositionen är felaktigt inställd för din region. | Använd `CurrencySymbolPositionType.Before` om symbolen ska föregå beloppet. |
| **Projektfil öppnas inte i MS Project** | Sparar i ett äldre format med inkompatibla inställningar. | Spara med `SaveFileFormat.MPP` för full kompatibilitet med senaste MS Project‑versioner. |

## Vanliga frågor

**Q: Kan jag ange flera valutor i ett enda projekt med Aspose.Tasks?**  
A: Ja, du kan tilldela olika valutainställningar till enskilda resurser eller uppgifter genom att ändra deras respektive kostnadsfält efter att projekt‑nivåvalutan har definierats.

**Q: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project‑filer?**  
A: Absolut. Biblioteket stödjer MPP‑filer från Project 2000 upp till de senaste versionerna, samt XML och andra utbytesformat.

**Q: Ger Aspose.Tasks stöd för anpassade valutaformat?**  
A: Ja, du kan definiera egna symboler, decimaler och positionering för att möta regionala krav, och dessa inställningar sparas i den sparade filen.

**Q: Kan jag integrera Aspose.Tasks med andra Java‑ramverk?**  
A: Självklart. API:et är ren Java, så det fungerar sömlöst med Spring, Hibernate, Maven, Gradle och andra ekosystem.

**Q: Var kan jag hitta ytterligare hjälp eller exempel?**  
A: Besök [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för gemenskapsstöd, eller konsultera den officiella dokumentationen för detaljerade API‑referenser.

## Slutsats
Du vet nu **hur du ändrar valutasymbol** i Aspose.Tasks‑projekt med Java, hur du ställer in valutakod, justerar decimaler och använder en anpassad symbol. Dessa funktioner låter dig skapa regionsspecifika kostnadsrapporter, anpassa projektbudgetar efter regionala redovisningsstandarder och hålla dina Microsoft Project‑filer konsekventa över globala team.

---

**Senast uppdaterad:** 2026-09-09  
**Testad med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Relaterade handledningar

- [java projekt egenskaper – Extrahera valutasymbol från MPP med Aspose.Tasks för Java](/tasks/java/currency/currency-symbols/)
- [Läs valutaproperty Java med Aspose.Tasks‑projekt](/tasks/java/currency-properties/read-properties/)
- [Hantera valutakoder Java med Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}