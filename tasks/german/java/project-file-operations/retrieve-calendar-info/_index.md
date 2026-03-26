---
date: 2025-12-20
description: Erfahren Sie, wie Sie Aspose.Tasks verwenden, um Projektkalenderdetails
  aus Microsoft Project‑Dateien mit Java zu extrahieren. Schritt‑für‑Schritt‑Anleitung
  mit Codebeispielen.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Aspose.Tasks verwendet, um MS Project‑Kalenderinformationen abzurufen
url: /de/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So verwenden Sie Aspose.Tasks, um MS Project Kalenderinformationen abzurufen

## Einführung
In diesem Tutorial **erfahren Sie, wie Sie Aspose.Tasks** programmatisch verwenden, um Kalenderinformationen aus Microsoft‑Project‑Dateien abzurufen. Der Zugriff auf Kalenderdaten wie Arbeitstage, Arbeitszeiten und Ausnahmen ist entscheidend, wenn Sie **Projektkalender**‑Details für Berichte, Integrationen oder benutzerdefinierte Terminlogik extrahieren müssen. Lassen Sie uns den Prozess Schritt für Schritt durchgehen.

## Schnelle Antworten
- **Welche Bibliothek wird in diesem Tutorial verwendet?** Aspose.Tasks für Java.  
- **Welches Haupt‑Keyword wird behandelt?** *how to use aspose.tasks*.  
- **Was können Sie extrahieren?** Projektkalender, einschließlich Arbeitstage und -stunden.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.

## Warum Projektkalenderinformationen extrahieren?
Projektkalender bestimmen Aufgabendaten, Ressourcenzuweisungen und Gesamtlaufzeit‑Berechnungen. Durch das Extrahieren dieser Daten können Sie:
- Benutzerdefinierte Berichte erstellen, die tatsächliche Arbeitspläne widerspiegeln.  
- Microsoft‑Project‑Zeitpläne mit externen Systemen (ERP, BI usw.) synchronisieren.  
- Was‑wenn‑Analysen durchführen, indem Sie Kalendereinstellungen programmgesteuert ändern.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundlegende Kenntnisse in der Java‑Programmierung.  
- Java Development Kit (JDK) auf Ihrem System installiert.  
- Aspose.Tasks für Java‑Bibliothek. Sie können sie von [hier](https://releases.aspose.com/tasks/java/) herunterladen.

## Pakete importieren
Importieren Sie zunächst die notwendigen Aspose.Tasks‑Klassen in Ihr Java‑Projekt.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Schritt 1: Datenverzeichnis festlegen
Definieren Sie den Ordner, der Ihre *.mpp*-Datei enthält.

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad zu dem Ordner, in dem **project.mpp** liegt.

## Schritt 2: Zeiteinheiten definieren
Erstellen Sie Konstanten, die dabei helfen, die interne Zeitdarstellung in menschenlesbare Stunden umzuwandeln.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Diese Werte werden in Mikrosekunden angegeben, da Aspose.Tasks die Zeit intern so speichert.

## Schritt 3: Projektinstanz erstellen
Laden Sie die Microsoft‑Project‑Datei in ein `Project`‑Objekt.

```java
Project project = new Project(dataDir + "project.mpp");
```

Der `Project`‑Konstruktor parsed die *.mpp*-Datei und macht alle Projektdaten, einschließlich Kalender, über die API zugänglich.

## Schritt 4: Kalenderinformationen abrufen
Holen Sie die Sammlung der im Projekt definierten Kalender.

```java
CalendarCollection alCals = project.getCalendars();
```

Ein Projekt kann mehrere Kalender enthalten (Standard‑, Ressourcen‑ und benutzerdefinierte Kalender). Diese Sammlung gibt Ihnen Zugriff auf jeden einzelnen.

## Schritt 5: Durch Kalender iterieren
Durchlaufen Sie jeden Kalender, geben Sie dessen UID, Namen und die Arbeitstage mit den entsprechenden Stunden aus.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Die innere Schleife prüft jedes `WeekDay`‑Objekt. Ist der Tag als Arbeitstag markiert, wird der Wochentyp (Monday, Tuesday, …) zusammen mit den berechneten Arbeitsstunden ausgegeben.

## Schritt 6: Abschlussnachricht anzeigen
Signalisiert, dass der Extraktionsvorgang abgeschlossen ist.

```java
System.out.println("Process completed Successfully");
```

## Fazit
Durch das Befolgen dieser Schritte **wissen Sie jetzt, wie Sie Aspose.Tasks verwenden, um Projektkalender**‑Informationen aus einer MS‑Project‑Datei mit Java zu extrahieren. Sie können diese Logik in größere Anwendungen integrieren, Berichte automatisieren oder Zeitpläne mit anderen Unternehmenssystemen synchronisieren.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?**  
A: Ja, Aspose.Tasks unterstützt mehrere Plattformen und Programmiersprachen, darunter .NET, C++, Python und Java.

**F: Gibt es eine kostenlose Testversion von Aspose.Tasks?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen.

**F: Wie erhalte ich Support für Aspose.Tasks?**  
A: Sie erhalten Support im Aspose.Tasks‑Community‑Forum [hier](https://forum.aspose.com/c/tasks/15).

**F: Kann ich eine temporäre Lizenz für Aspose.Tasks erwerben?**  
A: Ja, temporäre Lizenzen können Sie [hier](https://purchase.aspose.com/temporary-license/) erwerben.

**F: Wo finde ich ausführliche Dokumentation zu Aspose.Tasks?**  
A: Die Dokumentation finden Sie [hier](https://reference.aspose.com/tasks/java/).

---

**Zuletzt aktualisiert:** 2025-12-20  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}