---
date: 2026-01-18
description: Impara come creare un elenco di attività Java e aggiungere attività a
  Microsoft Project, impostando una baseline senza MS Project usando Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Crea elenco attività Java – baseline di MS Project con Aspose.Tasks
url: /it/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea elenco attività Java – Baseline di MS Project con Aspose.Tasks

## Introduction
In questo tutorial, **creerai un elenco attività Java** generando una baseline di attività di Microsoft Project utilizzando Aspose.Tasks per Java. Aspose.Tasks ti consente di lavorare con i file Project senza avere Microsoft Project installato, così puoi **aggiungere attività a Microsoft Project**, manipolare le risorse e persino **impostare la baseline senza MS Project** — tutto da puro codice Java.

## Quick Answers
- **Cosa fa Aspose.Tasks?** Fornisce un'API Java per creare, leggere e modificare file Microsoft Project senza MS Project.  
- **È necessario avere Microsoft Project installato?** No, Aspose.Tasks funziona in modo indipendente.  
- **Quale versione di Java è richiesta?** JDK 8 o superiore.  
- **Posso impostare una baseline per un singolo task?** Sì, usa `setBaseline` con un elenco di task.  
- **È necessaria una licenza per la produzione?** Sì, una licenza commerciale rimuove i limiti di valutazione.

## What is a Task Baseline?
Una baseline di task registra i valori originali pianificati di inizio, fine e lavoro per un task. Serve come punto di riferimento per confrontare l'avanzamento reale con il piano originale.

## Why use Aspose.Tasks to create task list Java?
- **Nessuna dipendenza da MS Project** – ideale per l'automazione lato server.  
- **Controllo completo** su task, risorse e calendari tramite codice Java.  
- **Compatibilità cross‑versione** con file Project 2007‑2024.

## Prerequisites
1. **Java Development Kit (JDK)** – installa JDK 8 o più recente.  
2. **Aspose.Tasks for Java** – scarica la libreria dal [download link](https://releases.aspose.com/tasks/java/).  

## Import Packages
Per iniziare a lavorare con Aspose.Tasks nel tuo progetto Java, importa i pacchetti necessari:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Step 1: Create a Project Object
```java
Project project = new Project();
```
Qui istanziamo un nuovo oggetto `Project` – rappresenta il file MS Project che conterrà il nostro elenco attività.

## Step 2: Add a Task to the Project
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Usando `getRootTask()` accediamo alla radice della gerarchia del progetto e **aggiungiamo un task a Microsoft Project**. La stringa `"Task"` è il nome del task; puoi sostituirla con qualsiasi descrizione necessaria.

## Step 3: Set Baseline for Specified Tasks
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Per **impostare la baseline senza MS Project**, crea un elenco dei task che desideri includere nella baseline (qui `myList`) e passalo a `setBaseline`. Popola `myList` con i task aggiunti se ti serve solo una baseline selettiva.

## Step 4: Set Baseline for the Entire Project
```java
project.setBaseline(BaselineType.Baseline);
```
Se preferisci impostare la baseline per l'intero progetto in un'unica chiamata, basta invocare `setBaseline` con il `BaselineType` desiderato.

## How to add task to Microsoft Project using Aspose.Tasks
Oltre al singolo task mostrato sopra, puoi aggiungere più task, sotto‑task e assegnare risorse. Ogni chiamata a `add()` restituisce un oggetto `Task` che puoi configurare ulteriormente (durata, data di inizio, ecc.).

## How to set baseline without MS Project
Aspose.Tasks consente la creazione della baseline interamente tramite codice. Puoi impostare diversi tipi di baseline (Baseline, Baseline1‑Baseline10) modificando l'enumerazione `BaselineType`, permettendoti di tracciare più revisioni di baseline senza mai aprire MS Project.

## Common Issues and Solutions
- **Baseline non appare:** Assicurati di chiamare `project.save("output.mpp")` dopo aver impostato la baseline (passo di salvataggio omesso qui per brevità).  
- **L'elenco dei task appare vuoto:** Verifica di aggiungere i task al genitore corretto (`getRootTask()` o a un sotto‑task).  
- **Errori di incompatibilità di versione:** Usa l'ultimo JAR di Aspose.Tasks per garantire la compatibilità con i formati .mpp più recenti.

## Frequently Asked Questions

**Q: Posso usare Aspose.Tasks per Java senza Microsoft Project installato?**  
A: Sì, Aspose.Tasks funziona in modo indipendente e non richiede Microsoft Project sulla macchina host.

**Q: Aspose.Tasks per Java è compatibile con diverse versioni di Microsoft Project?**  
A: Assolutamente. La libreria supporta file Project dal 2007 fino alle ultime versioni 2024.

**Q: Posso manipolare le risorse del progetto usando Aspose.Tasks per Java?**  
A: Sì, puoi aggiungere, aggiornare e cancellare risorse programmaticamente, proprio come i task.

**Q: Aspose.Tasks per Java supporta l'impostazione di dipendenze tra task?**  
A: Sì, puoi definire relazioni predecessore‑successore usando la classe `TaskLink`.

**Q: È disponibile supporto tecnico per Aspose.Tasks per Java?**  
A: Sì, puoi ottenere assistenza tramite il [forum di supporto](https://forum.aspose.com/c/tasks/15), dove lo staff di Aspose e la community rispondono alle domande.

## Conclusion
Seguendo questi passaggi, hai imparato come **creare un elenco attività Java**, **aggiungere task a Microsoft Project** e **impostare la baseline senza MS Project** usando Aspose.Tasks. Questo approccio semplifica l'automazione dei progetti, elimina la necessità di installazioni desktop di Project e ti offre un controllo programmatico completo sui dati del tuo progetto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-01-18  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose