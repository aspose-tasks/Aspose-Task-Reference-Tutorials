---
date: 2026-02-28
description: Leer hoe u Aspose.Tasks voor Java kunt gebruiken om taak‑tijdgebaseerde
  gegevens te beheren, download de bibliotheek, probeer het gratis en optimaliseer
  de projecttracking.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe Aspose.Tasks te gebruiken om taak‑tijdgebaseerde gegevens te beheren (Java)
url: /nl/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe Aspose.Tasks te gebruiken voor taak‑tijdgebaseerde gegevens

## Introductie
Als je op zoek bent naar **how to use Aspose** om je projectschema nauwlettend te beheren, ben je hier aan het juiste adres. Nauwkeurige tracking van taak‑tijdgebaseerde gegevens is een hoeksteen van succesvol projectmanagement, en Aspose.Tasks for Java biedt de tools die je nodig hebt om dat proces te automatiseren. In deze tutorial lopen we een volledig end‑to‑end voorbeeld door dat laat zien hoe je Aspose.Tasks gebruikt om een project te maken, resources toe te wijzen, baselines in te stellen en uiteindelijk tijdgebaseerde gegevens op te halen en weer te geven.

## Snelle antwoorden
- **Wat betekent “timephased data”?** Het zijn gegevens opgesplitst per tijdsintervallen (dagen, weken, maanden) die werk, kosten of resterend werk over de projecttijdlijn laten zien.  
- **Welke bibliotheek biedt deze functionaliteit?** Aspose.Tasks for Java.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8 of hoger.  
- **Kan ik de resultaten exporteren naar Excel?** Ja – je kunt de `TimephasedData`‑collectie itereren en waarden naar elk gewenst formaat schrijven.

## Wat is taak‑tijdgebaseerde gegevens?
Taak‑tijdgebaseerde gegevens geven de hoeveelheid werk (of kosten) weer die voor een taak is gepland gedurende elk tijdssegment van de projectkalender. Ze stellen je in staat te zien hoe werk wordt verdeeld, overbelasting te ontdekken en de geplande versus de werkelijke voortgang te vergelijken.

## Waarom Aspose.Tasks gebruiken om tijdgebaseerde gegevens te beheren?
- **Volledige controle** – programmeerbaar maken, wijzigen en opvragen van tijdgebaseerde informatie zonder Microsoft Project te openen.  
- **Cross‑platform** – werkt op elk OS dat Java ondersteunt.  
- **Geen COM‑afhankelijkheden** – ideaal voor automatisering aan de serverzijde.  
- **Rijke API** – ondersteunt baselines, werkcontouren en aangepaste velden direct uit de doos.

## Voorwaarden
Voor je in de code duikt, zorg dat je het volgende hebt:

- **Java‑ontwikkelomgeving** – JDK 8+ geïnstalleerd en `JAVA_HOME` geconfigureerd.  
- **Aspose.Tasks for Java‑bibliotheek** – Download en voeg de Aspose.Tasks‑bibliotheek toe aan je project. Je kunt de bibliotheek vinden [hier](https://releases.aspose.com/tasks/java/).  
- **Documentmap** – Een map op je computer waar het voorbeeldprojectbestand (`project.xml`) wordt gelezen en weggeschreven.

## Pakketten importeren
In je Java‑project importeer je de benodigde Aspose.Tasks‑klassen:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Stap 1: Project‑startdatum instellen
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Uitleg:* We maken een `Project`‑instantie, initialiseren een `Calendar` met de gewenste startdatum en wijzen deze toe aan de `START_DATE`‑eigenschap van het project.

## Stap 2: Taak en resource definiëren
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Uitleg:* Een nieuwe taak met de naam **Task** wordt toegevoegd onder de hoofdtaak. We maken ook een resource genaamd **Rsc** aan en stellen de standaard‑ en overurentarieven in.

## Stap 3: Taakduur instellen
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Uitleg:* De taak wordt gepland voor een duur van **6 dagen**.

## Stap 4: Resource aan taak toewijzen
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Uitleg:* De eerder gedefinieerde resource wordt via een `ResourceAssignment` aan de taak gekoppeld.

## Stap 5: Resource‑toewijzing configureren
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Uitleg:* We stellen de stop‑ en hervattingsdatums van de toewijzing in (met een tijdelijke waarde) en passen een **Back‑Loaded** werkcontour toe, waardoor meer werk naar het einde van de toewijzing wordt verschoven.

## Stap 6: Baseline instellen
```java
project.setBaseline(BaselineType.Baseline);
```
*Uitleg:* Het vastleggen van een baseline stelt je in staat later geplande waarden te vergelijken met de werkelijke waarden.

## Stap 7: Taakvoortgang bijwerken
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Uitleg:* De taak wordt gemarkeerd als **50 % voltooid**, wat invloed heeft op de berekening van het resterende werk.

## Stap 8: Tijdgebaseerde gegevens ophalen
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Uitleg:* Deze oproep haalt het **resterende werk** voor de toewijzing op, opgesplitst per tijdsinterval van het project.

## Stap 9: Tijdgebaseerde gegevens weergeven
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Uitleg:* We printen simpelweg het aantal tijdgebaseerde items en de waarde van het eerste item. In een real‑world scenario zou je de lijst itereren en de gegevens exporteren naar een rapport of UI.

## Veelvoorkomende problemen en oplossingen
- **NullPointerException bij `getTimephasedData`** – Zorg ervoor dat de `START`‑ en `FINISH`‑datums van de toewijzing zijn ingesteld voordat je de methode aanroept.  
- **Onjuiste werkcontour** – Controleer of het `WorkContourType` dat je kiest overeenkomt met je planningsstrategie; `BackLoaded` is slechts één van de opties.  
- **Baseline reflecteert geen wijzigingen** – Vergeet niet `project.setBaseline` aan te roepen *nadat* je taken, resources en toewijzingen hebt gedefinieerd.

## Veelgestelde vragen
### V: Kan ik Aspose.Tasks for Java in elk Java‑project gebruiken?
A: Ja, Aspose.Tasks for Java is compatibel met elk Java‑gebaseerd project.

### V: Waar kan ik extra ondersteuning vinden voor Aspose.Tasks for Java?
A: Bezoek het [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) voor ondersteuning en discussies.

### V: Is er een gratis proefversie beschikbaar voor Aspose.Tasks for Java?
A: Ja, je kunt een gratis proefversie verkennen [hier](https://releases.aspose.com/).

### V: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks for Java?
A: Je kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).

### V: Waar kan ik Aspose.Tasks for Java kopen?
A: Je kunt Aspose.Tasks for Java kopen [hier](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}