---
date: 2025-12-03
description: Erfahren Sie, wie Sie Arbeitswochen in Java aus einem Microsoft‑Project‑Kalender
  mit Aspose.Tasks lesen. Folgen Sie der Schritt‑für‑Schritt‑Anleitung mit vollständigen
  Codebeispielen.
language: de
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Arbeitswochen in Java aus dem MS Project‑Kalender mit Aspose.Tasks lesen
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Arbeitswochen in Java aus MS Project Kalender lesen mit Aspose.Tasks

## Einführung
In diesem Tutorial lesen Sie **Arbeitswochen in Java** aus einem Microsoft Project‑Kalender mithilfe der Aspose.Tasks‑Bibliothek. Egal, ob Sie ein Reporting‑Tool bauen, Zeitpläne synchronisieren oder Projekt‑Daten automatisiert extrahieren – der programmgesteuerte Zugriff auf Arbeitswochen‑Definitionen spart unzählige manuelle Stunden. Wir führen Sie durch die erforderliche Einrichtung, zeigen Ihnen den genauen Code zum Abrufen von Arbeitswochen‑Details und erklären jeden Schritt, sodass Sie die Lösung an Ihre eigenen Projekte anpassen können.

## Schnelle Antworten
- **Was bedeutet „Arbeitswochen in Java lesen“?** Es bezieht sich auf das Extrahieren von Arbeitswochen‑Definitionen aus einer Project‑Datei mittels Java‑Code.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (Kostenlose Testversion verfügbar).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine Testversion reicht für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Dateiformate werden unterstützt?** Sowohl *.mpp*‑ als auch Project‑XML‑Dateien werden verarbeitet.  
- **Wie lange dauert die Implementierung?** In der Regel unter 10 Minuten, sobald die Bibliothek eingerichtet ist.

## Was bedeutet „Arbeitswochen in Java lesen“?
Das Lesen von Arbeitswochen in Java bedeutet, die Aspose.Tasks‑API zu verwenden, um auf die `WorkWeekCollection` eines Kalender‑Objekts innerhalb einer Microsoft Project‑Datei zuzugreifen. Jede `WorkWeek` enthält Start‑/End‑Datum sowie die täglichen Arbeitszeit‑Definitionen, die festlegen, wie Ressourcen geplant werden.

## Warum Arbeitswochen in Java aus einem Microsoft Project Kalender lesen?
- **Automatisierung:** Manuelles Kopieren von Termin‑Daten entfällt.  
- **Integration:** Arbeitswochen‑Informationen können in ERP, HR oder benutzerdefinierte Reporting‑Systeme eingespeist werden.  
- **Konsistenz:** Sicherstellen, dass alle nachgelagerten Tools dieselben Kalenderregeln aus der Project‑Datei verwenden.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder höher installiert.  
2. **Aspose.Tasks für Java** – Laden Sie das aktuelle JAR von der offiziellen Seite herunter: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Eine **Beispiel‑Project‑Datei** (`ReadWorkWeeksInformation.mpp`) in einem bekannten Ordner.

## Pakete importieren
Zuerst importieren Sie die Klassen, die wir für die Arbeit mit Kalendern und Arbeitswochen benötigen:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der die `.mpp`‑Datei enthält. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner:

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Project‑Instanz erstellen und auf den Kalender zugreifen
Instanziieren Sie ein `Project`‑Objekt, wählen Sie den gewünschten Kalender (nach UID) und holen Sie dessen `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Profi‑Tipp:** Wenn Sie die Kalender‑UID nicht kennen, können Sie über `project.getCalendars()` iterieren und den Namen sowie die UID jedes Kalenders ausgeben.

## Schritt 3: Durch Arbeitswochen iterieren
Durchlaufen Sie jede `WorkWeek`, um deren Namen, Start‑/End‑Datum und die täglichen Arbeitszeiten anzuzeigen:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Was Sie sehen werden:** Die Konsole gibt das Label jeder Arbeitswoche (z. B. „Standard“), den gültigen Datumsbereich und die genauen Arbeitsstunden für jeden Tag aus.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| `NullPointerException` beim Zugriff auf `calendar` | Falsche UID oder Kalender existiert nicht | UID mit `project.getCalendars().size()` prüfen und verfügbare Kalender zuerst auflisten. |
| Keine Ausgabe für Arbeitswochen | Der ausgewählte Kalender hat keine benutzerdefinierten Arbeitswochen (verwendet Standard) | Standardkalender (`project.getDefaultCalendar()`) nutzen oder programmgesteuert eine Arbeitswoche erstellen. |
| Datumsformat wirkt seltsam | `System.out.println` verwendet das Standard‑`java.util.Date`‑Format | Einen `SimpleDateFormat` anwenden, um das Datum nach Bedarf zu formatieren. |

## Häufig gestellte Fragen

**F: Kann ich die Arbeitswochen‑Informationen mit Aspose.Tasks für Java ändern?**  
A: Ja. Die API bietet Methoden wie `addWorkWeek()`, `removeWorkWeek()` und Setter, um Namen, Daten und Arbeitszeiten zu ändern.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?**  
A: Absolut. Es unterstützt MPP‑Dateien von Project 98 bis zu den neuesten Versionen sowie Project‑XML‑Dateien.

**F: Kann ich Aspose.Tasks mit anderen Java‑Frameworks integrieren?**  
A: Ja. Die Bibliothek ist reines Java, sodass Sie sie neben Spring, Jakarta EE oder jedem anderen Framework verwenden können.

**F: Gibt es eine Testversion von Aspose.Tasks?**  
A: Ja, Sie können eine kostenlose 30‑Tage‑Testversion von der offiziellen Seite herunterladen: [Aspose.Tasks trial](https://releases.aspose.com/).

**F: Wo finde ich Support für Aspose.Tasks?**  
A: Das Aspose‑Community‑Forum ist die beste Anlaufstelle: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Fazit
Sie haben nun **Arbeitswochen in Java lesen** mit Aspose.Tasks gemeistert. Durch die oben beschriebenen Schritte können Sie programmgesteuert Arbeitswochen‑Definitionen aus jedem MS Project‑Kalender abrufen, diese Daten in Ihre Anwendungen integrieren und zeitplanbezogene Workflows automatisieren. Experimentieren Sie gern mit dem Erstellen oder Aktualisieren von Arbeitswochen – Aspose.Tasks macht das unkompliziert.

---

**Zuletzt aktualisiert:** 2025-12-03  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}