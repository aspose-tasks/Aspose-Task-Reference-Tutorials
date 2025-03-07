---
title: Genereer tijdgebonden gegevens in Aspose.Tasks
linktitle: Genereer tijdgebonden gegevens voor resourcetoewijzingen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u tijdgebonden gegevens genereert voor resourcetoewijzingen met Aspose.Tasks voor Java. Verbeter de efficiëntie van projectmanagement met deze uitgebreide gids.
weight: 24
url: /nl/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer tijdgebonden gegevens in Aspose.Tasks

## Invoering
In deze zelfstudie doorlopen we het proces van het genereren van tijdgebonden gegevens voor resourcetoewijzingen met behulp van Aspose.Tasks voor Java. Tijdgebonden gegevens bieden waardevolle inzichten in de manier waarop resources in de loop van de tijd binnen een project worden toegewezen, waardoor projectmanagers weloverwogen beslissingen kunnen nemen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd. U kunt JDK downloaden en installeren vanaf[hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks voor Java-bibliotheek: u hebt de Aspose.Tasks voor Java-bibliotheek nodig. Je kunt het downloaden van de[website](https://releases.aspose.com/tasks/java/).

## Pakketten importeren
Laten we eerst de benodigde pakketten importeren om met Aspose.Tasks te werken:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Stap 1: Lees het bron-MPP-bestand
```java
// Het pad naar de documentenmap.
String dataDir = "Your Data Directory";
// Lees het bron-MPP-bestand
Project project = new Project(dataDir + "project.mpp");
```
## Stap 2: Taak- en resourcetoewijzing ophalen
```java
// Verkrijg de eerste taak van het project
Task task = project.getRootTask().getChildren().getById(1);
// Haal de eerste resourcetoewijzing van het project op
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Stap 3: Genereer tijdgebonden gegevens met platte contouren
```java
// Platte contour is de standaardcontour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Stap 4: Verander de contour in Schildpad
```java
// Verander de contour naar Schildpad
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Stap 5: Wijzig Contour in BackLoaded
```java
// Wijzig de contour naar BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Stap 6: Wijzig Contour in FrontLoaded
```java
// Wijzig contour naar FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Stap 7: Verander de contour in Bell
```java
// Verander de contour naar Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Stap 8: Verander Contour naar EarlyPeak
```java
// Wijzig de contour naar EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Stap 9: Wijzig Contour in LatePeak
```java
// Wijzig de contour naar LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Stap 10: Wijzig de contour in DoublePeak
```java
// Wijzig de contour naar DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Conclusie
In deze zelfstudie hebben we besproken hoe u tijdgebonden gegevens kunt genereren voor resourcetoewijzingen met behulp van Aspose.Tasks voor Java. Het begrijpen van verschillende werkcontouren kan projectmanagers helpen de toewijzing van middelen en planning in hun projecten effectief te beheren.
## Veelgestelde vragen
### Kan ik Aspose.Tasks gebruiken met andere Java-bibliotheken?
Ja, Aspose.Tasks kan worden geïntegreerd met andere Java-bibliotheken om de mogelijkheden voor projectbeheer te verbeteren.
### Is Aspose.Tasks geschikt voor grootschalige ondernemingsprojecten?
Absoluut, Aspose.Tasks is ontworpen voor projecten van elke omvang, inclusief grootschalige ondernemingsprojecten.
### Biedt Aspose.Tasks ondersteuning voor verschillende projectbestandsformaten?
Ja, Aspose.Tasks ondersteunt verschillende projectbestandsindelingen, waaronder MPP, XML en MPX.
### Kan ik de werkcontouren aanpassen aan mijn projectvereisten?
Ja, met Aspose.Tasks kunnen gebruikers aangepaste werkcontouren definiëren die passen bij hun specifieke projectbehoeften.
### Is er een communityforum waar ik hulp kan krijgen bij Aspose.Tasks?
 Ja, u kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor ondersteuning en discussies.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
