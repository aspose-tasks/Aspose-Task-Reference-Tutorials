---
title: Configurare gli orari di lavoro in Aspose.Tasks
linktitle: Configurare gli orari di lavoro in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Migliora la pianificazione dei progetti in .NET con Aspose.Tasks. Configura facilmente gli orari di lavoro per una gestione precisa delle risorse. Scarica subito la libreria!
type: docs
weight: 13
url: /it/net/time-recurrence-configuration/working-times/
---
## introduzione
Nella gestione dei progetti, un controllo preciso sugli orari di lavoro è fondamentale per una pianificazione accurata e un'allocazione delle risorse. Aspose.Tasks per .NET fornisce una potente soluzione per la gestione delle informazioni sull'orario di lavoro all'interno dei tuoi progetti. Questo tutorial ti guiderà attraverso il processo di configurazione degli orari di lavoro utilizzando Aspose.Tasks in un ambiente .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere quanto segue:
- Conoscenza base del linguaggio di programmazione C#.
- Aspose.Tasks per la libreria .NET installata. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
- Configura Visual Studio o qualsiasi ambiente di sviluppo C# preferito.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## Passaggio 1: crea il calendario
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Qui, avviamo un nuovo progetto e creiamo un calendario denominato "MyCalendar" basato sul calendario standard. Questo calendario verrà utilizzato per definire orari di lavoro specifici.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Passaggio 2: visualizzare le informazioni sulla settimana lavorativa
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
Questo passaggio stampa il numero totale di giorni lavorativi nel calendario specificato.
## Passaggio 3: dettagli sull'orario di lavoro
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
In questa parte, iteriamo ogni giorno della settimana, stampando il tipo di giorno e gli orari di lavoro associati. Puoi personalizzare gli orari di lavoro per ogni giorno della settimana in base alle esigenze del tuo progetto.
## Conclusione
La configurazione efficace degli orari di lavoro in Aspose.Tasks per .NET garantisce un'accurata pianificazione del progetto e gestione delle risorse. Seguendo questa guida passo passo, puoi integrare perfettamente le modifiche dell'orario di lavoro nei flussi di lavoro del tuo progetto.
## Domande frequenti
### Aspose.Tasks è adatto alla gestione di progetti su larga scala?
Sì, Aspose.Tasks è progettato per gestire progetti di varie dimensioni, offrendo funzionalità robuste per una gestione efficiente dei progetti.
### Posso impostare orari di lavoro diversi per i diversi membri del team?
Assolutamente. È possibile personalizzare gli orari di lavoro in base alla risorsa, consentendo pianificazioni personalizzate.
### Aspose.Tasks supporta l'integrazione con altri strumenti di gestione dei progetti?
Sì, Aspose.Tasks facilita l'integrazione con vari strumenti di gestione dei progetti, migliorando l'interoperabilità.
### È possibile importare/esportare i dati del progetto in diversi formati?
Aspose.Tasks supporta più formati di file, consentendo operazioni di importazione/esportazione senza interruzioni per i dati di progetto.
### Con quale frequenza vengono rilasciati gli aggiornamenti di Aspose.Tasks?
Gli aggiornamenti vengono rilasciati regolarmente per garantire la compatibilità con le tecnologie più recenti e rispondere al feedback degli utenti.