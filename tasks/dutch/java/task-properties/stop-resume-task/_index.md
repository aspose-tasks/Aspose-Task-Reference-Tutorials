---
date: 2026-02-26
description: Leer hoe u een taak kunt hervatten en stoppen in Aspose.Tasks voor Java,
  inclusief het filteren van taken op datum voor nauwkeurige projectcontrole.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe taak hervatten en taak stoppen in Aspose.Tasks
url: /nl/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een taak te hervatten en te stoppen in Aspose.Tasks

## Introductie
Als je een op Java gebaseerd projectmanagement‑oplossing bouwt, moet je vaak een taak tijdelijk **pauzeren** en later **doorgaan**. Aspose.Tasks for Java maakt dit eenvoudig met ingebouwde eigenschappen voor het stoppen en hervatten van taken. In deze tutorial ontdek je **hoe een taak te hervatten** en **hoe een taak te stoppen** programmatisch, en zie je ook hoe je **taken kunt filteren op datum** zodat je alleen met de relevante items in je planning werkt.

## Snelle antwoorden
- **Wat betekent “stop” voor een taak?** Het stelt een stopdatum in, waardoor het werk na dat punt wordt gepauzeerd.  
- **Hoe kan ik een gestopte taak hervatten?** Door een hervattingsdatum toe te wijzen die later is dan de stopdatum.  
- **Kan ik de bewerking beperken tot een datumbereik?** Ja – gebruik een minimumdatum om taken te filteren.  
- **Welke bibliotheekversie is vereist?** Elke recente Aspose.Tasks for Java‑release (de API blijft stabiel).  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een licentie is vereist voor productie.

## Wat is “hoe een taak te hervatten” in Aspose.Tasks?
Een taak hervatten betekent simpelweg een **RESUME**‑datum op een `Task`‑object opgeven. Wanneer de projectengine het schema verwerkt, zal het werk vanaf die datum doorgaan. Dit is vooral nuttig voor het afhandelen van onderbrekingen zoals onbeschikbaarheid van resources of externe afhankelijkheden.

## Waarom de stop/hervat‑functie gebruiken?
- **Controle over tijdlijnen:** Pauzeer werk zonder de taak te verwijderen.  
- **Nauwkeurige rapportage:** Toon realistische start‑/einddatums in Gantt‑diagrammen.  
- **Eenvoudige automatisering:** Combineer met datumfilters om veel taken tegelijk bij te werken.

## Voorvereisten
Voordat je begint, zorg ervoor dat je het volgende hebt:

- Een stevige kennis van Java‑basisprincipes.  
- JDK geïnstalleerd op je machine.  
- De Aspose.Tasks for Java‑bibliotheek toegevoegd aan je project (download deze van [hier](https://releases.aspose.com/tasks/java/)).  

## Pakketten importeren
Breng eerst de benodigde klassen in scope zodat je met projecten en taken kunt werken.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Stap 1: Initialiseer het project en de collector
Maak een `Project`‑instantie die naar je MPP‑bestand wijst en stel een `ChildTasksCollector` in om elke taak in de hiërarchie te verzamelen.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Stap 2: Definieer een minimumdatum voor filteren
Als je alleen wilt werken met taken die betekenisvolle stop‑ of hervattingsdatums hebben, definieer dan een **minimumdatum**. Dit is de kern van de *filter taken op datum*‑techniek.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Stap 3: Itereren, controleren en stop/hervattingswaarden weergeven
Loop nu door de verzamelde taken, pas de **hoe een taak te stoppen**‑logica toe, en print de datums. De code toont ook **hoe een taak te hervatten** door de `RESUME`‑eigenschap te lezen.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Pro tip:** Vervang de `System.out.println`‑aanroepen door je eigen logica (bijv. het bijwerken van de datums, loggen naar een bestand, of het aanpassen van de taakobjecten) om daadwerkelijk taken te *stoppen* of *hervatten* indien nodig.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | Taak heeft geen stopdatum ingesteld. | Controleer op `null` voordat je `.before(minDate)` aanroept. |
| Dates appear as `NA` even after setting | Minimumdatum is te recent. | Gebruik een eerdere `minDate` of verwijder het filter. |
| Changes not reflected in the saved MPP | Project niet opgeslagen na aanpassingen. | Roep `project.save("output.mpp");` aan na het bijwerken van taken. |

## Veelgestelde vragen

### Is Aspose.Tasks for Java geschikt voor grootschalige projecten?
Absoluut! Aspose.Tasks for Java is ontworpen om projecten van verschillende groottes aan te kunnen, met behoud van efficiëntie en betrouwbaarheid.

### Kan ik de datum voor het stoppen en hervatten van taken aanpassen?
Ja, het meegeleverde voorbeeld biedt flexibiliteit bij het instellen van de minimumdatum volgens de eisen van je project.

### Waar kan ik extra ondersteuning vinden voor Aspose.Tasks for Java?
Bezoek het [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) voor community‑ondersteuning en discussies.

### Is er een gratis proefversie beschikbaar voor Aspose.Tasks for Java?
Ja, je kunt de [gratis proefversie](https://releases.aspose.com/) gebruiken om de functies te verkennen voordat je een aankoop doet.

### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks for Java?
Je kunt een tijdelijke licentie [hier](https://purchase.aspose.com/temporary-license/) verkrijgen voor testdoeleinden.

**Aanvullende Q&A**

**Q: Hoe stel ik eigenlijk een nieuwe stopdatum voor een taak in?**  
A: Gebruik `tsk.set(Tsk.STOP, new Date(...));` en sla vervolgens het project op.

**Q: Kan ik taken filteren op een specifiek bereik in plaats van alleen een minimumdatum?**  
A: Ja—vergelijk zowel `before` als `after` met je start‑ en einddatums.

**Q: Rekent de API automatisch het schema opnieuw na het wijzigen van stop‑/hervattingsdatums?**  
A: Na het aanpassen van datums, roep `project.calculateCriticalPath();` aan om het schema te vernieuwen.

## Conclusie
In deze gids hebben we **hoe een taak te hervatten** en **hoe een taak te stoppen** behandeld met Aspose.Tasks for Java, samen met een praktische methode om **taken te filteren op datum**. Door deze fragmenten in je applicatie te integreren, krijg je fijnmazige controle over projecttijdlijnen en kun je schema‑aanpassingen met vertrouwen automatiseren.

---

**Laatst bijgewerkt:** 2026-02-26  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}