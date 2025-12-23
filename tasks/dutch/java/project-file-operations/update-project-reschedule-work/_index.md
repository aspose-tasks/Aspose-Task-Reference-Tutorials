---
date: 2025-12-23
description: Leer hoe u MS Project‑bestanden bijwerkt en onvoltooide werkzaamheden
  opnieuw plant met Aspose.Tasks voor Java. Bekijk ook hoe u MS Project‑XML opslaat.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Werk MS Project bij en plan werk opnieuw met Aspose.Tasks
url: /nl/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Update MS Project en Werk Herplannen met Aspose.Tasks

## Inleiding
Microsoft Project is een veelgebruikt projectmanagement‑tool dat teams helpt plannen, volgen en werk op tijd af te leveren. Wanneer planningen verschuiven, moet je vaak **MS Project bijwerken**‑bestanden programmatisch—werk als voltooid markeren, resterende taken verplaatsen en de projectbaseline nauwkeurig houden. Aspose.Tasks voor Java biedt een schone, type‑veilige API om precies dat te doen zonder de GUI te openen. In deze tutorial zie je hoe je een project bijwerkt, werk markeert als voltooid tot een specifieke datum, en vervolgens **hoe je MS Project herplant**‑werk dat nog openstaat.

## Snelle Antwoorden
- **Wat betekent “MS Project bijwerken”?** Het markeert taken als voltooid tot een gegeven datum en schrijft de wijzigingen terug naar het bestand.  
- **Kan ik resterend werk automatisch herplannen?** Ja—gebruik `rescheduleUncompletedWorkToStartAfter` om onafgewerkte taken vooruit te schuiven.  
- **In welk bestandsformaat wordt opgeslagen?** De voorbeelden slaan het project op als XML (`SaveFileFormat.Xml`).  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** JDK 8 of hoger.

## Wat betekent “MS Project bijwerken” in code?
Een project bijwerken betekent programmatisch taakdatums, -duur of voltooiingspercentages wijzigen en die wijzigingen opslaan. Aspose.Tasks biedt methoden zoals `updateProjectWorkAsComplete` die de wijzigingen toepassen op basis van een referentie‑`Date` die je opgeeft.

## Waarom Aspose.Tasks voor Java gebruiken om MS Project bij te werken?
- **Geen UI‑afhankelijkheid** – automatiseer bulk‑wijzigingen over vele bestanden.  
- **Hoge getrouwheid** – de bibliotheek behoudt alle native Project‑gegevens (resources, agenda’s, aangepaste velden).  
- **Cross‑platform** – voer dezelfde code uit op Windows, Linux of macOS.  
- **MS Project XML opslaan** – je kunt het bijgewerkte project exporteren naar het breed ondersteunde XML‑formaat voor downstream‑tools.

## Voorvereisten
1. Java Development Kit (JDK) geïnstalleerd.  
2. Aspose.Tasks voor Java‑bibliotheek – download deze van [hier](https://releases.aspose.com/tasks/java/).  
3. Basiskennis van Java‑syntaxis en object‑georiënteerde concepten.

## Pakketten importeren
First, import the necessary Aspose.Tasks classes and Java utilities:

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
Maak een nieuw `Project`‑object aan, definieer een paar voorbeeldtaken, stel hun duur in en leg afhankelijkheden vast. Sla vervolgens de initiële staat op zodat je het voor‑en‑na‑effect kunt zien.

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
Markeer werk als voltooid tot een specifieke afkapdatum. Dit is de kern van **MS Project bijwerken**—de API past automatisch de voortgang en datums van taken aan.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Stap 3: Onvoltooid werk herplannen
Na het markeren van voltooid werk moet je vaak de resterende taken vooruit schuiven. De volgende aanroep verplaatst onvoltooid werk zodat het start na dezelfde afkapdatum, wat effectief **hoe je MS Project herplant**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Taken tonen geen bijgewerkte datums | Het project werd opgeslagen in een ander formaat (bijv. `.mpp`) | Gebruik `SaveFileFormat.Xml` om de XML‑structuur intact te houden. |
| `updateProjectWorkAsComplete` lijkt niets te doen | De referentiedatum ligt vóór de projectstart | Zorg ervoor dat de `Calendar`‑datum binnen de projecttijdlijn valt. |
| Hergeplande taken overlappen | Er is geen agenda‑ of resource‑leveling toegepast | Pas een `Project`‑agenda toe of gebruik `Task.setStart` handmatig na het herplannen. |

## Veelgestelde vragen (Uitgebreid)

**Q: Kan Aspose.Tasks voor Java complexe projectstructuren aan?**  
A: Ja, Aspose.Tasks voor Java biedt robuuste API’s om taken, afhankelijkheden, resources en andere projectelementen efficiënt te beheren.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?**  
A: Ja, je kunt een gratis proefversie krijgen via [hier](https://releases.aspose.com/).

**Q: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?**  
A: Je kunt het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) bezoeken voor hulp of vragen.

**Q: Kan ik een tijdelijke licentie aanschaffen voor Aspose.Tasks voor Java?**  
A: Ja, tijdelijke licenties zijn verkrijgbaar via aankoop [hier](https://purchase.aspose.com/temporary-license/).

**Q: Waar vind ik gedetailleerde documentatie voor Aspose.Tasks voor Java?**  
A: Je kunt de documentatie raadplegen [hier](https://reference.aspose.com/tasks/java/) voor uitgebreide handleidingen en API‑referenties.

## Conclusie
In deze tutorial hebben we het volledige proces doorlopen van **MS Project bijwerken**‑bestanden, werk markeren als voltooid, en vervolgens **hoe je MS Project**‑taken die nog onafgewerkt zijn herplant. Door het project als XML op te slaan behoud je compatibiliteit met andere tools en een duidelijk audit‑spoor van wijzigingen. Gebruik deze patronen om planningsaanpassingen in grote portfolio’s te automatiseren, te integreren met CI‑pipelines, of aangepaste rapportagedashboards te bouwen.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}