---
date: 2025-12-21
description: Leer hoe u SVG maakt van MPP‑bestanden in Java en het project opslaat
  als SVG met behulp van de Aspose.Tasks‑bibliotheek. Stapsgewijze handleiding met
  codevoorbeelden.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe maak je een SVG van een MPP in Java met Aspose.Tasks
url: /nl/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe SVG te maken van MPP in Java

## Inleiding
In deze tutorial leer je hoe je **SVG van MPP**‑bestanden maakt met Aspose.Tasks voor Java. Het converteren van een Microsoft Project‑bestand (MPP) naar scalable vector graphics (SVG) stelt je in staat om hoogwaardige, resolutie‑onafhankelijke diagrammen direct in webpagina’s, rapporten of dashboards te embedden. We lopen de benodigde setup door, tonen de exacte code die je nodig hebt, en leggen elke stap uit zodat je vol vertrouwen **project kunt opslaan als SVG** in je eigen applicaties.

## Snelle antwoorden
- **Wat betekent “create SVG from MPP”?**  
  Het zet een Microsoft Project‑bestand (.mpp) om in een SVG‑afbeelding die in elke browser kan worden weergegeven zonder kwaliteitsverlies.  
- **Welke bibliotheek voert de conversie uit?**  
  Aspose.Tasks voor Java biedt een één‑regelige `save`‑methode om de conversie uit te voeren.  
- **Heb ik een licentie nodig?**  
  Een tijdelijke licentie is vereist voor commercieel gebruik; een gratis proefversie is beschikbaar.  
- **Wat zijn de vereisten?**  
  Java JDK 8+ en de Aspose.Tasks voor Java JAR.  
- **Hoe lang duurt de conversie?**  
  Meestal minder dan een seconde voor standaard projectbestanden.

## Wat is “create SVG from MPP”?
Een SVG maken van een MPP‑bestand betekent dat je de visuele weergave van een projectschema—taken, tijdlijnen en resources—exporteert naar het Scalable Vector Graphics‑formaat. SVG is XML‑gebaseerd, lichtgewicht en schaalt perfect op high‑resolution displays.

## Waarom Aspose.Tasks gebruiken om project op te slaan als SVG?
- **Geen Microsoft Project‑installatie vereist** – de bibliotheek werkt onafhankelijk.  
- **Volledige nauwkeurigheid** – grafieken, Gantt‑balken en mijlpalen behouden hun stijlen.  
- **Cross‑platform** – voer de code uit op Windows, Linux of macOS.  
- **Eenvoudige integratie** – één‑regelige API‑aanroep past natuurlijk in bestaande Java‑pijplijnen.

## Vereisten
- **Java Development Kit (JDK)** – versie 8 of hoger. Download van de Oracle‑website.  
- **Aspose.Tasks voor Java** – verkrijg de bibliotheek van de officiële downloadpagina **[here](https://releases.aspose.com/tasks/java/)**.  

## Importeer pakketten
Eerst importeer je de klassen die je nodig hebt. Het import‑blok blijft ongewijzigd.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Stap 1: Definieer de gegevensmap
Geef aan waar je bron‑MPP‑bestand zich bevindt en waar de SVG moet worden weggeschreven.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Gebruik een absoluut pad of een pad relatief ten opzichte van de resources‑map van je project om een `FileNotFoundException` te voorkomen.

## Stap 2: Laad het MPP‑bestand
Maak een `Project`‑instantie door het bestaande Microsoft Project‑bestand te laden.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Deze regel leest *HomeMovePlan.mpp* uit de map die je eerder hebt gedefinieerd.

## Stap 3: Sla het project op als SVG
Nu kun je **project opslaan als SVG** met één enkele opdracht.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

De methode schrijft `project5.svg` naar dezelfde directory. De resulterende SVG kan in elke moderne browser worden geopend of direct in HTML worden ingebed.

## Veelvoorkomende problemen en oplossingen
| Issue | Reason | Fix |
|-------|--------|-----|
| **Bestand niet gevonden** | Onjuiste `dataDir`‑pad | Controleer of de directory‑string eindigt met een scheidingsteken (`/` of `\\`). |
| **Lege SVG‑output** | Project geladen zonder weergaven | Zorg ervoor dat het MPP‑bestand een Gantt‑chart‑weergave bevat voordat u opslaat. |
| **Licentie‑exception** | Geen geldige licentie toegepast | Pas een tijdelijke licentie toe met `License.setLicense("path/to/license.xml")` voordat u `save` aanroept. |

## Veelgestelde vragen

**Q: Is Aspose.Tasks voor Java compatibel met alle versies van Microsoft Project‑bestanden?**  
A: Ja, het ondersteunt MPP, MPT en XML‑formaten van oudere tot de nieuwste Project‑releases.

**Q: Kan ik het uiterlijk van de SVG‑output aanpassen?**  
A: Absoluut. Gebruik `SvgOptions` om lettertypen, kleuren en lay‑outopties in te stellen voordat u `save` aanroept.

**Q: Vereist Aspose.Tasks voor Java een licentie voor commercieel gebruik?**  
A: Ja, een geldige licentie is vereist voor productie. Je kunt een tijdelijke licentie verkrijgen **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Kan ik Aspose.Tasks voor Java eerst uitproberen voordat ik koop?**  
A: Ja, een gratis proefversie is beschikbaar **[here](https://purchase.aspose.com/buy)**.

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?**  
A: Bezoek het community‑forum **[here](https://forum.aspose.com/c/tasks/15)** om vragen te stellen en feedback te delen.

## Conclusie
Je weet nu hoe je **SVG van MPP**‑bestanden maakt in Java en efficiënt **project opslaat als SVG** met Aspose.Tasks. Deze mogelijkheid stelt je in staat om rijke projectvisualisaties te integreren in webportalen, rapportagedashboards of elke plek waar schaalbare graphics nodig zijn. Experimenteer met `SvgOptions` om de output fijn af te stemmen, en je hebt een krachtig hulpmiddel in je ontwikkel‑toolkit.

---

**Laatst bijgewerkt:** 2025-12-21  
**Getest met:** Aspose.Tasks voor Java 24.10  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}