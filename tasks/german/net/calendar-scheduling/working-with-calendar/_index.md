---
title: Arbeiten mit dem Kalender in Aspose.Tasks
linktitle: Arbeiten mit dem Kalender in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Verwalten Sie Projektkalender, berechnen Sie die Dauer und behandeln Sie Ausnahmen ganz einfach mit Aspose.Tasks für .NET.
weight: 10
url: /de/net/calendar-scheduling/working-with-calendar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Arbeiten mit dem Kalender in Aspose.Tasks

## Einführung

Aspose.Tasks für .NET bietet leistungsstarke Funktionen für die Arbeit mit Kalendern und ermöglicht Entwicklern eine effiziente Verwaltung von Projektzeitplänen und Ressourcenzuweisungen. In diesem Tutorial erfahren Sie, wie Sie Aspose.Tasks für die Interaktion mit Kalendern verwenden. Dabei werden wichtige Vorgänge wie das Abrufen von Kalenderinformationen, das Definieren von Arbeitswochen, das Berechnen von Arbeitsstunden und mehr behandelt.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundlegendes Verständnis der Programmiersprache C#.
-  Installation von Aspose.Tasks für .NET. Wenn es nicht installiert ist, laden Sie es herunter von[Hier](https://releases.aspose.com/tasks/net/).
- Vertrautheit mit Visual Studio oder einer anderen bevorzugten .NET-Entwicklungsumgebung.

## Namespaces importieren

Stellen Sie vor dem Codieren sicher, dass Sie die erforderlichen Namespaces importieren:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Lassen Sie uns nun jedes Beispiel in einer Schritt-für-Schritt-Anleitung in mehrere Schritte unterteilen:

## Schritt 1: Kalenderinformationen abrufen

Um Kalenderinformationen aus einem Projekt abzurufen, gehen Sie folgendermaßen vor:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Kalenderinformationen abrufen
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Durchlaufen Sie jeden Kalender im Projekt.
- Drucken Sie die UID und den Namen jedes Kalenders.

## Schritt 2: Informationen zur Arbeitswoche lesen

Gehen Sie folgendermaßen vor, um Informationen zur Arbeitswoche aus einem Kalender zu lesen:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Kalender per UID.
- Gehen Sie jede Arbeitswoche im Kalender durch.
- Drucken Sie den Namen, das Startdatum und das Enddatum jeder Arbeitswoche aus.
- Gehen Sie die Arbeitstage und Arbeitszeiten innerhalb jeder Woche durch.

## Schritt 3: Lesen Sie die Kalendereigenschaften

Um die Eigenschaften von Projektkalendern zu lesen, gehen Sie folgendermaßen vor:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Durchlaufen Sie jeden Kalender im Projekt.
- Drucken Sie UID, Namen und ob es sich um einen Basiskalender handelt.
- Drucken Sie die Arbeitszeiten für jeden Tagestyp aus.

## Schritt 4: Berechnen Sie die Arbeitszeit

Um die Arbeitsstunden für eine Aufgabe zu berechnen, gehen Sie folgendermaßen vor:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Erhalten Sie Aufgabendetails wie Kalender, Startdatum und Enddatum.
- Berechnen Sie die Arbeitszeit, indem Sie jeden Tag durchlaufen und prüfen, ob es ein Arbeitstag ist.
- Summieren Sie die Gesamtdauer in Minuten.

## Schritt 5: Wochentage für den Kalender definieren

Um Wochentage für einen Kalender zu definieren, gehen Sie folgendermaßen vor:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Erläuterung:
- Erstellen Sie ein neues Projekt und einen neuen Kalender.
- Fügen Sie Standardarbeitstage (Montag bis Donnerstag) und benutzerdefinierte Arbeitszeiten für Freitag hinzu.
- Legen Sie Samstag und Sonntag als arbeitsfreie Tage fest.

## Schritt 6: Aktualisierte Kalenderdaten in MPP schreiben

Um aktualisierte Kalenderdaten in eine MPP-Datei zu schreiben, gehen Sie folgendermaßen vor:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://Purchase.aspose.com/temporary-license/).");
    }
}
```

Erläuterung:
- Laden Sie die Projektdatei und rufen Sie den Standardkalender ab.
- Ändern Sie Kalenderdaten wie Ausnahmen und Arbeitszeiten.
- Speichern Sie das aktualisierte Projekt mit den geänderten Kalenderdaten.

## Schritt 7: Berechnen Sie das Enddatum der aufgeteilten Aufgabe

Um den Endtermin einer aufgeteilten Aufgabe zu berechnen, gehen Sie folgendermaßen vor:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Erläuterung:
- Laden Sie die Projektdatei und rufen Sie die geteilte Aufgabe ab.
- Holen Sie sich den Projektkalender.
- Berechnen Sie das Enddatum basierend auf einer benutzerdefinierten Dauer.

## Schritt 8: Kalenderausnahmen abrufen

Um Informationen zu Kalenderausnahmen abzurufen, führen Sie die folgenden Schritte aus:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Durchlaufen Sie jeden Kalender und seine Ausnahmen.
- Drucken Sie das Start- und Enddatum jeder Ausnahme aus.

## Schritt 9: Basisressourcenkalender abrufen

Um mit dem Basiskalender des Kalenders einer Ressource zu arbeiten, führen Sie die folgenden Schritte aus:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Fügen Sie eine Ressource und ihren Kalender hinzu.
- Drucken Sie den Basiskalendernamen für alle Ressourcen.

## Schritt 10: Kalender löschen

Um einen Kalender aus einem Projekt zu löschen, gehen Sie folgendermaßen vor:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Kalender nach Namen.
- Löschen Sie den Kalender.

## Schritt 11: Ermitteln Sie das Enddatum nach Start und Arbeit

Um einen Endtermin nach Starttermin und Arbeit zu berechnen, gehen Sie folgendermaßen vor:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Standardkalender.
- Definieren Sie ein Startdatum und eine Arbeitsdauer.
- Berechnen Sie den Endtermin basierend auf dem Starttermin und der Arbeit.

## Schritt 12: Starten Sie am nächsten Arbeitstag

Um mithilfe eines Kalenders den nächsten Arbeitstag zu beginnen, gehen Sie folgendermaßen vor:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Kalender per UID.
- Erhalten Sie die Startzeit am nächsten Werktag.

## Schritt 13: Erhalten Sie das Ende des vorherigen Arbeitstages

Um das Ende des vorherigen Arbeitstages mithilfe eines Kalenders anzuzeigen, gehen Sie folgendermaßen vor:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Kalender per UID.
- Rufen Sie die Endzeit des vorherigen Arbeitstages ab.

## Schritt 14: Startdatum aus Ende und Dauer ermitteln

Um ein Startdatum nach Enddatum und Dauer zu ermitteln, führen Sie die folgenden Schritte aus:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Kalender per UID.
- Berechnen Sie das Startdatum aus dem Enddatum und der Dauer.

## Schritt 15: Arbeitszeiten ermitteln

Um die Arbeitszeiten für ein bestimmtes Datum zu erhalten, gehen Sie folgendermaßen vor:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Kalender per UID.
- Rufen Sie die Arbeitszeiten für das angegebene Datum ab.

## Schritt 16: Arbeitszeiten ermitteln

Um Arbeitszeiten für ein bestimmtes Datum zu erhalten, gehen Sie folgendermaßen vor:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Erläuterung:
- Laden Sie die Projektdatei.
- Holen Sie sich den Kalender per UID.
- Rufen Sie die Arbeitszeiten für das angegebene Datum ab.

## Abschluss

Die Arbeit mit Kalendern in Aspose.Tasks für .NET ist für die effektive Verwaltung von Projektzeitplänen von entscheidender Bedeutung. Mit den bereitgestellten Beispielen und Schritt-für-Schritt-Anleitungen können Sie Kalenderdaten einfach bearbeiten, Aufgabendauern berechnen und Ausnahmen effizient behandeln. Durch die Integration dieser Funktionalitäten in Ihre Anwendungen können Sie Projektmanagementprozesse optimieren und eine genaue Terminplanung sicherstellen.

## FAQs

### F1: Benötige ich eine Lizenz, um Aspose.Tasks für .NET zu verwenden?

 A1: Ja, Sie benötigen eine gültige Lizenz, um Aspose.Tasks für .NET in Ihren Anwendungen nutzen zu können. Sie können eine Volllizenz erwerben oder eine 30-tägige temporäre Lizenz von erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### F2: Kann ich Kalenderausnahmen programmgesteuert ändern?

A2: Ja, Sie können Kalenderausnahmen mithilfe von Aspose.Tasks für .NET-APIs programmgesteuert hinzufügen, aktualisieren oder löschen.

### F3: Wie kann ich Aufgabenendtermine mit benutzerdefinierten Dauern berechnen?

 A3: Aspose.Tasks für .NET bietet Methoden wie`GetTaskFinishDateFromDuration()` um Aufgabenendtermine basierend auf benutzerdefinierten Dauern zu berechnen.

### F4: Ist es möglich, benutzerdefinierte Kalender zu erstellen, beispielsweise Nachtschichtkalender?

A4: Ja, Sie können mit Aspose.Tasks für .NET-APIs benutzerdefinierte Kalender wie Nachtschichtkalender erstellen.

### F5: Kann ich Informationen zu Kalenderausnahmen aus Projektdateien abrufen?

A5: Ja, Sie können mit Aspose.Tasks für .NET problemlos Informationen zu Kalenderausnahmen aus Projektdateien abrufen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
