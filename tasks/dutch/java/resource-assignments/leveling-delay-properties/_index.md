---
date: 2026-06-05
description: Leer hoe u een resource assignment maakt met Aspose.Tasks for Java, resources
  toevoegt aan een project en leveling delay properties beheert.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Beheer Leveling Delay Properties voor Resource Assignments in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Maak Resource Assignment met Aspose.Tasks for Java
url: /nl/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak resource‑toewijzing met Aspose.Tasks voor Java

In deze uitgebreide gids leer je **how to create resource assignment aspotasks** gebruiken met de Aspose.Tasks bibliotheek voor Java. Of je nu een aangepaste planningsengine bouwt, bulk‑projectupdates automatiseert, of gewoon Microsoft Project‑bestanden moet manipuleren zonder de desktop‑applicatie, het beheersen van deze stappen stelt je in staat om je projectgegevens nauwkeurig en volledig controleerbaar te houden.

## Snelle antwoorden
- **Wat betekent “add resource to project”?** Het maakt een nieuw resource‑item aan dat later aan taken kan worden toegewezen.  
- **Kan ik een leveling‑vertraging instellen na de toewijzing?** Ja, met de velden `Asn.DELAY` of `Asn.LEVELING_DELAY`.  
- **Heb ik een licentie nodig om deze code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een betaalde licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Is dit compatibel met alle MS Project‑bestandsformaten?** Aspose.Tasks ondersteunt meer dan 12 formaten—waaronder .MPP, .XML, .XER, .CSV, .PDF en meer.

## Wat is “add resource to project” in Aspose.Tasks?
Het toevoegen van een resource aan een project betekent het creëren van een `Resource`‑object binnen het `Project`‑model. Dit object kan later via `ResourceAssignment` aan taken worden gekoppeld, waardoor je werk, kosten en leveling‑instellingen kunt bijhouden. Door een resource in te voegen geef je de planner iets om toe te wijzen, en kun je later de eigenschappen zoals beschikbaarheid, tarieven en kalender‑toewijzingen opvragen of wijzigen.

## Waarom leveling‑vertragingseigenschappen behandelen?
Leveling‑vertraging vertelt de planner om de start van een over‑gealloceerde toewijzing uit te stellen, waardoor werk gelijkmatiger over de tijdlijn wordt verdeeld. Door deze vertraging te configureren vermijd je onrealistische startdatums, verminder je waarschuwingen voor overallocatie, en creëer je een planning die de realistische resource‑beperkingen weerspiegelt. Het aanpassen van de vertraging geeft je bovendien fijnmazige controle over hoeveel speling de engine mag invoegen, waardoor je projectdeadlines kunt halen terwijl je de resource‑limieten respecteert.

## Hoe maak je resource assignment aspotasks?
Laad je `Project`‑object, voeg een taak toe, maak een resource aan en koppel ze vervolgens met een `ResourceAssignment`. Deze end‑to‑end‑stroom stelt je in staat om programmatisch een volledige projectstructuur op te bouwen en direct de leveling‑vertraging op de toewijzing te regelen. Het proces toont de kernworkflow: projectinitialisatie, taakdefinitie, resource‑creatie, toewijzingskoppeling, en tenslotte het toepassen van planningsparameters zoals leveling‑vertraging.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je de volgende voorvereisten hebt:
1. Java Development Kit (JDK): Zorg ervoor dat je Java JDK op je systeem hebt geïnstalleerd. Je kunt het downloaden en installeren vanaf de [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java Library: Download de Aspose.Tasks for Java‑bibliotheek vanaf de [download page](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
De volgende imports brengen de kern‑Aspose.Tasks‑klassen binnen die nodig zijn voor projectmanipulatie.  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Hoe maak je resource assignment aspotasks?
Laad je `Project`‑object, voeg een taak toe, maak een resource aan en koppel ze vervolgens met een `ResourceAssignment`. Deze end‑to‑end‑stroom stelt je in staat om programmatisch een volledige projectstructuur op te bouwen en direct de leveling‑vertraging op de toewijzing te regelen. Het proces toont de kernworkflow: projectinitialisatie, taakdefinitie, resource‑creatie, toewijzingskoppeling, en tenslotte het toepassen van planningsparameters zoals leveling‑vertraging.

## Stap 1: Maak een Project‑object
De `Project`‑klasse is de top‑level container van Aspose.Tasks die een volledig projectbestand in het geheugen vertegenwoordigt. Een instantie ervan geeft je een schone lei om taken, resources en toewijzingen toe te voegen.
```java
Project prj = new Project();
```

## Stap 2: Maak een taak
De `Task`‑klasse vertegenwoordigt een enkel werkitem in de planning. Het toevoegen van een taak toont **how to add task** programmatisch en biedt een doelwit voor de aankomende resource‑toewijzing.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Stap 3: Stel taak‑startdatum en -duur in
Definieer wanneer de taak start en hoe lang deze zal duren. Juiste startdatums zijn essentieel omdat leveling‑berekeningen ze gebruiken als basis voor elke vertraging die je later opgeeft.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Stap 4: Voeg een resource toe
Nu **add resource to project** door een nieuw `Resource`‑item te creëren. De `Resource`‑klasse is de weergave van een persoon, uitrusting of materiaal dat aan taken kan worden toegewezen.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Stap 5: Maak een resource‑toewijzing
`ResourceAssignment` koppelt een `Task` en een `Resource`. Deze associatie stelt je in staat om werk, kosten en leveling‑details vast te leggen voor een specifieke resource op een specifieke taak.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Stap 6: Stel leveling‑vertraging in
Configureer de leveling‑vertraging voor de toewijzing. Instellen op nul betekent geen extra vertraging, maar je kunt de waarde naar behoefte aanpassen. Het veld `Asn.DELAY` bevat de vertraging in minuten; `Asn.LEVELING_DELAY` is een alias die op dezelfde manier werkt.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Stap 7: Resultaten weergeven
Print de belangrijke eigenschappen om te verifiëren dat alles correct is ingesteld. Deze stap helpt je te bevestigen dat de resource-, taak- en vertragingwaarden precies zijn wat je verwacht voordat je het bestand opslaat.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Veelvoorkomende valkuilen & tips
- **Valkuil:** Vergeten de taak‑startdatum in te stellen kan ertoe leiden dat de toewijzing standaard op de project‑start valt.  
- **Tip:** Gebruik `prj.getDuration(value, TimeUnitType.Day)` om de granulariteit van de vertraging te regelen.  
- **Tip:** Na het toevoegen van meerdere resources, roep `prj.updateResourceAssignments()` aan om de planner de leveling opnieuw te laten berekenen.  
- **Pro tip:** Voor grote projecten (10.000+ taken) schakel `prj.setAutoCalculate(false)` in vóór bulk‑updates, roep vervolgens `prj.calculate()` één keer aan het einde aan om de prestaties te verbeteren.

## Veelgestelde vragen

**Q: Kan ik Aspose.Tasks gebruiken met andere Java‑bibliotheken?**  
A: Ja, Aspose.Tasks integreert soepel met bibliotheken zoals Jackson voor JSON‑verwerking of Apache POI voor extra spreadsheet‑operaties, waardoor je rijkere project‑managementoplossingen kunt bouwen.

**Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?**  
A: Aspose.Tasks ondersteunt meer dan 12 bestandsformaten—waaronder .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML, en .MPP12—wat zorgt voor naadloze round‑trip‑bewerking over alle belangrijke Project‑versies.

**Q: Waar kan ik extra ondersteuning voor Aspose.Tasks vinden?**  
A: Je kunt ondersteuning en community‑discussies vinden op het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Kan ik Aspose.Tasks uitproberen voordat ik het koop?**  
A: Ja, een volledig functionele gratis proefversie is beschikbaar via de [releases page](https://releases.aspose.com/).

**Q: Hoe kan ik een tijdelijke licentie voor evaluatie verkrijgen?**  
A: Vraag een tijdelijke licentie aan via de [temporary license page](https://purchase.aspose.com/temporary-license/) om de bibliotheek zonder evaluatiebeperkingen te gebruiken.

---

**Laatst bijgewerkt:** 2026-06-05  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Maak resource‑toewijzingen in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Beheer toewijzingsbudget Java met Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Hoe stop je een toewijzing en hervat je resource‑toewijzingen in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}