---
date: 2026-02-28
description: Erfahren Sie, wie Sie die Dauer in Minuten, Tagen, Stunden, Wochen und
  Monaten mit Aspose.Tasks für Java ermitteln. Detaillierte Anleitung mit Codebeispielen.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man die Dauer in verschiedenen Einheiten mit Aspose.Tasks ermittelt
url: /de/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Dauer in verschiedenen Einheiten mit Aspose.Tasks erhält

## Einführung
Das Verständnis **wie man die Dauer ermittelt** für Aufgaben ist ein Kernteil jedes Projekt‑Management‑Workflows. Egal, ob Sie Minuten für feinkörniges Tracking oder Monate für die grobe Planung benötigen, Aspose.Tasks für Java macht die Umwandlung unkompliziert. In diesem Tutorial führen wir Sie durch das Abrufen der Dauer einer Aufgabe in Minuten, Tagen, Stunden, Wochen und Monaten und erklären, warum jede Einheit in realen Projekten nützlich sein kann.

## Schnelle Antworten
- **Was bedeutet „wie man die Dauer ermittelt“?** Es ist der Prozess, den Zeitspanne einer Aufgabe zu extrahieren und in die benötigte Einheit umzuwandeln.  
- **Welche API‑Methode führt die Umwandlung durch?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich in benutzerdefinierte Einheiten umwandeln?** Sie können Umwandlungen verketten oder `TimeSpan` für benutzerdefinierte Berechnungen verwenden.  
- **Ist der Code mit Java 17 kompatibel?** Ja, Aspose.Tasks unterstützt Java 8 und neuere Versionen.

## Was bedeutet „wie man die Dauer ermittelt“ in Aspose.Tasks?
Aspose.Tasks speichert die Länge einer Aufgabe als `Duration`‑Objekt. Durch Aufrufen der `convert`‑Methode und Angabe eines `TimeUnitType` (Minute, Hour, Day, Week, Month) können Sie denselben zugrunde liegenden Wert in der gewünschten Einheit abrufen. Diese Flexibilität ermöglicht das Erstellen von Berichten, das Durchführen von Berechnungen oder das Einspeisen von Daten in andere Systeme ohne manuelle Mathematik.

## Warum Aspose.Tasks für die Dauerumwandlung verwenden?
- **Genauigkeit:** Behandelt Kalenderausnahmen, Arbeitszeiten und nicht‑standardisierte Kalender automatisch.  
- **Leistung:** Einzeilige Umwandlung vermeidet Schleifen oder benutzerdefiniertes Parsen.  
- **Portabilität:** Funktioniert überall gleich in Windows-, Linux- und macOS‑Umgebungen.  
- **Integration:** Lässt sich nahtlos in bestehende Java‑Anwendungen einbinden, die bereits Aspose.Tasks verwenden.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) installiert
- Aspose.Tasks für Java‑Bibliothek. Sie können sie [hier](https://releases.aspose.com/tasks/java/) herunterladen
- Grundlegendes Verständnis der Java‑Programmierung

## Pakete importieren
Fügen Sie in Ihrem Java‑Projekt die Aspose.Tasks‑Bibliothek hinzu. Ergänzen Sie die folgende Import‑Anweisung am Anfang Ihres Codes:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Schritt 1: Projekt einrichten
Erstellen Sie ein neues Java‑Projekt in Ihrer bevorzugten IDE (IntelliJ, Eclipse, VS Code usw.) und fügen Sie das Aspose.Tasks‑JAR dem Klassenpfad des Projekts hinzu. Dadurch stehen die oben genannten Klassen zur Compile‑Zeit zur Verfügung.

## Schritt 2: Projektvorlage lesen
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Ordner, der Ihre `.xml`‑ oder `.mpp`‑Projektdatei enthält.

## Schritt 3: Aufgabe abrufen
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

Der Aufruf `getById(1)` holt die Aufgabe, deren ID 1 ist. Passen Sie die ID an, um eine andere Aufgabe in Ihrer Datei zu adressieren.

## Schritt 4: Dauer in Minuten – Wie man die Dauer in Minuten ermittelt?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

Die Variable `mins` enthält nun die Aufgabendauer in Minuten.

## Schritt 5: Dauer in Tagen – Wie man die Dauer in Tagen ermittelt?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

Verwenden Sie diesen Wert, wenn Sie eine Tagesgranularität für Berichte oder Ressourcenzuweisungen benötigen.

## Schritt 6: Dauer in Stunden – Wie man die Dauer in Stunden ermittelt?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

Stunden sind praktisch für Stundenzettel oder wenn Sie einen Tag in Arbeitsschichten aufteilen möchten.

## Schritt 7: Dauer in Wochen – Wie man die Dauer in Wochen ermittelt?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

Wochen werden häufig in groben Gantt‑Diagrammen oder Meilenstein‑Planungen verwendet.

## Schritt 8: Dauer in Monaten – Wie man die Dauer in Monaten ermittelt?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

Monatsbasierte Dauern helfen, wenn Sie Projektphasen an Geschäftsperioden anpassen.

## Häufige Probleme und Lösungen
| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| `NullPointerException` bei `task` | Falsche Task‑ID oder fehlende Unteraufgaben | Überprüfen Sie, ob die Task‑ID mit `project.getRootTask().getChildren()` existiert |
| Unerwartete Werte (z. B. 0) | Projekt verwendet einen benutzerdefinierten Kalender mit Nicht‑Arbeitstagen | Stellen Sie sicher, dass der Projektkalender korrekt definiert ist, oder verwenden Sie `project.getCalendar()`, um ihn zu prüfen |
| Umwandlung liefert Bruchteile von Wochen | Wochen werden basierend auf der Standardwochenlänge des Projekts berechnet (gewöhnlich 5 Tage) | Multiplizieren Sie mit 5, wenn Sie Kalendermwchen benötigen, oder passen Sie die Kalendereinstellungen an |

## Häufig gestellte Fragen
### F: Kann ich Aspose.Tasks für Java mit jeder Java‑IDE verwenden?
A: Ja, Aspose.Tasks für Java ist mit jeder Java‑Integrated Development Environment (IDE) kompatibel.

### F: Wie kann ich die ID einer Aufgabe in einer Microsoft‑Project‑Datei erhalten?
A: Sie können die Projektdatei manuell prüfen oder `project.getRootTask().getChildren()` aufrufen und durch die Sammlung iterieren, um die `ID` jeder Aufgabe zu lesen.

### F: Ist Aspose.Tasks für die Handhabung von groß angelegten Projekten geeignet?
A: Absolut. Aspose.Tasks ist darauf ausgelegt, Projekte mit Tausenden von Aufgaben und Ressourcen effizient zu verarbeiten.

### F: Wo finde ich weitere Dokumentation?
A: Besuchen Sie die [Dokumentation](https://reference.aspose.com/tasks/java/) für umfassende API‑Referenzen, Code‑Beispiele und Best‑Practice‑Leitfäden.

### F: Kann ich Aspose.Tasks für Java vor dem Kauf testen?
A: Ja, Sie können eine [kostenlose Testversion](https://releases.aspose.com/) ausprobieren, um die Funktionen zu bewerten.

---

**Zuletzt aktualisiert:** 2026-02-28  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}