---
date: 2026-11-06
description: Erstellen Sie mühelos custom calendar exceptions, integrieren Sie den
  MS Project calendar und verwalten, definieren, bearbeiten & abrufen von calendar
  exceptions in Java projects mit Aspose.Tasks. Optimieren Sie project workflows für
  ein effizientes project management.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Calendar Exceptions
og_description: Erfahren Sie, wie Sie calendar exceptions in Java mit Aspose.Tasks
  erstellen. Verwalten Sie project calendars, setzen Sie nonworking days und passen
  Sie MS Project calendars effizient an.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Calendar Exceptions mit Aspose.Tasks für Java erstellen
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Wie man Calendar Exceptions mit Aspose.Tasks für Java erstellt
url: /de/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Kalenderausnahmen mit Aspose.Tasks für Java erstellt

## Einführung

`Aspose.Tasks` ist eine Java-Bibliothek, die die programmgesteuerte Erstellung, Manipulation und Konvertierung von Microsoft Project‑Dateien ermöglicht. In diesem Tutorial lernen Sie, wie Sie **Kalenderausnahmen erstellen** – benutzerdefinierte Nicht‑Arbeitstage, die den Standardkalender eines Projekts überschreiben. Eine präzise Kontrolle über Arbeits‑ und Nicht‑Arbeitstage ist entscheidend für genaue Terminprognosen, Ressourcenzuweisung und die Einhaltung regionaler Feiertage. Am Ende dieses Leitfadens wissen Sie außerdem, wie Sie **einen MS Project‑Kalender** in Ihre Java‑Anwendung integrieren und dessen Ausnahmen abrufen oder ändern können.

## Schnelle Antworten
- **Was kann ich erreichen?** Erstellen, ändern und abrufen benutzerdefinierter Kalenderausnahmen in Java‑Projekten.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (neueste stabile Version).  
- **Benötige ich eine Lizenz?** Ja, eine gültige Aspose.Tasks‑Lizenz ist für den Produktionseinsatz erforderlich.  
- **Kann ich mit MS Project‑Dateien arbeiten?** Absolut – Sie können MS Project‑Kalenderdaten importieren, bearbeiten und exportieren.  
- **Ist eine spezielle Einrichtung erforderlich?** Fügen Sie einfach die Aspose.Tasks‑JAR zu Ihrem Klassenpfad hinzu und importieren Sie die relevanten Klassen.

## Wie erstellt man benutzerdefinierte Kalenderausnahmen in Aspose.Tasks für Java?

Um benutzerdefinierte Kalenderausnahmen in Aspose.Tasks für Java zu erstellen, laden Sie das Ziel‑Project, rufen dessen Calendar ab, definieren das Start‑ und Enddatum der Ausnahme mit der gewünschten Arbeitszeit, setzen optional ein Wiederholungsmuster und speichern anschließend das Projekt. Diese Sequenz fügt die Ausnahme sofort hinzu und speichert sie in der .mpp‑Datei.

`Project`‑Klasse ist das primäre Objekt von Aspose.Tasks, das eine gesamte Microsoft‑Project‑Datei modelliert. Die `Project`‑Klasse stellt eine Microsoft‑Project‑Datei dar und bietet Zugriff auf deren Inhalt. Das `Calendar`‑Objekt definiert Arbeits‑ und Nicht‑Arbeitszeiten für das Projekt. Die `Calendar`‑Klasse ist der Container für alle Arbeitszeit‑Regeln, einschließlich Ausnahmen. Die Methode `addException()` fügt dem Kalender eine neue Kalenderausnahme hinzu. `addException()` ist eine Ein‑Aufruf‑API, die einen Nicht‑Arbeit‑Zeitraum für den angegebenen Datumsbereich registriert.

Laden Sie das Ziel‑Projekt mit `Project project = new Project("example.mpp")`, holen Sie dessen `Calendar`‑Objekt und rufen Sie `addException()` mit dem gewünschten Datumsbereich und den Arbeitszeiteinstellungen auf. Dieses Zwei‑Schritt‑Muster erstellt sofort eine neue Ausnahme und speichert sie, wenn Sie das Projekt speichern. Für wiederkehrende Feiertage konfigurieren Sie das `RecurrencePattern` der Ausnahme vor dem Speichern.

Das Erstellen von Kalenderausnahmen auf diese Weise ermöglicht es Ihnen, **Nicht‑Arbeitstage** präzise festzulegen, egal ob es sich um einmalige Stilllegungen oder jährliche Feiertage handelt. Nachdem die Ausnahme hinzugefügt wurde, können Sie `project.save("updated.mpp")` aufrufen, um die Änderungen auf die Festplatte zu schreiben.

### Überblick über die Schritte
1. Laden Sie die Projektdatei.  
2. Rufen Sie eine `Calendar`‑Instanz ab oder erstellen Sie sie.  
3. Definieren Sie den Datumsbereich und die Arbeitszeit der Ausnahme.  
4. (Optional) Konfigurieren Sie die Wiederholung für jährliche Feiertage.  
5. Speichern Sie das Projekt.

## Kalenderausnahmen in Aspose.Tasks verwalten
[Erfahren Sie, wie Sie Kalenderausnahmen in Aspose.Tasks für Java effizient hinzufügen und entfernen](./add-remove/). Im Projektmanagement ist Flexibilität entscheidend. Aspose.Tasks ermöglicht es Ihnen, Kalenderausnahmen mühelos zu verwalten und dynamische Anpassungen an Projektzeitplänen vorzunehmen. Dieses Tutorial bietet eine Schritt‑für‑Schritt‑Anleitung, damit Sie den Prozess effizient verstehen. Entdecken Sie, wie Sie Ihre Projektmanagement‑Workflows mit Leichtigkeit verbessern können.

## Wochentage für Kalenderausnahmen mit Aspose.Tasks definieren
[Meistern Sie die Kunst, Wochentage für Kalenderausnahmen in Java‑Projekten zu definieren](./define-weekdays/) mit Aspose.Tasks. Eine genaue Projektplanung erfordert sorgfältige Detailgenauigkeit. Mit Aspose.Tasks können Sie Wochentage für Kalenderausnahmen präzise festlegen, sodass Ihre Projekte nahtlos mit spezifischen Zeitplänen übereinstimmen. Dieses Tutorial vermittelt Ihnen das Wissen, um die Planung zu optimieren und Ihnen Kontrolle über Projektzeitpläne zu geben.

## Vorkommnisse in Kalenderausnahmen mit Aspose.Tasks behandeln
[Effektives Handling von Kalenderausnahmen in Java‑Projekten](./handle-occurrences/) mit Aspose.Tasks für Java. Projektmanagement ist ein dynamischer Prozess, der häufig Anpassungen erfordert, um unvorhergesehene Vorkommnisse zu berücksichtigen. Aspose.Tasks ermöglicht es Ihnen, Kalenderausnahmen effektiv zu behandeln und bietet einen schlanken Ansatz für das Projektmanagement. Lernen Sie die Kunst, Projektrisiken mit Leichtigkeit zu managen, in diesem ausführlichen Tutorial.

## Kalenderausnahmen mit Aspose.Tasks abrufen
[Erfahren Sie, wie Sie Kalenderausnahmen aus MS Project mit Aspose.Tasks für Java abrufen](./retrieve/). Integrieren Sie Kalenderausnahmen nahtlos in Ihren Projektmanagement‑Prozess mit Aspose.Tasks. Dieses Tutorial führt Sie Schritt für Schritt durch das Abrufen von Kalenderausnahmen und sorgt für eine reibungslose und effiziente Integration in Ihre Projekte. Nutzen Sie die Leistungsfähigkeit von Aspose.Tasks, um Ihre Projektmanagement‑Fähigkeiten zu erweitern.

## Wie integriert man einen MS Project‑Kalender mit Aspose.Tasks?
Die Integration eines MS Project‑Kalenders mit Aspose.Tasks erfolgt durch das Laden der Quell‑.mpp‑Datei mit der Project‑Klasse, den Zugriff auf deren Standard‑ oder benutzerdefinierte Calendar‑Objekte, das Anpassen oder Zusammenführen von Ausnahmen nach Bedarf und anschließendem Speichern des aktualisierten Projekts. So können Sie programmgesteuert mit MS Project‑Kalendern arbeiten, ohne die Benutzeroberfläche manuell zu verwenden.

`Project`‑Klasse ist das primäre Objekt von Aspose.Tasks, das eine gesamte Microsoft‑Project‑Datei modelliert. Importieren Sie eine bestehende MS Project‑Datei mit `new Project("source.mpp")`; die Bibliothek lädt automatisch deren Standardkalender und alle benutzerdefinierten Ausnahmen. Sie können diese Ausnahmen dann lesen, ändern oder zusammenführen, bevor Sie das Projekt wieder auf die Festplatte speichern. Dieser Ansatz ermöglicht es Ihnen, **MS Project‑Kalender**‑Daten programmgesteuert zu ändern, ohne manuell im MS Project‑UI zu editieren.

## Häufige Anwendungsfälle
- **Feiertagsplanung** – Definieren Sie nationale Feiertage als Nicht‑Arbeitstage in mehreren Projekten.  
- **Schichtarbeit** – Richten Sie benutzerdefinierte Arbeitswochen für Teams ein, die nach nicht‑standardmäßigen Zeitplänen arbeiten.  
- **Projektphasen‑Gating** – Sperren Sie Zeiträume, in denen keine Arbeit geplant werden soll, z. B. Wartungsfenster.  
- **Legacy‑Migration** – Importieren Sie Kalender aus älteren MS Project‑Dateien und passen Sie sie programmgesteuert an.

## Tipps & bewährte Verfahren
- **Pro‑Tipp:** Rufen Sie stets den vorhandenen Kalender ab, bevor Sie neue Ausnahmen hinzufügen, um Duplikate zu vermeiden.  
- **Warnung:** Das Ändern eines Kalenders, der bereits Aufgaben zugewiesen ist, kann Aufgabendaten verschieben; berechnen Sie den Zeitplan nach Änderungen neu.  
- **Leistung:** Bündeln Sie mehrere Ausnahmewertungen in einer einzigen Transaktion, um den Datei‑I/O‑Overhead zu reduzieren. Aspose.Tasks verarbeitet Dateien bis zu 1 GB bei einem Speicherverbrauch unter 200 MB und kann auf typischer Serverhardware 30+ kalenderbezogene API‑Aufrufe pro Sekunde ausführen.

## Tutorials zu Kalenderausnahmen
### [Kalenderausnahmen in Aspose.Tasks verwalten](./add-remove/)
Erfahren Sie, wie Sie Kalenderausnahmen in Aspose.Tasks für Java effizient hinzufügen und entfernen. Verbessern Sie Projektmanagement‑Workflows mühelos.
### [Wochentage für Kalenderausnahmen mit Aspose.Tasks definieren](./define-weekdays/)
Erfahren Sie, wie Sie Wochentage für Kalenderausnahmen in Java‑Projekten mit Aspose.Tasks für eine genaue Projektplanung definieren.
### [Vorkommnisse in Kalenderausnahmen mit Aspose.Tasks behandeln](./handle-occurrences/)
Erfahren Sie, wie Sie Kalenderausnahmen in Java‑Projekten mit Aspose.Tasks für Java effektiv behandeln. Optimieren Sie Ihren Projektmanagement‑Prozess jetzt.
### [Kalenderausnahmen mit Aspose.Tasks abrufen](./retrieve/)
Erfahren Sie, wie Sie Kalenderausnahmen aus MS Project mit Aspose.Tasks für Java abrufen. Schritt‑für‑Schritt‑Tutorial für nahtlose Integration.

## Häufig gestellte Fragen

**F: Kann ich Kalenderausnahmen ändern, nachdem ein Projekt bereits veröffentlicht wurde?**  
A: Ja. Verwenden Sie die APIs zum Hinzufügen/Entfernen und Definieren von Wochentagen, um den Kalender zu aktualisieren, und speichern Sie die Projektdatei erneut.

**F: Unterstützt Aspose.Tasks wiederkehrende Ausnahmen (z. B. jeden ersten Montag im Monat)?**  
A: Absolut. Das Tutorial „Vorkommnisse behandeln“ erklärt, wie wiederkehrende Muster eingerichtet werden.

**F: Wie stelle ich sicher, dass mein benutzerdefinierter Kalender von allen Aufgaben im Projekt verwendet wird?**  
A: Weisen Sie den Kalender dem Standardkalender des Projekts zu oder setzen Sie ihn explizit auf die `Calendar`‑Eigenschaft jeder Aufgabe.

**F: Ist es möglich, Kalender aus mehreren MS Project‑Dateien zusammenzuführen?**  
A: Ja. Rufen Sie jeden Kalender ab, kombinieren Sie deren Ausnahmen programmgesteuert und weisen Sie den zusammengeführten Kalender dem Zielprojekt zu.

**F: Welche Version von Aspose.Tasks wird für diese Funktionen benötigt?**  
A: Alle Funktionen sind in der aktuellen stabilen Version von Aspose.Tasks für Java (2025.x) verfügbar.

## Verwandte Tutorials

- [Projektkalender mit Aspose erstellen – Wochentage für Kalenderausnahmen definieren](/tasks/java/calendar-exceptions/define-weekdays/)
- [Kalenderausnahmen mit Aspose.Tasks abrufen – Aspose Tasks Java‑Tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Kalenderausnahme mit Aspose für Java erstellen](/tasks/java/calendar-exceptions/add-remove/)

---

**Zuletzt aktualisiert:** 2026-11-06  
**Getestet mit:** Aspose.Tasks für Java 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}