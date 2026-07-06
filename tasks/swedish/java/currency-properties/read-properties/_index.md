---
date: 2026-02-07
description: Lär dig hur du läser valutainställningar i Java och extraherar valutasymbol
  i Java från MS Project‑filer med Aspose.Tasks för Java. Följ den här steg‑för‑steg‑guiden
  för att programatiskt extrahera valutakod, symbol, siffror och position.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Läs valutainställningar i Java med Aspose.Tasks-projekt
url: /sv/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs valutaegenskaper Java med Aspose.Tasks‑projekt

## Introduktion
I den här handledningen kommer du att **läsa valutaegenskaper java** från Microsoft Project‑filer med hjälp av Aspose.Tasks för Java‑API. Aspose.Tasks låter dig arbeta med .mpp‑filer utan att ha Microsoft Project installerat, vilket gör det idealiskt för automatiserad rapportering, datamigrering eller integration i Java‑baserade företagsapplikationer. I slutet av guiden kan du extrahera valutakod, symbol, antal decimaler och symbolens position direkt från en projektfil.

## Snabba svar
- **Vad betyder “read currency properties java”?** Det avser att hämta valutarelaterad metadata (kod, symbol, siffror, position) från en MS Project‑fil med Java‑kod.  
- **Behöver jag en licens för att prova detta?** En gratis provversion av Aspose.Tasks finns tillgänglig; en kommersiell licens krävs för produktionsbruk.  
- **Vilken JDK‑version krävs?** Java 8 eller högre.  
- **Kan jag ändra valutainställningarna efter att ha läst dem?** Ja, Aspose.Tasks tillåter både läs‑ och skrivoperationer på valutaegenskaper.  
- **Är detta kompatibelt med alla .mpp‑versioner?** API‑et stöder filer som skapats med Microsoft Project 2003‑2021.

## Vad är read currency properties java?
Att läsa valutaegenskaper i Java betyder att komma åt projekt‑nivåinställningarna som definierar hur monetära värden visas i en Microsoft Project‑fil. Dessa inställningar inkluderar ISO‑valutakoden (t.ex. **USD**), symbolen (**$**), antalet decimaler och om symbolen visas före eller efter beloppet.

## Varför läsa valutaegenskaper java med Aspose.Tasks?
- **Ingen Microsoft Project‑installation behövs** – API‑et fungerar på alla plattformar som stödjer Java.  
- **Snabb, in‑process‑extraktion** – idealisk för batch‑bearbetning av stora mängder projektfiler.  
- **Full kontroll** – du kan kombinera de hämtade värdena med anpassade rapporter eller integrera dem i ERP‑system.  
- **Stöd för flera versioner** – fungerar med .mpp‑filer från Project 2003 upp till den senaste 2021‑utgåvan.

## Förutsättningar
Innan du börjar, se till att du har:

1. **Java Development Kit (JDK)** – Java 8 eller nyare installerat och konfigurerat i din `PATH`.  
2. **Aspose.Tasks för Java JAR** – ladda ner det senaste biblioteket från [here](https://releases.aspose.com/tasks/java/) och lägg till det i ditt projekts classpath.  

## Importera paket
Börja med att importera det Aspose.Tasks‑namnrymd som krävs för projektmanipulation:

```java
import com.aspose.tasks.*;
```

## Steg 1: Ställ in din projektkatalog
Definiera mappen som innehåller `.mpp`‑filen du vill analysera. Att hålla sökvägen i en variabel gör koden återanvändbar:

```java
String dataDir = "Your Data Directory";
```

*Ersätt `"Your Data Directory"` med den absoluta eller relativa sökvägen till mappen där `project.mpp` ligger.*

## Steg 2: Skapa en Project‑läsare‑instans
Läs in Microsoft Project‑filen i ett `Project`‑objekt. Detta objekt ger dig åtkomst till alla projekt‑egenskaper, inklusive valutainställningarna:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Om din fil har ett annat namn, ändra `"project.mpp"` därefter.*

## Steg 3: Visa valutaegenskaper
Hämta nu varje valutaattribut med `Prj`‑enumerationen och skriv ut resultaten till konsolen. API‑et returnerar objekt som du kan konvertera till strängar för visning:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Det du kommer att se:**  
- **Currency Code** – ISO‑4217‑kod såsom `USD`, `EUR`, `JPY`.  
- **Currency Digits** – vanligtvis `2` för de flesta valutor, `0` för japanska yen.  
- **Currency Symbol** – tecknet som visas i rapporter (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` för **före** beloppet, `1` för **efter**.

## Hur extraherar man valutansymbol java?
Om du bara är intresserad av själva symbolen kan du fokusera på egenskapen `Prj.CURRENCY_SYMBOL`. Samma anrop `project.get(...)` returnerar symbolen, som du kan lagra, logga eller skicka till en annan tjänst för vidare bearbetning. Detta är särskilt användbart när du behöver **extract currency symbol java** för finansiella instrumentpaneler eller lokalanpassade UI‑komponenter.

## Steg 4: Processen slutförd
Signalera att extraktionen har avslutats framgångsrikt. Detta enkla meddelande är praktiskt när koden körs som en del av ett större batch‑jobb:

```java
System.out.println("Process completed Successfully");
```

## Vanliga problem och lösningar
| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir`‑sökvägen är felaktig eller filnamnet är felstavat. | Verifiera katalogsträngen och säkerställ att `.mpp`‑filen finns på den angivna platsen. |
| **NullPointerException on `project.get(...)`** | Projektfilen innehåller ingen valutainformation (osannolikt) eller nyckeln är fel. | Använd `project.contains(Prj.CURRENCY_CODE)` för att kontrollera existens innan läsning. |
| **LicenseException** | Kör utan en giltig Aspose.Tasks‑licens i en produktionsmiljö. | Applicera en licensfil med `License license = new License(); license.setLicense("Aspose.Tasks.lic");` innan du skapar `Project`‑objektet. |

## Vanliga frågor

**Q: Är Aspose.Tasks kompatibelt med alla versioner av Microsoft Project?**  
A: Aspose.Tasks stöder .mpp‑filer som genererats av Microsoft Project 2003‑2021, vilket täcker både äldre och de senaste formaten.

**Q: Kan jag ändra valutaegenskaper med Aspose.Tasks?**  
A: Ja, du kan både läsa och skriva valutainställningar. Använd `project.set(Prj.CURRENCY_CODE, "EUR");` och spara sedan projektet.

**Q: Är Aspose.Tasks lämpligt för kommersiell användning?**  
A: Absolut. Det är ett kommersiellt bibliotek; du kan köpa en licens [here](https://purchase.aspose.com/buy).

**Q: Erbjuder Aspose.Tasks en gratis provperiod?**  
A: Ja, en fullt funktionell provversion finns tillgänglig från [here](https://releases.aspose.com/).

**Q: Var kan jag söka hjälp eller support för Aspose.Tasks?**  
A: Det officiella Aspose.Tasks‑forumet är den bästa platsen för assistans – besök det [here](https://forum.aspose.com/c/tasks/15).

## Ytterligare FAQ (AI‑optimerad)

**Q: Hur extraherar jag programatiskt bara valutansymbolen i Java?**  
A: Anropa `project.get(Prj.CURRENCY_SYMBOL)` och kasta resultatet till en `String`. Detta returnerar exakt den symbol som används i projektfilen.

**Q: Kan jag läsa valutaegenskaper från en lösenordsskyddad .mpp‑fil?**  
A: Ja. Läs in filen med den lämpliga överlagringen av `Project`‑konstruktorn som accepterar ett lösenord, och läs sedan egenskaperna som visat.

**Q: Vilken prestanda kan jag förvänta mig när jag bearbetar många projektfiler?**  
A: Aspose.Tasks kör in‑process och läser vanligtvis en standard‑.mpp‑fil på några millisekunder. För massbearbetning, överväg att återanvända samma `Project`‑instans där det är möjligt.

## Slutsats
Du har nu lärt dig hur du **läser valutaegenskaper java** och **extraherar valutansymbol java** från en MS Project‑fil med Aspose.Tasks för Java. Denna funktion gör det möjligt att integrera valutametadata i anpassade rapporter, finansiella analyser eller integrationspipeline utan att förlita dig på Microsoft Project. Känn dig fri att experimentera med att modifiera egenskaperna eller kombinera dessa data med andra projektelement för att bygga rikare lösningar.

---

**Senast uppdaterad:** 2026-02-07  
**Testat med:** Aspose.Tasks för Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}