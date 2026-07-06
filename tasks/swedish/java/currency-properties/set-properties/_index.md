---
date: 2026-02-07
description: Lär dig hur du ställer in valutakod i Java i Aspose.Tasks‑projekt, ändrar
  valutasymbol och tillämpar ett anpassat valutaformat för Microsoft Project‑filer.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: valutakod java – Hur man anger i Aspose.Tasks‑projekt
url: /sv/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man anger valutakod i Aspose.Tasks – Java‑guide

## Introduktion
I den här handledningen kommer du att lära dig **hur man anger valutakod java** för en Microsoft Project‑fil med hjälp av Aspose.Tasks Java‑API. Oavsett om du behöver *ändra valuta* för internationella team, justera *valutasymbolen*, eller använda ett **anpassat valutaformat**, så kommer stegen nedan att guida dig genom processen med tydliga förklaringar och färdig‑körbar kod.

## Snabba svar
- **Vilket bibliotek krävs?** Aspose.Tasks for Java.  
- **Kan jag ändra valutasymbolen?** Ja – använd `CurrencySymbolPositionType` och `Prj.CURRENCY_SYMBOL`.  
- **Vilka filformat stöds?** XML, MPP och många andra via `SaveFileFormat`.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en licens krävs för produktion.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för en grundläggande konfiguration.

## Hur man anger valutakod Java i Aspose.Tasks
Ett projekts valuta definierar hur kostnadsvärden visas—kod (t.ex. `AUD`), antal decimaler, symbol (`$`) och symbolens position. Genom att ställa in dessa egenskaper säkerställer du att varje kostnadsrelaterat fält (resurspriser, uppgiftsbudgetar osv.) visar rätt monetärt format för din målgrupp.

## Varför använda Aspose.Tasks för att ändra valuta?
- **Ingen Microsoft Project‑installation behövs** – manipulera filer på vilken server som helst.  
- **Full API‑täckning** – alla valutarelaterade fält exponeras via `Prj`‑konstanter.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS med vilken Java‑kompatibel IDE som helst.  
- **Hög prestanda** – bearbeta stora projektfiler snabbt och pålitligt.  
- **Stöder anpassat valutaformat** – du kan definiera symboler, decimaler och positionering för att matcha regionala standarder.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK)** – version 8 eller högre.  
2. **Aspose.Tasks for Java** – ladda ner den senaste JAR‑filen från [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. **En IDE** – Eclipse, IntelliJ IDEA eller någon annan editor du föredrar.  
4. **En skrivbar mapp** – där den genererade projektfilen kommer att sparas.

## Importera paket
Importera först klasserna som ger åtkomst till projektets egenskaper och filhantering.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Steg‑för‑steg‑guide

### Steg 1: Definiera datakatalogen
Ange mappen som innehåller dina källfiler och där utdata ska skrivas.

```java
String dataDir = "Your Data Directory";
```

### Steg 2: Skapa en ny projektinstans
Instansiera ett nytt `Project`‑objekt. Detta objekt representerar en Microsoft Project‑fil i minnet.

```java
Project project = new Project();
```

### Steg 3: Ställ in valutapropertys
Här är där vi **hur man anger valuta** detaljer såsom kod, siffror, symbol och symbolposition.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Proffstips:** Om du behöver **ändra projektvaluta** för en befintlig fil, ladda helt enkelt den med `new Project("file.mpp")` innan du tillämpar inställningarna ovan.

### Steg 4: Spara det uppdaterade projektet
Skriv projektet tillbaka till disk i önskat format. I det här exemplet använder vi XML‑formatet, men du kan också välja `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Steg 5: Bekräfta framgång
Skriv ut ett vänligt meddelande så du vet att operationen slutfördes utan fel.

```java
System.out.println("Process completed Successfully");
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| **`NullPointerException` på `project.save`** | `dataDir` är inte en giltig sökväg eller saknar skrivbehörighet. | Se till att katalogen finns och att din Java‑process har skrivbehörighet. |
| **Valutasymbol visas inte** | Symbolens position är felaktigt inställd för din region. | Använd `CurrencySymbolPositionType.Before` om symbolen ska föregå beloppet. |
| **Projektfilen öppnas inte i MS Project** | Sparar i ett äldre format med inkompatibla inställningar. | Spara med `SaveFileFormat.MPP` för full kompatibilitet med senaste versionerna av MS Project. |

## Vanliga frågor

**Q: Kan jag ange flera valutor i ett enda projekt med Aspose.Tasks?**  
A: Ja, Aspose.Tasks låter dig hantera flera valutor i en enda projektfil genom att ställa in valutapropertys per resurs eller per uppgift.

**Q: Är Aspose.Tasks kompatibelt med olika versioner av Microsoft Project‑filer?**  
A: Absolut. Biblioteket stöder MPP‑filer från Project 2000 upp till de senaste versionerna, samt XML och andra format.

**Q: Ger Aspose.Tasks stöd för anpassade valutaformat?**  
A: Ja, du kan definiera egna symboler, decimaler och positionering för att uppfylla alla regionala krav.

**Q: Kan jag integrera Aspose.Tasks med andra Java‑bibliotek eller ramverk?**  
A: Självklart. API‑et är rent Java, så det fungerar sömlöst med Spring, Hibernate, Maven, Gradle och andra ekosystem.

**Q: Var kan jag hitta ytterligare support eller hjälp för Aspose.Tasks?**  
A: Besök [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för community‑hjälp, eller konsultera den officiella dokumentationen för detaljerade API‑referenser.

## Slutsats
Du vet nu **hur man anger valutakod java**, hur man **ändrar valutavärden**, och hur man **ändrar valutasymbol** med Aspose.Tasks för Java. Dessa funktioner låter dig anpassa kostnadsdata för globala team, generera regionsspecifika rapporter och hålla dina projektfiler konsekventa över gränser.

---

**Senast uppdaterad:** 2026-02-07  
**Testat med:** Aspose.Tasks for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}