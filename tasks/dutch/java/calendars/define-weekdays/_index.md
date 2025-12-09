---
date: 2025-12-02
description: Leer hoe u een agenda instelt, weekdagen definieert in MS Project en
  aangepaste werkdagen instelt met Aspose.Tasks voor Java. Sla het project op als
  XML met slechts een paar regels code.
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hoe de agenda instellen en weekdagen definiëren in MS Project met Aspose.Tasks
url: /nl/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een kalender instellen en weekdagen definiëren in MS Project met Aspose.Tasks

## Inleiding
In deze tutorial ontdek je **hoe je een kalender instelt** programmatisch en definieer je weekdagen in een Microsoft Project‑bestand met behulp van de Aspose.Tasks‑bibliotheek voor Java. Of je nu een standaardwerkweek wilt maken, weekendwerkdagen wilt toevoegen, of een kort vrijdag‑schema wilt configureren, deze gids leidt je stap voor stap – van het aanmaken van het project tot het opslaan van het bestand als XML.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Tasks for Java  
- **Kan ik weekendwerkdagen toevoegen?** Ja – voeg gewoon zaterdag en zondag toe als werkdagen.  
- **Hoe sla ik het project op?** Gebruik `prj.save(..., SaveFileFormat.Xml)`.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een licentie is vereist voor productie.  
- **Welke Java‑versie is vereist?** Java 8 of hoger.

## Wat betekent “hoe je een kalender instelt” in de context van MS Project?
Het instellen van een kalender in MS Project houdt in dat je bepaalt welke dagen werkdagen zijn, de dagelijkse werktijden, en eventuele uitzonderingen zoals feestdagen. Deze kalender bepaalt de taakplanning, resource‑toewijzing en de algehele projecttijdlijnen.

## Waarom Aspose.Tasks gebruiken voor kalendermanipulatie?
- **Volledige controle** – programmatisch kalenders maken, wijzigen of verwijderen zonder de UI te openen.  
- **Cross‑platform** – werkt op elk OS dat Java ondersteunt.  
- **Ondersteunt alle bestandsformaten** – MPP, MPT en XML, zodat je *project als XML kunt opslaan* voor eenvoudige integratie met andere systemen.  
- **Geen COM‑afhankelijkheden** – in tegenstelling tot de Microsoft Project Interop‑bibliotheek.

## Vereisten
Voordat je begint, zorg dat je het volgende hebt:

1. **Java Development Kit (JDK) 8+** – download van de [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – haal de nieuwste JAR op van de [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Een IDE of build‑tool (Maven/Gradle) om de Aspose.Tasks‑JAR aan de classpath van je project toe te voegen.

## Import Packages
Eerst importeer je de klassen die je nodig hebt. Deze imports geven je toegang tot project‑, kalender‑ en werktijd‑objecten.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Stapsgewijze handleiding

### Stap 1: Maak een Project‑instantie
Maak een nieuw `Project`‑object. Dit object vertegenwoordigt het MS Project‑bestand dat je gaat bewerken.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Stap 2: Definieer een nieuwe kalender
Voeg een nieuwe kalender toe aan het project. Een duidelijke naam helpt wanneer je meerdere kalenders hebt.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Stap 3: Voeg standaardwerkdagen toe (maandag‑donderdag)
Gebruik de ingebouwde helper `WeekDay.createDefaultWorkingDay` om het standaard 9 am‑5 pm‑schema voor de kernwerkweek in te stellen.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Stap 4: Voeg weekendwerkdagen toe
Als je project in het weekend loopt, voeg dan eenvoudigweg zaterdag en zondag toe als reguliere werkdagen. Dit demonstreert **weekendwerkdagen toevoegen**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Stap 5: Stel een aangepaste korte werkdag in (vrijdag)
Hier **stellen we aangepaste werkdagen in** voor vrijdag: een ochtendshift (9 am‑12 pm) en een middagshift (1 pm‑4 pm).

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Stap 6: Sla het project op als XML
Sla tenslotte de wijzigingen op. De optie `SaveFileFormat.Xml` stelt je in staat om **project als XML op te slaan**, wat nuttig is voor integratie met andere tools.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Veelvoorkomende problemen & oplossingen
| Probleem | Oplossing |
|----------|-----------|
| **Werkuren niet toegepast** | Zorg ervoor dat `setDayWorking(true)` wordt aangeroepen op de aangepaste `WeekDay`. |
| **Bestand niet gevonden bij opslaan** | Controleer of `dataDir` naar een bestaande map wijst en of je applicatie schrijfrechten heeft. |
| **Kalender niet weergegeven in taken** | Wijs de nieuw aangemaakte kalender toe aan resources of taken met `task.setCalendar(cal)`. |

## Veelgestelde vragen

**Q: Kan ik aangepaste niet‑werkdagen definiëren met Aspose.Tasks voor Java?**  
A: Ja. Stel de `DayWorking`‑eigenschap in op `false` voor elke `WeekDay` die je als niet‑werkdag wilt behandelen.

**Q: Hoe kan ik feestdagen of bedrijfsbrede uitzonderingen toevoegen?**  
A: Maak `CalendarException`‑objecten, specificeer de uitzonderingsdatums, en voeg ze toe aan `cal.getExceptions()`.

**Q: Is de bibliotheek compatibel met oudere MS Project‑versies?**  
A: Absoluut. Aspose.Tasks ondersteunt MPP, MPT en XML‑formaten over meerdere Project‑versies.

**Q: Kan ik een bestaande kalender in een geïmporteerd project wijzigen?**  
A: Laad het project met `new Project("existing.mpp")`, haal de gewenste kalender op, breng wijzigingen aan, en sla op.

**Q: Ondersteunt Aspose.Tasks ook terugkerende taken?**  
A: Ja, je kunt terugkerende taken maken en bewerken met de `RecurringTask`‑klasse.

## Conclusie
Je weet nu **hoe je een kalender instelt**, **weekdagen in MS Project definiëren**, weekendwerkdagen toevoegen en een kort vrijdag‑schema maken – alles met Aspose.Tasks for Java. Sla het resultaat op als XML en integreer de kalenderlogica in elke Java‑gebaseerde projectmanagementoplossing.

---

**Laatst bijgewerkt:** 2025-12-02  
**Getest met:** Aspose.Tasks for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}