---
title: Haal MS Project-agenda-informatie op in Aspose.Tasks
linktitle: Haal agenda-informatie op in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u MS Project-agendagegevens kunt ophalen met Aspose.Tasks voor Java. Stapsgewijze handleiding voor programmatische toegang tot agendagegevens.
type: docs
weight: 14
url: /nl/java/project-file-operations/retrieve-calendar-info/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u agendagegevens uit Microsoft Project-bestanden kunt ophalen met behulp van de Aspose.Tasks voor Java-bibliotheek. Aspose.Tasks biedt krachtige functies om projectgegevens te manipuleren, inclusief toegang tot agendagegevens zoals werkdagen en uren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
- Basiskennis van Java-programmeren.
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Tasks voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).
## Pakketten importeren
Eerst moet u de benodigde pakketten in uw Java-code importeren om de Aspose.Tasks-functionaliteiten te gebruiken.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Laten we nu het gegeven voorbeeld in meerdere stappen opsplitsen voor een beter begrip.
## Stap 1: Stel de gegevensmap in
```java
String dataDir = "Your Data Directory";
```
 Vervangen`"Your Data Directory"` met het pad naar de map met projectbestanden.
## Stap 2: Definieer tijdseenheden
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Deze constanten vertegenwoordigen tijdseenheden in microseconden.
## Stap 3: Maak een projectinstantie
```java
Project project = new Project(dataDir + "project.mpp");
```
 Deze regel maakt een exemplaar van de`Project` klasse, initialiseer deze met het pad naar het projectbestand (`project.mpp`).
## Stap 4: Agenda-informatie ophalen
```java
CalendarCollection alCals = project.getCalendars();
```
Hier halen we een verzameling kalenders op die aanwezig zijn in het projectbestand.
## Stap 5: Herhaal de kalenders
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Kalenderinformatie
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Herhaal door weekdagen
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Tijd in milliseconden
            double time = ts / (OneHour); // Converteren naar uren
            if (wd.getDayWorking()) {
                // Werkdagen en -uren weergeven
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Deze lus doorloopt elke kalender en drukt de UID, naam en werkdagen met de respectieve werkuren af.
## Stap 6: Geef het voltooiingsbericht weer
```java
System.out.println("Process completed Successfully");
```
Ten slotte wordt er een bericht weergegeven dat de voltooiing van het proces aangeeft.
## Conclusie
In deze zelfstudie hebben we geleerd hoe u agendagegevens uit MS Project-bestanden kunt ophalen met Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u op efficiënte wijze projectgegevens in uw Java-applicaties benaderen en manipuleren.

## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks met andere programmeertalen gebruiken?
A: Ja, Aspose.Tasks ondersteunt meerdere platforms en programmeertalen, waaronder .NET, C++, Python en Java.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?
 A: Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?
A: U kunt ondersteuning krijgen van het Aspose.Tasks-communityforum[hier](https://forum.aspose.com/c/tasks/15).
### Vraag: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks?
 A: Ja, tijdelijke licenties zijn te koop[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Waar kan ik gedetailleerde documentatie voor Aspose.Tasks vinden?
 A: U kunt de documentatie raadplegen[hier](https://reference.aspose.com/tasks/java/).