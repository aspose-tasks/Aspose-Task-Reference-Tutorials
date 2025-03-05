---
title: Padroneggiare i giorni feriali in Aspose.Tasks
linktitle: Raccolta dei giorni feriali in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri la potenza di Aspose.Tasks per .NET nella gestione dei giorni feriali senza sforzo. Personalizza i giorni lavorativi, rimuovi i fine settimana e crea facilmente calendari specializzati.
type: docs
weight: 11
url: /it/net/time-recurrence-configuration/weekday-collection/
---
## introduzione
Aspose.Tasks per .NET è una potente libreria che facilita la manipolazione efficiente dei dati di gestione del progetto. In questo tutorial esploreremo la raccolta di giorni feriali in Aspose.Tasks, consentendoti di personalizzare i giorni lavorativi, rimuovere i fine settimana e creare calendari specializzati per soddisfare i requisiti del tuo progetto. Che tu sia uno sviluppatore esperto o un nuovo arrivato, questa guida passo passo ti guiderà attraverso il processo di lavoro con i giorni feriali in Aspose.Tasks per .NET.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Installare la libreria Aspose.Tasks per .NET. Puoi scaricarlo da[Aspose.Tasks per la pagina di download di .NET](https://releases.aspose.com/tasks/net/).
- Conoscenza del linguaggio di programmazione C#.
- Ambiente di sviluppo integrato (IDE) come Visual Studio.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Passaggio 1: crea un'istanza del progetto
Inizializza un nuovo progetto Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Passaggio 2: accedi al calendario
Recupera il calendario del progetto:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Passaggio 3: personalizza i giorni feriali
Cancella i giorni feriali esistenti e imposta i giorni lavorativi predefiniti:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Aggiungi altri giorni feriali allo stesso modo...
```
## Passaggio 4: aggiungere gli orari di lavoro
Aggiungi orari di lavoro per giorni feriali specifici:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Passaggio 5: Visualizza le informazioni del calendario
Invia i dettagli del calendario alla console:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Visualizza ogni giorno della settimana e gli orari di lavoro...
```
## Passaggio 6: rimuovere i fine settimana
Rimuovere sabato e domenica dai giorni feriali:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Passaggio 7: Visualizza gli orari di lavoro aggiornati
Output degli orari di lavoro aggiornati dopo aver rimosso i fine settimana:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Visualizza ogni giorno della settimana e orario di lavoro aggiornati...
```
## Passaggio 8: crea un calendario di 24 ore
Crea un calendario di 24 ore e copia i giorni feriali:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Conclusione
In questo tutorial, abbiamo esplorato le potenti funzionalità di Aspose.Tasks per .NET nella gestione dei giorni feriali all'interno dei calendari di progetto. Dalla personalizzazione dei giorni lavorativi alla creazione di calendari specializzati di 24 ore, Aspose.Tasks semplifica il processo, offrendo flessibilità e controllo nella gestione dei progetti.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per .NET con altri linguaggi di programmazione?
R: Aspose.Tasks supporta principalmente i linguaggi .NET, ma offre anche versioni per Java.
### D: È disponibile una prova gratuita per Aspose.Tasks per .NET?
 R: Sì, puoi scaricare una versione di prova gratuita da[Pagina delle versioni di Aspose.Tasks](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.Tasks per .NET?
 R: Visita il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto della comunità o considera l'acquisto di un piano di supporto.
### D: Dove posso trovare la documentazione completa per Aspose.Tasks per .NET?
 R: Fare riferimento a[Aspose.Tasks per la documentazione .NET](https://reference.aspose.com/tasks/net/) per informazioni dettagliate.
### D: Come posso ottenere una licenza temporanea per Aspose.Tasks per .NET?
 R: Puoi acquisire una licenza temporanea da[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).