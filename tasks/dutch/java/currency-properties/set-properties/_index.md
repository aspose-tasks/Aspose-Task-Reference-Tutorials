---
date: 2026-02-07
description: Leer hoe u de valutacode in Java kunt instellen in Aspose.Tasks‑projecten,
  het valutasymbool kunt wijzigen en een aangepast valutaformaat kunt toepassen voor
  Microsoft Project‑bestanden.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Valutacode Java – Hoe in te stellen in Aspose.Tasks‑projecten
url: /nl/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe stel je de valutacode in Aspose.Tasks – Java-gids

## Introductie
In deze tutorial leer je **hoe je de valutacode java** instelt voor een Microsoft Project‑bestand met behulp van de Aspose.Tasks Java‑API. Of je nu de *valuta* moet wijzigen voor internationale teams, het *valutasymbool* moet aanpassen, of een **aangepast valuta‑formaat** wilt toepassen, de onderstaande stappen begeleiden je door het proces met duidelijke uitleg en kant‑klaar code.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java.  
- **Kan ik het valutasymbool wijzigen?** Ja – gebruik `CurrencySymbolPositionType` en `Prj.CURRENCY_SYMBOL`.  
- **Welke bestandsformaten worden ondersteund?** XML, MPP en vele andere via `SaveFileFormat`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een basisinstelling.

## Hoe stel je de valutacode Java in Aspose.Tasks
De valuta van een project bepaalt hoe kostwaarden worden weergegeven—code (bijv. `AUD`), aantal decimalen, symbool (`$`) en de positie van het symbool. Het instellen van deze eigenschappen zorgt ervoor dat elk kostgerelateerd veld (resource‑tarieven, taak‑budgetten, enz.) het juiste monetaire formaat voor je publiek weergeeft.

## Waarom Aspose.Tasks gebruiken om valuta te wijzigen?
- **Geen Microsoft Project‑installatie nodig** – bewerk bestanden op elke server.  
- **Volledige API‑dekking** – alle valuta‑gerelateerde velden zijn beschikbaar via `Prj`‑constanten.  
- **Cross‑platform** – werkt op Windows, Linux en macOS met elke Java‑compatibele IDE.  
- **Hoge prestaties** – verwerk grote projectbestanden snel en betrouwbaar.  
- **Ondersteunt aangepast valuta‑formaat** – je kunt symbolen, decimalen en positionering definiëren om aan regionale normen te voldoen.

## Voorvereisten
1. **Java Development Kit (JDK)** – versie 8 of hoger.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de [Aspose.Tasks downloadpagina](https://releases.aspose.com/tasks/java/).  
3. **Een IDE** – Eclipse, IntelliJ IDEA, of elke editor die je verkiest.  
4. **Een beschrijfbare map** – waar het gegenereerde projectbestand wordt opgeslagen.

## Pakketten importeren
Importeer eerst de klassen die toegang bieden tot project‑eigenschappen en bestandsafhandeling.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Stapsgewijze handleiding

### Stap 1: Definieer de gegevensdirectory
Geef de map op die je bronbestanden bevat en waar de uitvoer wordt weggeschreven.

```java
String dataDir = "Your Data Directory";
```

### Stap 2: Maak een nieuw project‑object aan
Instantieer een nieuw `Project`‑object. Dit object vertegenwoordigt een Microsoft Project‑bestand in het geheugen.

```java
Project project = new Project();
```

### Stap 3: Stel valutaproperties in
Hier stel je de **hoe je valuta instelt** details in, zoals code, decimalen, symbool en symboolpositie.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** Als je de **projectvaluta wilt wijzigen** voor een bestaand bestand, laad het dan eenvoudig met `new Project("file.mpp")` voordat je de bovenstaande instellingen toepast.

### Stap 4: Sla het bijgewerkte project op
Schrijf het project terug naar schijf in het gewenste formaat. In dit voorbeeld gebruiken we het XML‑formaat, maar je kunt ook `SaveFileFormat.MPP` kiezen.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Stap 5: Bevestig succes
Print een vriendelijke boodschap zodat je weet dat de bewerking zonder fouten is voltooid.

```java
System.out.println("Process completed Successfully");
```

## Veelvoorkomende problemen & oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`NullPointerException` bij `project.save`** | `dataDir` is geen geldig pad of heeft geen schrijfrechten. | Zorg ervoor dat de map bestaat en dat je Java‑proces schrijfrechten heeft. |
| **Valutasymbool wordt niet weergegeven** | De symboolpositie is onjuist ingesteld voor je locale. | Gebruik `CurrencySymbolPositionType.Before` als het symbool vóór het bedrag moet staan. |
| **Projectbestand opent niet in MS Project** | Opslaan in een ouder formaat met incompatibele instellingen. | Sla op met `SaveFileFormat.MPP` voor volledige compatibiliteit met recente MS Project‑versies. |

## Veelgestelde vragen

**Q: Kan ik meerdere valuta's in één project instellen met Aspose.Tasks?**  
A: Ja, Aspose.Tasks stelt je in staat meerdere valuta's te beheren binnen één projectbestand door valutaproperties per resource of per taak in te stellen.

**Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Absoluut. De bibliotheek ondersteunt MPP‑bestanden van Project 2000 tot de nieuwste releases, evenals XML en andere formaten.

**Q: Biedt Aspose.Tasks ondersteuning voor aangepaste valuta‑formaten?**  
A: Ja, je kunt aangepaste symbolen, decimalen en positionering definiëren om aan elke regionale eis te voldoen.

**Q: Kan ik Aspose.Tasks integreren met andere Java‑bibliotheken of -frameworks?**  
A: Zeker. De API is pure Java, dus werkt naadloos met Spring, Hibernate, Maven, Gradle en andere ecosystemen.

**Q: Waar kan ik extra ondersteuning of hulp vinden voor Aspose.Tasks?**  
A: Bezoek het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) voor community‑hulp, of raadpleeg de officiële documentatie voor gedetailleerde API‑referenties.

## Conclusie
Je weet nu **hoe je de valutacode java instelt**, hoe je **valuta**‑waarden wijzigt, en hoe je **valutasymbool** aanpast met Aspose.Tasks voor Java. Deze mogelijkheden stellen je in staat kostengegevens af te stemmen op wereldwijde teams, locale‑specifieke rapporten te genereren en je projectbestanden consistent te houden over grenzen heen.

---

**Laatst bijgewerkt:** 2026-02-07  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}