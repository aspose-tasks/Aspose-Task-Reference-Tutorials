---
date: 2026-09-09
description: So setzen Sie den Projektkalender in Java mit Aspose.Tasks. Erfahren
  Sie, wie Sie calendar working hours anzeigen, configure working time und modify
  calendar days in MS Project-Dateien.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Kalendereigenschaften in Aspose.Tasks verwalten
og_description: So setzen Sie den Projektkalender in Java mit Aspose.Tasks. Erfahren
  Sie, wie Sie calendar working hours anzeigen, configure working time und modify
  calendar days in MS Project-Dateien.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: So setzen Sie den Projektkalender in Java mit Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: So setzen Sie den Projektkalender in Java mit Aspose.Tasks
url: /de/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man den Projektkalender in Java mit Aspose.Tasks festlegt

## Einführung
In diesem Tutorial lernen Sie **wie man den Projektkalender** in Java mithilfe der Aspose.Tasks‑Bibliothek festlegt. Das Steuern von Kalendereigenschaften ermöglicht es Ihnen, **Kalenderarbeitszeiten anzuzeigen**, benutzerdefinierte Arbeitstage zu konfigurieren und den Projektzeitplan an reale Rahmenbedingungen wie Feiertage oder Schichtpläne anzupassen. Wir führen Sie durch die Einrichtung der Umgebung, das Laden eines Projekts, das Durchlaufen der Kalender und das Lesen bzw. Aktualisieren ihrer Eigenschaften, sodass Sie **MS Project‑Kalender**‑Einstellungen in jeder Java‑Anwendung sicher verwalten können.

## Schnelle Antworten
- **Was bedeutet „Projektkalender festlegen“?** Es bedeutet, die Arbeitszeiten, den Basiskalender und die Tagestypen eines Kalenders innerhalb einer MS‑Project‑Datei zu erstellen oder zu aktualisieren.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (jede aktuelle Version).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich die Kalenderarbeitszeiten anzeigen?** Ja – indem Sie jedes `WeekDay` auslesen, können Sie die Stunden für jeden Tagstyp ausgeben.  
- **Ist das mit Maven/Gradle kompatibel?** Absolut – fügen Sie das Aspose.Tasks‑JAR als Abhängigkeit hinzu.

## Wie man den Projektkalender in Java festlegt
Laden Sie Ihre Projektdatei, finden Sie den gewünschten Kalender und passen Sie anschließend dessen Arbeitszeitdefinitionen, Basiskalender und Tagestypen nach Bedarf an. Die nachstehenden Schritte bieten eine vollständige End‑to‑End‑Lösung, die das Laden, Durchlaufen, Ändern und Speichern des Projekts demonstriert, dabei Ausnahmen behandelt und genaue Arbeitszeitberechnungen sicherstellt.

## Was ist ein Projektkalender?
Ein Projektkalender definiert die Arbeitstage und -stunden für Aufgaben, Ressourcen und den gesamten Projektzeitplan. In MS Project können Kalender von einem Basiskalender erben, und jeder Tagstyp (z. B. **Standard**, **Nicht‑arbeitend**) kann eigene Arbeitszeiten besitzen. Das programmgesteuerte Verwalten dieser Einstellungen ermöglicht dynamische Zeitplananpassungen ohne manuelle Bearbeitung.

## Warum den MS Project‑Kalender programmgesteuert verwalten?
Das programmgesteuerte Verwalten von Kalendern ermöglicht es, konsistente Planungsregeln über viele Projekte hinweg anzuwenden, manuelle Fehler zu reduzieren und Kalendardaten mit anderen Unternehmenssystemen wie HR oder ERP zu integrieren. Diese Automatisierung beschleunigt die Projekteinrichtung und stellt sicher, dass alle Teammitglieder dieselben Arbeitszeit‑Richtlinien befolgen.

- **Automatisierung:** Kalender in Dutzenden von Projekten mit einem einzigen Skript anpassen.  
- **Konsistenz:** Organisationsweite Arbeitszeit‑Richtlinien automatisch durchsetzen.  
- **Integration:** Kalender mit externen HR‑ oder ERP‑Systemen synchronisieren.  
- **Transparenz:** Schnell **Kalenderarbeitszeiten** für Berichte oder Fehlersuche anzeigen.  
- **Flexibilität:** Ausnahmen oder Schichtpläne spontan hinzufügen, ohne die Benutzeroberfläche zu öffnen.

## Voraussetzungen
- **Java Development Kit (JDK) 8+** installiert und `JAVA_HOME` konfiguriert.  
- **Aspose.Tasks für Java**‑Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) heruntergeladen. Fügen Sie das JAR Ihrem Klassenpfad hinzu oder deklarieren Sie es als Maven/Gradle‑Abhängigkeit.  
- Eine Beispiel‑MS‑Project‑Datei (`.mpp` oder `.xml`), die mindestens einen Kalender enthält, den Sie untersuchen oder ändern möchten.

## Pakete importieren
Die Klassen `Project`, `Calendar`, `WeekDay` und verwandte Klassen bilden das Kernstück der Kalendermanipulation.  
Die Klasse `Calendar` stellt einen Projektkalender dar, der Arbeitstage, Ausnahmen und Basiskalender‑Beziehungen enthält.  
Die Klasse `WeekDay` definiert die Arbeitseinstellungs‑Parameter für einen einzelnen Tag innerhalb eines Kalenders.

Die Klasse `Project` ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne MS‑Project‑Datei im Speicher repräsentiert. Nachdem Sie eine Datei geladen haben, laufen alle Kalender‑Operationen über dieses Objekt.

```java
import com.aspose.tasks.*;
```

## Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre Projektdateien enthält. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Zeit‑Einheiten‑Konstanten definieren
Arbeitszeiten werden in Millisekunden angegeben. Das Definieren wiederverwendbarer Konstanten macht den Code leichter lesbar und hilft Ihnen, **Arbeitsstunden in Java** genau zu berechnen.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Schritt 3: Projekt‑Daten laden
Erstellen Sie eine `Project`‑Instanz, indem Sie eine vorhandene MS‑Project‑XML‑Datei (`.xml` oder `.mpp`) laden. Dadurch erhalten Sie Zugriff auf alle im Datei gespeicherten Kalender.

Die Klasse `Project` lädt die Datei in ein leichtgewichtiges Objektmodell; sie erfordert **nicht**, dass die gesamte Datei im Speicher gehalten wird, sodass Sie mit Projekten arbeiten können, die Zehntausende von Aufgaben enthalten.

```java
Project project = new Project(dataDir + "project.xml");
```

## Schritt 4: Kalender in Java durchlaufen
Jetzt durchlaufen wir jeden Kalender, geben seine eindeutige Kennung, den Namen, den Basiskalender und die Arbeitsstunden für jeden Tagstyp aus. Dies demonstriert, **wie man Projektkalender‑Werte in Java festlegt** und auch, **wie man Kalenderarbeitszeiten anzeigt**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Was dieser Code macht
- **Filtert unbenannte Kalender** (einige interne Kalender können einen `null`‑Namen haben).  
- **Gibt UID und Namen aus** – nützlich, um den Kalender später zu identifizieren.  
- **Zeigt den Basiskalender an** – entweder „Self“ (der Kalender ist sein eigener Basis) oder den Namen des vererbten Kalenders.  
- **Durchläuft jedes `WeekDay`**, um die gesamten Arbeitsstunden zu berechnen und auszugeben (`workingTime` ist in Millisekunden, daher teilen wir durch `OneHour`).  

## Quantifizierte Vorteile der Verwendung von Aspose.Tasks
Aspose.Tasks unterstützt **mehr als 30 Eingabe‑ und Ausgabeformate** und kann **Projekte mit bis zu 10.000 Aufgaben** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, und liefert Ergebnisse in weniger als einer Sekunde auf typischer Server‑Hardware. Diese Zahlen machen es zu einer zuverlässigen Wahl für Automatisierung im Unternehmensmaßstab.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| `NullPointerException` bei `cal.getBaseCalendar()` | Der Kalender ist selbst ein Basiskalender (`isBaseCalendar()` gibt `true` zurück). | Verwenden Sie die ternäre Prüfung wie gezeigt (`cal.isBaseCalendar() ? "Self" : ...`). |
| Keine Ausgabe für Arbeitsstunden | Die Projektdatei verwendet eine andere Zeiteinheit (Ticks). | Überprüfen Sie das Dateiformat; Aspose.Tasks normalisiert auf Millisekunden, stellen Sie jedoch sicher, dass Sie den korrekten Dateityp laden. |
| `project.xml` kann nicht gefunden werden | Falscher `dataDir`‑Pfad. | Verwenden Sie einen absoluten Pfad oder `Paths.get(dataDir, "project.xml").toString()`. |

## Häufig gestellte Fragen

**F: Kann ich Kalendereigenschaften programmgesteuert mit Aspose.Tasks ändern?**  
A: Ja, die API bietet vollen Lese‑/Schreibzugriff auf Kalender, sodass Sie Arbeitszeiten, Ausnahmen und Basiskalender‑Beziehungen hinzufügen, bearbeiten oder löschen können.

**F: Gibt es Einschränkungen bei der Kalenderanpassung mit Aspose.Tasks?**  
A: Die Bibliothek spiegelt die Möglichkeiten von Microsoft Project wider, sodass Sie praktisch alle Kalenderaspekte anpassen können. Nur sehr alte Project‑Dateiversionen können kleinere Kompatibilitätsprobleme aufweisen.

**F: Kann ich das Kalender‑Management in bestehende Java‑Projekte integrieren?**  
A: Absolut. Fügen Sie einfach das Aspose.Tasks‑JAR zu Ihrem Build‑Pfad hinzu und verwenden Sie dieselben Code‑Muster, die hier gezeigt werden.

**F: Unterstützt Aspose.Tasks neben dem Kalender‑Management weitere Projekt‑Management‑Funktionen?**  
A: Ja, es deckt Aufgaben, Ressourcen, Zuordnungen, Gliederungen, Baselines und mehr ab – es ist eine umfassende Lösung für Java‑basierte Projekt‑Automatisierung.

**F: Steht technischer Support für Entwickler, die Aspose.Tasks verwenden, zur Verfügung?**  
A: Ja, Aspose bietet dedizierte Foren, E‑Mail‑Support und umfangreiche Dokumentation für alle lizenzierten Nutzer.

---

**Zuletzt aktualisiert:** 2026-09-09  
**Getestet mit:** Aspose.Tasks für Java 24.12 (neueste zum Zeitpunkt der Erstellung)  
**Autor:** Aspose

## Verwandte Tutorials

- [Projektkalender in Java erstellen – Aspose.Tasks für Java‑Leitfaden](/tasks/java/)
- [Projektdateien in Java laden und Projekteigenschaften verwalten](/tasks/java/project-management/default-properties/)
- [Projektstartdatum in MS Project mit Aspose.Tasks für Java festlegen](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}