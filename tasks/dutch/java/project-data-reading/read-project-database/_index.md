---
title: Projectgegevens uit MS Project Database lezen in Aspose.Tasks
linktitle: Projectgegevens uit Microsoft Project Database lezen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u projectgegevens uit Microsoft Project Database leest met Aspose.Tasks voor Java. Stapsgewijze handleiding met codevoorbeelden.
weight: 12
url: /nl/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projectgegevens uit MS Project Database lezen in Aspose.Tasks

## Invoering
In deze zelfstudie onderzoeken we hoe u projectgegevens uit een Microsoft Project Database kunt lezen met Aspose.Tasks voor Java. Aspose.Tasks is een krachtige Java API waarmee ontwikkelaars Microsoft Project-documenten kunnen manipuleren zonder dat Microsoft Project hoeft te worden geïnstalleerd. Door de stappen in deze handleiding te volgen, leert u hoe u projectgegevens efficiënt uit een database kunt extraheren en in de gewenste indeling kunt opslaan.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Basiskennis van Java-programmeren.
2. Java Development Kit (JDK) op uw systeem geïnstalleerd.
3. Aspose.Tasks voor de Java-bibliotheek gedownload en geconfigureerd in uw project.

## Pakketten importeren
Importeer om te beginnen de benodigde pakketten:
```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```
## Stap 1: Databaseverbinding instellen
Eerst moet u de verbinding met de Microsoft Project Database instellen. Dit omvat het opgeven van de database-URL, servernaam, poortnummer, databasenaam, gebruikersnaam en wachtwoord.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Stap 2: Voeg JDBC-stuurprogramma toe
Vervolgens moet u het JDBC-stuurprogramma aan uw project toevoegen. Dit stuurprogramma vergemakkelijkt de communicatie tussen Java-applicaties en de Microsoft SQL Server-database.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Stap 3: Projectgegevens lezen
 Maak nu een`Project` object en laad projectgegevens uit de database met behulp van de eerder gedefinieerde instellingen.
```java
Project project = new Project(settings);
```
## Stap 4: Projectgegevens opslaan
Sla ten slotte de projectgegevens op in een gewenst formaat. In dit voorbeeld slaan we het op als een XML-bestand.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Gefeliciteerd! U hebt met succes projectgegevens uit een Microsoft Project Database gelezen met Aspose.Tasks voor Java.

## Conclusie
In deze zelfstudie hebben we het proces besproken van het lezen van projectgegevens uit een Microsoft Project Database met behulp van Aspose.Tasks voor Java. Door de beschreven stappen te volgen, kunt u naadloos projectinformatie extraheren en manipuleren volgens uw vereisten. Aspose.Tasks vereenvoudigt de verwerking van Microsoft Project-documenten, waardoor efficiënte gegevensextractie en -manipulatie mogelijk wordt.
## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks worden gebruikt om projectgegevens uit andere databases dan Microsoft Project te lezen?
A: Ja, Aspose.Tasks ondersteunt het lezen van projectgegevens uit verschillende bronnen, waaronder XML-bestanden, Primavera en Microsoft Project-databases.
### Vraag: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project?
A: Ja, Aspose.Tasks is ontworpen om met verschillende versies van Microsoft Project te werken, waardoor compatibiliteit en naadloze integratie worden gegarandeerd.
### Vraag: Kan ik de projectgegevens manipuleren voordat ik deze opsla?
A: Absoluut, Aspose.Tasks biedt een breed scala aan functies voor het manipuleren van projectgegevens, zoals het toevoegen van taken, het bijwerken van bronnen en het instellen van projecteigenschappen.
### Vraag: Ondersteunt Aspose.Tasks meerdere uitvoerformaten?
A: Ja, Aspose.Tasks ondersteunt verschillende uitvoerformaten, waaronder XML, PDF, HTML en afbeeldingsformaten zoals PNG en JPEG.
### Vraag: Waar kan ik verdere ondersteuning of hulp vinden met Aspose.Tasks?
 A: Voor aanvullende ondersteuning of assistentie kunt u het Aspose.Tasks-forum bezoeken of de documentatie raadplegen die beschikbaar is op de website[hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
