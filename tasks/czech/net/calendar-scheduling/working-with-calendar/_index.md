---
title: Práce s kalendářem v Aspose.Tasks
linktitle: Práce s kalendářem v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Spravujte projektové kalendáře, počítejte dobu trvání, snadno zpracujte výjimky pomocí Aspose.Tasks for .NET.
weight: 10
url: /cs/net/calendar-scheduling/working-with-calendar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Práce s kalendářem v Aspose.Tasks

## Úvod

Aspose.Tasks for .NET poskytuje výkonné funkce pro práci s kalendáři a umožňuje vývojářům efektivně řídit plány projektů a přidělování zdrojů. V tomto tutoriálu prozkoumáme, jak využít Aspose.Tasks k interakci s kalendáři, pokrývající základní operace, jako je získávání informací z kalendáře, definování pracovních týdnů, výpočet pracovní doby a další.

## Předpoklady

Než začneme, ujistěte se, že máte nastaveny následující předpoklady:

- Základní znalost programovacího jazyka C#.
-  Instalace Aspose.Tasks pro .NET. Pokud není nainstalován, stáhněte si jej z[tady](https://releases.aspose.com/tasks/net/).
- Znalost Visual Studia nebo jiného preferovaného vývojového prostředí .NET.

## Importovat jmenné prostory

Než začnete kódovat, nezapomeňte importovat potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Nyní si každý příklad rozdělíme do několika kroků ve formátu podrobného průvodce:

## Krok 1: Načtěte informace z kalendáře

Chcete-li načíst informace kalendáře z projektu, postupujte takto:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Načíst informace z kalendářů
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

Vysvětlení:
- Načtěte soubor projektu.
- Iterujte každý kalendář v projektu.
- Vytiskněte UID a název každého kalendáře.

## Krok 2: Přečtěte si informace o pracovních týdnech

Chcete-li číst informace o pracovních týdnech z kalendáře, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Získejte kalendář podle UID.
- Projděte si každý pracovní týden v kalendáři.
- Vytiskněte název, datum zahájení a datum ukončení každého pracovního týdne.
- Procházejte pracovní dny a pracovní doby v rámci každého týdne.

## Krok 3: Přečtěte si vlastnosti kalendáře

Chcete-li číst vlastnosti projektových kalendářů, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Iterujte každý kalendář v projektu.
- Vytisknout UID, jméno a zda se jedná o základní kalendář.
- Tisk pracovní doby pro každý typ dne.

## Krok 4: Vypočítejte pracovní dobu

Chcete-li vypočítat pracovní dobu pro úkol, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Získejte podrobnosti o úkolu, jako je kalendář, datum zahájení a datum ukončení.
- Vypočítejte pracovní dobu opakováním každého dne a kontrolou, zda se jedná o pracovní den.
- Sečtěte celkovou dobu trvání v minutách.

## Krok 5: Definujte pracovní dny pro kalendář

Chcete-li definovat dny v týdnu pro kalendář, postupujte takto:

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

Vysvětlení:
- Vytvořte nový projekt a kalendář.
- Přidejte výchozí pracovní dny (pondělí až čtvrtek) a vlastní pracovní dobu pro pátek.
- Nastavte sobotu a neděli jako dny pracovního klidu.

## Krok 6: Zapište aktualizovaná data kalendáře do MPP

Chcete-li zapsat aktualizovaná data kalendáře do souboru MPP, postupujte takto:

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://purchase.aspose.com/temporary-license/).");
    }
}
```

Vysvětlení:
- Načtěte soubor projektu a načtěte standardní kalendář.
- Upravte data kalendáře, jako jsou výjimky a pracovní doby.
- Uložte aktualizovaný projekt s upravenými daty kalendáře.

## Krok 7: Vypočítejte datum dokončení rozděleného úkolu

Chcete-li vypočítat datum dokončení rozděleného úkolu, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu a načtěte rozdělenou úlohu.
- Získejte kalendář projektu.
- Vypočítejte datum dokončení na základě vlastního trvání.

## Krok 8: Načtení výjimek kalendáře

Chcete-li načíst informace o výjimkách kalendáře, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Procházejte každý kalendář a jeho výjimky.
- Vytiskněte počáteční a koncové datum každé výjimky.

## Krok 9: Získejte základní kalendář zdrojů

Chcete-li pracovat se základním kalendářem kalendáře zdroje, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Přidejte zdroj a jeho kalendář.
- Vytiskněte název základního kalendáře pro všechny zdroje.

## Krok 10: Odstraňte kalendář

Chcete-li odstranit kalendář z projektu, postupujte takto:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Vysvětlení:
- Načtěte soubor projektu.
- Získejte kalendář podle jména.
- Smazat kalendář.

## Krok 11: Získejte datum dokončení podle začátku a práce

Chcete-li vypočítat datum dokončení podle data zahájení a práce, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Získejte standardní kalendář.
- Definujte datum zahájení a dobu trvání práce.
- Vypočítejte datum dokončení na základě data zahájení a práce.

## Krok 12: Získejte začátek dalšího pracovního dne

Chcete-li začít další pracovní den pomocí kalendáře, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Získejte kalendář podle UID.
- Získejte čas začátku následujícího pracovního dne.

## Krok 13: Získejte konec předchozího pracovního dne

Chcete-li získat konec předchozího pracovního dne pomocí kalendáře, postupujte takto:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Vysvětlení:
- Načtěte soubor projektu.
- Získejte kalendář podle UID.
- Získejte čas ukončení předchozího pracovního dne.

## Krok 14: Získejte datum zahájení od dokončení a trvání

Chcete-li získat datum zahájení podle data ukončení a trvání, postupujte takto:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Vysvětlení:
- Načtěte soubor projektu.
- Získejte kalendář podle UID.
- Vypočítejte datum zahájení z data ukončení a trvání.

## Krok 15: Získejte pracovní dobu

Chcete-li získat pracovní dobu pro konkrétní datum, postupujte takto:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Vysvětlení:
- Načtěte soubor projektu.
- Získejte kalendář podle UID.
- Získejte pracovní dobu pro zadané datum.

## Krok 16: Získejte pracovní dobu

Chcete-li získat pracovní dobu pro konkrétní datum, postupujte takto:

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

Vysvětlení:
- Načtěte soubor projektu.
- Získejte kalendář podle UID.
- Získejte pracovní dobu pro zadané datum.

## Závěr

Práce s kalendáři v Aspose.Tasks pro .NET je klíčová pro efektivní správu plánů projektů. S poskytnutými příklady a podrobnými průvodci můžete snadno manipulovat s daty kalendáře, vypočítat dobu trvání úkolů a efektivně zpracovávat výjimky. Integrací těchto funkcí do vašich aplikací můžete zefektivnit procesy řízení projektů a zajistit přesné plánování.

## FAQ

### Q1: Potřebuji licenci k používání Aspose.Tasks pro .NET?

 Odpověď 1: Ano, k využití Aspose.Tasks for .NET ve vašich aplikacích potřebujete platnou licenci. Můžete si zakoupit plnou licenci nebo získat 30denní dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).

### Q2: Mohu upravit výjimky kalendáře programově?

A2: Ano, můžete programově přidávat, aktualizovat nebo odstraňovat výjimky kalendáře pomocí Aspose.Tasks for .NET API.

### Q3: Jak mohu vypočítat data dokončení úkolu s vlastní dobou trvání?

 A3: Aspose.Tasks for .NET poskytuje metody jako`GetTaskFinishDateFromDuration()` vypočítat data dokončení úkolu na základě vlastního trvání.

### Q4: Je možné vytvořit vlastní kalendáře, jako jsou kalendáře nočních směn?

A4: Ano, můžete vytvořit vlastní kalendáře, jako jsou kalendáře noční směny, pomocí Aspose.Tasks for .NET API.

### Q5: Mohu načíst informace o výjimkách kalendáře ze souborů projektu?

A5: Ano, můžete snadno získat informace o výjimkách kalendáře ze souborů projektu pomocí Aspose.Tasks for .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
