---
date: 2026-02-05
description: Erfahren Sie, wie Sie Feiertage zu einem Kalender hinzufügen, den Kalender
  einem Projekt zuweisen und die MS Project‑Datei als MPP mit Aspose.Tasks für Java
  speichern.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Feiertage zum Kalender hinzufügen und als MPP mit Aspose.Tasks speichern
url: /de/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Feiertage zum Kalender hinzufügen und als MPP mit Aspose.Tasks speichern

## Einführung

Im modernen Projektmanagement müssen Sie häufig **add holidays to calendar**-Dateien hinzufügen, einen **MS Project calendar** erstellen und dann den Zeitplan im nativen MPP-Format teilen. Egal, ob Sie Zeitpläne aus mehreren Quellen konsolidieren oder Altdaten migrieren, das programmgesteuerte Erzeugen eines Kalenders eliminiert manuelle Fehler und beschleunigt die Bereitstellung. Dieses Tutorial führt Sie durch den gesamten Prozess, einen Kalender in MS Project zu erstellen, ihn mit Feiertagen anzupassen, **assign calendar to project** und schließlich **convert project to MPP** mithilfe der Aspose.Tasks Java API.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Hinzufügen von Feiertagen zu einem Kalender, Zuweisen zu einem Projekt und Speichern des Ergebnisses als MPP-Datei mit Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java-Version wird benötigt?** Java 8 oder höher (JDK 8+).  
- **Kann ich den Kalender anpassen?** Ja – Sie können Arbeitszeiten, Ausnahmen und Feiertage hinzufügen.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen einfachen Kalender.  

## Was bedeutet “create calendar MS Project”?

Ein **create calendar MS Project** zu erstellen bedeutet, programmgesteuert die Arbeitstage, -stunden und Ausnahmen zu definieren, die die Aufgabenplanung innerhalb einer Microsoft Project-Datei steuern. Durch die Verwendung von Aspose.Tasks können Sie **java create project calendar**, ändern und die Änderungen speichern, ohne die Microsoft Project-Benutzeroberfläche zu öffnen.

## Warum Aspose.Tasks für diese Aufgabe verwenden?

- **Full .NET/Java compatibility** – funktioniert auf jeder Plattform, die Java unterstützt.  
- **No COM or Office installation needed** – ideal für serverseitige Automatisierung und **automate schedule generation**.  
- **Rich API** – unterstützt jede Kalendereigenschaft, einschließlich benutzerdefinierter Arbeitswochen und Feiertage.  
- **Direct MPP output** – Sie können **save project as MPP** ohne Zwischenkonvertierungen.  

## Voraussetzungen

1. **Java Development Kit (JDK) 8+** – stellen Sie sicher, dass `java -version` 1.8 oder neuer ausgibt.  
2. **Aspose.Tasks for Java** – laden Sie das neueste JAR von der [Aspose-Website](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  
4. **Basic Java knowledge** – Vertrautheit mit Klassen, Methoden und Datei‑I/O.  

## Wie man Feiertage zum Kalender hinzufügt

Im Folgenden gehen wir jeden Schritt durch, von der Einrichtung der Umgebung bis zum Speichern der finalen MPP-Datei. Die Codeblöcke bleiben unverändert gegenüber dem Original‑Tutorial; die begleitenden Erklärungen wurden zur Klarheit erweitert.

### Schritt 1: Erforderliche Pakete importieren

Zuerst bringen Sie die Aspose.Tasks‑Klassen und Java‑Hilfsprogramme in den Gültigkeitsbereich.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Schritt 2: Datenverzeichnis einrichten

Definieren Sie, wo Ihre Eingabe‑Vorlage und Ausgabedateien gespeichert werden. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

### Schritt 3: Eingabe‑ und Ausgabedateinamen festlegen

Wir laden eine vorhandene MPP‑Datei (oder ein leeres Projekt) und schreiben das Ergebnis in eine neue Datei.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Schritt 4: Projekt laden und neuen Kalender hinzufügen

Erstellen Sie eine `Project`‑Instanz aus der Quelldatei und fügen Sie einen Kalender mit dem Namen **„Calendar 1“** hinzu.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Schritt 5: Kalender anpassen (optional)

Falls Sie spezifische Arbeitszeiten, Feiertage oder Ausnahmen benötigen, rufen Sie Ihre eigene Hilfsmethode auf. Das Beispiel verwendet `GetTestCalendar` als Platzhalter.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro Tipp:** Sie können `cal1.getWeekDays()` direkt manipulieren, um die Arbeitsstunden für jeden Wochentag festzulegen, oder `cal1.getExceptions()` verwenden, um **add holidays to calendar**.

### Schritt 6: Kalender dem Projekt zuweisen

Weisen Sie dem Projekt an, den neu erstellten Kalender für alle Terminberechnungen zu verwenden.

```java
project.set(Prj.CALENDAR, cal1);
```

### Schritt 7: Projekt als MPP speichern

Jetzt **convert project to MPP**, indem Sie es mit der Option `SaveFileFormat.Mpp` speichern.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Schritt 8: Erfolgreichen Abschluss bestätigen

Eine einfache Konsolennachricht informiert Sie darüber, dass der Vorgang ohne Fehler abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

## Häufige Anwendungsfälle

- **Automated schedule generation** für wiederkehrende Projekte (z. B. wöchentliche Sprints).  
- **Migrating legacy CSV or Excel calendars** in eine voll ausgestattete MS Project‑Datei.  
- **Server‑side reporting**, bei dem ein Webservice bei Bedarf eine MPP‑Datei zurückgibt.  

## Fehlerbehebung & häufige Fallstricke

| Problem | Ursache | Lösung |
|---------|---------|--------|
| `NullPointerException` bei `project.save` | `dataDir` verweist auf einen nicht vorhandenen Ordner | Stellen Sie sicher, dass das Verzeichnis existiert oder erstellen Sie es programmgesteuert. |
| Kalender wird nicht auf Aufgaben angewendet | Aufgaben verweisen weiterhin auf den Standardkalender | Nachdem Sie `Prj.CALENDAR` gesetzt haben, aktualisieren Sie ebenfalls das `Task.CALENDAR` jeder Aufgabe, falls diese zuvor überschrieben wurden. |
| Ausgabedatei ist 0 KB | Fehlende Schreibberechtigungen | Führen Sie die JVM mit entsprechenden Dateisystemrechten aus oder wählen Sie einen beschreibbaren Pfad. |

## Häufig gestellte Fragen

**F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?**  
A: Ja, Aspose.Tasks für Java unterstützt eine breite Palette von MS Project-Versionen, von Project 2007 bis zur neuesten Version, und gewährleistet nahtlose Kompatibilität.

**F: Kann ich Kalender nach spezifischen Projektanforderungen anpassen?**  
A: Absolut. Sie können Arbeitstage definieren, benutzerdefinierte Arbeitswochen festlegen, Feiertage hinzufügen und sogar mehrere Kalender innerhalb einer einzigen Projektdatei erstellen.

**F: Bietet Aspose.Tasks für Java Unterstützung bei der Fehlerbehebung und Hilfe?**  
A: Ja, Sie können Hilfe im Aspose.Tasks Community‑Forum [hier](https://forum.aspose.com/c/tasks/15) erhalten.

**F: Gibt es eine kostenlose Testversion von Aspose.Tasks für Java?**  
A: Ja, eine voll funktionsfähige Testversion ist [hier](https://releases.aspose.com/) verfügbar.

**F: Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?**  
A: Temporäre Lizenzen können über die Aspose-Website [hier](https://purchase.aspose.com/temporary-license/) angefordert werden.

---

**Zuletzt aktualisiert:** 2026-02-05  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}