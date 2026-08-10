---
date: 2026-06-25
description: Scopri come aggiungere un'attività e aggiornare i file MPP usando Aspose.Tasks
  per Java, una libreria di gestione progetti Java che consente di creare file Microsoft
  Project e salvare il progetto come MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Come aggiungere un'attività e aggiornare un file MPP in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come aggiungere un'attività e aggiornare un file MPP in Aspose.Tasks
url: /it/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un'attività e aggiornare il file MPP in Aspose.Tasks

## Introduzione
In questo tutorial imparerai **how to add task** a un file Microsoft Project (MPP) esistente e poi a salvare il programma aggiornato usando Aspose.Tasks per Java, una leading **java project management library**. Che tu stia creando un scheduler personalizzato, automatizzando aggiornamenti di massa o integrando i dati di progetto in un sistema più ampio, la guida passo‑passo qui sotto mostra esattamente come caricare un progetto, inserire una nuova attività, impostarne le date e persistere il risultato come un nuovo documento MPP.

## Risposte rapide
- **What does “how to add task” mean in this context?** Significa creare programmaticamente un nuovo elemento di lavoro all'interno di un file MPP esistente.  
- **Which library handles the operation?** Aspose.Tasks for Java, una robusta java project management library.  
- **Do I need a license?** Una prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Can I save the result as MPP?** Sì—usa `project.save(..., SaveFileFormat.Mpp)` per **save project as mpp**.  
- **What Java version is required?** Java 8 o successiva.

## Cos'è “how to add task” in un file MPP?
L'aggiunta di un'attività significa inserire un nuovo elemento di lavoro nella gerarchia del progetto, definire le sue date di inizio/fine e persistere la modifica nel file MPP. Aspose.Tasks astrae i dettagli del formato di file a basso livello, permettendoti di concentrarti sulla logica di business gestendo automaticamente le assegnazioni delle risorse, i calendari e i calcoli delle dipendenze. Aggiorna inoltre tutte le assegnazioni correlate e ricalcola il programma del progetto per mantenere la coerenza tra le attività dipendenti.

## Perché usare Aspose.Tasks per Java?
- **Full compatibility**: Supporta il 100% delle funzionalità di Microsoft Project 2007‑2021 (oltre 150 tipi di attività e 200 campi risorsa).  
- **Zero‑dependency**: Non richiede COM, Office o librerie native—l'API Java pura funziona ovunque sia presente la JRE.  
- **Rich feature set**: Include collegamenti tra attività, allocazione delle risorse, campi personalizzati e report integrati.  
- **High performance**: Elabora progetti con fino a 10.000 attività utilizzando meno di 200 MB di RAM, rendendolo ideale per l'automazione lato server.

## Prerequisiti
1. **Java Development Environment** – JDK 8+ installato e configurato.  
2. **Aspose.Tasks for Java** – Scarica dalla [download page](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – Familiarità con classi, oggetti e gestione delle date.  

## Importare i pacchetti
Per prima cosa, importa le classi necessarie. Questo ti dà accesso alla manipolazione del progetto, alle proprietà delle attività e alla gestione delle date.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` rappresenta un file Microsoft Project caricato in memoria. `SaveFileFormat` elenca i formati in cui è possibile salvare, come MPP o PDF. `Task` modella un singolo elemento di lavoro all'interno della gerarchia del progetto. `Tsk` fornisce costanti per i campi delle attività usati durante l'impostazione o il recupero dei valori. `Calendar` offre utility data‑ora per definire i programmi.

## Passo 1: Definire la directory dei dati
```java
String dataDir = "Your Data Directory";
```  
Sostituisci `"Your Data Directory"` con il percorso assoluto dove risiede il tuo file MPP sorgente.

## Passo 2: Leggere il progetto esistente
La classe `Project` è l'oggetto principale di Aspose.Tasks che rappresenta un file Microsoft Project in memoria.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Il costruttore carica **SampleMSP2010.mpp**, fornendoti un modello di oggetto completamente manipolabile.

## Passo 3: Creare una nuova attività (how to add task)
La classe `Task` rappresenta un singolo elemento di lavoro all'interno della gerarchia del progetto.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Questa riga **creates task in mpp** aggiungendo un figlio chiamato *Task1* all'attività radice.

## Passo 4: Impostare le date di inizio e fine
La classe `Calendar` fornisce utility data‑ora; i mesi sono indicizzati da zero (es., `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Qui definiamo il programma per l'attività appena aggiunta. Regola le date per adattarle alla timeline del tuo progetto.

## Passo 5: Salvare il progetto (save project as mpp)
`SaveFileFormat.Mpp` indica ad Aspose.Tasks di scrivere il file nuovamente nel formato nativo di Microsoft Project.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Il progetto aggiornato, ora contenente la nuova attività, viene salvato come **AfterLinking.mpp**.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **File not found** | Verifica che `dataDir` termini con un separatore di percorso (`/` o `\\`) e che il nome del file sia corretto. |
| **Incorrect dates** | Ricorda che i mesi di `Calendar` sono indicizzati da zero; `Calendar.JULY` è corretto per luglio. |
| **License exception** | Installa una licenza valida di Aspose.Tasks prima di chiamare qualsiasi API per evitare filigrane di valutazione. |

## Domande frequenti
**Q: Come aggiungere più attività contemporaneamente?**  
A: Itera su una collezione di nomi di attività e ripeti il blocco “create task” all'interno del ciclo.

**Q: Posso impostare campi personalizzati per la nuova attività?**  
A: Sì—usa `task.set(Tsk.CUSTOM_FIELD_x, value)` dove *x* è l'indice del campo.

**Q: È possibile copiare un'attività esistente come modello?**  
A: Clona l'attività sorgente (`Task cloned = sourceTask.clone();`) e poi aggiungila al genitore desiderato.

**Q: Cosa fare se devo aggiornare un'attività esistente invece di aggiungerne una nuova?**  
A: Recupera l'attività per ID (`Task existing = project.getRootTask().getChildren().getById(id);`) e modifica le sue proprietà.

**Q: Aspose.Tasks supporta il salvataggio in altri formati come PDF o PNG?**  
A: Sì—usa `project.save("output.pdf", SaveFileFormat.Pdf);` o `SaveFileFormat.Png` per rappresentazioni visive.

---

**Ultimo aggiornamento:** 2026-06-25  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Come creare un file MPP – Creare e salvare un progetto vuoto in formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Come creare un progetto – Impostare i nuovi attributi delle attività con Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Creare un elenco di attività Java – Baseline di MS Project usando Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}