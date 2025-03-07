---
title: Schrijf bijgewerkte brongegevens in Aspose.Tasks
linktitle: Schrijf bijgewerkte brongegevens in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u moeiteloos brongegevens in MS Project-bestanden kunt bijwerken met Aspose.Tasks voor Java.
weight: 21
url: /nl/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Schrijf bijgewerkte brongegevens in Aspose.Tasks

## Invoering
In deze zelfstudie begeleiden we u bij het bijwerken van Microsoft Project-brongegevens met Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java API waarmee u Microsoft Project-bestanden kunt manipuleren zonder dat Microsoft Project op uw systeem hoeft te worden geïnstalleerd.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2.  Aspose.Tasks voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/java/).
3. Basiskennis van Java-programmeren.

## Pakketten importeren

Eerst moet u de benodigde pakketten importeren om met Aspose.Tasks in uw Java-code te kunnen werken. Voeg de volgende importinstructies toe aan uw Java-bestand:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Stap 1: Stel uw gegevensdirectory in

Definieer de map waar uw gegevensbestanden zich bevinden:

```java
String dataDir = "Your Data Directory";
```

## Stap 2: Geef invoer- en uitvoerbestanden op

Definieer de paden voor het invoer-MS Project-bestand en het resulterende bijgewerkte bestand:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Testbestand met één rsc om bij te werken
String resultFile = dataDir + "OutputMPP.mpp"; // Bestand om testproject te schrijven
```

## Stap 3: Laad het project

 Laad het MS Project-bestand in een`Project` voorwerp:

```java
Project project = new Project(file);
```

## Stap 4: Voeg een resource toe en stel attributen in

Voeg een nieuwe resource toe aan het project en stel de kenmerken ervan in, zoals standaardtarief, overurentarief en groep:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Stap 5: Sla het project op

Sla het bijgewerkte project op met de gewijzigde resourcegegevens:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusie

In deze zelfstudie hebben we gedemonstreerd hoe u MS Project-brongegevens kunt bijwerken met Aspose.Tasks voor Java. Door deze stappen te volgen, kunt u efficiënt broninformatie in uw MS Project-bestanden programmatisch manipuleren.

## Veelgestelde vragen

### V1: Kan ik meerdere bronnen in hetzelfde project bijwerken met Aspose.Tasks voor Java?

A1: Ja, u kunt meerdere bronnen bijwerken door ze te doorlopen en hun kenmerken dienovereenkomstig in te stellen.

### V2: Ondersteunt Aspose.Tasks naast MS Project ook andere bestandsformaten?

A2: Ja, Aspose.Tasks ondersteunt verschillende bestandsformaten, waaronder XML, MPP en meer.

### V3: Is Aspose.Tasks compatibel met verschillende versies van Java?

A3: Aspose.Tasks is compatibel met Java-versies 6 en hoger.

### V4: Kan ik andere bewerkingen uitvoeren op MS Project-bestanden met Aspose.Tasks?

A4: Ja, u kunt een breed scala aan bewerkingen uitvoeren, zoals lezen, schrijven en manipuleren van taken, bronnen en agenda's.

### V5: Waar kan ik aanvullende hulp of ondersteuning vinden voor Aspose.Tasks?

 A5: U kunt de bezoeken[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor eventuele hulp of vragen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
