---
date: 2025-12-03
description: Erfahren Sie, wie Sie einen Kalender in MS Project erstellen, ein Projekt
  in MPP konvertieren und ein MPP‑Projekt mühelos mit Aspose.Tasks für Java speichern.
language: de
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Kalender in MS Project erstellen und als MPP mit Aspose.Tasks speichern
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalender in MS Project erstellen und als MPP mit Aspose.Tasks speichern

## Einleitung

Im modernen Projektmanagement müssen Sie häufig **Kalender‑MS‑Project**‑Dateien erstellen und diese dann im nativen MPP‑Format teilen. Egal, ob Sie Zeitpläne aus mehreren Quellen konsolidieren oder Altdaten migrieren, die programmatische Erstellung eines Kalenders spart Zeit und eliminiert manuelle Fehler. Dieses Tutorial führt Sie durch den gesamten Prozess, einen Kalender in MS Project zu erstellen, ihn anzupassen und schließlich das **Projekt in MPP zu konvertieren** mithilfe der Aspose.Tasks Java‑API.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Einen Kalender in MS Project erstellen und ihn als MPP‑Datei mit Aspose.Tasks für Java speichern.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher (JDK 8+).  
- **Kann ich den Kalender anpassen?** Ja – Sie können Arbeitszeiten, Ausnahmen und Feiertage hinzufügen.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für einen Basis‑Kalender.

## Was bedeutet „Kalender MS Project erstellen“?

Einen Kalender MS Project zu erstellen bedeutet, programmatisch die Arbeitstage, -stunden und Ausnahmen zu definieren, die die Aufgabenplanung innerhalb einer Microsoft‑Project‑Datei steuern. Durch die Verwendung von Aspose.Tasks können Sie diese Kalender erstellen, ändern und speichern, ohne die Microsoft‑Project‑Benutzeroberfläche zu öffnen.

## Warum Aspose.Tasks für diese Aufgabe verwenden?

- **Vollständige .NET/Java‑Kompatibilität** – funktioniert auf jeder Plattform, die Java unterstützt.  
- **Keine COM‑ oder Office‑Installation erforderlich** – ideal für serverseitige Automatisierung.  
- **Umfangreiche API** – unterstützt jede Kalendereigenschaft, einschließlich benutzerdefinierter Arbeitswochen und Feiertage.  
- **Direkter MPP‑Export** – Sie können **Projekt‑MPP speichern** ohne Zwischenschritte.

## Voraussetzungen

1. **Java Development Kit (JDK) 8+** – stellen Sie sicher, dass `java -version` 1.8 oder neuer ausgibt.  
2. **Aspose.Tasks für Java** – laden Sie das neueste JAR von der [Aspose-Website](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  
4. **Grundlegende Java‑Kenntnisse** – Vertrautheit mit Klassen, Methoden und Datei‑I/O.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Erforderliche Pakete importieren

Zuerst bringen Sie die Aspose.Tasks‑Klassen und Java‑Hilfsprogramme in den Gültigkeitsbereich.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Schritt 2: Datenverzeichnis einrichten

Legen Sie fest, wo Ihre Eingabe‑Vorlage und Ausgabedateien gespeichert werden. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner.

```java
String dataDir = "Your Data Directory";
```

### Schritt 3: Eingabe‑ und Ausgabedateinamen definieren

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

Wenn Sie bestimmte Arbeitszeiten, Feiertage oder Ausnahmen benötigen, rufen Sie Ihre eigene Hilfsmethode auf. Das Beispiel verwendet `GetTestCalendar` als Platzhalter.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro‑Tipp:** Sie können `cal1.getWeekDays()` direkt manipulieren, um die Arbeitszeiten für jeden Wochentag festzulegen.

### Schritt 6: Kalender dem Projekt zuweisen

Weisen Sie dem Projekt an, den neu erstellten Kalender für alle Planungsberechnungen zu verwenden.

```java
project.set(Prj.CALENDAR, cal1);
```

### Schritt 7: Projekt als MPP speichern

Jetzt **konvertieren Sie das Projekt in MPP**, indem Sie es mit der Option `SaveFileFormat.Mpp` speichern.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Schritt 8: Erfolgreichen Abschluss bestätigen

Eine einfache Konsolennachricht informiert Sie darüber, dass der Vorgang ohne Fehler abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

## Häufige Anwendungsfälle

- **Automatisierte Zeitplanerstellung** für wiederkehrende Projekte (z. B. wöchentliche Sprints).  
- **Migration von Legacy‑CSV‑ oder Excel‑Kalendern** in eine vollwertige MS‑Project‑Datei.  
- **Serverseitiges Reporting**, bei dem ein Webservice bei Bedarf eine MPP‑Datei zurückgibt.

## Fehlerbehebung & häufige Stolperfallen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| `NullPointerException` bei `project.save` | `dataDir` verweist auf einen nicht existierenden Ordner | Stellen Sie sicher, dass das Verzeichnis existiert oder erstellen Sie es programmgesteuert. |
| Kalender wird nicht auf Aufgaben angewendet | Aufgaben verweisen weiterhin auf den Standardkalender | Nachdem Sie `Prj.CALENDAR` gesetzt haben, aktualisieren Sie auch den `Task.CALENDAR` jeder Aufgabe, falls diese zuvor überschrieben wurden. |
| Ausgabedatei ist 0 KB | Fehlende Schreibberechtigungen | Führen Sie die JVM mit entsprechenden Dateisystemrechten aus oder wählen Sie einen beschreibbaren Pfad. |

## Häufig gestellte Fragen

**F: Ist Aspose.Tasks für Java mit verschiedenen Versionen von MS Project kompatibel?**  
**A:** Ja, Aspose.Tasks für Java unterstützt eine breite Palette von MS‑Project‑Versionen, von Project 2007 bis zur neuesten Version, und gewährleistet nahtlose Kompatibilität.

**F: Kann ich Kalender gemäß spezifischen Projektanforderungen anpassen?**  
**A:** Absolut. Sie können Arbeitstage definieren, benutzerdefinierte Arbeitswochen festlegen, Feiertage hinzufügen und sogar mehrere Kalender innerhalb einzigen Projektdatei erstellen.

**F: Bietet Aspose.Tasks für Java Unterstützung bei Fehlerbehebung und Hilfe?**  
**A:** Ja, Sie können Hilfe im Aspose.Tasks‑Community‑Forum erhalten [hier](https://forum.aspose.com/c/tasks/15).

**F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?**  
**A:** Ja, eine voll funktionsfähige Testversion ist verfügbar [hier](https://releases.aspose.com/).

**F: Wie kann ich eine temporäre Lizenz für Aspose.Tasks für Java erhalten?**  
**A:** Temporäre Lizenzen können über die Aspose-Website angefordert werden [hier](https://purchase.aspose.com/temporary-license/).

---

**Zuletzt aktualisiert:** 2025-12-03  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}