---
date: 2026-02-28
description: Leer hoe u de duur in minuten, dagen, uren, weken en maanden kunt verkrijgen
  met Aspose.Tasks voor Java. Gedetailleerde gids met codevoorbeelden.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe de duur in verschillende eenheden te verkrijgen met Aspose.Tasks
url: /nl/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de duur in verschillende eenheden te verkrijgen met Aspose.Tasks

## Introductie
Het begrijpen van **how to get duration** voor taken is een kernonderdeel van elke project‑management workflow. Of je nu minuten nodig hebt voor fijnmazige tracking of maanden voor strategische planning, Aspose.Tasks for Java maakt de conversie eenvoudig. In deze tutorial lopen we je stap voor stap door het ophalen van de duur van een taak in minuten, dagen, uren, weken en maanden, en leggen we uit waarom elke eenheid nuttig kan zijn in real‑world projecten.

## Snelle Antwoorden
- **Wat betekent “how to get duration”?** Het is het proces van het extraheren van de tijdsduur van een taak en deze omzetten naar de eenheid die je nodig hebt.  
- **Welke API‑methode voert de conversie uit?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik converteren naar aangepaste eenheden?** Je kunt conversies ketenen of `TimeSpan` gebruiken voor aangepaste berekeningen.  
- **Is de code compatibel met Java 17?** Ja, Aspose.Tasks ondersteunt Java 8 en nieuwere versies.

## Wat is “how to get duration” in Aspose.Tasks?
Aspose.Tasks slaat de lengte van een taak op als een `Duration`‑object. Door de `convert`‑methode aan te roepen en een `TimeUnitType` (Minute, Hour, Day, Week, Month) op te geven, kun je dezelfde onderliggende waarde ophalen, uitgedrukt in de gewenste eenheid. Deze flexibiliteit stelt je in staat rapporten te genereren, berekeningen uit te voeren, of gegevens aan andere systemen te leveren zonder handmatige wiskunde.

## Waarom Aspose.Tasks gebruiken voor duurconversie?
- **Nauwkeurigheid:** Handelt automatisch kalenderuitzonderingen, werktijd en niet‑standaard kalenders af.  
- **Prestaties:** Eén‑regelige conversie vermijdt loops of aangepaste parsing.  
- **Portabiliteit:** Werkt hetzelfde op Windows-, Linux- en macOS‑omgevingen.  
- **Integratie:** Past naadloos in bestaande Java‑applicaties die al Aspose.Tasks gebruiken.

## Vereisten
Voordat we in de code duiken, zorg ervoor dat je het volgende hebt:

- Java Development Kit (JDK) geïnstalleerd
- Aspose.Tasks for Java bibliotheek. Je kunt het downloaden [hier](https://releases.aspose.com/tasks/java/)
- Een basisbegrip van Java‑programmeren

## Import Pakketten
Voeg in je Java‑project de Aspose.Tasks‑bibliotheek toe. Voeg de volgende import‑statement toe aan het begin van je code:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Stap 1: Stel je project in
Maak een nieuw Java‑project aan in je favoriete IDE (IntelliJ, Eclipse, VS Code, enz.) en voeg de Aspose.Tasks‑JAR toe aan het classpath van het project. Dit zorgt ervoor dat de bovenstaande klassen beschikbaar zijn tijdens het compileren.

## Stap 2: Lees het project‑template
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

Vervang `"Your Document Directory"` door de daadwerkelijke map die je `.xml`‑ of `.mpp`‑projectbestand bevat.

## Stap 3: Haal een taak op
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

De `getById(1)`‑aanroep haalt de taak op waarvan de ID 1 is. Pas de ID aan om een andere taak in je bestand te selecteren.

## Stap 4: Duur in minuten – Hoe de duur in minuten te verkrijgen?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

De variabele `mins` bevat nu de taakduur uitgedrukt in minuten.

## Stap 5: Duur in dagen – Hoe de duur in dagen te verkrijgen?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

Gebruik deze waarde wanneer je dag‑niveau granulariteit nodig hebt voor rapportage of resource‑toewijzing.

## Stap 6: Duur in uren – Hoe de duur in uren te verkrijgen?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

Uren zijn handig voor urenstaten of wanneer je een dag wilt opsplitsen in werkshifts.

## Stap 7: Duur in weken – Hoe de duur in weken te verkrijgen?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

Weken worden vaak gebruikt in high‑level Gantt‑diagrammen of mijlpaalplanning.

## Stap 8: Duur in maanden – Hoe de duur in maanden te verkrijgen?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

Duur op maandniveau helpt bij het afstemmen van projectfasen op fiscale perioden.

## Veelvoorkomende problemen en oplossingen
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `NullPointerException` on `task` | Verkeerde taak‑ID of ontbrekende sub‑taken | Controleer of de taak‑ID bestaat met `project.getRootTask().getChildren()` |
| Unexpected values (e.g., 0) | Project gebruikt een aangepaste kalender met niet‑werkdagen | Zorg ervoor dat de projectkalender correct is gedefinieerd of gebruik `project.getCalendar()` om deze te inspecteren |
| Conversion returns fractional weeks | Weken worden berekend op basis van de standaard weeklengte van het project (meestal 5 dagen) | Vermenigvuldig met 5 als je kalenderweken nodig hebt, of pas de kalenderinstellingen aan |

## Veelgestelde vragen
### Q: Kan ik Aspose.Tasks for Java met elke Java‑IDE gebruiken?
A: Ja, Aspose.Tasks for Java is compatibel met elke Java Integrated Development Environment (IDE).

### Q: Hoe kan ik de ID van een taak verkrijgen in een Microsoft Project‑bestand?
A: Je kunt het projectbestand handmatig inspecteren of `project.getRootTask().getChildren()` aanroepen en door de collectie itereren om de `ID` van elke taak te lezen.

### Q: Is Aspose.Tasks geschikt voor het verwerken van grootschalige projecten?
A: Absoluut. Aspose.Tasks is ontworpen om efficiënt projecten met duizenden taken en resources te verwerken.

### Q: Waar kan ik meer documentatie vinden?
A: Visit the [documentation](https://reference.aspose.com/tasks/java/) for comprehensive API references, code samples, and best‑practice guides.

### Q: Kan ik Aspose.Tasks for Java uitproberen voordat ik het koop?
A: Yes, you can explore a [free trial](https://releases.aspose.com/) to evaluate its capabilities.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}