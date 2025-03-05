---
title: Padroneggiare i tempi di lavoro in Aspose.Tasks
linktitle: Raccolta degli orari di lavoro in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora la potenza di Aspose.Tasks per .NET nella gestione efficiente delle tempistiche dei progetti. Personalizza i calendari, imposta gli orari di lavoro e semplifica i tuoi progetti con facilità.
type: docs
weight: 14
url: /it/net/time-recurrence-configuration/working-time-collection/
---
## introduzione
Stai cercando di padroneggiare l'arte della gestione dell'orario di lavoro in Aspose.Tasks per .NET? Non guardare oltre! In questa guida passo passo, approfondiremo le complessità della raccolta dell'orario di lavoro utilizzando Aspose.Tasks, consentendoti di gestire in modo efficiente calendari personalizzati e semplificare le tempistiche del progetto.
## Prerequisiti
Prima di intraprendere questo viaggio, assicurati di possedere i seguenti prerequisiti:
-  Aspose.Tasks for .NET Library: Scarica e installa la libreria Aspose.Tasks for .NET dal[Pagina di rilascio di Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Ambiente di lavoro: impostare un ambiente di sviluppo adatto, preferibilmente utilizzando un IDE compatibile con .NET.
## Importa spazi dei nomi
Nel tuo progetto, importa gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Ora suddividiamo il tutorial in più passaggi, garantendo un'esperienza di apprendimento fluida.
## Passaggio 1: crea un calendario personalizzato
Inizia creando un nuovo progetto e aggiungendovi un calendario personalizzato:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Passaggio 2: definire i giorni lavorativi
Imposta i giorni lavorativi predefiniti dal lunedì al venerdì:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Passaggio 3: configura l'orario di lavoro del sabato
Specificare gli orari di lavoro per il sabato:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Passaggio 4: stampare i periodi lavorativi del sabato
Stampa gli orari di lavoro configurati per Sabato:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Passaggio 5: configurare l'orario di lavoro domenicale
Definire gli orari di lavoro per la domenica:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Passaggio 6: stampare i periodi lavorativi domenicali
Stampa gli orari di lavoro configurati per la domenica:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Passaggio 7: aggiungi giorni personalizzati al calendario
Includere il sabato e la domenica configurati nel calendario:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Passaggio 8: attraversare gli orari di lavoro
Sfoglia gli orari di lavoro e visualizzali per ogni giorno nel calendario:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Ora che hai seguito con successo i passaggi, sei in grado di sfruttare la potenza di Aspose.Tasks per .NET nella gestione efficace dei tempi di lavoro.
## Conclusione
Padroneggiare la raccolta degli orari di lavoro in Aspose.Tasks ti consente di personalizzare i calendari dei progetti, garantendo una pianificazione precisa e un utilizzo efficiente delle risorse. Immergiti nei tuoi progetti con sicurezza, armato delle conoscenze acquisite da questa guida completa.
## Domande frequenti
### Aspose.Tasks è adatto alla gestione di progetti su larga scala?
Sì, Aspose.Tasks è progettato per gestire progetti di varie dimensioni, fornendo funzionalità robuste per una gestione efficiente dei progetti.
### Posso integrare Aspose.Tasks con altre librerie .NET?
Certamente! Aspose.Tasks si integra perfettamente con altre librerie .NET, migliorandone la versatilità e la compatibilità.
### Con quale frequenza viene aggiornato Aspose.Tasks?
 Aspose.Tasks viene regolarmente aggiornato per incorporare nuove funzionalità, miglioramenti e miglioramenti della compatibilità. Controlla il[pagina di rilascio](https://releases.aspose.com/tasks/net/) per gli ultimi aggiornamenti.
### È disponibile una prova gratuita per Aspose.Tasks?
 Sì, puoi esplorare Aspose.Tasks con una prova gratuita visitando[questo link](https://releases.aspose.com/).
### Dove posso chiedere supporto per Aspose.Tasks?
 Per qualsiasi domanda o assistenza, visitare il[Forum di supporto Aspose.Tasks](https://forum.aspose.com/c/tasks/15).