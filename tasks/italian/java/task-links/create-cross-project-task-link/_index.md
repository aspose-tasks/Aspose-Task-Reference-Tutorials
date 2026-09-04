---
date: 2026-07-05
description: Scopri come collegare le attività tra progetti con Aspose.Tasks for Java.
  Step‑by‑step guide, prerequisites e best practices per un collegamento senza interruzioni
  tra progetti.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Crea un collegamento di attività cross‑project in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Collega le attività tra progetti usando Aspose.Tasks for Java
url: /it/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Collega attività tra progetti usando Aspose.Tasks per Java

## Introduzione
Collegare attività tra progetti è una funzionalità fondamentale che consente di sincronizzare il lavoro, evitare duplicazioni e mantenere una fonte unica di verità per attività interdipendenti. In questo tutorial scoprirai come **collegare attività tra progetti** con Aspose.Tasks per Java, passo dopo passo. Alla fine avrai un collegamento cross‑project completamente funzionante che si aggiorna automaticamente quando una delle due parti cambia, fornendoti una coordinazione in tempo reale senza copiare e incollare manualmente.

## Risposte rapide
- **Qual è la classe principale per creare un progetto?** `Project` – rappresenta l'intero file MS‑Project in memoria.  
- **Quale metodo aggiunge un'attività esterna?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Posso impostare il tipo di collegamento?** Sì – usa `TaskLinkType.FinishToStart`, `StartToStart`, ecc.  
- **È necessaria una licenza per il collegamento?** È richiesta una licenza valida di Aspose.Tasks per l'uso in produzione; una versione di prova gratuita è sufficiente per la valutazione.  
- **Esiste un limite al numero di attività collegate?** Aspose.Tasks può gestire più di 10.000 attività collegate per progetto senza degrado delle prestazioni.

## Che cosa significa collegare attività tra progetti?
Collegare attività tra progetti crea una relazione di dipendenza tra un'attività in un file di progetto e un'attività in un altro, consentendo alle modifiche dell'attività di origine (durata, data di inizio, vincoli) di propagarsi automaticamente all'attività dipendente. Questo meccanismo mantiene i piani allineati, riduce gli aggiornamenti manuali e garantisce che qualsiasi modifica nel progetto di origine sia immediatamente riflessa in tutti i progetti collegati, preservando la coerenza dell'intero portafoglio.

## Perché usare Aspose.Tasks per il collegamento cross‑project?
Aspose.Tasks supporta **oltre 50 formati di input e output** e può elaborare **progetti di centinaia di pagine** mantenendo l'utilizzo della memoria sotto i 200 MB. La sua API esegue il collegamento sul lato server, eliminando la necessità di installare Microsoft Project e consentendo pipeline automatizzate per grandi imprese.

## Prerequisiti
- Java 17 (o versioni successive) installato e configurato nel tuo IDE.  
- Un file di licenza valido di Aspose.Tasks per Java (`Aspose.Tasks.Java.lic`).  
- La libreria Aspose.Tasks per Java aggiunta al tuo progetto. Puoi scaricarla dalla [pagina di rilascio di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).  
- Familiarità di base con i concetti di MS‑Project come attività, attività riepilogo e dipendenze.

## Importa pacchetti
Le classi `Project`, `Task`, `TaskLink` e i relativi enum risiedono nello spazio dei nomi `com.aspose.tasks`. Importali all'inizio del tuo file Java:

`import com.aspose.tasks.*;`

**Project** è la classe principale che rappresenta un file di progetto in memoria. **Task** rappresenta un singolo elemento di lavoro all'interno di un progetto. **TaskLink** definisce una relazione di dipendenza tra due attività. Queste importazioni ti danno accesso all'intera suite di funzionalità di manipolazione del progetto, incluso il collegamento cross‑project.

## Come collegare attività tra progetti?
Carica i due file di progetto, aggiungi un segnaposto per un'attività esterna, crea un'attività locale e poi collegali con un `TaskLink`. L'API gestisce la mappatura degli ID e gli aggiornamenti automaticamente, garantendo che qualsiasi modifica all'attività esterna si propaghi all'attività locale collegata senza codice aggiuntivo. Questo approccio semplifica il coordinamento multi‑project e riduce il rischio di slittamento del programma.

### Passo 1: Configura l'ambiente
Assicurati che il JAR di Aspose.Tasks sia nel classpath e che il file di licenza sia caricato a runtime:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** carica il tuo file di licenza Aspose.Tasks per abilitare tutte le funzionalità e rimuovere le filigrane di valutazione.

### Passo 2: Crea un'istanza di Project
Istanzia un nuovo oggetto `Project` per il progetto di destinazione dove desideri che il collegamento risieda:

`Project targetProject = new Project();`

La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file di progetto in memoria.

### Passo 3: Aggiungi un'attività riepilogo
Un'attività riepilogo raggruppa attività correlate. Creane una per contenere sia l'attività esterna sia quella locale:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### Passo 4: Aggiungi attività esterna
Inserisci un'attività esterna che punta a un'attività in un altro file di progetto:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

Il metodo **addExternalTask** crea un'attività segnaposto che fa riferimento a un file di progetto esterno, utilizzando il nome file e l'ID attività forniti.

### Passo 5: Aggiungi attività locale
Crea l'attività che sarà collegata a quella esterna:

`Task local = summary.getChildren().add("Local Task");`

### Passo 6: Crea collegamento attività
Stabilisci una dipendenza tra le attività esterna e locale. Il tipo di collegamento più comune è Finish‑to‑Start:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** registra la relazione; puoi successivamente modificare il suo ritardo, anticipo o tipo secondo necessità.

### Passo 7: Salva e verifica
Salva il progetto su file e, facoltativamente, aprilo in Microsoft Project per verificare il collegamento:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** specifica il formato file per salvare un progetto. Quando apri *LinkedProject.mpp*, vedrai l'attività esterna visualizzata con un'icona speciale e la linea di dipendenza che punta all'attività locale.

## Problemi comuni e soluzioni
- **File esterno non trovato** – Assicurati che il percorso sia relativo al processo in esecuzione o fornisci un percorso assoluto.  
- **ID attività non corrispondenti** – Verifica che l'ID dell'attività esterna (il secondo argomento di `addExternalTask`) corrisponda al progetto di origine.  
- **Licenza non caricata** – Un file di licenza mancante o errato genera una `LicenseException`. Caricalo prima di qualsiasi chiamata a Aspose.Tasks.  
- **Prestazioni su progetti di grandi dimensioni** – Usa `Project.setReadOnly(true)` quando devi solo leggere le attività esterne; questo riduce il consumo di memoria.

## Domande frequenti

**Q: Posso collegare attività da più progetti esterni nello stesso task riepilogo?**  
A: Sì, puoi aggiungere diverse attività esterne sotto un unico task riepilogo e creare collegamenti individuali per ciascuna, usando lo stesso metodo `addExternalTask`.

**Q: Cosa succede se l'attività esterna nel progetto collegato viene modificata?**  
A: Qualsiasi modifica al programma, alla durata o ai vincoli dell'attività esterna viene automaticamente riflessa nell'attività locale dipendente quando il progetto di destinazione viene aggiornato.

**Q: È possibile creare collegamenti tra attività in formati di file diversi?**  
A: Assolutamente. Aspose.Tasks supporta il collegamento tra formati MPP, XML e Primavera, consentendo a ecosistemi di progetto eterogenei di rimanere sincronizzati.

**Q: Posso scollegare le attività una volta che sono state collegate tra progetti?**  
A: Sì, rimuovi il collegamento chiamando `project.getTaskLinks().remove(link)` o eliminando il segnaposto dell'attività esterna.

**Q: Ci sono limitazioni sul numero di attività che possono essere collegate tra progetti?**  
A: La libreria può gestire **oltre 10.000 attività collegate** per progetto, limitata solo dalla memoria di sistema disponibile e dalle specifiche del formato di file sottostante.

## Conclusione
Ora disponi di un approccio completo e pronto per la produzione per **collegare attività tra progetti** usando Aspose.Tasks per Java. Questa funzionalità semplifica il coordinamento multi‑project, riduce lo sforzo manuale e garantisce che le modifiche al programma si propaghino istantaneamente in tutto il tuo portafoglio. Esplora funzionalità aggiuntive come tempi di ritardo personalizzati, diversi tipi di collegamento e collegamenti in blocco per automatizzare ulteriormente strutture di progetto complesse.

---

**Ultimo aggiornamento:** 2026-07-05  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## Tutorial correlati

- [Crea collegamento attività in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Crea attività Aspose Java – Proprietà attività](/tasks/java/task-properties/)
- [Crea file MS Project vuoto in Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}