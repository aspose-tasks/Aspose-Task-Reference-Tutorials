---
date: 2026-07-05
description: Scopri come monitorare il budget del progetto e gestire i costi del progetto
  utilizzando Aspose.Tasks per .NET. Definisci Cost Accrual Types per un monitoraggio
  accurato dei costi.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Monitorare il budget del progetto con Cost Accrual Types in Aspose.Tasks
url: /it/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Monitorare il budget del progetto con i tipi di addebito dei costi in Aspose.Tasks

## Introduzione

Tracciare accuratamente **monitorare il budget del progetto** è la spina dorsale della consegna di progetto di successo. Quando le informazioni sui costi vengono catturate al momento giusto, è possibile prevedere i superamenti, regolare le risorse e tenere informati gli stakeholder. Aspose.Tasks per .NET offre agli sviluppatori un controllo fine‑grained sul cost accrual, consentendo di decidere *quando* un costo viene registrato—sia all'inizio del lavoro, in modo continuo, o solo al completamento del lavoro. Questo tutorial ti guida attraverso i concetti, mostra come impostare un tipo di addebito e dimostra le migliori pratiche per un monitoraggio affidabile del budget.

## Risposte rapide
- **Qual è lo scopo principale dei tipi di addebito dei costi?** Determinano il punto nel ciclo di vita di un'attività in cui il costo viene riconosciuto, consentendo un monitoraggio preciso del budget.  
- **Quale valore enum ritarda il costo fino al completamento del lavoro?** `CostAccrualType.End`.  
- **È necessario una licenza per eseguire il codice?** Sì, è richiesta una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso modificare i tipi di addebito per molte risorse contemporaneamente?** Sì—itera attraverso la collezione `Resources` e assegna il tipo desiderato.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è il tipo di addebito dei costi?
Un **cost accrual type** indica ad Aspose.Tasks quando applicare il costo di una risorsa al budget del progetto. È rappresentato dall'enumerazione `CostAccrualType` e può essere impostato per‑resource o per‑task. Scegliere il tipo corretto garantisce che i dati sui costi siano allineati alle politiche di fatturazione della tua organizzazione, sia che tu abbia bisogno di registrare i costi all'inizio del lavoro, pro-rata sulla durata, o solo dopo il completamento.

## Perché monitorare il budget del progetto usando i tipi di addebito dei costi?
Aspose.Tasks supporta **four** opzioni di addebito—`Start`, `Prorated`, `Duration` e `End`—coprendo l'intera gamma di scenari tipici di contabilità di progetto. Selezionare l'opzione appropriata ti consente di allineare il riconoscimento dei costi ai cicli di fatturazione contrattuali, ridurre la varianza nei report finanziari e generare dichiarazioni di costo che si integrano senza problemi con i sistemi ERP, il tutto mantenendo un uso di memoria ridotto per progetti di grandi dimensioni.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

### 1. Installa Aspose.Tasks per .NET
Per iniziare, devi avere Aspose.Tasks per .NET installato nel tuo ambiente di sviluppo. Puoi scaricare la libreria dalla [download page](https://releases.aspose.com/tasks/net/) e seguire le istruzioni di installazione fornite.

### 2. Familiarità con .NET Framework
È necessaria una conoscenza di base del framework .NET e del linguaggio di programmazione C# per seguire gli esempi in questo tutorial.

## Come impostare il tipo di addebito dei costi per una risorsa?

Carica il progetto, individua la risorsa target e assegna il `CostAccrualType` desiderato. Il modello a due righe qui sotto è l'approccio standard: crea un'istanza `Project`, recupera la risorsa per ID, quindi imposta `CostAccrualType`. Questa sequenza concisa garantisce che tu **monitorare il budget del progetto** accuratamente dal momento in cui la risorsa viene aggiunta.

### Passo 1: Importa gli spazi dei nomi
Iniziamo importando gli spazi dei nomi necessari per accedere alle funzionalità di Aspose.Tasks nel nostro progetto .NET:

```csharp

```

### Passo 2: Carica il file di progetto
La classe `Project` rappresenta un file Microsoft Project e fornisce l'accesso a attività, risorse e altri dati.

```csharp
var project = new Project("Project2.mpp");
```

Per prima cosa, dobbiamo caricare il file di progetto nella nostra applicazione. Creiamo un nuovo oggetto `Project` e lo inizializziamo con il percorso del nostro file di progetto.

### Passo 3: Accedi alla risorsa
La collezione `Resources` contiene tutte le risorse definite nel progetto. Il metodo `GetById` recupera una risorsa per il suo identificatore unico.

```csharp
var resource = project.Resources.GetById(1);
```

Successivamente, accediamo alla risorsa a cui vogliamo applicare il tipo di addebito dei costi. Utilizziamo il metodo `GetById` della collezione `Resources` e passiamo l'ID della risorsa come argomento. Questo dimostra **access resource by id**, un requisito comune quando si automatizzano gli aggiornamenti dei costi.

### Passo 4: Imposta il tipo di addebito dei costi
Il metodo `Set` assegna un valore a un campo della risorsa.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Qui impostiamo il tipo di addebito dei costi per la risorsa. In questo esempio, lo impostiamo su `CostAccrualType.End`, il che significa che i costi non saranno addebitati finché il lavoro rimanente non sarà zero. Scegliere `End` è ideale quando vuoi **monitorare il budget del progetto** solo dopo che un'attività è stata completata interamente.

### Passo 5: Continua a lavorare con il progetto
Dopo aver impostato il tipo di addebito dei costi, puoi continuare a lavorare con il progetto secondo necessità, eseguendo operazioni aggiuntive o calcoli come la generazione di report sui costi, l'aggiornamento delle assegnazioni o l'esportazione del file.

## Problemi comuni e consigli professionali
- **Pro tip:** Chiama sempre `project.Save` dopo aver modificato i tipi di addebito per persistere le modifiche.  
- **Pitfall:** Impostare `CostAccrualType.Start` su una risorsa che non inizia mai il lavoro gonfierà i report di budget—verifica prima i programmi delle attività.  
- **Pro tip:** Usa `project.Resources.ToList()` quando devi aggiornare in batch molte risorse; ciò evita ricerche ripetute nella collezione e migliora le prestazioni su progetti di grandi dimensioni.

## Domande frequenti

**Q: Posso modificare il tipo di addebito dei costi per più risorse simultaneamente?**  
A: Sì, itera attraverso `project.Resources` e assegna il `CostAccrualType` desiderato a ciascuna risorsa all'interno di un ciclo `foreach`.

**Q: Quali sono gli altri tipi di addebito dei costi disponibili oltre a `End`?**  
A: Aspose.Tasks fornisce `Start`, `Prorated` e `Duration`—ognuno si allinea a una diversa strategia di fatturazione.

**Q: Come posso determinare il tipo di addebito dei costi corrente per una risorsa specifica?**  
A: Recupera il valore tramite `resource.Get(TskResource.CostAccrualType)`; restituisce l'enumerazione che rappresenta l'impostazione corrente.

**Q: È possibile applicare diversi tipi di addebito dei costi a diverse attività nello stesso progetto?**  
A: Assolutamente. Sia le attività che le risorse espongono una proprietà `CostAccrualType`, consentendo configurazioni indipendenti per entità.

**Q: Aspose.Tasks supporta tipi di addebito dei costi personalizzati?**  
A: No, la libreria attualmente supporta solo i quattro tipi integrati; la logica personalizzata deve essere implementata esternamente se necessaria.

---

**Ultimo aggiornamento:** 2026-07-05  
**Testato con:** Aspose.Tasks 24.8 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Aspose.Tasks Calendar and Scheduling](/tasks/net/calendar-scheduling/)
- [Handling MS Project Rates with Aspose.Tasks for .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Effortlessly Manage MS Project Resources with Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}