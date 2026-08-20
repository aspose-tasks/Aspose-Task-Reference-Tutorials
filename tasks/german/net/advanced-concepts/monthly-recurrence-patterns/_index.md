---
date: 2026-03-08
description: Erfahren Sie, wie Sie in Aspose.Tasks für .NET eine monatlich wiederkehrende
  Aufgabe mit diesem Schritt‑für‑Schritt‑Tutorial erstellen.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Wie man in Aspose.Tasks eine monatlich wiederkehrende Aufgabe erstellt
url: /de/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Monatliche wiederkehrende Aufgabe mit Aspose.Tasks erstellen

## Einführung

Aspose.Tasks für .NET ermöglicht es Ihnen, Microsoft Project‑Dateien programmgesteuert zu manipulieren, und einer der häufigsten Praxisfälle ist das **Erstellen von monatlich wiederkehrenden Aufgaben**‑Zeitplänen. Egal, ob Sie ein Projekt‑Tracking‑Tool bauen, die Ressourcen‑Zuweisung automatisieren oder wiederkehrende Wartungsarbeiten erzeugen, führt Sie dieses Tutorial Schritt für Schritt durch das Hinzufügen eines monatlichen Wiederholungsmusters zu einer Aufgabe.

In den folgenden Abschnitten sehen Sie, wie Sie das Projekt einrichten, die Wiederholungsparameter definieren und schließlich die aktualisierte Datei speichern – alles mit klaren Erklärungen und praktischen Tipps.

## Schnelle Antworten
- **Was bedeutet „monatliche wiederkehrende Aufgabe“?** Eine Aufgabe, die sich jeden Monat nach einem definierten Tag‑oder‑Wochen‑Muster wiederholt.  
- **Welche API‑Klasse behandelt Wiederholungen?** `RecurringTaskParameters` zusammen mit `MonthlyRecurrencePattern`.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine Lizenz erforderlich.  
- **Kann ich das Intervall ändern?** Ja – setzen Sie `RepetitionInterval` auf die Anzahl der Monate zwischen den Vorkommnissen.  
- **Welche Dateiformate werden unterstützt?** Sowohl `.mpp`‑ als auch `.xml`‑Projektdateien können geladen und gespeichert werden.

## Was ist ein monatliches Wiederholungsmuster?

Ein monatliches Wiederholungsmuster gibt Microsoft Project (und Aspose.Tasks) an, wie oft eine Aufgabe jeden Monat wiederholt werden soll. Sie können einen festen Tag im Monat festlegen (z. B. den 1.) oder eine relative Position (z. B. den letzten Freitag). Die API übersetzt diese Regeln in die zugrunde liegende Projektdateistruktur.

## Warum Aspose.Tasks dafür verwenden?

- **Vollständige Kontrolle** – Keine UI‑Einschränkungen; Sie definieren jeden Aspekt des Musters im Code.  
- **Plattformübergreifend** – Funktioniert auf .NET Framework, .NET Core und .NET 5/6+.  
- **Kein Microsoft Project erforderlich** – Erzeugen oder ändern Sie Dateien auf einem Server oder in einer CI‑Pipeline.  

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie:

- .NET 6 (oder .NET 5/Framework 4.7+) installiert haben.  
- Das NuGet‑Paket Aspose.Tasks für .NET zu Ihrem Projekt hinzugefügt haben.  
- Eine Beispiel‑Projektdatei (`Project1.mpp`) in einem bekannten Ordner (`DataDir`) abgelegt haben.  

## Namespaces importieren

Importieren Sie zunächst die Namespaces, die für die Arbeit mit Aufgaben und das Speichern von Projekten erforderlich sind:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Schritt 1: Projekt initialisieren

Erzeugen Sie eine `Project`‑Instanz, die auf Ihre vorhandene `.mpp`‑Datei verweist. Dadurch wird die Datei in den Speicher geladen, sodass Sie sie bearbeiten können.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Pro‑Tipp:** Wenn die Datei nicht existiert, erstellt Aspose.Tasks automatisch ein neues leeres Projekt.

## Schritt 2: Wiederkehrende Aufgabenparameter festlegen

Definieren Sie die Details der wiederkehrenden Aufgabe, einschließlich ihres Namens, ihrer Dauer und des monatlichen Musters, das Sie anwenden möchten.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` bedeutet, dass die Aufgabe am **ersten Tag** des Monats stattfindet.  
- `RepetitionInterval = 2` lässt die Aufgabe **alle zwei Monate** wiederholen.  
- `Start` und `Finish` definieren das gesamte Zeitfenster, in dem die Wiederholung aktiv ist.

## Schritt 3: Parameter zum Projekt hinzufügen

Fügen Sie das Objekt `RecurringTaskParameters` der Kindersammlung der Root‑Aufgabe hinzu. Dadurch wird die wiederkehrende Aufgabe effektiv in der Projekt‑Hierarchie erstellt.

```csharp
project.RootTask.Children.Add(parameters);
```

## Schritt 4: Projekt speichern

Speichern Sie die Änderungen, indem Sie das Projekt in einer neuen Datei sichern. Sie können jedes unterstützte Format wählen; hier verwenden wir das native `.mpp`‑Format.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Nachdem Sie den Code ausgeführt haben, öffnen Sie die resultierende Datei in Microsoft Project, um die gerade erstellte monatliche wiederkehrende Aufgabe zu sehen.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| Aufgabe erscheint nach dem Speichern nicht | Projekt wurde in der UI nicht aktualisiert | Öffnen Sie die Datei erneut oder rufen Sie `project.UpdateTaskLinks()` vor dem Speichern auf. |
| Falsches Startdatum | `Start` auf ein Wochenende gesetzt | Verwenden Sie ein `DateTime`, das auf einen Arbeitstag fällt, oder passen Sie den Kalender an. |
| Wiederholungsintervall ignoriert | Verwendung von `ByMonthDayRepetition` mit `DayPosition` = 0 | Stellen Sie sicher, dass `DayPosition` zwischen 1‑31 liegt. |

## Fazit

Wenn Sie diese Schritte befolgt haben, wissen Sie nun, wie Sie mit Aspose.Tasks für .NET **monatliche wiederkehrende Aufgaben**‑Zeitpläne erstellen. Die API bietet Ihnen eine feinkörnige Kontrolle über Wiederholungsintervalle, Start‑/End‑Bereiche und das spezifische Tagesmuster, sodass Sie komplexe Projektplanungs‑Szenarien automatisieren können.

## FAQ

### Q1: Ist Aspose.Tasks mit allen Versionen von Microsoft Project‑Dateien kompatibel?

A1: Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project‑Dateien, einschließlich MPP, MPT, XML und MPX.

### Q2: Kann ich das Wiederholungsmuster weiter anpassen?

A2: Ja, Aspose.Tasks bietet umfangreiche Optionen zur Anpassung von Wiederholungsmustern, einschließlich täglich, wöchentlich, monatlich und jährlich.

### Q3: Gibt es eine kostenlose Testversion von Aspose.Tasks?

A3: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks über die Website [hier](https://releases.aspose.com/) erhalten.

### Q4: Wie kann ich Support für Aspose.Tasks erhalten?

A4: Sie können Hilfe erhalten und an Diskussionen im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) teilnehmen.

### Q5: Wo kann ich eine Lizenz für Aspose.Tasks erwerben?

A5: Sie können eine Lizenz für Aspose.Tasks über die Website [hier](https://purchase.aspose.com/buy) erwerben.

## Häufig gestellte Fragen

**Q: Kann ich diesen Code in einer .NET Core‑Anwendung verwenden?**  
A: Absolut. Aspose.Tasks für .NET unterstützt .NET Core 3.1 und spätere Versionen vollständig.

**Q: Wie ändere ich die Wiederholung zu „letzter Werktag des Monats“?**  
A: Verwenden Sie `ByMonthDayRepetition` mit `DayPosition = -1` (negative Werte zählen vom Monatsende) und setzen Sie `WeekDay` entsprechend.

**Q: Was passiert, wenn der Wiederholungszeitraum den Projektkalender überschreitet?**  
A: Die API respektiert den Projektkalender; Vorkommnisse, die auf Nicht‑Arbeitstage fallen, werden entweder übersprungen oder basierend auf den Kalendereinstellungen verschoben.

**Q: Ist es möglich, ein bestimmtes Vorkommen einer wiederkehrenden Aufgabe zu löschen?**  
A: Ja. Nachdem Sie die wiederkehrende Aufgabe hinzugefügt haben, können Sie einzelne Vorkommen über `Task.GetOccurrences()` abrufen und die nicht benötigten löschen.

**Q: Handhabt Aspose.Tasks Zeitzonen‑Unterschiede automatisch?**  
A: Die Bibliothek speichert Daten in UTC; bei Bedarf können Sie mit den Standard‑.NET‑`DateTime`‑Methoden in die lokale Zeit konvertieren.

---

**Zuletzt aktualisiert:** 2026-03-08  
**Getestet mit:** Aspose.Tasks 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}