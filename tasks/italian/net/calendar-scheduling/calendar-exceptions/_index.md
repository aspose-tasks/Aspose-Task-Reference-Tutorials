---
title: Gestione delle eccezioni del calendario in Aspose.Tasks
linktitle: Gestione delle eccezioni del calendario in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le eccezioni del calendario in Aspose.Tasks per .NET con tutorial ed esempi passo passo.
weight: 12
url: /it/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione delle eccezioni del calendario in Aspose.Tasks

## introduzione

In questo tutorial esploreremo come gestire le eccezioni del calendario in Aspose.Tasks utilizzando il framework .NET. Le eccezioni del calendario ci consentono di definire date o periodi speciali nel calendario di un progetto in cui il normale orario di lavoro viene modificato, come festività o chiusure temporanee. Tratteremo vari metodi per gestire le eccezioni del calendario passo dopo passo, utilizzando Aspose.Tasks per .NET.

## Prerequisiti

Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio installato nel sistema.
- Libreria Aspose.Tasks per .NET aggiunta al tuo progetto.

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per il nostro progetto:

```csharp
using Aspose.Tasks;
using System;


```

## Passaggio 1: eliminazione di un'eccezione del calendario

Per eliminare un'eccezione del calendario, procedi nel seguente modo:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Visualizza le informazioni del calendario
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Rimuovere la prima eccezione
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Passaggio 2: ottenere l'orario di lavoro di un'eccezione del calendario

Per recuperare l'orario di lavoro di un'eccezione del calendario, attenersi alla seguente procedura:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Visualizza il calendario e le informazioni sulle eccezioni
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Ottieni l'orario di lavoro e visualizza i dettagli
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Passaggio 3: definizione delle eccezioni del calendario

Per aggiungere o rimuovere eccezioni del calendario, procedi nel seguente modo:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Crea una nuova eccezione del calendario
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Imposta i dettagli dell'eccezione
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Controlla se una data è un'eccezione
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Aggiungi l'eccezione al calendario
    calendar.Exceptions.Add(exception);

    // Rimuovere un'eccezione se esiste
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Aggiungi una nuova eccezione
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Stampa le eccezioni
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Conclusione

In questo articolo abbiamo trattato vari aspetti della gestione delle eccezioni del calendario in Aspose.Tasks per .NET. Seguendo i passaggi forniti, puoi gestire in modo efficace le eccezioni nelle pianificazioni del tuo progetto, garantendo una rappresentazione accurata dell'orario di lavoro e degli eventi speciali.

## Domande frequenti

### Q1: Posso aggiungere più eccezioni a un singolo calendario?

R1: Sì, puoi aggiungere più eccezioni a un calendario per accogliere varie date o periodi speciali.

### Q2: Come posso verificare se una data specifica costituisce un'eccezione?

 A2: Puoi usare il file`CheckException()` metodo per verificare se una data particolare rientra in un'eccezione.

### Q3: è possibile rimuovere un'eccezione esistente da un calendario?

 R3: Sì, puoi rimuovere le eccezioni accedendo a`Exceptions` raccolta del calendario e utilizzo del`Remove()` metodo.

### Q4: quali tipi di eccezioni di calendario sono supportati?

A4: Aspose.Tasks supporta vari tipi di eccezioni, incluse eccezioni giornaliere, settimanali, mensili e annuali, fornendo flessibilità nella definizione delle regole di eccezione.

### D5: Posso personalizzare l'orario di lavoro per date di eccezione specifiche?

A5: Sì, è possibile definire orari di lavoro personalizzati per le singole date di eccezione utilizzando i metodi appropriati forniti da Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
