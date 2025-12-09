---
date: 2025-12-02
description: Leer hoe u een agenda aan een project toevoegt, hoe u een MS Project‑agenda
  maakt en hoe u een project opslaat als XML met Aspose.Tasks voor Java.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Kalender toevoegen aan project met Aspose.Tasks voor Java
url: /nl/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalender toevoegen aan project met Aspose.Tasks voor Java

## Introductie
In moderne project‑managementworkflows kan de mogelijkheid om **een kalender aan een project** toe te voegen via code uren handmatig bewerken besparen. Aspose.Tasks voor Java biedt ontwikkelaars een nette, type‑veilige API om Microsoft Project‑bestanden te manipuleren zonder ooit de desktop‑client te openen. In deze tutorial leer je **hoe je een kalender toevoegt**, **hoe je een MS Project‑kalender maakt**, en **het project opslaat als XML** — allemaal met slechts een paar regels Java‑code.

## Snelle antwoorden
- **Wat betekent “add calendar to project”?**  
  Het betekent een nieuwe definitie van werktijd (kalender) in een Microsoft Project‑bestand invoegen via code.  
- **Welke bibliotheek regelt dit?**  
  Aspose.Tasks voor Java levert de `Calendar`‑klasse en de `Project`‑container om kalenders te beheren.  
- **Heb ik een licentie nodig?**  
  Een tijdelijke evaluatielicentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Kan ik het bestand opslaan als XML?**  
  Ja — gebruik `SaveFileFormat.Xml` om het project te exporteren als een XML‑bestand.  
- **Wat zijn de vereisten?**  
  Java JDK 8+ en de Aspose.Tasks voor Java‑JAR op je classpath.

## Wat is “add calendar to project”?
Een kalender aan een project toevoegen creëert een aangepast schema dat werkdagen, feestdagen en dagelijkse werktijden definieert. Deze kalender kan vervolgens worden toegewezen aan taken, resources of het gehele project, zodat berekeningen zoals startdatums en duur de gedefinieerde werktijd respecteren.

## Waarom Aspose.Tasks voor Java gebruiken om een kalender aan een project toe te voegen?
- **Volledige controle** – Geen UI nodig; automatiseer bulk‑kalendercreatie over vele projecten.  
- **Cross‑versie compatibiliteit** – Werkt met Project 2007, 2010, 2013, 2016 en latere bestanden.  
- **Geen Microsoft Project‑installatie** – Draai op elke server of CI‑pipeline.  
- **Exportflexibiliteit** – Opslaan als XML, MPP of andere ondersteunde formaten.

## Vereisten
- **Java Development Kit (JDK) 8 of nieuwer** geïnstalleerd en geconfigureerd.  
- **Aspose.Tasks voor Java** bibliotheek – download van de [officiële website](https://releases.aspose.com/tasks/java/) en voeg de JAR toe aan de classpath van je project.  
- Een IDE of build‑tool (Maven/Gradle) naar keuze.

## Stapsgewijze handleiding

### Stap 1: Importeer het benodigde Aspose.Tasks‑pakket
Importeer eerst de Aspose.Tasks‑klassen zodat je met projecten en kalenders kunt werken.

```java
import com.aspose.tasks.*;
```

### Stap 2: Stel het gegevensdirectory‑pad in
Definieer waar het gegenereerde projectbestand wordt weggeschreven. Vervang de placeholder door een absoluut of relatief pad op jouw machine.

```java
String dataDir = "Your Data Directory";
```

### Stap 3: Maak een nieuw Project‑object aan
Instantieer een `Project`‑object – dit vertegenwoordigt een leeg Microsoft Project‑bestand dat je kunt vullen.

```java
Project prj = new Project();
```

### Stap 4: Definieer de kalenders die je wilt toevoegen
Gebruik de methode `Calendars.add(String name)` om nieuwe kalenderitems te maken. In dit voorbeeld voegen we drie kalenders toe, maar je kunt er zoveel toevoegen als nodig en later hun werktijden configureren.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro tip:** Na het toevoegen van een kalender kun je de werkdagen aanpassen met `cal1.getWeekDays().add(...)` en de dagelijkse werktijd instellen via `cal1.getBaseCalendar().setWorkingTime(...)`.

### Stap 5: Sla het project op (save project as XML)
Sla het project, inclusief de nieuw toegevoegde kalenders, op in een XML‑bestand. Dit formaat is gemakkelijk te inspecteren en compatibel met veel tools.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Stap 6: Toon een voltooiingsbericht
Informeer de gebruiker dat de bewerking succesvol is afgerond.

```java
System.out.println("Process completed Successfully");
```

Door deze zes beknopte stappen te volgen, heb je met succes **een kalender aan een project toegevoegd** en het resultaat opgeslagen als een XML‑bestand.

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **`NullPointerException` op `prj.getCalendars()`** | Projectobject niet correct geïnitialiseerd. | Zorg ervoor dat `new Project()` wordt aangeroepen voordat je kalenders benadert. |
| **Bestand niet gevonden bij opslaan** | `dataDir` wijst naar een niet‑bestaande map. | Maak de map eerst aan of gebruik een absoluut pad. |
| **Kalendernaam verschijnt als “no info”** | Placeholder‑namen werden in het voorbeeld gebruikt. | Vervang door betekenisvolle namen die het schema weergeven (bijv. “US Holiday Calendar”). |
| **Opgeslagen XML kan niet worden geopend in MS Project** | Een verouderde versie van Aspose.Tasks wordt gebruikt. | Werk bij naar de nieuwste Aspose.Tasks voor Java‑release. |

## Veelgestelde vragen

**V: Kan Aspose.Tasks complexe kalenders met meerdere uitzonderingen aan?**  
A: Ja – na het toevoegen van een kalender kun je uitzonderingen, werktijden en niet‑werkdagen definiëren met de `WeekDay`‑ en `Exception`‑klassen.

**V: Is het mogelijk de nieuwe kalender toe te wijzen aan specifieke taken?**  
A: Absoluut. Haal een taak op via `prj.getRootTask().getChildren().add("Task Name")` en stel `task.set(Tsk.CALENDAR, cal3);`.

**V: Ondersteunt de bibliotheek opslaan in andere formaten zoals MPP?**  
A: Ja. Vervang `SaveFileFormat.Xml` door `SaveFileFormat.Mpp` of `SaveFileFormat.P6` indien nodig.

**V: Heb ik een licentie nodig voor ontwikkel‑builds?**  
A: Een tijdelijke evaluatielicentie is voldoende voor testen; een volledige licentie is vereist voor productie‑implementaties.

**V: Waar kan ik hulp krijgen als ik tegen problemen aanloop?**  
A: Het Aspose.Tasks‑communityforum is een uitstekende bron: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusie
Met Aspose.Tasks voor Java kun je programmatisch **een kalender aan een project toevoegen**, planningsregels aanpassen, en **het project opslaan als XML** met slechts enkele regels code. Deze automatisering vermindert handmatige inspanning, elimineert menselijke fouten en maakt batchverwerking van grote projectportefeuilles mogelijk.

---

**Laatst bijgewerkt:** 2025-12-02  
**Getest met:** Aspose.Tasks voor Java 24.12 (latest at time of writing)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}