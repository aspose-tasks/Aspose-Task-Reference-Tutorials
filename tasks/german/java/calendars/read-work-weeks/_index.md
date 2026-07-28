---
date: 2026-02-05
description: Erfahren Sie, wie Sie Arbeitswochen in Java aus einem Microsoft‑Project‑Kalender
  mit Aspose.Tasks auslesen. Folgen Sie der Schritt‑für‑Schritt‑Anleitung mit vollständigen
  Codebeispielen.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Arbeitswochen in Java aus dem MS‑Project‑Kalender mit Aspose.Tasks
  liest
url: /de/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Arbeitswochen in Java aus dem MS Project Kalender liest – Aspose.Tasks

## Einführung
In diesem Tutorial **lernen Sie, wie Sie Arbeitswochen in Java** aus einem Microsoft‑Project‑Kalender mithilfe der Aspose.Tasks‑Bibliothek auslesen. Egal, ob Sie ein Reporting‑Tool bauen, Zeitpläne synchronisieren oder die Extraktion von Projektdaten automatisieren – der programmgesteuerte Zugriff auf Arbeitswochen‑Definitionen spart unzählige manuelle Stunden. Wir führen Sie durch die erforderliche Einrichtung, zeigen Ihnen den genauen Code zum Abrufen von Arbeitswochen‑Details und erklären jeden Schritt, sodass Sie die Lösung an Ihre eigenen Projekte anpassen können.

## Schnelle Antworten
- **Was bedeutet „read workweeks java“?** Es bezeichnet das Extrahieren von Arbeitswochen‑Definitionen aus einer Projektdatei mittels Java‑Code.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (kostenlose Testversion verfügbar).  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine Testversion reicht für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche Dateiformate werden unterstützt?** Sowohl *.mpp*‑ als auch Project‑XML‑Dateien werden verarbeitet.  
- **Wie lange dauert die Implementierung?** In der Regel weniger als 10 Minuten, sobald die Bibliothek eingerichtet ist.

## Wie man Arbeitswochen in Java aus einem Microsoft Project Kalender ausliest
Das Auslesen von Arbeitswochen in Java bedeutet, die Aspose.Tasks‑API zu nutzen, um auf die `WorkWeekCollection` eines Kalenderobjekts innerhalb einer Microsoft‑Project‑Datei zuzugreifen. Jede `WorkWeek` enthält Start‑/End‑Datum sowie die täglichen Arbeitszeit‑Definitionen, die bestimmen, wie Ressourcen geplant werden.

## Warum Arbeitswochen in Java aus einem Microsoft Project Kalender auslesen?
- **Automatisierung:** Manuelles Kopieren‑und‑Einfügen von Termin‑Daten eliminieren.  
- **Integration:** Arbeitswochen‑Informationen in ERP-, HR‑ oder benutzerdefinierte Reporting‑Systeme einspeisen.  
- **Konsistenz:** Sicherstellen, dass alle nachgelagerten Werkzeuge dieselben Kalenderregeln aus der Projektdatei respektieren.

## Voraussetzungen
Bevor wir zum Code kommen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Version 8 oder höher installiert.  
2. **Aspose.Tasks für Java** – Laden Sie das aktuelle JAR von der offiziellen Seite herunter: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Eine **Beispiel‑Projektdatei** (`ReadWorkWeeksInformation.mpp`) in einem bekannten Ordner.

## Pakete importieren
Importieren Sie zunächst die Klassen, die wir für die Arbeit mit Kalendern und Arbeitswochen benötigen:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Schritt 1: Datenverzeichnis festlegen
Definieren Sie den Ordner, der die `.mpp`‑Datei enthält. Ersetzen Sie den Platzhalter durch den tatsächlichen Pfad auf Ihrem Rechner:

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: Projektinstanz erstellen und auf den Kalender zugreifen
Instanziieren Sie ein `Project`‑Objekt, wählen Sie den gewünschten Kalender (nach UID) und holen Sie dessen `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro Tipp:** Wenn Sie die Kalender‑UID nicht kennen, können Sie über `project.getCalendars()` iterieren und den Namen sowie die UID jedes Kalenders ausgeben.

## Schritt 3: Durch Arbeitswochen iterieren
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
| `NullPointerException` beim Zugriff auf `calendar` | Falsche UID oder Kalender existiert nicht | UID mit `project.getCalendars().size()` prüfen und zuerst verfügbare Kalender auflisten. |
| Keine Ausgabe für Arbeitswochen | Der ausgewählte Kalender hat keine benutzerdefinierten Arbeitswochen (verwendet Standard) | Den Standardkalender (`project.getDefaultCalendar()`) nutzen oder programmgesteuert eine Arbeitswoche erstellen. |
| Datumsformat wirkt seltsam | `System.out.println` verwendet das Standardformat von `java.util.Date` | Einen `SimpleDateFormat` anwenden, um das Datum nach Bedarf zu formatieren. |

## Häufig gestellte Fragen

**F: Kann ich die Arbeitswochen‑Informationen mit Aspose.Tasks für Java ändern?**  
A: Ja. Die API stellt Methoden wie `addWorkWeek()`, `removeWorkWeek()` und Property‑Setter bereit, um Namen, Daten und Arbeitszeiten zu ändern.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Absolut. Es unterstützt MPP‑Dateien von Project 98 bis zu den neuesten Versionen sowie Project‑XML‑Dateien.

**F: Kann ich Aspose.Tasks in andere Java‑Frameworks integrieren?**  
A: Ja. Die Bibliothek ist reines Java, sodass Sie sie neben Spring, Jakarta EE oder jedem anderen Framework verwenden können.

**F: Gibt es eine Testversion von Aspose.Tasks?**  
A: Ja, Sie können eine kostenlose 30‑Tage‑Testversion von der offiziellen Seite herunterladen: [Aspose.Tasks trial](https://releases.aspose.com/).

**F: Wo finde ich Support für Aspose.Tasks?**  
A: Das Aspose‑Community‑Forum ist die beste Anlaufstelle: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Fazit
Sie haben nun **gelernt, wie Sie Arbeitswochen in Java** mit Aspose.Tasks auslesen. Durch Befolgen der obigen Schritte können Sie programmgesteuert Arbeitswochen‑Definitionen aus jedem MS‑Project‑Kalender abrufen, diese Daten in Ihre Anwendungen integrieren und arbeitsplanbezogene Workflows automatisieren. Experimentieren Sie gern mit dem Erstellen oder Aktualisieren von Arbeitswochen – Aspose.Tasks macht das unkompliziert.

---

**Zuletzt aktualisiert:** 2026‑02‑05  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}