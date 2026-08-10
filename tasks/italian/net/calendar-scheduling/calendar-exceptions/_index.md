---
date: 2026-04-13
description: Scopri come eliminare le eccezioni del calendario in Aspose.Tasks per
  .NET e verificare la data dell'eccezione durante la gestione della programmazione
  del calendario ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Elimina eccezione del calendario con Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Elimina eccezione del calendario con Aspose.Tasks
url: /it/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Elimina eccezione del calendario con Aspose.Tasks

## Introduzione

In questo tutorial, imparerai come **eliminare un'eccezione del calendario** e gestire altre eccezioni del calendario in Aspose.Tasks usando il framework .NET. Le eccezioni del calendario ti consentono di modellare festività, chiusure temporanee o qualsiasi periodo speciale in cui il normale orario di lavoro cambia. Comprendere come aggiungere, interrogare e rimuovere queste eccezioni è essenziale per una pianificazione accurata del progetto, specialmente quando si lavora con scenari di **pianificazione del calendario ASP.NET**.

## Risposte rapide
- **Qual è il metodo principale per rimuovere un'eccezione?** Usa il metodo `Delete()` sull'oggetto `CalendarException`.  
- **Quale classe verifica una data rispetto a un'eccezione?** `CalendarException.CheckException()` — utile per **verificare la data dell'eccezione**.  
- **È necessaria una licenza per eseguire il codice?** Sì, è necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso aggiungere più eccezioni a un calendario?** Assolutamente; la collezione `Exceptions` supporta molte voci.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è un'eccezione del calendario?

Una **eccezione del calendario** rappresenta una deviazione dal calendario di lavoro regolare — pensala come una regola che dice “in queste date, le ore di lavoro sono diverse o assenti”. In Aspose.Tasks, ogni eccezione può avere i propri orari di lavoro, modello di ricorrenza e flag che indicano se il giorno è lavorativo.

## Perché gestire le eccezioni del calendario nella pianificazione del calendario ASP.NET?

- **Scadenze accurate:** I progetti rispettano automaticamente le festività e le chiusure speciali, evitando scadenze irrealistiche.  
- **Flessibilità:** È possibile definire modelli giornalieri, settimanali, mensili o annuali, corrispondenti ai calendari aziendali del mondo reale.  
- **Automazione:** Verificare programmaticamente una data di eccezione ti consente di costruire logiche di pianificazione dinamiche nelle applicazioni ASP.NET.

## Prerequisiti

- Conoscenza di base della programmazione C#.  
- Visual Studio (qualsiasi versione recente).  
- Libreria Aspose.Tasks per .NET aggiunta al tuo progetto (tramite NuGet o riferimento manuale).  

## Importa spazi dei nomi

Per prima cosa, importa gli spazi dei nomi di cui avrai bisogno:

```csharp
using Aspose.Tasks;
using System;
```

## Passo 1: Elimina eccezione del calendario

Rimuovere un'eccezione indesiderata è semplice. Il codice seguente carica un progetto, seleziona il primo calendario, visualizza informazioni di base, elimina la prima eccezione e poi mostra il conteggio aggiornato.

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

> **Suggerimento professionale:** Verifica sempre che l'indice dell'eccezione esista prima di chiamare `Delete()` per evitare `IndexOutOfRangeException`.

## Passo 2: Ottieni orario di lavoro di un'eccezione del calendario

Se hai bisogno di ispezionare le ore di lavoro definite per un'eccezione, usa `GetWorkingTime()`. Questo esempio dimostra anche come **verificare la data dell'eccezione** con `CheckException`.

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

## Passo 3: Definisci eccezioni del calendario

Di seguito è riportata una guida completa che mostra come **aggiungere**, **verificare** e **rimuovere** le eccezioni del calendario. Nota l'uso di `CheckException` per **verificare la data dell'eccezione** per un momento specifico.

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

## Problemi comuni e suggerimenti

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **`IndexOutOfRangeException` durante l'eliminazione** | Tentativo di eliminare un'eccezione che non esiste. | Verifica che `calendar.Exceptions.Count` > indice prima di chiamare `Delete()`. |
| **Orari di lavoro errati** | Non impostare correttamente `DayWorking` o `WorkingTimes`. | Usa `exception.WorkingTimes.Add(new WorkingTime(...))` per definire periodi espliciti. |
| **Eccezione non riconosciuta** | `CheckException` restituisce `false` perché la data cade al di fuori dell'intervallo definito. | Verifica nuovamente `FromDate`/`ToDate` e il `Type` (Daily, Weekly, ecc.). |

## Domande frequenti

**D: Posso aggiungere più eccezioni a un singolo calendario?**  
R: Sì, puoi aggiungere quante eccezioni desideri per rappresentare festività, finestre di manutenzione o qualsiasi regola di pianificazione speciale.

**D: Come **verificare la data dell'eccezione** per un giorno specifico?**  
R: Usa il metodo `CheckException(DateTime date)` su un'istanza `CalendarException`. Restituisce `true` se la data fornita cade nell'intervallo dell'eccezione.

**D: È possibile rimuovere un'eccezione esistente da un calendario?**  
R: Assolutamente. Accedi alla collezione `Exceptions` e chiama `Remove()` o invoca `Delete()` sull'oggetto `CalendarException` specifico.

**D: Quali tipi di eccezioni del calendario sono supportati?**  
R: Aspose.Tasks supporta i tipi di eccezione Daily, Weekly, Monthly e Yearly, offrendoti flessibilità per modellare quasi qualsiasi modello di ricorrenza.

**D: Posso personalizzare le ore di lavoro per date di eccezione specifiche?**  
R: Sì. Dopo aver creato un'eccezione, popola la sua collezione `WorkingTimes` con oggetti `WorkingTime` che definiscono gli orari di inizio e fine per quel giorno.

## Conclusione

Abbiamo illustrato l'intero ciclo di vita delle operazioni di **eliminare un'eccezione del calendario**, dall'ispezione delle eccezioni esistenti all'aggiunta di nuove e alla verifica delle date. Padroneggiare queste tecniche garantisce che i piani dei tuoi progetti rispettino i calendari del mondo reale, rendendo le tue implementazioni di pianificazione del calendario ASP.NET robuste e affidabili.

---

**Ultimo aggiornamento:** 2026-04-13  
**Testato con:** Aspose.Tasks for .NET (latest release)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}