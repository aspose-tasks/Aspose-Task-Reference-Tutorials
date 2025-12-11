---
date: 2025-12-09
description: Leer hoe u de gegevensmap instelt en de Gantt-diagramweergave configureert
  in Aspose.Tasks met Java. Deze gids laat ook zien hoe u tabelvelden aanpast en Gantt-diagram‑Java‑projecten
  stap voor stap configureert.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Stel gegevensmap in voor Gantt-diagramweergave in Aspose.Tasks
url: /nl/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Stel Data Directory in voor Gantt-diagramweergave in Aspose.Tasks

## Introductie
In deze tutorial leer je **hoe je de data directory instelt** en de Gantt MS Project Chart View configureert in Aspose.Tasks‑projecten met Java. Aspose.Tasks is een robuuste Java‑API waarmee je Microsoft Project‑bestanden programmatisch kunt manipuleren. Aan het einde van deze gids kun je **tabelvelden aanpassen**, de data directory wijzigen en je project visualiseren precies zoals je het nodig hebt.

## Snelle Antwoorden
- **Wat is de eerste stap?** Stel het pad van de data directory in waar uw projectbestanden zich bevinden.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (downloadbaar van de officiële site).  
- **Kan ik aangepaste attributen toevoegen?** Ja – u kunt uitgebreide attributen definiëren en ze weergeven in het Gantt‑diagram.  
- **Heb ik een licentie nodig voor testen?** Een tijdelijke licentie is beschikbaar voor evaluatiedoeleinden.  
- **Welke IDE werkt het beste?** Elke Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) werkt.

## Wat is “set data directory” en waarom is het belangrijk?
Het instellen van de data directory vertelt Aspose.Tasks waar projectbestanden gelezen en geschreven moeten worden. Zonder een correct pad kan de API uw `.mpp`‑bestanden niet vinden, wat leidt tot FileNotFound‑fouten. Het definiëren van deze directory aan het begin van uw code maakt de rest van de workflow schoon en herhaalbaar.

## Waarom tabelvelden aanpassen in een Gantt‑diagram?
Aangepaste tabelvelden laten u extra informatie tonen – zoals aangepaste attributen, resource‑data of projectspecifieke notities – direct in de Gantt‑weergave. Dit maakt het diagram informatie‑rijker voor belanghebbenden en vermindert de noodzaak om tussen meerdere rapporten te schakelen.

## Voorvereisten
Voordat u begint, zorg ervoor dat u het volgende heeft:

1. **Java Development Kit (JDK)** – elke recente versie (8+).  
2. **Aspose.Tasks Library** – download deze van [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, of elke Java‑compatibele editor die u verkiest.

## Pakketten importeren
Importeer eerst de Aspose.Tasks‑namespace zodat u met de klassen kunt werken:

```java
import com.aspose.tasks.*;
```

## Stapsgewijze gids

### Stap 1: Data Directory instellen
Definieer de map die uw projectbestanden bevat. Dit is de **set data directory**‑stap waar de tutorial zich op richt.

```java
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het absolute pad naar de map waar `project.mpp` is opgeslagen.

### Stap 2: Projectbestand laden
Maak een `Project`‑instantie door een bestaand Microsoft Project‑bestand te laden.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Stap 3: Nieuwe activiteit toevoegen
Voeg een nieuwe taak (activiteit) toe aan de root van het project.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Stap 4: Aangepast attribuut definiëren
Maak een definitie voor een aangepast attribuut die later aan taken kan worden gekoppeld.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Stap 5: Aangepast attribuut toevoegen aan taak
Wijs het nieuw gedefinieerde attribuut toe aan de taak die u hebt aangemaakt.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Stap 6: Tabel aanpassen – **customize table fields**
Voeg het aangepaste attribuut toe als kolom in de Gantt‑diagramtabel, met specificatie van breedte, titel en uitlijning.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Stap 7: Project opslaan
Sla de wijzigingen op in een nieuw bestand dat geopend kan worden in Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **FileNotFoundException** bij het laden van het project | Het **set data directory**‑pad is onjuist of mist een afsluitende slash. | Controleer of `dataDir` naar de exacte map wijst en voeg de juiste scheidingsteken toe (`/` of `\\`). |
| Aangepast attribuut niet zichtbaar in Gantt‑weergave | Het tabelveld is op de verkeerde index toegevoegd of de kolombreedte is te klein. | Zorg ervoor dat `table.getTableFields().add(3, attrField);` een geldige index gebruikt en pas `setWidth` indien nodig aan. |
| LicenseException bij opslaan | Er is geen geldige licentie toegepast voor productiegebruik. | Pas een tijdelijke of permanente licentie toe voordat u `project.save()` aanroept. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks is beschikbaar voor meerdere programmeertalen, waaronder .NET, Java en C++.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, u kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning vinden voor Aspose.Tasks?**  
A: U kunt ondersteuning vinden en vragen stellen op het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Hoe kan ik een licentie voor Aspose.Tasks aanschaffen?**  
A: U kunt een licentie kopen via [hier](https://purchase.aspose.com/buy).

**Q: Heb ik een tijdelijke licentie nodig voor testdoeleinden?**  
A: Ja, u kunt een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie
U heeft nu geleerd hoe u **data directory instelt**, een nieuwe activiteit toevoegt, een aangepast attribuut definieert en koppelt, en **tabelvelden aanpast** in een Gantt‑diagramweergave met Aspose.Tasks voor Java. Deze stappen geven u volledige controle over hoe projectdata wordt weergegeven, waardoor uw Gantt‑diagrammen informatie‑rijker en beter afgestemd zijn op de behoeften van uw belanghebbenden.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}