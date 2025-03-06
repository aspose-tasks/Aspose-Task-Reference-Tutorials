---
title: Schrijf een MPP-projectsamenvatting in Aspose.Tasks
linktitle: Schrijf een MPP-projectsamenvatting in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u MPP-projectsamenvattingen schrijft in Java met behulp van Aspose.Tasks. Moeiteloos projectinformatie instellen en ophalen.
type: docs
weight: 27
url: /nl/java/project-file-operations/write-mpp-project-summary/
---
## Invoering
In deze zelfstudie leren we hoe u Aspose.Tasks voor Java kunt gebruiken om MPP-projectsamenvattingen te schrijven. Aspose.Tasks is een krachtige Java-bibliotheek voor het werken met Microsoft Project-bestanden. Door de onderstaande stappen te volgen, kunt u met behulp van deze bibliotheek verschillende samenvattende informatie over een project instellen en ophalen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java: Download en installeer de Aspose.Tasks voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Kies de IDE van uw voorkeur voor Java-ontwikkeling, zoals IntelliJ IDEA, Eclipse of NetBeans.

## Pakketten importeren
Importeer eerst de benodigde pakketten in uw Java-klasse:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Stap 1: Project instellen en samenvattende informatie definiëren
```java
// Het pad naar de documentenmap.
String dataDir = "Your Data Directory";
//Initialiseer een nieuw Project-object met het pad naar uw projectbestand
Project project = new Project(dataDir + "project.mpp");
// Stel samenvattende informatie over het project in
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Stel de aanmaakdatum van het project in
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Stel trefwoorden in voor het project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Stel de laatst afgedrukte datum van het project in
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Stap 2: Bewaar projectsamenvattingsinformatie
```java
// Sla het project weer op in MPP-indeling
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Geef een succesbericht weer
System.out.println("Process completed Successfully");
```
## Stap 3: Lees de projectsamenvattingsinformatie
```java
// Projectsamenvattingsinformatie lezen
project = new Project(dataDir + "MppAspose.xml");
// Print auteur van het project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Laatste auteur van het project afdrukken
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Druk het revisienummer van het project af
System.out.println("Revision: " + project.get(Prj.REVISION));
// Druk trefwoorden van het project af
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Opmerkingen over het project afdrukken
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Aanmaakdatum van het project afdrukken
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Trefwoorden van het project (opnieuw) afdrukken
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print de laatst afgedrukte datum van het project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Conclusie
In deze zelfstudie hebben we besproken hoe u MPP-projectsamenvattingen schrijft met Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u efficiënt verschillende samenvattende informatie over uw projectbestanden instellen en ophalen. Aspose.Tasks vereenvoudigt het proces van het werken met Microsoft Project-bestanden in Java-applicaties en biedt robuuste functionaliteit en gebruiksgemak.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor Java gebruiken met andere Java-bibliotheken?
A: Ja, Aspose.Tasks voor Java kan naadloos worden geïntegreerd met andere Java-bibliotheken om uw projectbeheermogelijkheden te verbeteren.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Vraag: Hoe vaak wordt Aspose.Tasks voor Java bijgewerkt?
A: Aspose.Tasks voor Java wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste versies van Java- en Microsoft Project-bestanden te garanderen.
### Vraag: Kan ik de samenvattingsinformatie van het project verder aanpassen?
A: Absoluut, Aspose.Tasks voor Java biedt uitgebreide opties voor het aanpassen van projectsamenvattingsinformatie volgens uw specifieke vereisten.
### Vraag: Waar kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
A: U kunt ondersteuning krijgen van het Aspose.Tasks-communityforum[hier](https://forum.aspose.com/c/tasks/15).