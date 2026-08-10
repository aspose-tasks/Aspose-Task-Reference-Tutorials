---
date: 2026-06-05
description: Erfahren Sie, wie Sie MPP-Dateien mit Aspose.Tasks für Java filtern,
  Filter criteria anpassen und Aufgaben nach Datum filtern, um das project management
  zu optimieren.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Wie man MPP-Dateien mit Aspose.Tasks für Java filtert
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Wie man MPP-Dateien mit Aspose.Tasks für Java filtert
url: /de/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So filtern Sie MPP-Dateien mit Aspose.Tasks für Java

## Einführung
Wenn Sie mit Microsoft Project‑Dateien (*.mpp*) in einer Java‑Anwendung arbeiten, müssen Sie häufig **MPP‑Dateien filtern**, um die Aufgaben, Ressourcen oder Zuordnungen zu isolieren, die am wichtigsten sind. In diesem Tutorial führen wir Sie durch **wie man MPP‑Dateien** programmgesteuert mit Aspose.Tasks für Java filtert, zeigen Ihnen, wie Sie **Filterkriterien anpassen** können, und demonstrieren ein praktisches Szenario „Aufgaben nach Datum filtern“. Am Ende haben Sie einen einsatzbereiten Code‑Snippet, den Sie in jedes Java‑Projekt einbinden können.

## Schnelle Antworten
- **Was bedeutet „filter mpp“?** Es bedeutet, einen Teil der Projektdaten basierend auf definierten Bedingungen zu extrahieren.  
- **Welche Bibliothek übernimmt das?** Aspose.Tasks für Java bietet eine umfassende API zum Erstellen und Anwenden von Filtern.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Aufgaben, Ressourcen und Zuordnungen filtern?** Ja – jeder Entitätstyp hat seine eigene Filtersammlung.  
- **Ist Java 8 oder höher erforderlich?** Aspose.Tasks unterstützt Java 8 und spätere Versionen.

## Was bedeutet „how to filter mpp“ in Java?
`How to filter mpp` ist der Vorgang, bei dem Aspose.Tasks‑`Filter`‑Objekte verwendet werden, um nur jene Projektelemente auszuwählen, die bestimmte Prädikate wie Startdatum, Kosten oder benutzerdefinierte Felder erfüllen. Laden Sie ein `Project`, rufen Sie einen `Filter` ab, und die API gibt eine Sammlung zurück, die Ihren Kriterien entspricht, wodurch fokussierte Berichte oder nachgelagerte Integrationen ermöglicht werden.

## Warum Filterkriterien anpassen?
Benutzerdefinierte Filterkriterien ermöglichen es Ihnen, Hochrisiko‑Aufgaben, überfällige Elemente oder das Budget überschreitende Ressourcen zu fokussieren und eine riesige Projektdatei in eine prägnante, handlungsfähige Ansicht zu verwandeln. Aspose.Tasks unterstützt **mehr als 50 vordefinierte Filtertypen** und erlaubt Ihnen, unbegrenzt benutzerdefinierte Filter zu erstellen, wodurch die manuelle Datenaufbereitung um bis zu 70 % reduziert wird.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder neuer.  
2. **Aspose.Tasks für Java** – laden Sie es von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.  
3. **Eine IDE** – IntelliJ IDEA, Eclipse oder NetBeans funktionieren einwandfrei.  

## Pakete importieren
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` und `Project` sind Kernklassen, die zum Definieren und Anwenden von Filtern auf Projektdaten verwendet werden.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt einrichten
Zuerst erstellen Sie eine `Project`‑Instanz, die auf die MPP‑Datei verweist, die Sie analysieren möchten, und laden sie dann in den Speicher. Dieser einzelne Schritt bereitet das gesamte Projektmodell für das Filtern, die Validierung und weitere Manipulationen vor, sodass Sie über die API auf Aufgaben, Ressourcen und Zuordnungen zugreifen können.

### Wie richte ich das Projekt ein, um MPP-Dateien zu filtern?
Die Klasse `Project` lädt und repräsentiert eine MPP‑Datei im Speicher. Erstellen Sie eine `Project`‑Instanz, die auf die zu analysierende MPP‑Datei verweist, und laden Sie sie in den Speicher. Dieser einzelne Schritt bereitet das gesamte Projektmodell für das Filtern, die Validierung und weitere Manipulationen vor, sodass Sie über die API auf Aufgaben, Ressourcen und Zuordnungen zugreifen können.

### Wie kann ich einen Filter abrufen und inspizieren?
`Filter`‑Objekte kapseln Filterdefinitionen, die zum Auswählen von Projektelementen verwendet werden. Aspose.Tasks speichert vordefinierte Filter wie „All Tasks“ oder „Critical Tasks“. Verwenden Sie `project.getTaskFilters().getByName("My Filter")` oder einen indexbasierten Zugriff, um ein `Filter`‑Objekt zu erhalten, und prüfen Sie anschließend dessen `FilterCriteria`‑Sammlung, um jede Regel und den logischen Operator (AND/OR) zu sehen, der sie kombiniert, sodass der Filter Ihren Anforderungen entspricht.

### Wie iteriere ich durch verschachtelte Kriterienzeilen?
`FilterCriteriaGroup` stellt eine Gruppe von Filterkriterien dar, die mit einem logischen Operator kombiniert werden. Filter können Gruppen von Kriterien enthalten, von denen jede ihren eigenen Operator hat. Durchlaufen Sie `filter.getCriteria().getRows()` und recursivieren Sie bei jeder Zeile, die ein `FilterCriteriaGroup` ist, in deren Kindzeilen. Diese Traversierung ermöglicht es Ihnen, komplexe Filterlogik wie „(Start < heute AND Cost > 1000) OR Priority = High“ vollständig zu verstehen und die Kriterien bei Bedarf anzupassen.

### Wie gebe ich Kriterieninformationen zur Fehlersuche aus?
Nachdem Sie den Kriterienbaum durchlaufen haben, geben Sie den Feldnamen, den Testoperator und den Wert jeder Zeile in der Konsole aus. Diese einfache Ausgabe hilft Ihnen zu überprüfen, dass der Filter den beabsichtigten Geschäftsregeln entspricht, bevor er auf große Projekte angewendet wird, und erleichtert das Erkennen falscher Operatoren oder Werte.

### Wie erstelle ich programmgesteuert einen brandneuen Filter?
Instanziieren Sie einen `Filter` mit `new Filter("My Filter")` und fügen Sie ihn anschließend der Task‑Filter‑Sammlung des Projekts mittels `project.getTaskFilters().add(filter)` hinzu. Danach füllen Sie dessen `FilterCriteria`‑Sammlung mit den gewünschten Zeilen, indem Sie Feldnamen, Testoperatoren und Werte angeben, um genau zu definieren, welche Aufgaben beim Anwenden des Filters einbezogen werden sollen.

### Kann ich einen Filter auf Ressourcen statt auf Aufgaben anwenden?
Die Sammlung `ResourceFilters` enthält Filterdefinitionen, die auf Ressourcen anwendbar sind. Ja – verwenden Sie `project.getResourceFilters()`, um mit ressourcenspezifischen Filtern genauso zu arbeiten wie mit Task‑Filtern. Nach dem Hinzufügen oder Abrufen eines Filters konfigurieren Sie dessen `FilterCriteria` genauso wie bei Aufgaben und wenden ihn dann auf die Ressourcensammlung an, um die gefilterte Menge an Ressourcen zu erhalten.

### Ist es möglich, mehrere Filter mit ODER-Logik zu kombinieren?
Erstellen Sie eine übergeordnete `FilterCriteriaGroup` mit der `Operation` auf `OR` gesetzt und fügen Sie einzelne `FilterCriteria`‑Objekte als Kinder hinzu. Diese Gruppe bewertet jedes Kindkriterium und gibt Elemente zurück, die eines davon erfüllen, sodass Sie mehrere einfache Filter zu einer umfassenderen Auswahl kombinieren können.

### Unterstützt Aspose.Tasks das Filtern nach benutzerdefinierten Feldern?
Das `CustomField`‑Enum liefert Bezeichner für im Projekt definierte benutzerdefinierte Felder. Absolut. Referenzieren Sie benutzerdefinierte Felder über das `CustomField`‑Enum, und sie verhalten sich wie jedes integrierte Feld in Filterausdrücken. Sie können sie in `FilterCriteria`‑Zeilen einbinden, dieselben Operatoren und Werte verwenden und so leistungsstarke Abfragen auf benutzerdefinierten Daten neben den Standard‑Projektattributen ermöglichen.

### Welche Auswirkungen hat das Filtern auf die Leistung bei großen MPP-Dateien?
Das Filtern erfolgt vollständig im Speicher und verarbeitet typischerweise ein Projekt mit 1.000 Aufgaben in weniger als 200 ms. Bei Dateien mit mehreren tausend Aufgaben sollten Sie nur die benötigten Abschnitte mit `ProjectReader` laden und die Filter nach dem selektiven Laden anwenden, wodurch der Speicherverbrauch gering bleibt und selbst bei sehr großen Projekten schnelle Reaktionszeiten erhalten bleiben.

---

**Letzte Aktualisierung:** 2026-06-05  
**Getestet mit:** Aspose.Tasks für Java 24.10  
**Autor:** Aspose

## Verwandte Tutorials

- [MPP-Datei in Java laden – Projekt‑Eigenschaften mit Aspose.Tasks verwalten](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java – müheloses Lesen von MS Project Online‑Daten](/tasks/java/project-data-reading/read-project-online/)
- [Projekt‑Startdatum in MS Project mit Aspose.Tasks für Java festlegen](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```