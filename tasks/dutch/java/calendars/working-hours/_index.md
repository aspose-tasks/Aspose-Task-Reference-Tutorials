---
title: Haal werkuren op uit Agenda met Aspose.Tasks
linktitle: Haal werkuren op uit Agenda met Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Haal eenvoudig werkuren uit MS Project-kalenders met Aspose.Tasks voor Java. Vereenvoudig projectbeheertaken.
weight: 13
url: /nl/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Haal werkuren op uit Agenda met Aspose.Tasks

## Invoering
Het beheren van projectkalenders en het extraheren van werkuren is essentieel voor effectief projectmanagement. Aspose.Tasks voor Java biedt robuuste functionaliteit om moeiteloos werkuren uit MS Project-agenda's op te halen. In deze tutorial begeleiden wij u stap voor stap door het proces.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2.  Aspose.Tasks voor de Java-bibliotheek gedownload en toegevoegd aan uw project. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).
3. Basiskennis van de Java-programmeertaal.
## Pakketten importeren
Importeer eerst de benodigde pakketten om met Aspose.Tasks voor Java te werken:
```java
import com.aspose.tasks.*;
```
## Stap 1: Projectbestand laden
Begin met het laden van uw MS Project-bestand:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Stap 2: Taak- en agenda-informatie ophalen
Extraheer taak- en kalendergegevens uit het project:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Stap 3: Definieer de begin- en einddatum
Stel begin- en einddatums voor de taak in:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Stap 4: Herhaal de datums
Doorloop datums binnen de taakduur:
```java
java.util.Calendar tempDate = calStartDate;
```
## Stap 5: Bereken de duur
Bereken de duur in minuten, uren en dagen:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Conclusie
In deze zelfstudie hebben we besproken hoe u werkuren kunt ophalen uit een MS Project-agenda met behulp van Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u projectplanningen efficiënt beheren en eenvoudig de taakduur berekenen.
## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks voor Java complexe projectstructuren aan?
A: Ja, Aspose.Tasks voor Java biedt uitgebreide ondersteuning voor het omgaan met complexe projectstructuren, inclusief taken, bronnen en kalenders.
### Vraag: Is Aspose.Tasks voor Java compatibel met verschillende versies van MS Project?
A: Absoluut, Aspose.Tasks voor Java ondersteunt verschillende versies van MS Project, waardoor compatibiliteit tussen verschillende omgevingen wordt gegarandeerd.
### Vraag: Kan ik werktijden en vakantiedagen in projectkalenders aanpassen?
A: Ja, u kunt werktijden en vakantiedagen eenvoudig aanpassen aan uw projectvereisten met behulp van Aspose.Tasks voor Java API's.
### Vraag: Biedt Aspose.Tasks voor Java ondersteuning en documentatie?
A: Ja, Aspose.Tasks voor Java biedt uitgebreide documentatie en speciale ondersteuningsforums om ontwikkelaars te helpen de functies ervan effectief te gebruiken.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt toegang krijgen tot een gratis proefversie van Aspose.Tasks voor Java vanaf[hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
