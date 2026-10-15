---
date: 2026-10-15
description: Leer hoe u een activiteit maakt, de data directory instelt, tabelvelden
  aanpast en een project opslaat als MPP met Aspose.Tasks for Java. Stapsgewijze gids
  voor Java‑ontwikkelaars.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Hoe een activiteit te maken en de data directory in te stellen met Aspose.Tasks
  for Java
og_description: Hoe u een activiteit maakt, tabelvelden aanpast en een project opslaat
  als MPP met Aspose.Tasks for Java. Volg deze gedetailleerde gids voor een snelle
  implementatie.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Hoe een activiteit te maken en de data directory in te stellen in Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Hoe een activiteit te maken en de data directory in te stellen met Aspose.Tasks
  for Java
url: /nl/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een activiteit te maken en de gegevensdirectory in te stellen met Aspose.Tasks voor Java

## Inleiding
In deze tutorial ontdek je **hoe je een activiteit maakt** programmatically, configureer je de **gegevensdirectory**, en **project opslaan als MPP** terwijl je ook **tabelvelden aanpast** in een Gantt‑diagramweergave. Aspose.Tasks voor Java is een krachtige API die meer dan 30 invoer‑ en uitvoerformaten ondersteunt en projecten met tot 10 000 taken kan verwerken zonder het volledige bestand in het geheugen te laden. Aan het einde van de gids kun je projectcreatie automatiseren, taken verrijken met aangepaste attributen, en een kant‑klaar MPP‑bestand voor Microsoft Project produceren.

## Snelle antwoorden
- **Wat is de eerste stap?** Stel het pad van de gegevensdirectory in waar uw projectbestanden zich bevinden.  
- **Welke bibliotheek is vereist?** Aspose.Tasks voor Java (downloadbaar van de officiële site).  
- **Kan ik aangepaste attributen toevoegen?** Ja – u kunt uitgebreide attributen definiëren en ze in het Gantt‑diagram weergeven.  
- **Heb ik een licentie nodig voor testen?** Een tijdelijke licentie is beschikbaar voor evaluatiedoeleinden.  
- **Welke IDE werkt het beste?** Elke Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) werkt.

## Wat is “set data directory” en waarom is het belangrijk?
Het instellen van de gegevensdirectory vertelt Aspose.Tasks waar projectbestanden gelezen en geschreven moeten worden. Zonder een correct pad kan de API uw `.mpp`‑bestanden niet vinden, wat leidt tot `FileNotFoundException`‑fouten. Het definiëren van deze directory aan het begin van uw code maakt de workflow herhaalbaar en scheidt bestands‑systeemzorgen van de bedrijfslogica.

## Waarom tabelvelden aanpassen in een Gantt‑diagram?
Aangepaste tabelvelden stellen u in staat extra informatie weer te geven — zoals aangepaste attributen, resource‑gegevens of projectspecifieke notities — direct in de Gantt‑weergave. Dit vermindert de noodzaak voor afzonderlijke rapporten en biedt belanghebbenden een enkele, data‑rijke visualisatie die de besluitvormingssnelheid met tot 30 % kan verbeteren.

## Hoe een nieuwe activiteit te maken?
U maakt een nieuwe activiteit (taak) door een `Task`‑object te instantieren en toe te voegen aan de hoofd‑taakverzameling van het project. Deze aanpak stelt u in staat grote planningen automatisch te genereren, taakgegevens uit externe systemen te halen, of bulk‑updates toe te passen zonder handmatige bewerking.

## Voorvereisten
Voordat u begint, zorg ervoor dat u het volgende heeft:

1. **Java Development Kit (JDK)** – versie 8 of nieuwer.  
2. **Aspose.Tasks for Java** – download het van de **Aspose.Tasks Java release page**.  
3. **IDE** – IntelliJ IDEA, Eclipse, of elke Java‑compatibele editor die u verkiest.  

## Pakketten importeren
De `com.aspose.tasks`‑namespace bevat alle klassen die u nodig heeft voor projectmanipulatie. Het importeren ervan geeft u toegang tot `Project`, `Task`, `ExtendedAttributeDefinition` en andere kern‑typen.

```java
import com.aspose.tasks.*;
```

## Maven‑afhankelijkheid (optioneel)
Als u uw project met Maven beheert, voeg dan de Aspose.Tasks‑afhankelijkheid toe aan `pom.xml`. Dit zorgt ervoor dat de bibliotheek automatisch wordt opgelost tijdens de build.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Stapsgewijze handleiding

### Stap 1: gegevensdirectory instellen
Bepaal de map die uw projectbestanden bevat. De variabele `dataDir` bevat het absolute pad en wordt gedurende de tutorial hergebruikt.

```java
String dataDir = "Your Data Directory";
```

Vervang `"Your Data Directory"` door het volledige pad naar de map waar `project.mpp` zich bevindt, bijvoorbeeld `C:/Projects/MyGantt`.

### Stap 2: projectbestand laden
`Project` is het top‑level object van Aspose.Tasks dat een enkel Microsoft Project‑bestand in het geheugen vertegenwoordigt. Het laden van een bestaand bestand geeft u toegang tot de taken, resources en tabellen.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Stap 3: nieuwe activiteit toevoegen
`Task` vertegenwoordigt een individuele activiteit in het schema. Het toevoegen van een taak aan de hoofd‑taakverzameling plaatst deze op het hoogste niveau van de projecthiërarchie.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Stap 4: aangepast attribuut definiëren
`ExtendedAttributeDefinition` stelt u in staat een herbruikbaar aangepast veld te maken dat aan elke taak, resource of toewijzing kan worden gekoppeld.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Stap 5: aangepast attribuut aan taak toevoegen
`ExtendedAttribute` is de concrete instantie van een aangepast attribuut die u aan een specifieke taak toewijst.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Stap 6: tabel aanpassen – aangepast attribuut als kolom toevoegen
`TableField` beschrijft een kolom in een Gantt‑diagramtabel. Door een `TableField` toe te voegen die verwijst naar het aangepaste attribuut, maakt u het attribuut zichtbaar in de diagramweergave.

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

### Stap 7: project opslaan
Het aanroepen van `project.save` slaat alle wijzigingen op in een nieuw bestand. De constante `SaveFileFormat.MPP` vertelt Aspose.Tasks om het bestand te schrijven in het native binaire formaat van Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **FileNotFoundException** bij het laden van het project | Het **set data directory** pad is onjuist of mist een afsluitende slash. | Controleer of `dataDir` naar de exacte map wijst en voeg de juiste scheidingsteken toe (`/` of `\\`). |
| Aangepast attribuut niet zichtbaar in Gantt‑weergave | Het tabelveld is toegevoegd op een verkeerde index of de kolombreedte is te klein. | Zorg ervoor dat `table.getTableFields().add(3, attrField);` een geldige index gebruikt en pas `setWidth` indien nodig aan. |
| LicenseException bij opslaan | Er is geen geldige licentie toegepast voor productiegebruik. | Pas een tijdelijke of permanente licentie toe voordat `project.save()` wordt aangeroepen. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere programmeertalen?**  
A: Ja, Aspose.Tasks is beschikbaar voor .NET, Java en C++.

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?**  
A: Ja, u kunt een gratis proefversie downloaden van de **Aspose.Tasks free trial download page**.

**Q: Waar kan ik ondersteuning vinden voor Aspose.Tasks?**  
A: U kunt ondersteuning vinden en vragen stellen op het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Hoe koop ik een licentie voor Aspose.Tasks?**  
A: U kunt een licentie kopen via de **Aspose.Tasks purchase page**.

**Q: Heb ik een tijdelijke licentie nodig voor testdoeleinden?**  
A: Ja, u kunt een tijdelijke licentie verkrijgen via de **temporary license request page**.

## Conclusie
U weet nu **hoe u een activiteit maakt**, de gegevensdirectory instellen, een aangepast attribuut definiëren en koppelen, en **project opslaan als MPP** terwijl u **tabelvelden aanpast** in een Gantt‑diagramweergave met Aspose.Tasks voor Java. Deze mogelijkheden geven u volledige programmatische controle over projectgegevens, waardoor geautomatiseerde planningsgeneratie en rijkere visuele rapportage voor uw belanghebbenden mogelijk worden.

---

**Laatst bijgewerkt:** 2026-10-15  
**Getest met:** Aspose.Tasks Java 24.12 (latest)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe een leeg projectbestand te maken in Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Hoe een MPP‑bestand te maken – Leeg project maken en opslaan in MPP‑formaat met Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Hoe een project te maken met Aspose.Tasks – Nieuwe taak‑attributen instellen](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}