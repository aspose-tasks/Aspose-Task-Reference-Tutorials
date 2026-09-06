---
date: 2026-08-13
description: Erfahren Sie, wie Sie mit Aspose.Tasks einen Standard‑MS‑Project‑Kalender
  in Java erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie Sie einen Standard‑MS‑Project‑Kalender
  erstellen, ihn als Standard festlegen und die Datei speichern.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Standardkalender in Aspose.Tasks erstellen
og_description: Wie man in Java mit Aspose.Tasks einen Kalender erstellt. Erfahren
  Sie, wie Sie einen Standard‑MS‑Project‑Kalender erstellen, ihn als Standard festlegen
  und die Projektdatei in wenigen Minuten speichern.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Wie man einen Kalender erstellt – Standardkalender in Aspose.Tasks erstellen
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Wie man einen Kalender erstellt – Standardkalender in Aspose.Tasks erstellen
url: /de/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Kalender erstellt – Standardkalender in Aspose.Tasks

## Einleitung
In diesem Tutorial lernen Sie **wie man einen Kalender erstellt**-Objekte für Microsoft Project‑Dateien mit der Aspose.Tasks‑Bibliothek für Java. Wir führen Sie durch das Erstellen eines Standard‑MS‑Project‑Kalenders, das Festlegen als Standard‑Kalender und das Speichern der Projektdatei. Am Ende des Leitfadens können Sie die Kalendererstellung in jede Java‑basierte Projektmanagement‑Lösung integrieren.

## Schnelle Antworten
- **Was bedeutet „Standardkalender“?** Es ist die standardmäßige Arbeitszeitdefinition, die auf Aufgaben angewendet wird, die keinen benutzerdefinierten Kalender zugewiesen haben.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java – eine reine Java‑API, die ohne installierten Microsoft Project funktioniert.  
- **Brauche ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welches Dateiformat wird erzeugt?** Eine XML‑basierte Microsoft‑Project‑Datei (`.xml`).  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für eine einfache Kalendereinrichtung.

## Was ist ein Standardkalender in Microsoft Project?
Ein Standardkalender definiert die standardmäßigen Arbeitstage und -stunden für ein Projekt, typischerweise Montag bis Freitag, 8 Uhr bis 17 Uhr. Wenn Sie einen Standardkalender hinzufügen, erbt jede Aufgabe, der kein benutzerdefinierter Kalender zugewiesen ist, diese Arbeitszeiten, wodurch eine konsistente Terminplanung im gesamten Projekt gewährleistet wird.

## Warum Aspose.Tasks zur Erstellung eines Kalenders verwenden?
Aspose.Tasks für Java unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann Projekte mit bis zu **10.000 Aufgaben** verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Diese reine Java‑Bibliothek ermöglicht es Ihnen, die Erstellung von Project‑Dateien auf Servern, CI‑Pipelines oder in jeder Java‑Anwendung zu automatisieren und so die Notwendigkeit einer lizenzierten Microsoft‑Project‑Installation zu eliminieren.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Folgendes vorhanden ist:

### Installation des Java Development Kit (JDK)
Installieren Sie das neueste JDK von der Oracle‑Website oder einer OpenJDK‑Distribution.

### Aspose.Tasks für Java Bibliothek
Laden Sie die Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter. Fügen Sie die JAR‑Datei dem Klassenpfad Ihres Projekts hinzu.

## Pakete importieren
Für dieses Tutorial benötigen wir nur einen Import:

```java
import com.aspose.tasks.*;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis einrichten
Definieren Sie, wo die erzeugte Projektdatei gespeichert werden soll.

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad auf Ihrem Rechner (z. B. `C:/Projects/Output/`).

### Schritt 2: Projektinstanz erstellen
`Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne Microsoft‑Project‑Datei im Speicher repräsentiert. Durch die Instanziierung erhalten Sie einen Container für Kalender, Aufgaben, Ressourcen und weitere Projektdaten.

```java
Project project = new Project();
```

### Schritt 3: Kalender definieren und zum Standard machen
`Calendar` ist die Klasse, die einen Arbeitszeitplan modelliert. Durch Hinzufügen eines neuen Kalenders mit dem Namen **„My Cal“** und dem Aufruf von `makeStandardCalendar` wird er zum Standardkalender für das gesamte Projekt.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Pro‑Tipp:** Die Methode `makeStandardCalendar` markiert den übergebenen Kalender automatisch als Standard für das Projekt, was genau das ist, was Sie benötigen, wenn Sie die **Standardkalender**‑Funktionalität hinzufügen möchten.

### Schritt 4: Projekt speichern
SaveFileFormat ist eine Aufzählung, die das beim Speichern eines Projekts zu verwendende Dateiformat angibt.  
Speichern Sie das Projekt (einschließlich des neuen Kalenders) in einer XML‑Datei.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Sie können den Dateinamen oder das Format (`SaveFileFormat.Pp`) ändern, wenn Sie eine andere Project‑Version bevorzugen.

### Schritt 5: Abschlussnachricht anzeigen
Geben Sie sich einen visuellen Hinweis darauf, dass der Vorgang fehlerfrei abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|-------|-------|-----|
| **Datei nicht gefunden** | `dataDir` verweist auf einen nicht vorhandenen Ordner | Erstellen Sie den Ordner oder verwenden Sie einen absoluten Pfad |
| **Lizenzausnahme** | Ausführung ohne gültige Aspose.Tasks‑Lizenz in der Produktion | Legen Sie eine Lizenzdatei fest mittels `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Leerer Kalender** | Vergessen, Arbeitszeitdefinitionen hinzuzufügen | Verwenden Sie `cal1.getWeekDays().add(WeekDay.DayType.Monday)` usw., falls Sie benutzerdefinierte Stunden benötigen |

## Häufig gestellte Fragen

**F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?**  
A: Ja, Aspose.Tasks unterstützt eine breite Palette von Microsoft‑Project‑Versionen, von 2000 bis zu den neuesten Releases.

**F: Kann ich die Kalendereinstellungen weiter anpassen?**  
A: Absolut! Sie können Arbeitstage ändern, Ausnahmen hinzufügen und spezifische Arbeitszeiten mit den Klassen `WeekDay` und `WorkingTime` definieren.

**F: Ist Aspose.Tasks für Unternehmens‑Anwendungen geeignet?**  
A: Auf jeden Fall. Die Bibliothek ist für Hochleistungs‑ und skalierbare Umgebungen konzipiert und bietet umfassende Unterstützung für große Project‑Dateien.

**F: Bietet Aspose.Tasks technischen Support für Entwickler?**  
A: Ja, Aspose stellt dedizierte Foren, ticketbasierten Support und umfangreiche Dokumentation bereit, um Ihnen bei der schnellen Lösung von Problemen zu helfen.

**F: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion auf der [Website](https://purchase.aspose.com/buy) ausprobieren, die es Ihnen ermöglicht, alle Funktionen vor einer Verpflichtung zu bewerten.

---

**Zuletzt aktualisiert:** 2026-08-13  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Kalender zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/calendars/create/)
- [Projektkalender in Java mit Aspose.Tasks festlegen](/tasks/java/calendars/properties/)
- [Benutzerdefinierte Kalenderaussnahmen mit Aspose.Tasks für Java erstellen](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}