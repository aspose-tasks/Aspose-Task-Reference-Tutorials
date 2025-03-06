---
title: Padroneggiare i giorni feriali in Aspose.Tasks per .NET
linktitle: Definizione dei giorni feriali in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora il potere di definire i giorni feriali in Aspose.Tasks .NET. Segui il nostro tutorial dettagliato per gestire in modo efficiente i calendari dei progetti, personalizzare gli orari di lavoro e altro ancora.
weight: 10
url: /it/net/time-recurrence-configuration/defining-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare i giorni feriali in Aspose.Tasks per .NET

## introduzione
Se ti stai immergendo nel mondo della gestione dei progetti utilizzando Aspose.Tasks per .NET, comprendere e manipolare i giorni feriali è un aspetto cruciale. Gestire e personalizzare in modo efficiente i giorni feriali all'interno del calendario del progetto può avere un impatto significativo sulle tempistiche del progetto. In questo tutorial ti guideremo attraverso il processo di definizione dei giorni feriali utilizzando Aspose.Tasks, fornendo istruzioni dettagliate ed esempi per una maggiore chiarezza.
## Prerequisiti
Prima di intraprendere questo viaggio, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione C#.
-  Aspose.Tasks per la libreria .NET installata. In caso contrario, scaricalo da[Qui](https://releases.aspose.com/tasks/net/).
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Controllare l'uguaglianza dei giorni feriali
```csharp
// La tua directory dei documenti
String DataDir = "Your Document Directory";
// Carica il file di progetto
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Accesso nei giorni feriali
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Verifica l'uguaglianza in base a varie proprietà
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Aggiungi istruzioni di output simili per DayWorking, FromDate, ToDate e WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Clonare un giorno della settimana
```csharp
// Carica il file di progetto
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Crea una copia approfondita del giorno della settimana
var weekDay2 = weekDay1.Clone();
// Proprietà di uscita di entrambi i giorni della settimana
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Aggiungi istruzioni di output simili per DayWorking, FromDate, ToDate e WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Ottieni il codice hash di un giorno feriale
```csharp
// Carica il file di progetto
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Proprietà di uscita di entrambi i giorni della settimana
// Aggiungi istruzioni di output simili per DayWorking, FromDate, ToDate e WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Crea un nuovo calendario con giorni feriali definiti
```csharp
// Crea un nuovo progetto
var project = new Project();
// Definire un calendario
var calendar = project.Calendars.Add("Calendar1");
// Aggiungi giorni lavorativi e giorni eccezionali
// Aggiungi istruzioni di output simili per FromDate e ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Imposta l'orario di lavoro per venerdì
// Aggiungi istruzioni di output simili per DayWorking, FromDate, ToDate e WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Imposta l'orario di lavoro predefinito per un giorno
```csharp
// Crea un nuovo progetto
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Aggiungi orari di lavoro predefiniti dal lunedì al venerdì
// Aggiungi istruzioni di output simili per DayWorking, FromDate, ToDate e WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Ripetere per martedì, mercoledì, giovedì e venerdì
// Imposta i giorni non lavorativi per sabato e domenica
// Aggiungi istruzioni di output simili per DayWorking, FromDate, ToDate e WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Conclusione
In questo tutorial, abbiamo trattato gli aspetti essenziali della definizione dei giorni feriali in Aspose.Tasks per .NET. La manipolazione dei giorni feriali è una competenza chiave per una gestione efficace del progetto. Sperimenta gli esempi forniti, personalizzali in base alle esigenze del tuo progetto e sblocca tutto il potenziale di Aspose.Tasks.
## Domande frequenti
### Posso definire orari di lavoro personalizzati per ogni giorno?
Sì, puoi impostare orari di lavoro personalizzati per giorni feriali specifici utilizzando gli esempi forniti.
### È possibile aggiungere più giorni di eccezione al calendario?
Assolutamente. Modificare il codice nel quarto esempio per includere ulteriori giorni di eccezione.
### Come posso rimuovere un giorno della settimana specifico dal calendario?
Utilizzare i metodi appropriati forniti dalla libreria Aspose.Tasks per rimuovere i giorni feriali secondo necessità.
### Le modifiche apportate ai giorni feriali sono persistenti nel file di progetto?
Sì, qualsiasi modifica ai giorni feriali si riflette nel file di progetto una volta salvata.
### Posso utilizzare Aspose.Tasks con altri linguaggi di programmazione?
Aspose.Tasks supporta vari linguaggi di programmazione, ma gli esempi qui sono specifici per .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
