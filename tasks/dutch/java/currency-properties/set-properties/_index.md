---
date: 2025-12-04
description: Leer hoe u valuta instelt in Aspose.Tasks Java‑projecten, inclusief hoe
  u valuta en het valutateken in Java wijzigt. Beheer Microsoft Project‑bestanden
  moeiteloos.
language: nl
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Hoe valuta instellen in Aspose.Tasks‑projecten – Java‑gids
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe valuta in te stellen in Aspose.Tasks‑projecten – Java‑gids

## Introductie
In deze tutorial leer je **hoe je valuta instelt** voor een Microsoft Project‑bestand met behulp van de Aspose.Tasks Java‑API. Of je nu de *valuta moet wijzigen* voor internationale teams of het *valutasymbool* in Java moet aanpassen, de onderstaande stappen begeleiden je door het proces met duidelijke uitleg en kant‑klaar code.

## Snelle antwoorden
- **Welke bibliotheek is vereist?** Aspose.Tasks for Java.  
- **Kan ik het valutasymbool wijzigen?** Ja – gebruik `CurrencySymbolPositionType` en `Prj.CURRENCY_SYMBOL`.  
- **Welke bestandsformaten worden ondersteund?** XML, MPP en vele andere via `SaveFileFormat`.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.  
- **Hoe lang duurt de implementatie?** Ongeveer 5‑10 minuten voor een basisopstelling.

## Wat is “valuta” in een Project‑bestand?
De valuta van een Project bepaalt hoe kostenwaarden worden weergegeven – code (bijv. `AUD`), aantal decimalen, symbool (`$`) en de positie van het symbool. Het instellen van deze eigenschappen zorgt ervoor dat elk kosten‑gerelateerd veld (resource‑tarieven, taak‑budgetten, enz.) het juiste monetaire formaat toont voor je doelgroep.

## Waarom Aspose.Tasks gebruiken om valuta te wijzigen?
- **Geen Microsoft Project‑installatie nodig** – bewerk bestanden op elke server.  
- **Volledige API‑dekking** – alle valuta‑gerelateerde velden zijn beschikbaar via `Prj`‑constanten.  
- **Cross‑platform** – werkt op Windows, Linux en macOS met elke Java‑compatibele IDE.  
- **Hoge prestaties** – verwerk grote projectbestanden snel en betrouwbaar.

## Voorvereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – versie 8 of hoger.  
2. **Aspose.Tasks for Java** – download de nieuwste JAR van de [Aspose.Tasks downloadpagina](https://releases.aspose.com/tasks/java/).  
3. **Een IDE** – Eclipse, IntelliJ IDEA of een andere editor naar keuze.  
4. **Een schrijfbare map** – waar het gegenereerde projectbestand wordt opgeslagen.

## Pakketten importeren
Importeer eerst de klassen die toegang geven tot project‑eigenschappen en bestandsverwerking.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Stapsgewijze handleiding

### Stap 1: Definieer de gegevensdirectory
Geef de map op die je bronbestanden bevat en waar de output wordt weggeschreven.

```java
String dataDir = "Your Data Directory";
```

### Stap 2: Maak een nieuw Project‑object aan
Instantieer een nieuw `Project`‑object. Dit object vertegenwoordigt een Microsoft Project‑bestand in het geheugen.

```java
Project project = new Project();
```

### Stap 3: Stel valutaproperties in
Hier stel je **hoe je valuta instelt** details in zoals code, decimalen, symbool en symboolpositie.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** Als je **valuta wilt wijzigen** voor een bestaand project, laad dan eerst het bestand met `new Project("file.mpp")` voordat je de bovenstaande instellingen toepast.

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
| **`NullPointerException` bij `project.save`** | `dataDir` is geen geldig pad of heeft geen schrijfrechten. | Zorg dat de directory bestaat en dat je Java‑proces schrijfrechten heeft. |
| **Valutasymbool wordt niet weergegeven** | De symboolpositie is onjuist ingesteld voor je locale. | Gebruik `CurrencySymbolPositionType.Before` als het symbool vóór het bedrag moet staan. |
| **Projectbestand opent niet in MS Project** | Opslaan in een ouder formaat met incompatibele instellingen. | Sla op met `SaveFileFormat.MPP` voor volledige compatibiliteit met recente MS Project‑versies. |

## Veelgestelde vragen

**V: Kan ik meerdere valuta’s in één project instellen met Aspose.Tasks?**  
A: Ja, Aspose.Tasks maakt het mogelijk om meerdere valuta’s binnen één projectbestand te beheren door valutaproperties per resource of per taak in te stellen.

**V: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Absoluut. De bibliotheek ondersteunt MPP‑bestanden van Project 2000 tot de nieuwste releases, evenals XML en andere formaten.

**V: Biedt Aspose.Tasks ondersteuning voor aangepaste valutavormen?**  
A: Ja, je kunt aangepaste symbolen, decimalen en positionering definiëren om aan elke regionale eis te voldoen.

**V: Kan ik Aspose.Tasks integreren met andere Java‑bibliotheken of -frameworks?**  
A: Zeker. De API is pure Java, dus hij werkt naadloos met Spring, Hibernate, Maven, Gradle en andere ecosystemen.

**V: Waar vind ik extra ondersteuning of hulp voor Aspose.Tasks?**  
A: Bezoek het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) voor community‑ondersteuning, of raadpleeg de officiële documentatie voor gedetailleerde API‑referenties.

## Conclusie
Je weet nu **hoe je valuta instelt**, hoe je **valuta wijzigt** en hoe je **valutasymbool in Java** aanpast met Aspose.Tasks for Java. Deze mogelijkheden stellen je in staat om kostengegevens af te stemmen op wereldwijde teams, locale‑specifieke rapporten te genereren en je projectbestanden consistent te houden over grenzen heen.

---

**Laatst bijgewerkt:** 2025-12-04  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}