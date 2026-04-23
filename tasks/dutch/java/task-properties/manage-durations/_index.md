---
date: 2026-02-20
description: Ontdek hoe u een taak aan een project kunt toevoegen en de duur kunt
  beheren met Aspose.Tasks voor Java. Leer hoe u de duur kunt instellen en hoe u de
  duur eenvoudig kunt converteren.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Taak toevoegen aan project en duur beheren met Aspose.Tasks
url: /nl/java/task-properties/manage-durations/
weight: 20
---

 keep markdown formatting exactly.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Taak toevoegen aan project en duur beheren met Aspose.Tasks

## Inleiding
In deze tutorial leer je **hoe je een taak aan een project toevoegt** en de duur ervan beheert met Aspose.Tasks voor Java. Of je nu een nieuw project‑planningsinstrument bouwt of een bestaande oplossing uitbreidt, het beheersen van taak‑duur is essentieel voor nauwkeurige planning en rapportage.

## Snelle antwoorden
- **Wat betekent “add task to project”?** Het maakt een nieuw taakobject aan onder de root van een project of onder een specifieke samenvattende taak.  
- **Welke klasse vertegenwoordigt een duur?** `com.aspose.tasks.Duration`.  
- **Hoe stel je een duur in?** Gebruik `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Kan ik een duur omzetten naar een andere eenheid?** Ja, roep `duration.convert(TimeUnitType.Hour)` of een andere `TimeUnitType` aan.  
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose.Tasks‑licentie is vereist voor commercieel gebruik.

## Wat is “add task to project”?
Een taak aan een project toevoegen betekent het creëren van een `Task`‑object en dit koppelen aan de taakhiërarchie van het project. Deze handeling is de eerste stap voordat je werk, resources of duur voor die taak kunt definiëren.

## Waarom taakduurtijden beheren?
Nauwkeurige duurwaarden zorgen voor realistische tijdslijnen, resource‑toewijzing en kritieke‑pad‑analyse. Met Aspose.Tasks kun je duurwaarden programmatic instellen, lezen, omzetten en aanpassen, waardoor je volledige controle hebt over projectplanningen.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

- Java Development Kit (JDK): Zorg ervoor dat Java op uw machine is geïnstalleerd. U kunt het downloaden [hier](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks‑bibliotheek: Download en voeg de Aspose.Tasks‑bibliotheek toe aan uw project. U vindt de bibliotheek [hier](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Importeer in uw Java‑project de benodigde pakketten om met Aspose.Tasks te werken:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Stap 1: Uw project instellen
```java
// Create a new project
Project project = new Project();
```

## Stap 2: Een nieuwe taak toevoegen (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Hoe duur instellen
Nu de taak bestaat, kunt u de lengte ervan definiëren. Standaard worden duurwaarden uitgedrukt in dagen.

## Stap 3: Taakduur ophalen en omzetten
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Hoe duur omzetten
De `convert`‑methode stelt u in staat een `Duration` van het ene `TimeUnitType` naar het andere te vertalen (bijv. dagen → uren, weken → dagen).

## Stap 4: Taakduur bijwerken naar 1 week
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Stap 5: Taakduur verkleinen
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Door deze stappen te volgen, heeft u met succes **een taak aan een project toegevoegd** en de duur ervan beheerd met Aspose.Tasks voor Java.

## Veelvoorkomende valkuilen & tips
- **Valkuil:** Het vergeten om de duur om te zetten voordat u rekenkundige bewerkingen uitvoert, kan tot onjuiste resultaten leiden. Controleer altijd de eenheid met `duration.getTimeUnit()`.
- **Tip:** Gebruik `project.getDuration(value, TimeUnitType)` om duurwaarden direct in de gewenste eenheid te creëren in plaats van later om te zetten.
- **Valkuil:** Het instellen van een negatieve duur veroorzaakt een uitzondering. Zorg ervoor dat u invoerwaarden valideert.

## Conclusie
In deze gids hebben we behandeld hoe je **een taak aan een project toevoegt**, de standaardduur uitleest, **de duur instelt**, en **de duur omzet** naar verschillende tijdseenheden. U kunt deze technieken nu integreren in grotere planningsapplicaties voor precieze projectplanning.

## Veelgestelde vragen
### Is Aspose.Tasks compatibel met alle Java‑versies?
Aspose.Tasks is compatibel met Java 6 en latere versies.

### Kan ik Aspose.Tasks gebruiken voor commerciële projecten?
Ja, u kunt Aspose.Tasks gebruiken voor zowel persoonlijke als commerciële projecten. Bezoek [hier](https://purchase.aspose.com/buy) voor licentie‑details.

### Waar vind ik extra ondersteuning en bronnen?
Bezoek het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) voor community‑ondersteuning en discussies.

### Hoe kan ik een tijdelijke licentie verkrijgen voor testdoeleinden?
U kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/) voor testen en evaluatie.

### Is er een gratis proefversie beschikbaar voor Aspose.Tasks?
Ja, u kunt de gratis proefversie [hier](https://releases.aspose.com/) verkennen voordat u een aankoop doet.

## Frequently Asked Questions

**Q: Hoe wijzig ik de duur van een taak nadat deze is ingesteld?**  
A: Haal de huidige duur op met `task.get(Tsk.DURATION)`, wijzig deze (bijv. `add`, `subtract` of `convert`), en stel hem vervolgens opnieuw in met `task.set(Tsk.DURATION, newDuration)`.

**Q: Kan ik een duur in minuten instellen?**  
A: Ja, gebruik `TimeUnitType.Minute` bij het aanroepen van `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Werkt het wijzigen van de duur automatisch de start‑ en einddatums van de taak bij?**  
A: Alleen als de planningsmodus van het project op automatisch is ingesteld. Anders moet u mogelijk de planning opnieuw berekenen met `project.calculateCriticalPath()`.

**Q: Is het mogelijk de duur als een ruwe getalwaarde op te halen?**  
A: Roep `duration.getTimeSpan()` aan om de numerieke waarde in de huidige tijdseenheid te krijgen.

**Q: Wat gebeurt er als ik meer aftrek dan de huidige duur?**  
A: De API zal een `ArgumentOutOfRangeException` werpen. Valideer altijd dat de resulterende duur positief blijft.

---

**Laatst bijgewerkt:** 2026-02-20  
**Getest met:** Aspose.Tasks voor Java (latest)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}