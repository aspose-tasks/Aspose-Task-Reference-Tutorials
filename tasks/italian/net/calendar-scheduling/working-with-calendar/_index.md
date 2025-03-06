---
title: Lavorare con il calendario in Aspose.Tasks
linktitle: Lavorare con il calendario in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Gestisci i calendari dei progetti, calcola le durate, gestisci le eccezioni con facilità utilizzando Aspose.Tasks per .NET.
weight: 10
url: /it/net/calendar-scheduling/working-with-calendar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lavorare con il calendario in Aspose.Tasks

## introduzione

Aspose.Tasks per .NET fornisce potenti funzionalità per lavorare con i calendari, consentendo agli sviluppatori di gestire in modo efficiente le pianificazioni dei progetti e le allocazioni delle risorse. In questo tutorial esploreremo come utilizzare Aspose.Tasks per interagire con i calendari, coprendo operazioni essenziali come il recupero delle informazioni del calendario, la definizione delle settimane lavorative, il calcolo delle ore lavorative e altro ancora.

## Prerequisiti

Prima di iniziare, assicurati di aver configurato i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
-  Installazione di Aspose.Tasks per .NET. Se non è installato, scaricalo da[Qui](https://releases.aspose.com/tasks/net/).
- Familiarità con Visual Studio o qualsiasi altro ambiente di sviluppo .NET preferito.

## Importa spazi dei nomi

Prima di iniziare a scrivere codice, assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Ora suddividiamo ciascun esempio in più passaggi in un formato di guida passo passo:

## Passaggio 1: recupera le informazioni del calendario

Per recuperare le informazioni del calendario da un progetto, attenersi alla seguente procedura:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Recupera le informazioni sui calendari
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

Spiegazione:
- Carica il file di progetto.
- Scorrere ogni calendario del progetto.
- Stampa l'UID e il nome di ciascun calendario.

## Passaggio 2: leggere le informazioni sulle settimane lavorative

Per leggere le informazioni sulle settimane lavorative da un calendario, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario tramite UID.
- Ripeti ogni settimana lavorativa nel calendario.
- Stampa il nome, la data di inizio e la data di fine di ogni settimana lavorativa.
- Attraversa i giorni lavorativi e gli orari lavorativi all'interno di ogni settimana.

## Passaggio 3: leggere le proprietà del calendario

Per leggere le proprietà dei calendari di progetto, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Scorrere ogni calendario del progetto.
- Stampa UID, nome e se si tratta di un calendario di base.
- Stampa l'orario di lavoro per ogni tipologia di giorno.

## Passaggio 4: calcolare le ore di lavoro

Per calcolare le ore lavorative per un'attività, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Ottieni dettagli sulle attività come calendario, data di inizio e data di fine.
- Calcola le ore di lavoro scorrendo ogni giorno e controllando se è un giorno lavorativo.
- Riassumi la durata totale in minuti.

## Passaggio 5: definire i giorni feriali per il calendario

Per definire i giorni feriali per un calendario, attenersi alla seguente procedura:

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

Spiegazione:
- Crea un nuovo progetto e calendario.
- Aggiungi giorni lavorativi predefiniti (dal lunedì al giovedì) e orari di lavoro personalizzati per il venerdì.
- Imposta sabato e domenica come giorni non lavorativi.

## Passaggio 6: scrivere i dati del calendario aggiornati su MPP

Per scrivere i dati del calendario aggiornati in un file MPP, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto e recupera il calendario standard.
- Modifica i dati del calendario come eccezioni e orari di lavoro.
- Salvare il progetto aggiornato con i dati del calendario modificati.

## Passaggio 7: calcolare la data di fine dell'attività divisa

Per calcolare la data di fine di un'attività divisa, attenersi alla seguente procedura:

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

Spiegazione:
- Caricare il file di progetto e recuperare l'attività divisa.
- Ottieni il calendario del progetto.
- Calcola la data di fine in base a una durata personalizzata.

## Passaggio 8: recuperare le eccezioni del calendario

Per recuperare informazioni sulle eccezioni del calendario, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Scorri ogni calendario e le sue eccezioni.
- Stampa le date di inizio e fine di ciascuna eccezione.

## Passaggio 9: ottieni il calendario delle risorse di base

Per utilizzare il calendario di base del calendario di una risorsa, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Aggiungi una risorsa e il relativo calendario.
- Stampa il nome del calendario di base per tutte le risorse.

## Passaggio 10: elimina il calendario

Per eliminare un calendario da un progetto, procedi nel seguente modo:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario per nome.
- Elimina il calendario.

## Passaggio 11: ottenere la data di fine per inizio e lavoro

Per calcolare una data di fine in base alla data di inizio e al lavoro, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario standard.
- Definire una data di inizio e una durata del lavoro.
- Calcolare la data di fine in base alla data di inizio e al lavoro.

## Passaggio 12: ottieni l'inizio del giorno lavorativo successivo

Per iniziare il giorno lavorativo successivo utilizzando un calendario, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario tramite UID.
- Ottieni l'orario di inizio del giorno lavorativo successivo.

## Passaggio 13: ottenere la fine del giorno lavorativo precedente

Per ottenere la fine del giorno lavorativo precedente utilizzando un calendario, attenersi alla seguente procedura:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario tramite UID.
- Ottieni l'ora di fine del giorno lavorativo precedente.

## Passaggio 14: ottieni la data di inizio dalla fine e dalla durata

Per ottenere una data di inizio in base alla data di fine e alla durata, attenersi alla seguente procedura:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario tramite UID.
- Calcolare la data di inizio dalla data di fine e dalla durata.

## Passaggio 15: ottieni l'orario di lavoro

Per ottenere l'orario di lavoro per una data specifica, procedi nel seguente modo:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario tramite UID.
- Ottieni l'orario di lavoro per la data specificata.

## Passaggio 16: ottenere gli orari di lavoro

Per ottenere gli orari di lavoro per una data specifica, attenersi alla seguente procedura:

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

Spiegazione:
- Carica il file di progetto.
- Ottieni il calendario tramite UID.
- Ottieni gli orari di lavoro per la data specificata.

## Conclusione

Lavorare con i calendari in Aspose.Tasks per .NET è fondamentale per gestire in modo efficace la pianificazione dei progetti. Con gli esempi forniti e le guide dettagliate, puoi manipolare facilmente i dati del calendario, calcolare la durata delle attività e gestire le eccezioni in modo efficiente. Integrando queste funzionalità nelle tue applicazioni, puoi semplificare i processi di gestione dei progetti e garantire una pianificazione accurata.

## Domande frequenti

### Q1: ho bisogno di una licenza per utilizzare Aspose.Tasks per .NET?

 A1: Sì, è necessaria una licenza valida per utilizzare Aspose.Tasks per .NET nelle tue applicazioni. È possibile acquistare una licenza completa o ottenere una licenza temporanea di 30 giorni da[Qui](https://purchase.aspose.com/temporary-license/).

### Q2: posso modificare le eccezioni del calendario a livello di codice?

A2: Sì, è possibile aggiungere, aggiornare o eliminare a livello di codice le eccezioni del calendario utilizzando Aspose.Tasks per le API .NET.

### Q3: Come posso calcolare le date di fine delle attività con durate personalizzate?

 A3: Aspose.Tasks per .NET fornisce metodi come`GetTaskFinishDateFromDuration()` per calcolare le date di fine delle attività in base a durate personalizzate.

### Q4: È possibile creare calendari personalizzati, ad esempio calendari dei turni di notte?

A4: Sì, puoi creare calendari personalizzati come calendari dei turni di notte utilizzando Aspose.Tasks per le API .NET.

### Q5: Posso recuperare informazioni sulle eccezioni del calendario dai file di progetto?

A5: Sì, puoi facilmente recuperare informazioni sulle eccezioni del calendario dai file di progetto utilizzando Aspose.Tasks per .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
