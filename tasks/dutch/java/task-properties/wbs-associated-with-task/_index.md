---
date: 2026-03-03
description: Leer hoe u WBS in Aspose.Tasks voor Java kunt hernummeren, werkonderdelen
  kunt beheren en WBS-codes efficiënt kunt aanpassen met stapsgewijze voorbeelden.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe WBS te hernummeren in Aspose.Tasks voor Java
url: /nl/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe WBS opnieuw nummeren in Aspose.Tasks voor Java

## Introductie
Als je **hoe WBS opnieuw te nummeren** in een Microsoft Project‑bestand met Aspose.Tasks voor Java nodig hebt, ben je hier op de juiste plek. Deze tutorial leidt je door het lezen van bestaande WBS‑codes, het aanpassen ervan, en vervolgens het opnieuw nummeren van de hiërarchie zodat je project georganiseerd blijft. Of je nu een legacy‑planning opruimt of een nieuwe vanaf nul bouwt, het beheersen van deze stappen helpt je **werkonderverdeling**‑structuren met vertrouwen te beheren.

## Snelle antwoorden
- **Wat doet het opnieuw nummeren van WBS?** Het herberekent de hiërarchische nummering van taken om eventuele structurele wijzigingen weer te geven.  
- **Welke klasse voert het opnieuw nummeren uit?** `Project.renumberWBSCode`.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Kan ik het WBS‑formaat aanpassen?** Ja—gebruik `Task.set(Tsk.WBS, "...")` om elke gewenste tekenreeks toe te wijzen.  
- **Wat zijn de belangrijkste vereisten?** Java JDK, Aspose.Tasks voor Java‑bibliotheek, en een geldig projectbestand (.mpp).

## Wat is een Work Breakdown Structure (WBS)?
Een Work Breakdown Structure (WBS) is een hiërarchische weergave van de leveringen en taken van een project. Elke taak krijgt een code (bijv. 1.2.3) die haar positie in de hiërarchie weergeeft. Het opnieuw nummeren wordt essentieel wanneer taken worden toegevoegd, verwijderd of herschikt, zodat de codes logisch en gemakkelijk leesbaar blijven.

## Waarom werkonderverdeling beheren en WBS‑codes aanpassen?
- **Duidelijkheid:** Duidelijke WBS‑codes maken het eenvoudig voor belanghebbenden om taken te vinden.  
- **Rapportage:** Veel rapportagetools vertrouwen op consistente nummering.  
- **Flexibiliteit:** Aangepaste codes laten je de projectstructuur afstemmen op interne standaarden.  

## Vereisten
Voordat we in de code duiken, controleer je of je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd op je machine.  
- Aspose.Tasks voor Java‑bibliotheek toegevoegd aan je project. Je kunt het verkrijgen via [hier](https://releases.aspose.com/tasks/java/).  

## Pakketten importeren
Zorg ervoor dat je de benodigde pakketten importeert om je project te starten:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## WBS‑codes lezen
Eerst lezen we de bestaande WBS‑codes zodat je kunt zien waarmee je werkt.

### Stap 1: Het project laden
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Stap 2: Taken verzamelen
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Stap 3: Ontleden en aanpassen
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

De bovenstaande code toont de huidige WBS en het niveau van elke taak, en demonstreert vervolgens **WBS‑codes aanpassen** door een nieuwe tekenreeks toe te wijzen.

## WBS‑codes van taken opnieuw nummeren
Laten we nu de WBS‑hiërarchie daadwerkelijk opnieuw nummeren.

### Stap 1: Het project laden (hernummeringsvoorbeeld)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Stap 2: Alle taken selecteren
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Stap 3: Initiële WBS‑codes weergeven
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Stap 4: WBS‑codes opnieuw nummeren
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Stap 5: Bijgewerkte WBS‑codes weergeven
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Door deze stappen te volgen, kun je effectief **hoe WBS opnieuw te nummeren** voor elke set taken in je projectbestand.

## Veelvoorkomende problemen en oplossingen
- **WBS verandert niet na `set`‑aanroep:** Zorg ervoor dat je met de juiste taak‑instantie werkt en dat het project na wijzigingen wordt opgeslagen.  
- **`renumberWBSCode` geeft een uitzondering:** Controleer of de lijst met ID's overeenkomt met het aantal top‑level taken; anders kan de methode nieuwe nummers niet correct toewijzen.  
- **Ontbrekende WBS‑waarden:** Sommige taken kunnen een `null` WBS hebben als ze zijn geïmporteerd uit een bestand dat er geen definieerde. Gebruik een fallback‑waarde vóór het afdrukken.

## Veelgestelde vragen

**Q: Waar kan ik de documentatie voor Aspose.Tasks voor Java vinden?**  
A: De documentatie is beschikbaar [hier](https://reference.aspose.com/tasks/java/).

**Q: Hoe kan ik Aspose.Tasks voor Java downloaden?**  
A: Je kunt het downloaden [hier](https://releases.aspose.com/tasks/java/).

**Q: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt een gratis proefversie krijgen [hier](https://releases.aspose.com/).

**Q: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?**  
A: Bezoek het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) voor ondersteuning.

**Q: Kan ik een tijdelijke licentie voor Aspose.Tasks voor Java verkrijgen?**  
A: Ja, haal een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/).

**Q: Kan ik het WBS‑formaat na het opnieuw nummeren hernoemen?**  
A: Absoluut. Na het aanroepen van `renumberWBSCode` kun je over de taken itereren en `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` toepassen om aan je naamgevingsconventies te voldoen.

**Q: Heeft het opnieuw nummeren invloed op taak‑afhankelijkheden?**  
A: Nee. De methode werkt alleen de WBS‑tekenreeks bij; taak‑koppelingen en -beperkingen blijven ongewijzigd.

---

**Laatst bijgewerkt:** 2026-03-03  
**Getest met:** Aspose.Tasks voor Java 24.12 (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}