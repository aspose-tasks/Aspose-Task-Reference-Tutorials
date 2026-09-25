---
date: 2026-09-25
description: Scopri come creare un programma di progetto in Java utilizzando Aspose.Tasks.
  Questa guida ti mostra come aggiungere attività di riepilogo, gestire la gerarchia
  del progetto e impostare la directory dei documenti in modo efficiente.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Crea attività in Aspose.Tasks
og_description: Scopri come creare un programma di progetto in Java utilizzando Aspose.Tasks.
  Segui le istruzioni passo‑passo per aggiungere attività di riepilogo, gestire la
  gerarchia e impostare la directory dei documenti.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Come creare un programma di progetto con Aspose.Tasks per Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Come creare un programma di progetto con Aspose.Tasks per Java
url: /it/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un programma di progetto con Aspose.Tasks per Java

## Introduzione
In questo tutorial imparerai a **creare un programma di progetto** in un'applicazione Java utilizzando Aspose.Tasks. Che tu stia costruendo una semplice lista di cose da fare o un complesso pianificatore a livello aziendale, i passaggi seguenti ti guideranno nell'aggiungere attività di riepilogo, gestire la gerarchia del progetto e impostare la cartella dei documenti — il tutto con snippet di codice chiari e eseguibili. Alla fine, avrai un programma completamente strutturato pronto per ulteriori manipolazioni o esportazioni.

## Risposte rapide
- **Cosa gestisce Aspose.Tasks?** Gestisce gerarchie di attività, risorse, calendari e formati di file di progetto (MS‑Project, Primavera, ecc.).  
- **È necessaria una licenza per lo sviluppo?** Una licenza temporanea gratuita è sufficiente per la valutazione; è richiesta una licenza completa per la produzione.  
- **Quale versione di Java è supportata?** Java 8 e versioni successive sono pienamente supportate.  
- **Posso aggiungere campi personalizzati alle attività?** Sì, è possibile estendere le attività con campi definiti dall'utente tramite l'API.  
- **Esiste un supporto integrato per i diagrammi di Gantt?** Aspose.Tasks può esportare in PDF/HTML includendo visualizzazioni Gantt.

## Che cos'è un programma di progetto in Aspose.Tasks?
Un programma di progetto è l'insieme completo di attività, dipendenze e tempistiche che definiscono come il lavoro verrà svolto. Aspose.Tasks memorizza queste informazioni in un oggetto `Project` che puoi leggere, modificare e salvare in vari formati. Include date di inizio e fine, vincoli e assegnazioni di risorse, consentendo una pianificazione e una reportistica complete.

## Perché usare Aspose.Tasks per la gestione di progetti Java?
Aspose.Tasks supporta **oltre 30 formati di input e output** e può elaborare progetti con **fino a 10.000 attività** senza caricare l'intero file in memoria, offrendo alte prestazioni per scenari di gestione di progetti Java su larga scala.

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- **Java Development Kit (JDK)** – JDK 8 o successivo installato sulla tua macchina.  
- **Libreria Aspose.Tasks per Java** – Scarica e installa la libreria da [download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – Usa Eclipse, IntelliJ IDEA o qualsiasi IDE Java-friendly che preferisci.

## Importare i pacchetti
`Project`, `Task` e le classi correlate si trovano nello spazio dei nomi `com.aspose.tasks`. Importale all'inizio del tuo file Java:

La classe `Project` rappresenta un programma di progetto completo e fornisce metodi per manipolare attività e risorse.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

La classe `Project` è il punto di ingresso per tutte le operazioni su un file di progetto.

## Come creare un programma di progetto con Aspose.Tasks?

Carica una nuova istanza `Project`, imposta la cartella dei documenti e inizia ad aggiungere attività. Questo paragrafo di risposta diretta spiega il flusso principale: crei un `Project`, configuri il suo `RootFolder` (la cartella dei documenti), quindi aggiungi un'attività di riepilogo seguita da attività secondarie. Tutte le modifiche rimangono in memoria fino a quando non chiami `save` per persistere il programma su file.

### Passo 1: impostare la cartella dei documenti
Definisci dove verrà scritto il file di progetto risultante. Impostare la cartella in anticipo garantisce che tutte le successive operazioni di salvataggio utilizzino un percorso coerente.

La proprietà `RootFolder` specifica la cartella di base da cui i file di progetto vengono letti o in cui vengono scritti.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Passo 2: creare un nuovo progetto
Istanzia un nuovo oggetto `Project` che conterrà il tuo programma. Puoi opzionalmente passare un percorso di file preesistente per caricare un programma esistente da modificare.

Il costruttore `Project` crea un programma vuoto pronto per l'aggiunta di attività.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Passo 3: aggiungere un'attività di riepilogo
Un'attività di riepilogo raggruppa attività secondarie correlate e appare come un nodo comprimibile nei diagrammi di Gantt. Usa la classe `Task` e imposta `IsSummary` su `true`.

Il metodo `addTask` crea una nuova attività sotto un genitore specificato e restituisce il suo ID.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Passo 4: aggiungere un'attività secondaria
Le attività secondarie ereditano le date di inizio/fine dalla loro attività di riepilogo padre, a meno che non le sovrascrivi. Aggiungere un'attività secondaria è semplice come chiamare nuovamente `addTask` specificando l'ID del padre.

Chiamare `addTask` con un ID di padre aggiunge un'attività secondaria sotto quell'attività di riepilogo.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Continua ad aggiungere quante attività e attività secondarie desideri per il tuo progetto. Ogni passaggio contribuisce a costruire una gerarchia di progetto strutturata che può essere esportata in MS‑Project, PDF o altri formati supportati.

## Problemi comuni e soluzioni
- **Problema:** “Cartella dei documenti non trovata.”  
  **Soluzione:** Verifica che il percorso assegnato a `RootFolder` esista nel file system e che il tuo processo Java abbia i permessi di scrittura.
- **Problema:** Le attività secondarie non compaiono sotto l'attività di riepilogo.  
  **Soluzione:** Assicurati di passare l'ID corretto dell'attività padre quando chiami `addTask`. L'API richiede l'ID del padre come secondo argomento.
- **Problema:** Progetti di grandi dimensioni causano OutOfMemoryError.  
  **Soluzione:** Aspose.Tasks elabora le attività in modalità streaming; aumenta la dimensione dell'heap JVM (`-Xmx2g`) o suddividi il programma in più file.

## Domande frequenti
**D: Aspose.Tasks è adatto a progetti di piccola scala?**  
R: Assolutamente. La libreria scala da una singola lista di attività a programmi a livello aziendale con migliaia di attività.

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks per Java?**  
R: Consulta la documentazione [Riferimento API Java di Aspose.Tasks](https://reference.aspose.com/tasks/java/).

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
R: Visita la [pagina di richiesta licenza temporanea](https://purchase.aspose.com/temporary-license/) per una licenza a tempo limitato valida per sviluppo e test.

**D: Posso personalizzare gli attributi delle attività usando Aspose.Tasks?**  
R: Sì, puoi estendere le attività con campi personalizzati, assegnare risorse e modificare i calendari programmaticamente.

**D: Esiste una community di supporto per gli utenti di Aspose.Tasks?**  
R: Assolutamente! Unisciti alla community di Aspose.Tasks sul [forum di supporto](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2026-09-25  
**Testato con:** Aspose.Tasks 24.12 per Java  
**Autore:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Tutorial correlati

- [Imposta la data di inizio del progetto in MS Project usando Aspose.Tasks per Java](/tasks/java/project-properties/write-project-info/)
- [Crea dipendenze tra attività di gestione progetto in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Come aggiungere risorse al progetto e creare assegnazioni di risorse in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}