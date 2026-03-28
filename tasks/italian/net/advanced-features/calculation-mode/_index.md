---
date: 2026-03-24
description: Scopri come impostare la modalità di calcolo in Aspose.Tasks per .NET,
  coprendo le modalità di calcolo automatica, manuale e nessuna, per gestire le dipendenze
  delle attività.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Come impostare la modalità di calcolo in Aspose.Tasks per .NET
url: /it/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la modalità di calcolo in Aspose.Tasks per .NET

## Introduzione

Aspose.Tasks for .NET è una potente API che consente di lavorare con i file Microsoft Project in modo programmatico. Una delle impostazioni più importanti che incontrerai è la **modalità di calcolo**, che controlla come vengono aggiornate le date delle attività e i calendari del progetto. In questo tutorial imparerai **come impostare la modalità di calcolo**, esplorerai **modalità di calcolo automatica**, **modalità di calcolo manuale** e **modalità di calcolo nessuna**, e vedrai come queste opzioni influenzano **gestire le dipendenze delle attività**, **creare la data di inizio del progetto** e **collegare le relazioni attività fine‑inizio**.

## Risposte rapide
- **Che cos'è la modalità di calcolo?** Determina se le date delle attività vengono ricalcolate automaticamente, manualmente o per nulla.  
- **Perché usare la modalità di calcolo manuale?** Per avere il pieno controllo su quando il calendario viene aggiornato, utile in aggiornamenti massivi.  
- **Qual è la modalità predefinita?** La modalità di calcolo automatica, che aggiorna le date istantaneamente dopo le modifiche.  
- **Posso cambiare la modalità a runtime?** Sì—basta impostare la proprietà `CalculationMode` sull'oggetto `Project`.  
- **Ho bisogno di una licenza?** È necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.

## Che cos'è “come impostare il calcolo” in Aspose.Tasks?

Impostare la modalità di calcolo è semplice come assegnare un valore enum alla proprietà `Project.CalculationMode`. L'enum fornisce tre opzioni: `Automatic`, `Manual` e `None`. Scegliere la modalità giusta dipende dal tuo flusso di lavoro—se desideri aggiornamenti istantanei, elaborazione batch o controllo completo.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Visual Studio** – qualsiasi versione recente (2019, 2022 o successiva).  
2. **Aspose.Tasks for .NET** – scarica e installa la libreria da [qui](https://releases.aspose.com/tasks/net/).  
3. **Conoscenza di base di C#** – dovresti sentirti a tuo agio nella creazione di applicazioni console e nell'uso dei pacchetti NuGet.

## Importare gli spazi dei nomi

Prima di iniziare a lavorare con Aspose.Tasks per .NET, importiamo gli spazi dei nomi necessari:

```csharp
using Aspose.Tasks;
using System;
```

## Come impostare la modalità di calcolo

Di seguito troverai esempi passo‑passo per ciascuna modalità di calcolo. I blocchi di codice sono invariati rispetto al tutorial originale; le spiegazioni circostanti sono state ampliate per maggiore chiarezza.

### Applicare la modalità di calcolo automatica

La modalità automatica ricalcola le date istantaneamente ogni volta che modifichi attività o collegamenti.

#### Passo 1: Creare una nuova istanza di Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Passo 2: Impostare la data di inizio del progetto e aggiungere attività

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Passo 3: Collegare le attività (fine‑a‑inizio)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Passo 4: Verificare le date ricalcolate

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Applicare la modalità di calcolo manuale

La modalità manuale disabilita gli aggiornamenti automatici, offrendoti la possibilità di elaborare le modifiche in batch prima di forzare un ricalcolo.

#### Passo 1: Creare una nuova istanza di Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Passo 2: Impostare la data di inizio del progetto e aggiungere attività

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Passo 3: Verificare le proprietà dell'attività

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Passo 4: Collegare le attività e verificare le date (nessun ricalcolo automatico)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Applicare la modalità di calcolo nessuna

La modalità nessuna disattiva tutti i calcoli interni. Usala quando devi solo leggere o esportare dati senza alcuna modifica al calendario.

#### Passo 1: Creare una nuova istanza di Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Passo 2: Aggiungere una nuova attività

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Passo 3: Verificare le proprietà dell'attività (nessun ID automatico)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Problemi comuni e soluzioni

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| Le date non si aggiornano dopo il collegamento delle attività | Il progetto è in modalità **Manual** o **None** | Imposta `project.CalculationMode = CalculationMode.Automatic` o chiama manualmente `project.Calculate()` |
| Gli ID delle attività rimangono a 0 | L'uso della modalità **None** impedisce la generazione degli ID | Passa alla modalità **Automatic** o **Manual**, quindi ricalcola |
| Il collegamento fallisce con `ArgumentException` | La data di inizio del predecessore è successiva a quella del successivo quando si usa la modalità **Manual** senza ricalcolo | Assicurati che le date di inizio siano corrette o ricalcola dopo aver aggiunto i collegamenti |

## Domande frequenti

**D1: Posso cambiare la modalità di calcolo dinamicamente durante il runtime?**  
R1: Sì, puoi modificare la proprietà `CalculationMode` in qualsiasi punto del tuo codice e poi chiamare `project.Calculate()` se necessiti di un aggiornamento immediato.

**D2: Aspose.Tasks supporta altri formati di file di gestione progetti oltre a Microsoft Project?**  
R2: Aspose.Tasks si concentra principalmente sui formati Microsoft Project, ma supporta anche Primavera P6 XML, Primavera DB e Asta Powerproject XML.

**D3: Aspose.Tasks è adatto sia per progetti di piccola scala che per progetti a livello enterprise?**  
R3: Assolutamente. L'API scala da semplici elenchi di attività a complessi calendari aziendali multi‑fase.

**D4: Posso integrare Aspose.Tasks con altre librerie e framework .NET?**  
R4: Sì, puoi combinare Aspose.Tasks con ASP.NET, WPF, Xamarin o qualsiasi altra tecnologia .NET per costruire soluzioni di gestione progetti avanzate.

**D5: Esiste un forum della community o un canale di supporto disponibile per gli utenti di Aspose.Tasks?**  
R5: Sì, puoi visitare il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto della community e discussioni.

---

**Ultimo aggiornamento:** 2026-03-24  
**Testato con:** Aspose.Tasks 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}