---
date: 2025-12-28
description: Leer hoe u taken kunt toevoegen en MPP‑bestanden kunt bijwerken met Aspose.Tasks
  for Java, een Java‑projectmanagementbibliotheek. Volg onze stapsgewijze handleiding
  om een taak in MPP te maken en het project als MPP op te slaan.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe een taak toe te voegen en een MPP‑bestand bij te werken in Aspose.Tasks
url: /nl/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een taak toe te voegen en een MPP-bestand bij te werken in Aspose.Tasks

## Introductie
In deze tutorial laten we u zien **hoe u een taak kunt toevoegen** en een MPP-bestand bijwerken met Aspose.Tasks for Java, een toonaangevende **java projectmanagementbibliotheek**. Of u nu een aangepaste planner bouwt of bestaande projectplannen programmatisch moet wijzigen, deze gids leidt u door elke stap — van het laden van het bestand tot het opslaan van de wijzigingen als een nieuw MPP-document.

## Snelle antwoorden
- **Wat betekent “how to add task” in deze context?** Het verwijst naar het programmatisch aanmaken van een nieuwe taak binnen een bestaand Microsoft Project (MPP)-bestand.  
- **Welke bibliotheek voert de bewerking uit?** Aspose.Tasks for Java, een robuuste java projectmanagementbibliotheek.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik het resultaat opslaan als MPP?** Ja — gebruik `project.save(..., SaveFileFormat.Mpp)` om **project op te slaan als mpp**.  
- **Welke Java-versie is vereist?** Java 8 of hoger.

## Wat is “how to add task” in een MPP-bestand?
Een taak toevoegen betekent een nieuw werkitem in de projecthiërarchie invoegen, de start-/einddatums definiëren en de wijziging terug opslaan in het MPP-bestand. Aspose.Tasks abstraheert de low‑level bestandsformaatdetails, zodat u zich kunt concentreren op de bedrijfslogica.

## Waarom Aspose.Tasks for Java gebruiken?
- **Volledige compatibiliteit** met Microsoft Project 2007‑2021 bestanden.  
- **Geen COM- of Office‑installatie** vereist — pure Java API.  
- **Rijke functionaliteit**: taakkoppelingen, resource‑toewijzing, aangepaste velden, en meer.  
- **Hoge prestaties** voor grote projectbestanden, waardoor het ideaal is voor server‑side automatisering.

## Vereisten
1. **Java-ontwikkelomgeving** – JDK 8+ geïnstalleerd en geconfigureerd.  
2. **Aspose.Tasks for Java** – Download van de [downloadpagina](https://releases.aspose.com/tasks/java/).  
3. **Basiskennis van Java** – Vertrouwdheid met klassen, objecten en datumafhandeling.  

## Importer pakketten
Eerst importeert u de klassen die u nodig heeft. Hiermee krijgt u toegang tot projectmanipulatie, taak‑eigenschappen en datumafhandeling.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Stap 1: Definieer gegevensdirectory
```java
String dataDir = "Your Data Directory";
```
Vervang `"Your Data Directory"` door het absolute pad waar uw bron‑MPP‑bestand zich bevindt.

## Stap 2: Lees bestaand project
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
De `Project`‑constructor laadt **SampleMSP2010.mpp**, waardoor u een bewerkbaar objectmodel krijgt.

## Stap 3: Maak een nieuwe taak (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Deze regel **maakt taak in mpp** door een kind met de naam *Task1* toe te voegen aan de hoofdtaak.

## Stap 4: Stel start‑ en einddatums in
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Hier definiëren we het schema voor de nieuw toegevoegde taak. Pas de datums aan zodat ze overeenkomen met uw projecttijdlijn.

## Stap 5: Sla het project op (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Het bijgewerkte project, nu met de nieuwe taak, wordt opgeslagen als **AfterLinking.mpp**.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Bestand niet gevonden** | Controleer of `dataDir` eindigt op een pad‑scheidingsteken (`/` of `\\`) en of de bestandsnaam correct is. |
| **Onjuiste datums** | Onthoud dat de maanden van `Calendar` nul‑gebaseerd zijn; `Calendar.JULY` is correct voor juli. |
| **Licentie‑exceptie** | Installeer een geldige Aspose.Tasks‑licentie voordat u een API aanroept om evaluatiewatermerken te vermijden. |

## FAQ's
### Q: Kan Aspose.Tasks for Java complexe projectstructuren aan?
A: Ja, Aspose.Tasks for Java biedt robuuste functies om complexe projectstructuren efficiënt te verwerken.  
### Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks for Java?
A: Ja, u kunt een gratis proefversie downloaden van de [website](https://releases.aspose.com/).  
### Q: Ondersteunt Aspose.Tasks for Java verschillende versies van Microsoft Project‑bestanden?
A: Absoluut, Aspose.Tasks for Java ondersteunt verschillende versies van Microsoft Project‑bestanden, inclusief MPP-, MPT- en XML‑formaten.  
### Q: Kan ik tijdelijke licenties krijgen voor Aspose.Tasks for Java?
A: Ja, tijdelijke licenties zijn beschikbaar voor testdoeleinden. U kunt ze verkrijgen via de [tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/).  
### Q: Waar kan ik hulp of ondersteuning krijgen voor Aspose.Tasks for Java?
A: U kunt het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) bezoeken voor hulp of vragen.

## Veelgestelde vragen
**Q: Hoe voeg ik meerdere taken tegelijk toe?**  
A: Loop over een collectie van taaknamen en herhaal het “create task”‑blok binnen de lus.

**Q: Kan ik aangepaste velden instellen voor de nieuwe taak?**  
A: Ja — gebruik `task.set(Tsk.CUSTOM_FIELD_x, value)` waarbij *x* de veld‑index is.

**Q: Is het mogelijk om een bestaande taak als sjabloon te kopiëren?**  
A: Clone de bron‑taak (`Task cloned = sourceTask.clone();`) en voeg deze vervolgens toe aan de gewenste ouder.

**Q: Wat als ik een bestaande taak moet bijwerken in plaats van een nieuwe toe te voegen?**  
A: Haal de taak op via ID (`Task existing = project.getRootTask().getChildren().getById(id);`) en wijzig de eigenschappen.

**Q: Ondersteunt Aspose.Tasks het opslaan naar andere formaten zoals PDF of PNG?**  
A: Ja — gebruik `project.save("output.pdf", SaveFileFormat.Pdf);` of `SaveFileFormat.Png` voor visuele weergaven.

---

**Laatst bijgewerkt:** 2025-12-28  
**Getest met:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}