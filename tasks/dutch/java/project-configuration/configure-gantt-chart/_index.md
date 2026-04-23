---
date: 2026-02-13
description: Leer hoe u een nieuwe activiteit maakt, de gegevensmap instelt en het
  project opslaat als MPP in Aspose.Tasks Java. Deze stapsgewijze handleiding behandelt
  ook het aanpassen van tabelvelden.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe een nieuwe activiteit te maken en de gegevensdirectory in te stellen Aspose.Tasks
url: /nl/java/project-configuration/configure-gantt-chart/
weight: 10
---

 to create new activity?" -> "Hoe een nieuwe activiteit te maken?"

Prerequisites: translate.

Import Packages: translate.

Step‑by‑Step Guide: translate.

Step headings: translate.

Replace text inside code placeholders? Not needed.

Common Issues and Solutions table: translate headers and content, but keep code terms.

FAQ: translate Q and A.

Conclusion: translate.

Also translate "Last Updated", "Tested With", "Author". Keep dates.

Make sure to keep markdown syntax.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een nieuwe activiteit te maken & gegevensdirectory instellen Aspose.Tasks

## Inleiding
In deze tutorial leer je **hoe je de gegevensdirectory instelt**, hoe je **een nieuwe activiteit maakt**, en hoe je **een project opslaat als MPP** terwijl je de Gantt MS Project Chart View configureert in Aspose.Tasks‑projecten met Java. Aspose.Tasks is een robuuste Java‑API waarmee je Microsoft Project‑bestanden programmatisch kunt manipuleren. Aan het einde van deze gids kun je **tabelvelden aanpassen**, de gegevensdirectory wijzigen, en je project visualiseren precies zoals je dat nodig hebt.

## Snelle antwoorden
- **Wat is de eerste stap?** Stel het pad van de gegevensdirectory in waar je projectbestanden zich bevinden.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (downloadbaar vanaf de officiële site).  
- **Kan ik aangepaste attributen toevoegen?** Ja – je kunt uitgebreide attributen definiëren en ze weergeven in het Gantt‑diagram.  
- **Heb ik een licentie nodig voor testen?** Een tijdelijke licentie is beschikbaar voor evaluatiedoeleinden.  
- **Welke IDE werkt het beste?** Elke Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) werkt.

## Wat is “set data directory” en waarom is het belangrijk?
Het instellen van de gegevensdirectory vertelt Aspose.Tasks waar projectbestanden gelezen en geschreven moeten worden. Zonder een correct pad kan de API je `.mpp`‑bestanden niet vinden, wat leidt tot FileNotFound‑fouten. Het definiëren van deze directory aan het begin van je code maakt de rest van de workflow schoon en herhaalbaar.

## Waarom tabelvelden aanpassen in een Gantt‑diagram?
Aangepaste tabelvelden laten je extra informatie tonen – zoals aangepaste attributen, resource‑data of projectspecifieke notities – direct in de Gantt‑weergave. Dit maakt het diagram informatie‑rijker voor belanghebbenden en vermindert de noodzaak om tussen meerdere rapporten te schakelen.

## Hoe een nieuwe activiteit te maken?
Een nieuwe activiteit (taak) maken is een van de kernbewerkingen bij het bouwen of bijwerken van een projectschema. Door taken programmatisch toe te voegen kun je de generatie van complexe projectplannen automatiseren, data uit andere systemen integreren, of bulk‑wijzigingen toepassen zonder handmatige bewerking.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK)** – elke recente versie (8+).  
2. **Aspose.Tasks Library** – download deze van [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, of een andere Java‑compatibele editor die je verkiest.

## Pakketten importeren
Importeer eerst de Aspose.Tasks‑namespace zodat je met de klassen kunt werken:

```java
import com.aspose.tasks.*;
```

## Stapsgewijze handleiding

### Stap 1: Gegevensdirectory instellen
Definieer de map die je projectbestanden bevat. Dit is de **set data directory**‑stap waar de tutorial zich op richt.

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
Voeg een nieuwe taak (activiteit) toe aan de root van het project. Dit toont **hoe je een nieuwe activiteit maakt** programmatisch.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Stap 4: Aangepast attribuut definiëren
Maak een definitie voor een aangepast attribuut die je later aan taken kunt koppelen.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Stap 5: Aangepast attribuut aan taak toevoegen
Ken het zojuist gedefinieerde attribuut toe aan de taak die je hebt aangemaakt.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Stap 6: Tabel aanpassen – **customize table fields**
Voeg het aangepaste attribuut toe als kolom in de Gantt‑tabel, met specificatie van breedte, titel en uitlijning.

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
Sla de wijzigingen op in een nieuw bestand dat geopend kan worden in Microsoft Project. Deze stap **slaat het project op als MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **FileNotFoundException** bij het laden van het project | Het **set data directory**‑pad is onjuist of mist een afsluitende slash. | Controleer of `dataDir` naar de exacte map wijst en voeg de juiste scheidingsteken (`/` of `\\`) toe. |
| Aangepast attribuut niet zichtbaar in Gantt‑weergave | Het tabelveld is op de verkeerde index toegevoegd of de kolombreedte is te klein. | Zorg ervoor dat `table.getTableFields().add(3, attrField);` een geldige index gebruikt en pas `setWidth` indien nodig aan. |
| LicenseException bij opslaan | Er is geen geldige licentie toegepast voor productiegebruik. | Pas een tijdelijke of permanente licentie toe voordat je `project.save()` aanroept. |

## Veelgestelde vragen

**V: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks is beschikbaar voor meerdere programmeertalen, waaronder .NET, Java en C++.

**V: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, je kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).

**V: Waar vind ik ondersteuning voor Aspose.Tasks?**  
A: Je kunt ondersteuning vinden en vragen stellen op het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15).

**V: Hoe kan ik een licentie voor Aspose.Tasks aanschaffen?**  
A: Je kunt een licentie kopen via [hier](https://purchase.aspose.com/buy).

**V: Heb ik een tijdelijke licentie nodig voor testdoeleinden?**  
A: Ja, je kunt een tijdelijke licentie verkrijgen via [hier](https://purchase.aspose.com/temporary-license/).

## Conclusie
Je hebt nu geleerd hoe je **de gegevensdirectory instelt**, **een nieuwe activiteit maakt**, een aangepast attribuut definieert en koppelt, en **het project opslaat als MPP** terwijl je **tabelvelden aanpast** in een Gantt‑diagramweergave met Aspose.Tasks voor Java. Deze stappen geven je volledige controle over hoe projectdata wordt weergegeven, waardoor je Gantt‑diagrammen informatie‑rijker en beter afgestemd op de behoeften van je belanghebbenden worden.

---

**Laatst bijgewerkt:** 2026-02-13  
**Getest met:** Aspose.Tasks Java 24.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}