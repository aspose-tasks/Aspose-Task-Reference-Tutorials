---
date: 2025-12-28
description: Leer hoe u Primavera‑XML‑bestanden kunt lezen in MS Project met Aspose.Tasks
  voor Java, waardoor naadloze gegevensuitwisseling en verbeterd projectbeheer mogelijk
  worden.
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe Primavera‑XML inlezen in MS‑Project met Aspose.Tasks voor Java
url: /nl/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lees MS Project van Primavera met Aspose.Tasks voor Java

## Inleiding
In modern projectmanagement is het verplaatsen van gegevens tussen tools zonder verlies van details essentieel. Deze tutorial laat u zien **hoe u primavera xml**-bestanden kunt lezen en importeren in Microsoft Project met behulp van Aspose.Tasks voor Java. Aan het einde kunt u Primavera‑specifieke taak‑eigenschappen extraheren, waardoor cross‑platformanalyse eenvoudig en efficiënt wordt.

## Snelle antwoorden
- **Wat doet Aspose.Tasks voor Java?** Het leest en schrijft vele projectbestandsformaten, waaronder Primavera XML en Microsoft Project (MPP).  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een licentie is vereist voor productiegebruik.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger is vereist.  
- **Kan ik andere formaten lezen naast Primavera XML?** Ja, Aspose.Tasks ondersteunt MPP, XML en nog veel meer.  
- **Is deze aanpak geschikt voor grote bedrijfsprojecten?** Absoluut—Aspose.Tasks is ontworpen voor high‑performance, enterprise‑grade scenario's.

## Wat is read primavera xml?
Het lezen van Primavera XML betekent het parseren van de XML-export van Oracle Primavera P6 om projectplanningsgegevens—taken, duur, resources en Primavera‑specifieke attributen—op te halen, zodat deze door andere tools zoals Microsoft Project kan worden gebruikt.

## Waarom Aspose.Tasks voor Java gebruiken om primavera xml te lezen?
- **Volledige nauwkeurigheid:** Alle Primavera‑specifieke eigenschappen blijven behouden.  
- **Geen externe afhankelijkheden:** Pure Java‑bibliotheek, geen Primavera‑ of MS Project‑installaties nodig.  
- **Schaalbaar:** Verwerkt grote projecten met duizenden taken efficiënt.  
- **Cross‑platform:** Werkt op Windows, Linux en macOS.

## Voorvereisten
1. **Java Development Kit (JDK)** – Java 8 of nieuwer geïnstalleerd.  
2. **Aspose.Tasks for Java** – Download het vanaf [here](https://releases.aspose.com/tasks/java/).  
3. Een Primavera XML‑bestand (bijv. `PrimaveraProject.xml`) dat u wilt lezen.

## Hoe lees ik een projectbestand java met Aspose.Tasks?
Hieronder vindt u een stapsgewijze handleiding die u door het hele proces leidt.

### Import pakketten
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Stap 1: Stel de gegevensdirectory in
```java
String dataDir = "Your Data Directory";
```
Vervang `"Your Data Directory"` door het absolute pad waar uw Primavera XML‑bestand zich bevindt.

### Stap 2: Lees project van Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Werk `"PrimaveraProject.xml"` bij met de werkelijke bestandsnaam van uw Primavera‑export.

### Stap 3: Doorloop taken en haal Primavera‑specifieke eigenschappen op
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Deze lus drukt de Primavera‑specifieke details van elke taak af, zoals Activity ID, WBS‑volgorde, duurtypes, kostenverdeling en meer.

## Veelvoorkomende problemen en oplossingen
- **Fout: bestand niet gevonden:** Controleer of `dataDir` eindigt op een pad‑scheidingsteken (`/` of `\\`) en of de XML‑bestandsnaam correct is.  
- **Ontbrekende Primavera‑eigenschappen:** Zorg ervoor dat de XML is geëxporteerd met alle vereiste velden; oudere Primavera‑versies kunnen sommige attributen weglaten.  
- **Prestaties bij grote bestanden:** Overweeg de JVM‑heap‑grootte te verhogen (`-Xmx2g` of hoger) voor projecten met tienduizenden taken.

## Veelgestelde vragen
### V: Kan ik de Primavera‑specifieke eigenschappen van taken wijzigen met Aspose.Tasks voor Java?
A: Ja, Aspose.Tasks voor Java biedt API's om Primavera‑specifieke eigenschappen van taken naar behoefte te wijzigen.

### V: Ondersteunt Aspose.Tasks voor Java het lezen van andere projectbestandsformaten?
A: Ja, Aspose.Tasks voor Java ondersteunt het lezen van verschillende projectbestandsformaten, waaronder MPP, XML en Primavera XML.

### V: Is Aspose.Tasks voor Java geschikt voor enterprise‑level projectmanagement applicaties?
A: Absoluut, Aspose.Tasks voor Java biedt robuuste functies en schaalbaarheid, waardoor het geschikt is voor enterprise‑level projectmanagementapplicaties.

### V: Kan ik resource‑informatie extraheren uit Primavera‑projecten met Aspose.Tasks voor Java?
A: Ja, Aspose.Tasks voor Java maakt het mogelijk om resource‑informatie samen met taakdetails uit Primavera‑projecten te extraheren.

### V: Waar kan ik extra ondersteuning of documentatie vinden voor Aspose.Tasks voor Java?
A: U kunt uitgebreide documentatie en toegang tot forums voor ondersteuning vinden op de pagina [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## Conclusie
U heeft nu geleerd **hoe u primavera xml**‑bestanden kunt lezen en gedetailleerde taak‑informatie kunt ophalen in een Java‑applicatie met behulp van Aspose.Tasks. Deze mogelijkheid overbrugt de kloof tussen Primavera en Microsoft Project, geeft u volledige zichtbaarheid over platforms en verhoogt de algehele efficiëntie van projectmanagement.

---

**Laatst bijgewerkt:** 2025-12-28  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}