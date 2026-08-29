---
date: 2026-08-29
description: Scopri come aggiungere un'attività a un progetto in Java, creare un elenco
  di attività e impostare una baseline senza Microsoft Project usando Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Creare una baseline di attività in Aspose.Tasks
og_description: Scopri come aggiungere un'attività a un progetto in Java e impostare
  una baseline usando Aspose.Tasks. Questa guida mostra il codice passo‑passo senza
  necessità di Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Come aggiungere un'attività a un progetto in Java e impostare una baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Come aggiungere un'attività a un progetto in Java e impostare una baseline
url: /it/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un'attività a un progetto in Java e impostare una baseline

## Introduzione
In questo tutorial **aggiungerai un'attività a un progetto** programmaticamente, genererai una baseline di attività di Microsoft Project e salverai il file—tutto senza mai aprire Microsoft Project. Aspose.Tasks per Java ti offre un'API pure‑Java che funziona su qualsiasi piattaforma, rendendola perfetta per pipeline di build automatizzate, servizi di reporting o qualsiasi soluzione server‑side che deve manipolare file .mpp.

## Risposte rapide
- **Che cosa fa Aspose.Tasks?** Fornisce un'API Java per creare, leggere e modificare file Microsoft Project senza richiedere Microsoft Project.  
- **È necessario avere Microsoft Project installato?** No, la libreria funziona completamente in modo indipendente.  
- **Quale versione di Java è richiesta?** JDK 8 o superiore.  
- **Posso impostare una baseline per un'unica attività?** Sì – chiama `setBaseline` su una lista che contiene solo le attività desiderate.  
- **È necessaria una licenza per la produzione?** Sì, una licenza commerciale rimuove i limiti di valutazione e sblocca tutte le funzionalità.

## Cos'è una baseline di attività?
Una baseline di attività cattura la data di inizio, la data di fine e lo sforzo di lavoro originariamente pianificati per un'attività al momento in cui il programma viene salvato per la prima volta. Questa istantanea funge da punto di riferimento, consentendo ai project manager di confrontare l'avanzamento reale e i costi rispetto al piano iniziale e di calcolare le varianze per l'analisi delle prestazioni.

## Perché usare Aspose.Tasks per aggiungere un'attività a un progetto in Java?
Puoi creare, modificare e impostare le baseline delle attività senza alcuna installazione desktop, il che consente flussi di lavoro completamente automatizzati. Aspose.Tasks supporta **oltre 50 formati di input e output** e può gestire progetti con **centinaia di attività** mantenendo l'uso della memoria sotto i 200 MB, rendendola ideale per servizi cloud e pipeline CI/CD.

## Prerequisiti
1. **Java Development Kit (JDK)** – installa JDK 8 o più recente.  
2. **Aspose.Tasks for Java** – scarica la libreria dal [download link](https://releases.aspose.com/tasks/java/).  

## Importare i pacchetti
Per iniziare a lavorare con Aspose.Tasks nel tuo progetto Java, importa i pacchetti necessari:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Passo 1: creare un oggetto progetto
La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un file Microsoft Project in memoria. Istanziandola ottieni un progetto vuoto che puoi popolare con attività, risorse e calendari.

```java
Project project = new Project();
```
Qui istanziamo un nuovo oggetto `Project` – questo rappresenta il file MS Project che conterrà la nostra lista di attività.

## Passo 2: aggiungere un'attività al progetto
La classe `Task` rappresenta un singolo elemento di lavoro in un programma di progetto. Ogni `Task` può avere la propria durata, data di inizio e assegnazioni di risorse.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Usando `getRootTask()` accediamo alla radice della gerarchia del progetto e **aggiungiamo un'attività a Microsoft Project**. La stringa `"Task"` è il nome dell'attività; puoi sostituirla con qualsiasi descrizione necessaria.

## Passo 3: impostare la baseline per le attività specificate
`BaselineType` è un'enumerazione che definisce quale slot di baseline (Baseline, Baseline1 … Baseline10) vuoi scrivere. Passando una lista di attività puoi impostare la baseline solo per gli elementi selezionati.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Per **impostare la baseline senza MS Project**, crea una lista delle attività che desideri includere nella baseline (qui `myList`) e passala a `setBaseline`. Popola `myList` con le attività aggiunte se ti serve solo una baseline selettiva.

## Passo 4: impostare la baseline per l'intero progetto
`setBaseline` scrive i valori di baseline selezionati su ogni attività del progetto.  
Se preferisci impostare la baseline per l'intero progetto in una sola chiamata, basta invocare `setBaseline` con il `BaselineType` desiderato.

```java
project.setBaseline(BaselineType.Baseline);
```
Questa chiamata scrive i valori di baseline scelti per **ogni attività** nel progetto, garantendo un'istantanea completa del programma originale.

## Come aggiungere un'attività a Microsoft Project usando Aspose.Tasks
`add()` crea una nuova attività figlia sotto l'attività genitore specificata e restituisce l'oggetto `Task` appena creato.  
Aggiungi un'attività chiamando `add()` su un oggetto `Task` genitore (di solito l'attività radice). Il metodo restituisce una nuova istanza di `Task` che puoi configurare ulteriormente—durata, data di inizio, risorse o campi personalizzati—prima di salvare il file del progetto.

## Come impostare la baseline senza MS Project
Aspose.Tasks consente la creazione della baseline interamente tramite codice. Scegli un `BaselineType` (ad esempio `BaselineType.Baseline`) e invoca `setBaseline`. Puoi ripetere l'operazione con `Baseline1`‑`Baseline10` per mantenere più baseline di revisione, tutto senza aprire Microsoft Project.

## Problemi comuni e soluzioni
- **Baseline non appare:** Assicurati di chiamare `project.save("output.mpp")` dopo aver impostato la baseline (passo di salvataggio omesso qui per brevità).  
- **La lista delle attività appare vuota:** Verifica di aggiungere le attività al genitore corretto (`getRootTask()` o a un sotto‑task).  
- **Errori di incompatibilità di versione:** Usa l'ultimo JAR di Aspose.Tasks per garantire la compatibilità con i formati .mpp più recenti.

## Domande frequenti

**D: Posso usare Aspose.Tasks per Java senza Microsoft Project installato?**  
R: Sì, Aspose.Tasks funziona in modo indipendente e non richiede Microsoft Project sulla macchina host.

**D: Aspose.Tasks per Java è compatibile con diverse versioni di Microsoft Project?**  
R: Assolutamente. La libreria supporta file Project dal 2007 fino alle ultime versioni del 2024.

**D: Posso manipolare le risorse di progetto usando Aspose.Tasks per Java?**  
R: Sì, puoi aggiungere, aggiornare e eliminare risorse programmaticamente, proprio come le attività.

**D: Aspose.Tasks per Java supporta l'impostazione delle dipendenze tra attività?**  
R: Sì, puoi definire relazioni predecessore‑successore usando la classe `TaskLink`.

**D: È disponibile supporto tecnico per Aspose.Tasks per Java?**  
R: Sì, puoi ottenere aiuto tramite il [forum di supporto](https://forum.aspose.com/c/tasks/15), dove lo staff di Aspose e la community rispondono alle domande.

## Conclusione
Seguendo questi passaggi hai imparato come **aggiungere un'attività a un progetto** in Java, creare una lista di attività e **impostare la baseline senza MS Project** usando Aspose.Tasks. Questo approccio semplifica l'automazione dei progetti, elimina la necessità di installazioni desktop di Project e ti offre il pieno controllo programmatico su ogni aspetto del tuo programma.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutorial correlati

- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [How to Set Baseline Duration in Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Create Tasks Aspose Java – Task Properties](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}