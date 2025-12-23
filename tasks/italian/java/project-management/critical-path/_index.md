---
date: 2025-12-23
description: Scopri come creare dipendenze tra attività e calcolare il percorso critico
  in MS Project usando Aspose.Tasks per Java. Guida passo‑passo per la gestione dei
  progetti.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Creare dipendenze delle attività e calcolare il percorso critico in Aspose.Tasks
url: /it/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea dipendenze tra attività e calcola il percorso critico in Aspose.Tasks

## Introduction
In questo tutorial, **imparerai come creare dipendenze tra attività** e calcolare il percorso critico in un file MS Project utilizzando Aspose.Tasks per Java. Comprendere e visualizzare il percorso critico ti aiuta a mantenere il progetto nei tempi previsti, mentre collegare correttamente le attività garantisce che qualsiasi ritardo sia immediatamente visibile. Percorriamo l'intero processo, dalla configurazione dell'ambiente alla visualizzazione del percorso critico finale.

## Quick Answers
- **Qual è il primo passo?** Configura il tuo progetto Java e aggiungi la libreria Aspose.Tasks.  
- **Quale modalità deve essere abilitata?** `CalculationMode.Automatic` (imposta il calcolo automatico).  
- **Come collego le attività?** Usa `project.getTaskLinks().add(...)` per creare dipendenze tra le attività.  
- **Come posso visualizzare il percorso critico?** Itera su `project.getCriticalPath()` e stampa il nome di ogni attività.  
- **È necessaria una licenza?** Sì, è richiesta una licenza valida di Aspose.Tasks per l'uso in produzione.

## What is “create task dependencies”?
Creare dipendenze tra attività significa definire relazioni (ad esempio Finish‑to‑Start) tra le attività affinché il programma rifletta le restrizioni del mondo reale. In Aspose.Tasks, ciò avviene tramite oggetti `TaskLink`.

## Why calculate the critical path in MS Project?
Il **percorso critico di MS Project** mostra la sequenza più lunga di attività dipendenti che determina la durata minima del progetto. Calcolandolo, puoi identificare rapidamente le attività che non possono subire ritardi senza influire sulla timeline complessiva—essenziale per applicazioni **project management Java** efficaci.

## Prerequisites
Prima di iniziare, assicurati di avere:

1. Java Development Kit (JDK) installato sul tuo sistema.  
2. La libreria Aspose.Tasks per Java scaricata e aggiunta al tuo progetto. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).

## Import Packages
Per iniziare, importa i pacchetti necessari nella tua classe Java:
```java
import com.aspose.tasks.*;
```

## How to set automatic calculation?
Impostare la modalità di calcolo su automatico garantisce che qualsiasi modifica a attività o collegamenti aggiorni immediatamente il programma, incluso il percorso critico.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
Definisci il percorso della cartella che contiene il tuo file MS Project.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load MS Project File
Carica il file di progetto esistente (ad esempio *New project 2013.mpp*) utilizzando Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Step 3: Add Tasks
Crea tre semplici sotto‑attività che collegheremo successivamente.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Step 4: Create Task Links (create task dependencies)
Definisci le dipendenze tra le attività. Qui utilizziamo un collegamento Finish‑to‑Start, che è il tipo più comune.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Step 5: Display Critical Path (display critical path)
Recupera e stampa il percorso critico. Il metodo `getCriticalPath()` restituisce l'elenco delle attività che formano la catena critica.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Step 6: Confirm Completion
Mostra un messaggio amichevole una volta terminato il processo.
```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Problema | Soluzione |
|----------|-----------|
| **Il percorso critico è vuoto** | Assicurati che `CalculationMode.Automatic` sia impostato prima di aggiungere i collegamenti. |
| **Attività non collegate** | Verifica di aver aggiunto gli oggetti `TaskLink` per ogni dipendenza. |
| **Eccezione di licenza** | Carica una licenza valida di Aspose.Tasks prima di creare l'istanza `Project`. |

## FAQ's
### Q: Posso usare Aspose.Tasks per Java con qualsiasi versione di file MS Project?
A: Sì, Aspose.Tasks per Java supporta varie versioni di file MS Project, inclusi i file .mpp da MS Project 2003 a MS Project 2019.  

### Q: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?
A: Sì, puoi scaricare una versione di prova gratuita da [qui](https://releases.aspose.com/).  

### Q: Dove posso trovare supporto per Aspose.Tasks per Java?
A: Puoi trovare supporto sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).  

### Q: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
A: Sì, puoi acquistare una licenza temporanea da [qui](https://purchase.aspose.com/temporary-license/).  

### Q: Come posso acquistare Aspose.Tasks per Java?
A: Puoi acquistare Aspose.Tasks per Java dal sito web [qui](https://purchase.aspose.com/buy).

## Conclusion
Seguendo questi passaggi hai **creato dipendenze tra attività**, impostato il **calcolo automatico** e visualizzato con successo il **percorso critico** del tuo file MS Project. Questo flusso di lavoro ti offre il pieno controllo sulla logica di programmazione e ti aiuta a mantenere i progetti in carreggiata utilizzando codice **project management** basato su Java.

---

**Ultimo aggiornamento:** 2025-12-23  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}