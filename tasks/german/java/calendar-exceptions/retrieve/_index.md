---
date: 2026-08-24
description: Erfahren Sie, wie Sie Kalenderausnahmen in Java aus MS Project‑Dateien
  abrufen und wie Sie den mpp‑Kalender mit Aspose.Tasks für Java lesen. Dieses Tutorial
  bietet Schritt‑für‑Schritt‑Codebeispiele.
keywords:
- retrieve calendar exceptions java
- how to read mpp calendar
- Aspose.Tasks Java
- MS Project calendar API
lastmod: 2026-08-24
linktitle: Wie man Kalenderausnahmen in Java mit Aspose.Tasks abruft
og_description: Erfahren Sie, wie Sie Kalenderausnahmen in Java aus MS Project‑Dateien
  abrufen und den mpp‑Kalender mit Aspose.Tasks für Java lesen. Dieser Schritt‑für‑Schritt‑Leitfaden
  hilft Ihnen, eine präzise Kalenderverarbeitung in Ihre Java‑Anwendungen zu integrieren.
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: Wie man Kalenderausnahmen in Java mit Aspose.Tasks abruft
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: Wie man Kalenderausnahmen in Java mit Aspose.Tasks abruft
url: /de/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Kalenderausnahmen in Java mit Aspose.Tasks abruft

## Einleitung
In diesem **asp tasks java tutorial** lernen Sie, wie Sie Kalenderausnahmen aus einer Microsoft‑Project‑Datei mithilfe der Aspose.Tasks‑Bibliothek für Java abrufen. Kalenderausnahmen stellen nicht‑arbeitende Zeiträume wie Feiertage oder benutzerdefinierte Arbeitszeitregeln dar, und das programmgesteuerte Auslesen ist entscheidend für die Ressourcen‑Ausbalancierung, Berichterstellung und benutzerdefinierte Terminlogik. Wir führen Sie Schritt für Schritt durch den gesamten Prozess, sodass Sie diese Fähigkeit sicher in Ihre eigenen Java‑Anwendungen integrieren können.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Abrufen von Kalenderausnahmen aus einer MPP‑Datei mit Aspose.Tasks für Java.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für eine Grundkonfiguration.  
- **Voraussetzungen?** JDK, Aspose.Tasks für Java und eine IDE (IntelliJ IDEA oder Eclipse).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Unterstützte Project‑Versionen?** Alle gängigen MS‑Project‑Formate (MPP, MPT, XML).

## Was ist asp tasks java tutorial?
Das **asp tasks java tutorial** erklärt, wie die Aspose.Tasks‑API in Java‑Projekten verwendet wird. Es liefert konkrete Code‑Snippets, Best‑Practice‑Erklärungen und praxisnahe Szenarien, sodass Entwickler Projektdateien manipulieren können, ohne Microsoft Project installiert zu haben. Durch die Befolgung eines solchen Tutorials erhalten Entwickler ein klares, praxisnahes Verständnis der API‑Struktur, gängiger Nutzungsmuster und wie sie deren Funktionen in größere Unternehmensanwendungen integrieren können.

## Warum Kalenderausnahmen abrufen?
Das Abrufen von Kalenderausnahmen ermöglicht es Ihnen, präzise Projektzeitpläne zu erstellen, die Feiertage und benutzerdefinierte Arbeitspläne berücksichtigen, Berichtswerkzeuge zu bauen, die nicht‑arbeitende Tage hervorheben, und Project‑Kalender mit externen Systemen wie ERP‑ oder HR‑Plattformen zu synchronisieren. Aspose.Tasks kann Ausnahmen aus **30+** Kalendertypen lesen und unterstützt **3 wichtige** MS‑Project‑Dateiformate (MPP, MPT, XML), ohne die gesamte Datei in den Speicher zu laden, was eine effiziente Verarbeitung von Projekten mit mehreren hundert Seiten ermöglicht.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. **Java Development Kit (JDK)** – Stellen Sie sicher, dass JDK 8 oder höher installiert ist.  
2. **Aspose.Tasks for Java** – Laden Sie Aspose.Tasks für Java von der **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** herunter und installieren Sie es.  
3. **Integrated Development Environment (IDE)** – Sie können jede IDE Ihrer Wahl verwenden, z. B. IntelliJ IDEA oder Eclipse.

## Pakete importieren
Die Import‑Anweisungen bringen die Aspose.Tasks‑Klassen in Ihre Java‑Quelldatei, sodass Sie mit Projekten, Kalendern und Ausnahmen arbeiten können.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## Schritt 1: Datenverzeichnis einrichten
Definieren Sie einen Ordner, der die Projektdatei enthält, die Sie analysieren möchten. Die Verwendung eines absoluten Pfads oder eines Pfads relativ zu Ihrem Projekt‑Ressourcenordner verhindert `FileNotFoundException`.

```java
String dataDir = "C:/Projects/Data/";
```

> **Profi‑Tipp:** Speichern Sie Ihre Projektdateien in einem dedizierten Ressourcenordner und referenzieren Sie sie mit `Paths.get(...)` für plattformunabhängige Pfade.

## Schritt 2: MS‑Project‑Datei laden
Die Klasse `Project` repräsentiert eine MS‑Project‑Datei und bietet Zugriff auf deren Kalender, Aufgaben, Ressourcen und weitere Projektdaten. Laden Sie die Project‑Datei in ein `Project`‑Objekt. Dieses Objekt stellt die gesamte MS‑Project‑Datei im Speicher dar und ermöglicht den Zugriff auf Kalender, Aufgaben, Ressourcen und mehr.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Schritt 3: Kalenderausnahmen abrufen
Iterieren Sie über jeden Kalender im Projekt und anschließend über jede Kalenderausnahme innerhalb dieses Kalenders. Geben Sie das Start‑ und Enddatum jeder Ausnahme aus.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| **Keine Ausgabe** | Die Projektdatei enthält keine Kalenderausnahmen. | Überprüfen Sie, ob im Kalender von MS Project Ausnahmen definiert sind (z. B. Feiertage). |
| **`NullPointerException`** | Der Pfad `dataDir` ist falsch oder die Datei wurde nicht gefunden. | Überprüfen Sie den Verzeichnispfad und stellen Sie sicher, dass `project.mpp` existiert. |
| **Zeitzonen‑Abweichung** | Daten werden in UTC angezeigt. | Verwenden Sie `calExc.getFromDate().toLocalDateTime()`, um bei Bedarf in die lokale Zeit zu konvertieren. |

## Häufig gestellte Fragen
### Kann Aspose.Tasks verschiedene Versionen von MS‑Project‑Dateien verarbeiten?
Ja, Aspose.Tasks unterstützt **alle gängigen** MS‑Project‑Formate, einschließlich MPP, MPT und XML, für Versionen von 2000 bis zur neuesten Veröffentlichung.

### Gibt es eine kostenlose Testversion für Aspose.Tasks?
Ja, Sie können eine kostenlose Testversion von Aspose.Tasks von der **[Aspose free trial download page](https://releases.aspose.com/)** herunterladen.

### Wo finde ich die Dokumentation für Aspose.Tasks für Java?
Sie können die Dokumentation unter **[Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)** einsehen.

### Wie kann ich Support für Aspose.Tasks erhalten?
Sie erhalten Support im Community‑Forum **[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)**.

### Gibt es eine Option für temporäre Lizenzen für Aspose.Tasks?
Ja, temporäre Lizenzen können Sie über die **[temporary license purchase page](https://purchase.aspose.com/temporary-license/)** erwerben.

**Zusätzliche Fragen & Antworten**

**Q:** *Kann ich Kalenderausnahmen nach dem Abrufen ändern?*  
**A:** Absolut. Verwenden Sie `CalendarException.setFromDate()` und `setToDate()`, um Daten anzupassen, und speichern Sie das Projekt anschließend mit `project.save(...)`.

**Q:** *Behält Aspose.Tasks benutzerdefinierte Felder in Kalendern bei?*  
**A:** Ja, alle benutzerdefinierten Felder und erweiterten Attribute werden beim Laden und Speichern des Projekts beibehalten.

## Fazit
In diesem **asp tasks java tutorial** haben wir gelernt, wie man Kalenderausnahmen aus MS Project mit Aspose.Tasks für Java abruft. Durch das Befolgen dieser einfachen Schritte können Sie diese Funktion nahtlos in Ihre Java‑Anwendungen integrieren und damit umfangreichere Terminplanungsfunktionen sowie genauere Projektanalysen ermöglichen.

---

**Zuletzt aktualisiert:** 2026-08-24  
**Getestet mit:** Aspose.Tasks für Java 24.11  
**Autor:** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## Verwandte Tutorials

- [Benutzerdefinierte Kalenderausnahmen mit Aspose.Tasks für Java erstellen](/tasks/java/calendar-exceptions/)
- [Wie man Aspose.Tasks verwendet, um MS‑Project‑Kalenderinformationen abzurufen](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [Wie man Arbeitswochen in Java aus dem MS‑Project‑Kalender mit Aspose.Tasks liest](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}