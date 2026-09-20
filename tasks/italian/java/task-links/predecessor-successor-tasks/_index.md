---
date: 2026-09-20
description: Scopri come gestire le dipendenze delle attività di progetto usando Aspose.Tasks
  for Java. Questa guida ti mostra come aggiungere collegamenti di predecessore, stampare
  i nomi delle attività e impostare le dipendenze delle attività in modo efficiente.
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: Gestisci le dipendenze delle attività di progetto tramite Aspose.Tasks
  for Java
og_description: Scopri come gestire le dipendenze delle attività di progetto usando
  Aspose.Tasks for Java. Questa guida ti mostra come aggiungere collegamenti di predecessore,
  stampare i nomi delle attività e impostare le dipendenze delle attività in modo
  efficiente.
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: Gestisci le dipendenze delle attività di progetto tramite Aspose.Tasks for
  Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: Gestisci le dipendenze delle attività di progetto tramite Aspose.Tasks for
  Java
url: /it/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestisci le dipendenze delle attività di progetto tramite Aspose.Tasks per Java

## Introduzione
Le dipendenze delle attività di progetto sono la spina dorsale di qualsiasi programma realistico, consentendo di modellare quale lavoro deve terminare prima che un altro possa iniziare. In questo tutorial imparerai a gestire **le dipendenze delle attività di progetto** con Aspose.Tasks per Java, inclusa l'aggiunta di collegamenti predecessori, la stampa dei nomi delle attività e l'impostazione delle dipendenze delle attività in modo programmatico.

## Risposte rapide
- **Qual è il primo passo?** Carica il tuo file MPP in un oggetto `Project`.  
- **Come si aggiunge un predecessore?** Crea un `TaskLink` e imposta i suoi `PredecessorTaskUid` e `SuccessorTaskUid`.  
- **Puoi elencare tutti i collegamenti?** Usa `project.getTaskLinks()` e itera sulla collezione.  
- **Ho bisogno di una licenza?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore.

## Cos'è la dipendenza delle attività di progetto?
Le dipendenze delle attività di progetto definiscono la relazione logica tra due attività, come Finish‑to‑Start o Start‑to‑Start, e determinano l'ordine in cui il lavoro deve essere eseguito. Stabilendo questi collegamenti, il programma rispetta automaticamente le restrizioni del mondo reale, impedisce attività sovrapposte e garantisce che le attività successive inizino solo quando i loro prerequisiti sono soddisfatti.

## Perché usare Aspose.Tasks per Java?
Aspose.Tasks per Java supporta più di trenta formati di file di progetto, incluse le versioni più recenti di Microsoft Project, e può elaborare file fino a due gigabyte senza caricare l'intero documento in memoria. Questa capacità ad alte prestazioni ti consente di manipolare programmi massivi, generare report e eseguire aggiornamenti di massa in modo efficiente, rendendola ideale per soluzioni di gestione progetti su scala aziendale.

## Prerequisiti
- Ambiente di sviluppo Java: Java 8 o versioni più recenti installate sulla tua macchina.  
- Libreria Aspose.Tasks per Java: Scarica e installa la libreria Aspose.Tasks dalla [pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).  
- Ambiente di sviluppo integrato (IDE): Eclipse, IntelliJ IDEA, o qualsiasi IDE compatibile con Java che preferisci.

## Importa pacchetti
È necessario importare le classi core che consentono la manipolazione del progetto.

La classe `Project` è il punto di ingresso per caricare e salvare i file Microsoft Project.  
La classe `TaskLink` rappresenta una dipendenza tra due attività.  

## Come aggiungere un collegamento predecessore tra due attività?
Crea un'istanza di `TaskLink`, assegna l'UID dell'attività predecessore e l'UID dell'attività successore, seleziona il `TaskLinkType` appropriato, come Finish‑to‑Start, e quindi aggiungi il collegamento alla collezione dei collegamenti delle attività del progetto. Una volta aggiunto, il programma riflette immediatamente la nuova relazione di dipendenza.

### Passo 1: inizializza l'oggetto progetto
Crea una nuova istanza della classe `Project` e fornisci il percorso al tuo file di progetto (ad esempio, `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### Passo 2: accedi ai collegamenti delle attività
Recupera tutti i collegamenti delle attività dal progetto usando il metodo `getTaskLinks()`.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Passo 3: itera attraverso i collegamenti delle attività
Usa un ciclo per iterare attraverso ogni collegamento delle attività nella collezione e stampa le informazioni sui compiti predecessori e successori.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### Passo 4: aggiungi un nuovo collegamento predecessore (opzionale)
Se hai bisogno di creare una nuova dipendenza, istanzia un `TaskLink`, imposta i suoi `PredecessorTaskUid`, `SuccessorTaskUid` e `LinkType`, quindi aggiungilo alla collezione dei collegamenti del progetto.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

Ripeti questi passaggi secondo le esigenze del tuo progetto specifico.

## Problemi comuni e soluzioni
- **Predecessore mancante dopo aver aggiunto un collegamento** – Assicurati di chiamare `project.updateTaskLinks()` (o salva e ricarica) affinché il grafo interno si aggiorni.  
- **Rallentamento delle prestazioni su file di grandi dimensioni** – Usa `project.setReadOnly(true)` prima delle operazioni di massa per ridurre l'overhead di memoria.  
- **Tipo di collegamento errato** – Verifica di utilizzare il valore enum `TaskLinkType` corretto (ad esempio, `FinishToStart`) per corrispondere alla logica del tuo programma.

## Domande frequenti

**D: Posso usare Aspose.Tasks per Java nel mio progetto Java esistente?**  
R: Sì, basta aggiungere il JAR di Aspose.Tasks al tuo classpath o alle dipendenze Maven/Gradle.

**D: Aspose.Tasks è compatibile con diversi formati di file di progetto?**  
R: Sì, supporta MPP, XML, CSV e più di 30 formati aggiuntivi.

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
R: Ottieni una licenza temporanea dalla [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare supporto aggiuntivo per Aspose.Tasks?**  
R: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto della community e discussioni.

**D: Posso scaricare una versione di prova gratuita di Aspose.Tasks per Java?**  
R: Sì, scarica una prova gratuita dalla [pagina di prova gratuita di Aspose](https://releases.aspose.com/).

---

**Ultimo aggiornamento:** 2026-09-20  
**Testato con:** Aspose.Tasks per Java 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Crea dipendenze delle attività di gestione progetti in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Imposta la data di inizio del progetto e gestisci attività padre e figlio in Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Leggi e imposta le priorità delle attività con Aspose.Tasks per Java](/tasks/java/task-properties/handle-priorities/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}