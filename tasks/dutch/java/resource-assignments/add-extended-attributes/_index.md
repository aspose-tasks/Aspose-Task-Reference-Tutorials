---
title: Beheersing van MS-projectmanipulatie met Aspose.Tasks voor Java
linktitle: Voeg uitgebreide kenmerken toe aan resourcetoewijzingen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u efficiënt MS Project-informatie kunt schrijven met Aspose.Tasks voor Java. Stapsgewijze handleiding voor Java-ontwikkelaars.
weight: 10
url: /nl/java/resource-assignments/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheersing van MS-projectmanipulatie met Aspose.Tasks voor Java

## Invoering
In deze zelfstudie gaan we dieper in op het gebruik van Aspose.Tasks voor Java, een krachtige bibliotheek voor het programmatisch manipuleren van Microsoft Project-bestanden. We zullen ons concentreren op een fundamentele taak: het schrijven van MS Project-informatie met behulp van Aspose.Tasks. Of u nu een doorgewinterde ontwikkelaar bent of net begint met programmeren in Java, deze gids begeleidt u stap voor stap door het proces.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd.
2.  Aspose.Tasks voor Java-bibliotheek: Download en installeer de Aspose.Tasks voor Java-bibliotheek. U kunt deze verkrijgen bij[hier](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Kies een IDE van uw voorkeur. Wij raden IntelliJ IDEA of Eclipse aan.

## Pakketten importeren
Importeer eerst de benodigde pakketten in uw Java-project:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```
#Laten we het gegeven voorbeeld in meerdere stappen opsplitsen:
## Stap 1: Gegevensmap instellen
Definieer de map waarin uw projectgegevens worden opgeslagen.
```java
String dataDir = "Your Data Directory";
```
## Stap 2: Projectinstantie maken
Initialiseer een nieuw projectexemplaar.
```java
Project project = new Project();
```
## Stap 3: Stel de projectinformatie-eigenschappen in
Stel eigenschappen voor het project in, zoals startdatum, planning vanaf start en statusdatum.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## Stap 4: Project opslaan als XML
Sla het project met de bijgewerkte informatie op als XML-bestand.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u MS Project-informatie kunt schrijven met Aspose.Tasks voor Java. Met deze nieuwe kennis kunt u verschillende taken met betrekking tot Microsoft Project-bestanden automatiseren, waardoor uw productiviteit als Java-ontwikkelaar toeneemt.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor Java gebruiken om MS Project-bestanden te lezen?
A: Ja, Aspose.Tasks voor Java biedt robuuste functionaliteiten voor zowel het lezen als schrijven van MS Project-bestanden.
### Vraag: Is Aspose.Tasks voor Java compatibel met verschillende versies van MS Project?
A: Absoluut, Aspose.Tasks voor Java ondersteunt verschillende versies van MS Project, waardoor compatibiliteit tussen verschillende bestandsformaten wordt gegarandeerd.
### Vraag: Zijn er beperkingen voor de proefversie van Aspose.Tasks voor Java?
A: Hoewel u met de proefversie de mogelijkheden van de bibliotheek kunt verkennen, kent deze bepaalde beperkingen, zoals watermerken op uitvoerbestanden.
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor Java?
 A: U kunt hulp zoeken op het Aspose.Tasks-communityforum[hier](https://forum.aspose.com/c/tasks/15).
### Vraag: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks voor Java?
 A: Ja, er zijn tijdelijke licenties beschikbaar voor gebruik op korte termijn. U kunt er één verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
