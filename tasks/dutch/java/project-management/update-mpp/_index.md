---
date: 2026-06-25
description: Leer hoe u een taak kunt toevoegen en MPP-bestanden kunt bijwerken met
  Aspose.Tasks voor Java, een Java projectmanagementbibliotheek die u in staat stelt
  taak‑Microsoft Project‑bestanden te maken en een project op te slaan als MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Hoe een taak toe te voegen en een MPP-bestand bij te werken in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hoe een taak toe te voegen en een MPP-bestand bij te werken in Aspose.Tasks
url: /nl/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe taak toe te voegen en MPP-bestand bij te werken in Aspose.Tasks

## Introductie
In deze tutorial leer je **hoe taak toe te voegen** aan een bestaand Microsoft Project (MPP)-bestand en vervolgens het bijgewerkte schema opslaan met Aspose.Tasks for Java, een toonaangevende **java project management library**. Of je nu een aangepaste planner bouwt, bulkupdates automatiseert, of projectgegevens integreert in een groter systeem, de stap‑voor‑stap‑gids hieronder laat precies zien hoe je een project laadt, een nieuwe taak invoegt, de datums instelt en het resultaat opslaat als een nieuw MPP‑document.

## Snelle antwoorden
- **Wat betekent “how to add task” in deze context?** Het betekent programmatisch een nieuw werkitem maken binnen een bestaand MPP‑bestand.  
- **Welke bibliotheek voert de bewerking uit?** Aspose.Tasks for Java, een robuuste java project management library.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik het resultaat opslaan als MPP?** Ja—gebruik `project.save(..., SaveFileFormat.Mpp)` om **save project as mpp** op te slaan.  
- **Welke Java‑versie is vereist?** Java 8 of hoger.

## Wat is “how to add task” in een MPP‑bestand?
Een taak toevoegen betekent een nieuw werkitem in de projecthiërarchie invoegen, de start‑/einddatums definiëren en de wijziging terugschrijven naar het MPP‑bestand. Aspose.Tasks abstraheert de low‑level bestandsformaatdetails, zodat je je kunt concentreren op de bedrijfslogica terwijl automatisch resource‑toewijzingen, kalenders en afhankelijkheidsberekeningen worden afgehandeld. Het werkt ook gerelateerde toewijzingen bij en herberekent het projectschema om consistentie tussen afhankelijke taken te behouden.

## Waarom Aspose.Tasks voor Java gebruiken?
- **Volledige compatibiliteit**: Ondersteunt 100 % van de functies van Microsoft Project 2007‑2021 (meer dan 150 taaktypen en 200 resource‑velden).  
- **Zero‑dependency**: Geen COM, Office of native bibliotheken nodig—pure Java‑API draait overal waar de JRE draait.  
- **Rijke functionaliteit**: Bevat taakkoppelingen, resource‑toewijzing, aangepaste velden en ingebouwde rapportage.  
- **Hoge prestaties**: Verwerkt projecten met tot 10.000 taken met minder dan 200 MB RAM, waardoor het ideaal is voor server‑side automatisering.

## Voorvereisten
1. **Java Development Environment** – JDK 8+ geïnstalleerd en geconfigureerd.  
2. **Aspose.Tasks for Java** – Download van de [download page](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – Vertrouwd met klassen, objecten en datumafhandeling.  

## Importeer pakketten
Eerst importeer je de klassen die je nodig hebt. Hiermee krijg je toegang tot projectmanipulatie, taak‑eigenschappen en datumafhandeling.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` vertegenwoordigt een Microsoft Project‑bestand dat in het geheugen is geladen. `SaveFileFormat` somt de formaten op waarnaar je kunt opslaan, zoals MPP of PDF. `Task` modelleert een individueel werkitem binnen de projecthiërarchie. `Tsk` biedt constanten voor taakvelden die worden gebruikt bij het instellen of ophalen van waarden. `Calendar` biedt datum‑tijd‑hulpmiddelen voor het definiëren van schema's.

## Stap 1: Definieer gegevensdirectory
```java
String dataDir = "Your Data Directory";
```  
Vervang `"Your Data Directory"` door het absolute pad waar je bron‑MPP‑bestand zich bevindt.

## Stap 2: Lees bestaand project
De `Project`‑klasse is het kernobject van Aspose.Tasks dat een Microsoft Project‑bestand in het geheugen vertegenwoordigt.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
De constructor laadt **SampleMSP2010.mpp**, waardoor je een volledig manipuleerbaar objectmodel krijgt.

## Stap 3: Maak een nieuwe taak (how to add task)
De `Task`‑klasse vertegenwoordigt een individueel werkitem binnen de projecthiërarchie.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Deze regel **creates task in mpp** door een kind met de naam *Task1* toe te voegen aan de root‑taak.

## Stap 4: Stel start‑ en einddatums in
De `Calendar`‑klasse biedt datum‑tijd‑hulpmiddelen; maanden zijn nul‑gebaseerd (bijv. `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Hier definiëren we het schema voor de nieuw toegevoegde taak. Pas de datums aan om overeen te komen met je projectschema.

## Stap 5: Sla het project op (save project as mpp)
`SaveFileFormat.Mpp` vertelt Aspose.Tasks het bestand terug te schrijven in het native Microsoft Project‑formaat.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Het bijgewerkte project, nu met de nieuwe taak, wordt opgeslagen als **AfterLinking.mpp**.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Bestand niet gevonden** | Controleer of `dataDir` eindigt op een pad‑scheidingsteken (`/` of `\\`) en of de bestandsnaam correct is. |
| **Onjuiste datums** | Onthoud dat `Calendar`‑maanden nul‑gebaseerd zijn; `Calendar.JULY` is correct voor juli. |
| **Licentie‑uitzondering** | Installeer een geldige Aspose.Tasks‑licentie voordat je een API‑aanroep doet om evaluatiewatermerken te vermijden. |

## Veelgestelde vragen
**Q: Hoe voeg ik meerdere taken tegelijk toe?**  
A: Loop over een verzameling taaknamen en herhaal het “create task”‑blok binnen de lus.

**Q: Kan ik aangepaste velden instellen voor de nieuwe taak?**  
A: Ja—gebruik `task.set(Tsk.CUSTOM_FIELD_x, value)` waarbij *x* de veld‑index is.

**Q: Is het mogelijk een bestaande taak als sjabloon te kopiëren?**  
A: Clone de bron‑taak (`Task cloned = sourceTask.clone();`) en voeg deze vervolgens toe aan de gewenste ouder.

**Q: Wat als ik een bestaande taak moet bijwerken in plaats van een nieuwe toe te voegen?**  
A: Haal de taak op via ID (`Task existing = project.getRootTask().getChildren().getById(id);`) en wijzig de eigenschappen.

**Q: Ondersteunt Aspose.Tasks het opslaan naar andere formaten zoals PDF of PNG?**  
A: Ja—gebruik `project.save("output.pdf", SaveFileFormat.Pdf);` of `SaveFileFormat.Png` voor visuele weergaven.

**Laatst bijgewerkt:** 2026-06-25  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe een MPP‑bestand te maken – Maak & sla leeg project op in MPP‑formaat met Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Hoe een project te maken – Stel nieuwe taak‑attributen in met Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Taaklijst maken Java – MS Project-baseline met Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}