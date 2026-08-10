---
date: 2026-07-29
description: Erfahren Sie, wie Sie mit Aspose.Tasks for Java Java-Code für Kalenderausnahmen
  erstellen – Vorkommnisse festlegen, Ausnahmetyp konfigurieren und Projektkalender
  effizient verwalten.
keywords:
- create calendar exception java
- Aspose.Tasks calendar
- Java project scheduling
lastmod: 2026-07-29
linktitle: Kalenderausnahme in Java erstellen – Vorkommnisse verarbeiten
og_description: Das Tutorial zur Erstellung von Kalenderausnahmen in Java zeigt, wie
  Sie Vorkommnisse festlegen und den Ausnahmetyp mit Aspose.Tasks for Java konfigurieren.
  Beherrschen Sie die Handhabung von Projektkalendern in wenigen Minuten.
og_image_alt: 'Guide: create calendar exception Java using Aspose.Tasks'
og_title: Kalenderausnahme in Java erstellen – Vorkommnisse verarbeiten
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to create calendar exception Java code using Aspose.Tasks
    for Java – set occurrences, configure exception type, and manage project calendars
    efficiently.
  headline: Create Calendar Exception Java – Handle Occurrences
  type: TechArticle
- description: Learn how to create calendar exception Java code using Aspose.Tasks
    for Java – set occurrences, configure exception type, and manage project calendars
    efficiently.
  name: Create Calendar Exception Java – Handle Occurrences
  steps:
  - name: Create a Calendar Exception Object
    text: '`CalendarException` is Aspose.Tasks'' class that represents a single calendar
      exception entry. We start by creating an instance of this class, which will
      hold all the details of the exception we want to define.'
  - name: Indicate That the Exception Is Defined By Occurrences
    text: Setting `EnteredByOccurrences` tells Aspose.Tasks that the exception follows
      a recurring pattern rather than a single date.
  - name: Set the Number of Occurrences
    text: Here we **how to set occurrences** for the exception. The example uses five
      occurrences, but you can change this value to match your schedule. `setOccurrences(int)`
      sets how many times the exception repeats.
  - name: Configure the Exception Type
    text: Finally, we **configure exception type** to specify how the recurrence is
      interpreted. In this case we choose a yearly pattern that occurs on a specific
      day. `CalendarExceptionType` enum defines the pattern type for the exception,
      such as YearlyByDay, MonthlyByDay, or Weekly. > **Pro tip:** If you n
  type: HowTo
- questions:
  - answer: While some Java knowledge helps, Aspose.Tasks provides extensive documentation
      and sample projects that guide beginners through each step.
    question: Can I use Aspose.Tasks for Java without prior programming experience?
  - answer: Yes. It supports Microsoft Project formats (MPP, XML) and can import/export
      to other tools, making it easy to **manage project calendar** data across platforms.
    question: Is Aspose.Tasks compatible with other project‑management tools?
  - answer: Aspose releases regular updates—typically every few months—to add features,
      fix bugs, and ensure compatibility with the latest Java versions.
    question: How often are updates released for Aspose.Tasks for Java?
  - answer: Absolutely. You can combine multiple `CalendarException` objects, each
      with its own occurrence count and type, to model complex schedules.
    question: Can I customize calendar exceptions for a specific project timeline?
  - answer: Yes, you can download a fully functional trial from the [website](https://releases.aspose.com/).
    question: Does Aspose.Tasks offer a free trial?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create calendar exception
- Aspose.Tasks
- Java calendar API
title: Kalenderausnahme in Java erstellen – Vorkommnisse verarbeiten
url: /de/java/calendar-exceptions/handle-occurrences/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalenderausnahme in Java erstellen

## Einführung
In diesem **Java‑Kalender‑Tutorial** lernen Sie, wie Sie mit Aspose.Tasks für Java **Kalenderausnahmen in Java** erstellen. Das Verwalten von Kalenderausnahmen – insbesondere wiederkehrender – hält Ihren Projektzeitplan genau, reduziert Ressourcenkonflikte und spart Ihnen kostspielige Neuplanungen. Am Ende dieses Leitfadens können Sie Vorkommen festlegen, den Ausnahmetyp konfigurieren und die Ausnahme mit nur wenigen Zeilen Java an einen Projektkalender anhängen.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Umgang mit Vorkommen von Kalenderausnahmen mit Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher (JDK 8+).  
- **Wie viele Vorkommen kann ich festlegen?** Jeder ganzzahlige Wert; das Beispiel verwendet 5.  
- **Kann ich den Ausnahmetyp ändern?** Ja – verwenden Sie `setType` mit einem beliebigen `CalendarExceptionType`‑Enum‑Wert.

## Was ist ein Java‑Kalender‑Tutorial?
`Java calendar tutorial` ist ein schritt‑für‑schritt Leitfaden, der zeigt, wie man datumsbasierte Objekte in einer Java‑zentrierten Projektmanagement‑Bibliothek manipuliert. In diesem Artikel liegt der Fokus auf Aspose.Tasks, einer Bibliothek, die es Ihnen ermöglicht, Projektkalender, Feiertage und Arbeitszeiten programmgesteuert zu verwalten.

## Warum Aspose.Tasks für Kalenderausnahmen verwenden?
Aspose.Tasks gibt Ihnen die vollständige programmgesteuerte Kontrolle über sowohl wiederkehrende als auch einmalige Ausnahmen. Es unterstützt **30+ Eingabe‑ und Ausgabeformate** (einschließlich MPP, XML und CSV) und kann Kalender für Projekte mit **bis zu 10.000 Aufgaben** verarbeiten, ohne merkliche Leistungseinbußen. Da es auf jeder Java‑kompatiblen Plattform läuft, vermeiden Sie COM‑Interop und können es auf Linux, Windows oder Cloud‑Containern mit identischem Verhalten bereitstellen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Download von der Oracle‑Website.  
2. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  
3. **Aspose.Tasks for Java** – Bibliothek von dem [Download‑Link](https://releases.aspose.com/tasks/java/) beziehen.

### Pakete importieren
Zuerst importieren Sie die Namespaces, die für die Arbeit mit Aspose.Tasks erforderlich sind.

```java
import com.aspose.tasks.*;
```

Diese Import‑Anweisung gibt Ihnen Zugriff auf Klassen wie `Project`, `Calendar` und `CalendarException`.

## Wie erstelle ich eine Kalenderausnahme in Java?
Laden Sie Ihr Projekt, erstellen Sie eine Instanz von `CalendarException`, definieren Sie sie durch Vorkommen, geben Sie die Anzahl der Vorkommen an und weisen Sie schließlich den gewünschten `CalendarExceptionType` zu. Die folgenden Schritte führen Sie detailliert durch jede Aktion. Dieser Prozess stellt sicher, dass die Ausnahme korrekt an den Projektkalender angehängt wird und bei der Terminberechnung berücksichtigt wird.

### Schritt 1: Ein CalendarException‑Objekt erstellen
`CalendarException` ist die Aspose.Tasks‑Klasse, die einen einzelnen Kalendereintrag für eine Ausnahme darstellt. Wir beginnen damit, eine Instanz dieser Klasse zu erstellen, die alle Details der zu definierenden Ausnahme enthält.

```java
CalendarException except = new CalendarException();
```

### Schritt 2: Angeben, dass die Ausnahme durch Vorkommen definiert ist  
Durch Setzen von `EnteredByOccurrences` teilen Sie Aspose.Tasks mit, dass die Ausnahme einem wiederkehrenden Muster folgt und nicht einem einzelnen Datum entspricht.

```java
except.setEnteredByOccurrences(true);
```

### Schritt 3: Anzahl der Vorkommen festlegen  
Hier zeigen wir **wie Vorkommen für die Ausnahme festgelegt werden**. Das Beispiel verwendet fünf Vorkommen, Sie können diesen Wert jedoch an Ihren Zeitplan anpassen. `setOccurrences(int)` legt fest, wie oft die Ausnahme wiederholt wird.

```java
except.setOccurrences(5);
```

### Schritt 4: Ausnahmeart konfigurieren  
Abschließend **konfigurieren wir die Ausnahmeart**, um festzulegen, wie das Wiederholungsmuster interpretiert wird. In diesem Fall wählen wir ein jährliches Muster, das an einem bestimmten Tag auftritt. Das Enum `CalendarExceptionType` definiert den Mustertyp für die Ausnahme, z. B. YearlyByDay, MonthlyByDay oder Weekly.

```java
except.setType(CalendarExceptionType.YearlyByDay);
```

> **Pro Tipp:** Wenn Sie ein monatliches oder wöchentliches Muster benötigen, ersetzen Sie `YearlyByDay` durch `MonthlyByDay` oder `Weekly`. Die gleiche `setOccurrences`‑Methode funktioniert für alle Typen.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|----------------|-----|
| **Ausnahme nicht angewendet** | `EnteredByOccurrences` blieb `false`. | Stellen Sie sicher, dass `except.setEnteredByOccurrences(true);` aufgerufen wird. |
| **Falsche Wiederholung** | Verwendung des falschen `CalendarExceptionType`. | Wählen Sie das Enum, das Ihrem Zeitplan entspricht (z. B. `MonthlyByDay`). |
| **Vorkommen ignoriert** | Der Kalender ist keinem Projekt zugeordnet. | Fügen Sie die Ausnahme einem `Calendar`‑Objekt hinzu und weisen Sie es Ihrem `Project` zu. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks für Java ohne vorherige Programmiererfahrung nutzen?**  
A: Grundkenntnisse in Java helfen, aber Aspose.Tasks bietet umfangreiche Dokumentation und Beispielprojekte, die Anfängern jeden Schritt erklären.

**F: Ist Aspose.Tasks mit anderen Projekt‑Management‑Tools kompatibel?**  
A: Ja. Es unterstützt Microsoft‑Project‑Formate (MPP, XML) und kann zu anderen Tools importieren/exportieren, wodurch Sie **Projektkalender**‑Daten plattformübergreifend verwalten können.

**F: Wie häufig werden Updates für Aspose.Tasks für Java veröffentlicht?**  
A: Aspose veröffentlicht regelmäßig Updates – typischerweise alle paar Monate – um neue Funktionen hinzuzufügen, Fehler zu beheben und die Kompatibilität mit den neuesten Java‑Versionen sicherzustellen.

**F: Kann ich Kalenderausnahmen für einen bestimmten Projektzeitplan anpassen?**  
A: Absolut. Sie können mehrere `CalendarException`‑Objekte kombinieren, jedes mit eigener Vorkommenszahl und Typ, um komplexe Zeitpläne abzubilden.

**F: Bietet Aspose.Tasks eine kostenlose Testversion an?**  
A: Ja, Sie können eine voll funktionsfähige Testversion von der [Website](https://releases.aspose.com/) herunterladen.

## Fazit
Durch das Befolgen dieses **Java‑Kalender‑Tutorials** wissen Sie jetzt, wie Sie **Kalenderausnahmen in Java** erstellen, Vorkommen festlegen und den Ausnahmetyp mit Aspose.Tasks für Java konfigurieren. Diese Möglichkeiten ermöglichen es Ihnen, Projektzeitpläne fein abzustimmen, Ressourcenkonflikte zu vermeiden und Zeitpläne zuverlässig zu halten. Erkunden Sie die API weiter, um benutzerdefinierte Arbeitszeiten, Feiertagskalender hinzuzufügen oder sie in externe Planungssysteme zu integrieren.

---

**Zuletzt aktualisiert:** 2026-07-29  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Kalenderausnahme mit Aspose für Java erstellen](/tasks/java/calendar-exceptions/add-remove/)
- [Kalenderausnahmen mit Aspose.Tasks abrufen – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [Benutzerdefinierte Kalenderausnahmen mit Aspose.Tasks für Java erstellen](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}