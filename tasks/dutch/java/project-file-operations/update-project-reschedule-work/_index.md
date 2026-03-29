---
date: 2026-03-29
description: Leer hoe u onvoltooide werkzaamheden kunt herschikken, projectwerk kunt
  bijwerken en MS Project‑bestanden als XML kunt opslaan met Aspose.Tasks voor Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Plan onafgewerkt werk opnieuw in en werk MS Project‑bestanden bij met Aspose.Tasks
url: /nl/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Herplan onvoltooide werkzaamheden en werk MS Project-bestanden bij met Aspose.Tasks

## Inleiding
Microsoft Project is een veelgebruikt projectmanagementtool die teams helpt taken te plannen, middelen toe te wijzen en tijdlijnen bij te houden. Aspose.Tasks for Java biedt ontwikkelaars een uitgebreide API om Microsoft Project‑bestanden programmatisch te manipuleren. In deze tutorial leer je hoe je **projectwerk bijwerkt**, **onvoltooide werkzaamheden herscheduleert**, en **het MS Project‑bestand opslaat** in XML‑formaat met Aspose.Tasks for Java.

## Snelle antwoorden
- **Wat betekent “onvoltooide werkzaamheden herscheduleën”?** Het verplaatst alle resterende taakwerk zodat het start na een gekozen datum, terwijl voltooide delen onaangeroerd blijven.  
- **Welke methode markeert werk als voltooid?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Hoe bewaar ik de wijzigingen?** Gebruik `project.save(<path>, SaveFileFormat.Xml)`.  
- **Heb ik een licentie nodig voor productie?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor commercieel gebruik.  
- **Welke Java‑versie wordt ondersteund?** Java 8 en hoger worden volledig ondersteund.  

## Wat is “onvoltooide werkzaamheden herscheduleën”?
Het herscheduleën van onvoltooide werkzaamheden past de startdatums van alle taken die nog niet voltooid zijn aan, zodat ze beginnen na een opgegeven afkapdatum. Dit is nuttig wanneer een projecttijdlijn verschuift door vertragingen of wijziging van de scope.

## Waarom Aspose.Tasks gebruiken om projectwerk bij te werken en taken te herscheduleën?
- **Fijne controle:** Stel direct percentages en data van werkvoltooiing in.  
- **Geen UI vereist:** Automatiseer bulkupdates over vele projectbestanden.  
- **Cross‑platform:** Werkt op elk systeem dat Java draait.  
- **Behoudt gegevensintegriteit:** Alle afhankelijkheden, beperkingen en middelen blijven consistent.  

## Vereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:
1. Java Development Kit (JDK) geïnstalleerd op je systeem.  
2. Aspose.Tasks for Java bibliotheek. Je kunt deze downloaden van [hier](https://releases.aspose.com/tasks/java/).  
3. Basiskennis van de programmeertaal Java.  

## Pakketten importeren
Importeer eerst de benodigde pakketten in je Java‑code:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Stap 1: Het project opzetten
Initialiseer een nieuw `Project`‑object, definieer taken, stel duur in en leg afhankelijkheden vast. Dit creëert het basisproject dat we later zullen bijwerken en herscheduleën.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Stap 2: Projectwerk bijwerken
Markeer werk als voltooid tot een specifieke datum. Deze stap demonstreert de **update project work**‑operatie, die vaak de eerste handeling is vóór het herscheduleën.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Stap 3: Onvoltooide werkzaamheden herscheduleën
Nu verplaatsen we eventueel resterend (onvoltooid) werk zodat het start na dezelfde afkapdatum. Dit is de kernfunctionaliteit van **reschedule uncompleted work**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusie
In deze tutorial hebben we behandeld hoe je **projectwerk bijwerkt**, **onvoltooide werkzaamheden herscheduleert**, en **het MS Project‑bestand opslaat** als XML met Aspose.Tasks for Java. Deze mogelijkheden zijn essentieel wanneer projecttijdlijnen moeten worden aangepast op basis van de werkelijke voortgang of veranderende zakelijke prioriteiten.

## Veelgestelde vragen
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Ja, Aspose.Tasks for Java biedt robuuste API's om taken, afhankelijkheden, middelen en andere projectelementen efficiënt te beheren.  
### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Ja, je kunt een gratis proefversie krijgen via [hier](https://releases.aspose.com/).  
### Q: How can I get support for Aspose.Tasks for Java?
A: Je kunt het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) bezoeken voor hulp of vragen.  
### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Ja, tijdelijke licenties zijn beschikbaar voor aankoop [hier](https://purchase.aspose.com/temporary-license/).  
### Q: Where can I find detailed documentation for Aspose.Tasks for Java?
A: Je kunt de documentatie raadplegen [hier](https://reference.aspose.com/tasks/java/) voor uitgebreide handleidingen en API‑referenties.  

## Aanvullende veelgestelde vragen

**Q: How do I ensure the saved file is compatible with older versions of Microsoft Project?**  
A: Sla het project op met `SaveFileFormat.Xml`; XML wordt breed ondersteund in verschillende Project‑versies.  

**Q: Can I reschedule only a subset of tasks instead of the whole project?**  
A: Ja, je kunt over specifieke taken itereren en `task.setStart(date)` aanroepen na het berekenen van de nieuwe startdatum.  

**Q: What happens to resource allocations when I reschedule uncompleted work?**  
A: Resource‑toewijzingen worden automatisch verschoven om overeen te komen met de nieuwe startdatums van taken, waardoor de toewijzingslogica behouden blijft.  

**Q: Is it possible to undo a reschedule operation programmatically?**  
A: Je kunt het originele projectbestand (of een backup) opnieuw laden om wijzigingen terug te draaien.  

**Q: Does Aspose.Tasks support saving to other formats like .mpp?**  
A: Zeker. Gebruik `SaveFileFormat.MPP` om op te slaan in het native Microsoft Project‑formaat.  

---

**Laatst bijgewerkt:** 2026-03-29  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}