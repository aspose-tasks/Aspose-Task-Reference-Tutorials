---
date: 2026-04-13
description: Erfahren Sie, wie Sie Kalenderausnahmen in Aspose.Tasks für .NET löschen
  und das Ausnahmedatum beim Verwalten der ASP.NET‑Kalenderplanung überprüfen.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Kalenderausnahme mit Aspose.Tasks löschen
second_title: Aspose.Tasks .NET API
title: Kalenderausnahme mit Aspose.Tasks löschen
url: /de/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kalenderausnahme löschen mit Aspose.Tasks

## Einführung

In diesem Tutorial lernen Sie, wie Sie **Kalenderausnahmen löschen** und andere Kalenderausnahmen in Aspose.Tasks mit dem .NET‑Framework verwalten. Kalenderausnahmen ermöglichen es, Feiertage, vorübergehende Schließungen oder andere besondere Zeiträume zu modellieren, in denen der normale Arbeitsplan geändert wird. Das Verständnis, wie man diese Ausnahmen hinzufügt, abfragt und entfernt, ist für eine genaue Projektplanung unerlässlich, insbesondere bei **ASP.NET‑Kalenderplanung**‑Szenarien.

## Schnelle Antworten
- **Was ist die primäre Methode zum Entfernen einer Ausnahme?** Verwenden Sie die `Delete()`‑Methode des `CalendarException`‑Objekts.  
- **Welche Klasse prüft ein Datum gegen eine Ausnahme?** `CalendarException.CheckException()` — nützlich, um das **Ausnahmedatum zu prüfen**.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Ja, für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.  
- **Kann ich mehrere Ausnahmen zu einem Kalender hinzufügen?** Absolut; die `Exceptions`‑Sammlung unterstützt viele Einträge.  
- **Unterstützte .NET‑Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist eine Kalenderausnahme?

Eine **Kalenderausnahme** stellt eine Abweichung vom regulären Arbeitskalender dar – man kann sie als Regel verstehen, die besagt: „An diesen Daten sind die Arbeitszeiten anders oder es gibt keine Arbeitszeit.“ In Aspose.Tasks kann jede Ausnahme eigene Arbeitszeiten, ein Wiederholungsmuster und Flags haben, die anzeigen, ob der Tag ein Arbeitstag ist.

## Warum Kalenderausnahmen in ASP.NET‑Kalenderplanung verwalten?

- **Genauere Zeitpläne:** Projekte berücksichtigen automatisch Feiertage und Sonderschließungen, wodurch unrealistische Fristen vermieden werden.  
- **Flexibilität:** Sie können tägliche, wöchentliche, monatliche oder jährliche Muster definieren, die den realen Geschäftskalendern entsprechen.  
- **Automatisierung:** Das programmgesteuerte Prüfen eines Ausnahmedatums ermöglicht den Aufbau dynamischer Planungslogik in ASP.NET‑Anwendungen.

## Voraussetzungen

- Grundkenntnisse in C#‑Programmierung.  
- Visual Studio (beliebige aktuelle Version).  
- Aspose.Tasks für .NET‑Bibliothek zu Ihrem Projekt hinzugefügt (via NuGet oder manuelle Referenz).  

## Namespaces importieren

Importieren Sie zunächst die benötigten Namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Schritt 1: Kalenderausnahme löschen

Das Entfernen einer unerwünschten Ausnahme ist unkompliziert. Der folgende Code lädt ein Projekt, wählt den ersten Kalender aus, zeigt grundlegende Informationen an, löscht die erste Ausnahme und zeigt anschließend die aktualisierte Anzahl.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Profi‑Tipp:** Überprüfen Sie stets, ob der Ausnahmindex existiert, bevor Sie `Delete()` aufrufen, um `IndexOutOfRangeException` zu vermeiden.

## Schritt 2: Arbeitszeit einer Kalenderausnahme abrufen

Wenn Sie die für eine Ausnahme definierten Arbeitszeiten prüfen müssen, verwenden Sie `GetWorkingTime()`. Dieses Beispiel zeigt zudem, wie man mit `CheckException` das **Ausnahmedatum prüft**.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Schritt 3: Kalenderausnahmen definieren

Im Folgenden finden Sie eine vollständige Schritt‑für‑Schritt‑Durchführung, die zeigt, wie man Kalenderausnahmen **hinzufügt**, **prüft** und **entfernt**. Beachten Sie die Verwendung von `CheckException`, um das **Ausnahmedatum** für einen bestimmten Moment zu prüfen.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Häufige Probleme & Tipps

| Problem | Grund | Lösung |
|-------|--------|----------|
| **`IndexOutOfRangeException` beim Löschen** | Versuch, eine nicht existente Ausnahme zu löschen. | Stellen Sie sicher, dass `calendar.Exceptions.Count` > Index ist, bevor Sie `Delete()` aufrufen. |
| **Falsche Arbeitszeiten** | `DayWorking` oder `WorkingTimes` wurden nicht korrekt gesetzt. | Verwenden Sie `exception.WorkingTimes.Add(new WorkingTime(...))`, um explizite Zeiträume zu definieren. |
| **Ausnahme nicht erkannt** | `CheckException` gibt `false` zurück, weil das Datum außerhalb des definierten Bereichs liegt. | Überprüfen Sie `FromDate`/`ToDate` und den `Type` (Daily, Weekly usw.). |

## Häufig gestellte Fragen

**F: Kann ich mehrere Ausnahmen zu einem einzelnen Kalender hinzufügen?**  
A: Ja, Sie können beliebig viele Ausnahmen hinzufügen, um Feiertage, Wartungsfenster oder andere spezielle Planungsregeln darzustellen.

**F: Wie prüfe ich das **Ausnahmedatum** für einen bestimmten Tag?**  
A: Verwenden Sie die Methode `CheckException(DateTime date)` einer `CalendarException`‑Instanz. Sie gibt `true` zurück, wenn das angegebene Datum innerhalb des Ausnahmereichs liegt.

**F: Ist es möglich, eine bestehende Ausnahme aus einem Kalender zu entfernen?**  
A: Absolut. Greifen Sie auf die `Exceptions`‑Sammlung zu und rufen Sie `Remove()` auf oder verwenden Sie `Delete()` auf dem jeweiligen `CalendarException`‑Objekt.

**F: Welche Arten von Kalenderausnahmen werden unterstützt?**  
A: Aspose.Tasks unterstützt tägliche, wöchentliche, monatliche und jährliche Ausnahmetypen, was Ihnen Flexibilität bietet, fast jedes Wiederholungsmuster zu modellieren.

**F: Kann ich Arbeitszeiten für bestimmte Ausnahmedaten anpassen?**  
A: Ja. Nachdem Sie eine Ausnahme erstellt haben, füllen Sie deren `WorkingTimes`‑Sammlung mit `WorkingTime`‑Objekten, die Start‑ und Endzeiten für diesen Tag definieren.

## Fazit

Wir haben den gesamten Lebenszyklus von **Kalenderausnahmen löschen**‑Operationen durchlaufen, von der Inspektion vorhandener Ausnahmen bis zum Hinzufügen neuer und dem Prüfen von Daten. Das Beherrschen dieser Techniken stellt sicher, dass Ihre Projektpläne reale Kalender berücksichtigen und Ihre ASP.NET‑Kalenderplanungs‑Implementierungen robust und zuverlässig machen.

---

**Zuletzt aktualisiert:** 2026-04-13  
**Getestet mit:** Aspose.Tasks für .NET (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}