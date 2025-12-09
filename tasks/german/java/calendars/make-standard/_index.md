---
date: 2025-12-03
description: Erfahren Sie, wie Sie in Java mit Aspose.Tasks einen Kalender erstellen.
  Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie einen Standard‑MS‑Project‑Kalender
  erstellen, einen Standardkalender hinzufügen und Aspose.Tasks effektiv nutzen.
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man einen Kalender erstellt – Standardkalender in Aspose.Tasks
url: /de/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Kalender erstellt – Standardkalender in Aspose.Tasks erstellen

## Einführung
In diesem Tutorial lernen Sie **wie man Kalender**‑Objekte für Microsoft‑Project‑Dateien mithilfe der Aspose.Tasks‑Bibliothek für Java erstellt. Wir gehen Schritt für Schritt durch das Erstellen eines Standard‑MS‑Project‑Kalenders, das Festlegen dieses Kalenders als Standard (Standard‑Kalender) und das Speichern der Projektdatei. Am Ende der Anleitung können Sie die Kalendererstellung in jede Java‑basierte Projekt‑Management‑Lösung integrieren.

## Schnellantworten
- **Was bedeutet „Standardkalender“?** Es ist die voreingestellte Arbeitszeitdefinition, die von Aufgaben verwendet wird, die keinen eigenen Kalender festlegen.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (der „Wie‑man‑Aspose‑verwendet“-Teil).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welches Dateiformat wird erzeugt?** Eine XML‑basierte Microsoft‑Project‑Datei (`.xml`).  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für einen einfachen Kalender.

## Was ist ein Standardkalender in Microsoft Project?
Ein **Standardkalender** definiert die voreingestellten Arbeitstage und -stunden für ein Projekt. Wenn Sie einen Standardkalender hinzufügen, folgen alle Aufgaben, denen kein spezieller Kalender zugewiesen ist, dessen Zeitplan.

## Warum Aspose.Tasks zum Erstellen eines Kalenders verwenden?
Aspose.Tasks bietet eine reine Java‑API, mit der Sie Project‑Dateien manipulieren können, ohne Microsoft Project installiert zu haben. Das macht es ideal für serverseitige Automatisierung, CI‑Pipelines oder jede Java‑Anwendung, die **MS‑Project‑Kalender**‑Objekte programmgesteuert **erstellen** muss.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:

### Installation des Java Development Kit (JDK)
Installieren Sie das neueste JDK von der Oracle‑Website oder einer OpenJDK‑Distribution.

### Aspose.Tasks für Java‑Bibliothek
Laden Sie die Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter. Fügen Sie die JAR‑Datei Ihrem Projekt‑Klassenpfad hinzu.

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
Instanziieren Sie ein neues, leeres `Project`‑Objekt, das den Kalender aufnehmen wird.

```java
Project project = new Project();
```

### Schritt 3: Kalender definieren und zum Standard machen
Fügen Sie einen neuen Kalender mit dem Namen **„My Cal“** hinzu und setzen Sie ihn als Standardkalender für das Projekt.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Pro‑Tipp:** Die Methode `makeStandardCalendar` markiert den übergebenen Kalender automatisch als Standard für das Projekt – genau das, was Sie benötigen, wenn Sie **Standardkalender**‑Funktionalität hinzufügen wollen.

### Schritt 4: Projekt speichern
Speichern Sie das Projekt (inklusive des neuen Kalenders) in einer XML‑Datei.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Sie können den Dateinamen oder das Format (`SaveFileFormat.Pp`) ändern, wenn Sie eine andere Project‑Version bevorzugen.

### Schritt 5: Abschlussnachricht anzeigen
Geben Sie sich selbst ein visuelles Signal, dass der Vorgang ohne Fehler abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|---------|----------|--------|
| **Datei nicht gefunden** | `dataDir` verweist auf einen nicht existierenden Ordner | Ordner erstellen oder einen absoluten Pfad verwenden |
| **Lizenz‑Ausnahme** | Ausführung ohne gültige Aspose.Tasks‑Lizenz in der Produktion | Lizenzdatei laden via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Leerer Kalender** | Vergessen, Arbeitszeitdefinitionen hinzuzufügen | Verwenden Sie `cal1.getWeekDays().add(WeekDay.DayType.Monday)` usw., falls Sie benutzerdefinierte Stunden benötigen |

## Häufig gestellte Fragen

**F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?**  
A: Ja, Aspose.Tasks unterstützt eine breite Palette von Microsoft‑Project‑Versionen, von 2000 bis zu den neuesten Releases.

**F: Kann ich die Kalendereinstellungen weiter anpassen?**  
A: Absolut! Sie können Arbeitstage ändern, Ausnahmen hinzufügen und spezifische Arbeitszeiten mit den Klassen `WeekDay` und `WorkingTime` definieren.

**F: Eignet sich Aspose.Tasks für Enterprise‑Anwendungen?**  
A: Sicherlich. Die Bibliothek ist für hochperformante, skalierbare Umgebungen konzipiert und bietet umfassende Unterstützung für große Projektdateien.

**F: Bietet Aspose.Tasks technischen Support für Entwickler?**  
A: Ja, Aspose stellt dedizierte Foren, ticketbasierten Support und umfangreiche Dokumentation bereit, um Ihnen bei der schnellen Lösung von Problemen zu helfen.

**F: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion auf der [Website](https://purchase.aspose.com/buy) ausprobieren, um alle Funktionen vor einer Kaufentscheidung zu evaluieren.

## Fazit
Sie wissen jetzt **wie man Kalender**‑Objekte in Aspose.Tasks für Java erstellt, sie zum Standardkalender macht und die resultierende Projektdatei speichert. Diese Fähigkeit ermöglicht Ihnen die Automatisierung der Projektplanung, die Durchsetzung einheitlicher Arbeitszeiten und die direkte Integration von Microsoft‑Project‑Daten in Ihre Java‑Anwendungen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2025-12-03  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

---