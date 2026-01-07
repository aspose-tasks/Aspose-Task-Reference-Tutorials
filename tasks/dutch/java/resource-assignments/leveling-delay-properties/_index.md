---
date: 2026-01-07
description: Leer hoe u een resource aan een project toevoegt en de eigenschappen
  voor nivelleringvertraging van resource‑toewijzingen beheert met Aspose.Tasks voor
  Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe een resource aan een project toevoegen en de nivelleringvertraging‑eigenschappen
  in Aspose.Tasks afhandelen
url: /nl/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een resource aan een project toe te voegen en levelingsvertragingseigenschappen te beheren in Aspose.Tasks

## Introductie
In deze tutorial leer je **hoe je een resource aan een project toevoegt** terwijl je ook de levelingsvertragingseigenschappen voor resource‑toewijzingen beheert met Aspose.Tasks voor Java. Of je nu een planningsengine bouwt of projectupdates automatiseert, het beheersen van deze stappen stelt je in staat om je projectgegevens nauwkeurig te houden zonder Microsoft Project geïnstalleerd te hebben.

## Snelle antwoorden
- **Wat betekent “resource aan project toevoegen”?** Het maakt een nieuw resource‑item aan dat aan taken kan worden toegewezen.  
- **Kan ik een levelingsvertraging instellen na toewijzing?** Ja, met de velden `Asn.DELAY` of `Asn.LEVELING_DELAY`.  
- **Heb ik een licentie nodig om deze code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een betaalde licentie is vereist voor productie.  
- **Welke Java‑versie wordt ondersteund?** Java 8 of hoger.  
- **Is dit compatibel met alle MS Project‑bestandsformaten?** Aspose.Tasks ondersteunt .MPP, .XML, .XER en meer.

## Wat is “resource aan project toevoegen” in Aspose.Tasks?
Een resource aan een project toevoegen betekent het creëren van een `Resource`‑object binnen het `Project`‑model. Dit object kan later via `ResourceAssignment` aan taken worden gekoppeld, waardoor je werk, kosten en levelingsinstellingen kunt bijhouden.

## Waarom levelingsvertragingseigenschappen behandelen?
Levelingsvertraging helpt de planner om werk te spreiden wanneer resources overbelast zijn. Door een vertraging in te stellen, vertel je de engine om de start van een toewijzing uit te stellen, waardoor conflicten worden vermeden en het project realistisch blijft.

## Voorwaarden
Voordat we beginnen, zorg dat je de volgende voorwaarden hebt:
1. Java Development Kit (JDK): Zorg ervoor dat je Java JDK op je systeem hebt geïnstalleerd. Je kunt het downloaden en installeren via de [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java Library: Download de Aspose.Tasks for Java‑bibliotheek vanaf de [downloadpagina](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Importeer eerst de benodigde pakketten in je Java‑project om de functionaliteit van Aspose.Tasks te gebruiken:
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

## Stap 1: Een Project‑object maken
Instantieer een `Project`‑object, dat dient als container voor alle taken, resources en toewijzingen:
```java
Project prj = new Project();
```

## Stap 2: Een taak maken
Voeg een taak toe aan het project. Dit demonstreert **hoe je een taak programmeermatig toevoegt**:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Stap 3: Startdatum en duur van de taak instellen
Definieer wanneer de taak start en hoe lang deze duurt:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Stap 4: Een resource toevoegen
Nu **voegen we een resource aan het project toe** door een nieuw `Resource`‑item te creëren:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Stap 5: Een resource‑toewijzing maken
Koppel de taak en de nieuw toegevoegde resource aan elkaar:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Stap 6: Levelingsvertraging instellen
Configureer de levelingsvertraging voor de toewijzing. Instellen op nul betekent geen extra vertraging, maar je kunt de waarde aanpassen naar behoefte:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Stap 7: Resultaten weergeven
Print de belangrijke eigenschappen om te verifiëren dat alles correct is ingesteld:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Veelvoorkomende valkuilen & tips
- **Valstrik:** Het vergeten instellen van de startdatum van de taak kan ertoe leiden dat de toewijzing standaard op de projectstart valt.  
- **Tip:** Gebruik `prj.getDuration(value, TimeUnitType.Day)` om de granulariteit van de vertraging te regelen.  
- **Tip:** Na het toevoegen van meerdere resources, roep `prj.updateResourceAssignments()` aan zodat de planner de levelings opnieuw berekent.

## Conclusie
Door deze stappen te volgen, weet je nu **hoe je een resource aan een project toevoegt**, deze aan een taak toewijst, en levelingsvertragingseigenschappen beheert met Aspose.Tasks voor Java. Deze kennis stelt je in staat robuuste project‑automatiseringsoplossingen te bouwen die synchroon blijven met real‑world resource‑beperkingen.

## FAQ's
### Q: Kan ik Aspose.Tasks gebruiken met andere Java‑bibliotheken?
A: Ja, Aspose.Tasks kan worden geïntegreerd met andere Java‑bibliotheken om de mogelijkheden voor projectbeheer uit te breiden.

### Q: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project‑bestanden?
A: Ja, Aspose.Tasks ondersteunt diverse versies van Microsoft Project‑bestanden, waardoor compatibiliteit over verschillende omgevingen heen gewaarborgd is.

### Q: Waar kan ik extra ondersteuning voor Aspose.Tasks vinden?
A: Je kunt ondersteuning en bronnen vinden op het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15).

### Q: Kan ik Aspose.Tasks uitproberen voordat ik het koop?
A: Ja, je kunt een gratis proefversie van Aspose.Tasks verkrijgen via de [releases‑pagina](https://releases.aspose.com/).

### Q: Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?
A: Je kunt een tijdelijke licentie aanvragen via de [tijdelijke licentie‑pagina](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.

## Aanvullende veelgestelde vragen

**Q: Wat gebeurt er als ik een niet‑nul levelingsvertraging instel?**  
A: De planner stelt de start van de toewijzing uit met de opgegeven duur, waardoor over‑allocaties worden opgelost.

**Q: Kan ik de levelingsvertraging ophalen nadat ik het project heb opgeslagen?**  
A: Ja, je kunt het projectbestand opnieuw openen en de eigenschap `Asn.DELAY` van de toewijzing lezen.

**Q: Is er een manier om levelingsvertraging op alle toewijzingen tegelijk toe te passen?**  
A: Je kunt itereren over `prj.getResourceAssignments()` en in een lus de vertraging voor elke toewijzing instellen.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}