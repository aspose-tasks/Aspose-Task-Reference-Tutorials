---
date: 2026-04-09
description: Erfahren Sie, wie Sie den Standardkalender festlegen und Projektfeiertage
  in Ihren .NET‑Projekten mit Aspose.Tasks für eine genaue Terminplanung verwalten.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Standardkalender festlegen und Ausnahmen in Aspose.Tasks behandeln
second_title: Aspose.Tasks .NET API
title: Standardkalender festlegen und Ausnahmen in Aspose.Tasks behandeln
url: /de/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Standardkalender festlegen und Ausnahmen in Aspose.Tasks behandeln

## Einführung

Eine genaue Terminplanung ist das Rückgrat jedes erfolgreichen Projekts, und reale Pläne müssen häufig vom Standardarbeitskalender abweichen, etwa wegen Feiertagen, besonderen Ereignissen oder unerwarteten Stilllegungen. Aspose.Tasks für .NET erleichtert das **Festlegen eines Standardkalenders** und das Hinzufügen benutzerdefinierter Ausnahmen. In diesem Tutorial lernen Sie, wie Sie einen Projektkalender laden, einen Standardkalender festlegen und Projektfeiertage über die Calendar Exception Collection verwalten.

## Schnelle Antworten
- **Was bewirkt „set standard calendar“?** Es setzt einen Kalender auf die Standardarbeitszeit zurück (9 Uhr‑17 Uhr, Montag‑Freitag), bevor Sie benutzerdefinierte Ausnahmen hinzufügen.  
- **Welche Methode löscht vorhandene Ausnahmen?** `Calendar.Exceptions.Clear()` entfernt alle zuvor definierten Ausnahmen.  
- **Wie kann ich einen Feiertag hinzufügen?** Erstellen Sie ein `CalendarException` mit `DayWorking = false` und fügen Sie es zur Sammlung hinzu.  
- **Muss ich das Projekt nach Änderungen neu laden?** Nein, Änderungen werden direkt auf das im Speicher befindliche `Project`‑Objekt angewendet.  
- **Welche Bibliotheken werden benötigt?** Aspose.Tasks für .NET (jede unterstützte .NET‑Version) und die `System`‑Namespaces.  

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.Tasks für .NET** – laden Sie es [hier](https://releases.aspose.com/tasks/net/) herunter.  
2. Grundkenntnisse in **C#** – Sie werden ein paar kurze Code‑Snippets schreiben.  
3. Eine Entwicklungsumgebung wie **Visual Studio** oder **JetBrains Rider**.  

## Namespaces importieren

Diese `using`‑Direktiven geben Ihnen Zugriff auf die Klassen, die für die Kalendermanipulation benötigt werden.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Was ist eine Calendar Exception?

Eine *Calendar Exception* stellt einen Zeitraum dar, in dem der normale Arbeitsplan geändert wird – zum Beispiel ein unternehmensweiter Feiertag oder ein vorübergehender Überstundenplan. Durch das Hinzufügen von Ausnahmen zu einem Kalender können Sie reale Einschränkungen modellieren, ohne den Basis‑Kalender zu ändern.

## Wie man einen Standardkalender in Aspose.Tasks festlegt

Der erste Schritt besteht darin, Ihre Projektdatei zu laden und den Kalender abzurufen, mit dem Sie arbeiten möchten.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Schritt 1: Vorhandene Ausnahmen löschen und auf einen Standardkalender zurücksetzen

Bevor Sie neue Regeln hinzufügen, ist es ratsam, alte Ausnahmen zu löschen und die **Standardkalender**‑Einstellungen festzulegen. Das sorgt für eine saubere Ausgangsbasis.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Schritt 2: Eine Arbeitszeit‑Ausnahme definieren

Manchmal müssen Sie einen vorübergehenden Zeitplan erstellen (z. B. verlängerte Arbeitszeiten für eine Produkteinführung). Das folgende Snippet definiert eine Arbeitszeit‑Ausnahme, die mehrere Tage umfasst und zwei tägliche Arbeitsperioden enthält.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Schritt 3: Nicht‑Arbeitszeit‑Ausnahmen hinzufügen (Feiertage)

Um **Projektfeiertage zu verwalten**, erstellen Sie Ausnahmen, bei denen `DayWorking` auf `false` gesetzt ist. Das nachstehende Beispiel fügt einen zweitägigen Feiertagsblock hinzu.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Schritt 4: Kalenderausnahmen anzeigen (Verifizierung)

Nach dem Hinzufügen von Ausnahmen möchten Sie häufig überprüfen, ob sie korrekt erfasst wurden. Die folgende Schleife gibt die Details jeder Ausnahme in der Konsole aus.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Schritt 5: Alle Ausnahmen entfernen (Aufräumen)

Wenn Sie den Kalender in seinen ursprünglichen Zustand zurückversetzen müssen, können Sie jede Ausnahme programmgesteuert entfernen.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|---------|----------|--------|
| Ausnahmen erscheinen nach dem Speichern nicht | Projekt wurde nach Änderungen nicht gespeichert | Rufen Sie `project.Save("output.mpp")` nach den Änderungen auf. |
| Überschneidende Ausnahmen führen zu unerwarteten Arbeitszeiten | Aspose.Tasks verwendet für überlappende Zeiträume die zuletzt hinzugefügte Ausnahme | Ordnen Sie Ihre `Add`‑Aufrufe sorgfältig oder passen Sie die Prioritäten manuell an. |
| `MakeStandardCalendar` setzt benutzerdefinierte Arbeitszeiten zurück | Es löscht absichtlich benutzerdefinierte Zeiten; fügen Sie sie bei Bedarf nach dem Aufruf erneut hinzu. | Fügen Sie Ihre benutzerdefinierten `WorkingTime`‑Objekte nach dem Aufruf von `MakeStandardCalendar` hinzu. |

## Häufig gestellte Fragen

**Q: Kann ich mehrere Ausnahmen zu einem einzelnen Kalender hinzufügen?**  
A: Ja, Sie können mehrere Ausnahmen zu einem Kalender hinzufügen, indem Sie die Methode `AddRange` verwenden.

**Q: Wie gehe ich mit wiederkehrenden Ausnahmen um, z. B. wöchentlichen Feiertagen?**  
A: Sie können wiederkehrende Ausnahmen programmgesteuert berechnen und sie mit benutzerdefinierter Logik zum Kalender hinzufügen.

**Q: Ist es möglich, Kalenderausnahmen aus externen Quellen zu importieren?**  
A: Ja, Sie können Kalenderausnahmen aus externen Quellen wie Datenbanken oder CSV‑Dateien lesen und in Ihr Projekt integrieren.

**Q: Was passiert, wenn im Kalender überlappende Ausnahmen vorhanden sind?**  
A: Aspose.Tasks für .NET ermöglicht es Ihnen, überlappende Ausnahmen zu handhaben, indem Sie Prioritäten festlegen oder Konflikte basierend auf Ihren Projektanforderungen lösen.

**Q: Kann ich die Arbeitszeiten für jeden Tag innerhalb einer Ausnahme anpassen?**  
A: Ja, Sie können für einzelne Tage innerhalb einer Ausnahme benutzerdefinierte Arbeitszeiten festlegen, um spezifische Terminierungsbedürfnisse zu erfüllen.

## Fazit

Indem Sie zuerst einen **Standardkalender festlegen** und anschließend benutzerdefinierte Ausnahmen hinzufügen, erhalten Sie die volle Kontrolle über die Projektplanung, wodurch es einfach wird, **Projektfeiertage** und andere Sonderzeitpläne zu **verwalten**. Die Calendar Exception Collection in Aspose.Tasks bietet eine saubere, programmgesteuerte Methode, reale Kalender direkt in Ihren .NET‑Anwendungen zu modellieren.

---

**Zuletzt aktualisiert:** 2026-04-09  
**Getestet mit:** Aspose.Tasks 24.12 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}