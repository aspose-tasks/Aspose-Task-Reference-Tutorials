---
title: Taak Tijdgebonden gegevens in Aspose.Tasks
linktitle: Taak Tijdgebonden gegevens in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Ontdek Aspose.Tasks voor Java en beheer taaktijdgebonden gegevensbeheer. Download de bibliotheek, profiteer van een gratis proefperiode en stroomlijn het bijhouden van uw projecten.
type: docs
weight: 34
url: /nl/java/task-properties/task-timephased-data/
---
## Invoering
Op het gebied van projectmanagement is het nauwkeurig volgen van tijdgebonden taakgegevens cruciaal voor een efficiënte projectuitvoering. Aspose.Tasks voor Java komt naar voren als een krachtig hulpmiddel om dit proces te stroomlijnen en biedt robuuste functies en flexibiliteit. Deze tutorial begeleidt u bij het gebruik van Aspose.Tasks voor Java om tijdgebonden taakgegevens effectief te beheren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java-ontwikkelomgeving: Zorg ervoor dat Java op uw systeem is geïnstalleerd.
-  Aspose.Tasks voor Java-bibliotheek: Download de Aspose.Tasks-bibliotheek en neem deze op in uw project. Je kunt de bibliotheek vinden[hier](https://releases.aspose.com/tasks/java/).
- Documentmap: Stel een map in voor uw projectdocumenten.
## Pakketten importeren
Importeer in uw Java-project de benodigde pakketten voor Aspose.Tasks:
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
## Stap 1: Stel de startdatum van het project in
```java
Project project = new Project(dataDir + "project.xml");
// Aanvullende code voor pakketimport
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Uitleg: Initialiseer een kalenderobject, stel de startdatum in en pas dit toe op het project.
## Stap 2: Taak en resource definiëren
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Uitleg: Maak een taak en resource aan en stel tarieven in voor standaard- en overuren.
## Stap 3: Stel de taakduur in
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Toelichting: Definieer de duur van de taak (bijvoorbeeld 6 dagen).
## Stap 4: Wijs een resource toe aan een taak
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Verklaring: Wijs de resource toe aan de taak.
## Stap 5: Resourcetoewijzing configureren
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Verklaring: Stel parameters zoals stoppen, hervatten en werkcontour voor de resourcetoewijzing in.
## Stap 6: Basislijn instellen
```java
project.setBaseline(BaselineType.Baseline);
```
Uitleg: Stel een basislijn voor het project vast.
## Stap 7: Voltooiing van taak bijwerken
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Toelichting: Geef het voltooiingspercentage van de taak aan.
## Stap 8: Tijdgebonden gegevens ophalen
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Uitleg: Tijdgebonden gegevens ophalen voor het resterende werk van de opdracht.
## Stap 9: Tijdgebonden gegevens weergeven
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Aanvullende code voor het weergeven van andere waarden
```
Uitleg: Voer de tijdgebonden gegevens uit en geef ze weer.
## Conclusie
Het effectief beheren van tijdgebonden taakgegevens is onmisbaar voor het succes van projecten. Aspose.Tasks voor Java vereenvoudigt dit proces en biedt een uitgebreide reeks functionaliteiten. Door deze tutorial te volgen, kunt u Aspose.Tasks naadloos integreren in uw Java-project, waardoor u nauwkeurige controle krijgt over de projecttijdlijnen en de toewijzing van middelen.
## Veel Gestelde Vragen
### Vraag: Kan ik Aspose.Tasks voor Java in elk Java-project gebruiken?
A: Ja, Aspose.Tasks voor Java is compatibel met elk op Java gebaseerd project.
### Vraag: Waar kan ik aanvullende ondersteuning vinden voor Aspose.Tasks voor Java?
 A: Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor ondersteuning en discussies.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt een gratis proefperiode uitproberen[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Tasks voor Java?
 A: U kunt een tijdelijke licentie aanschaffen[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Waar kan ik Aspose.Tasks voor Java kopen?
 A: U kunt Aspose.Tasks voor Java kopen[hier](https://purchase.aspose.com/buy).