---
date: 2026-08-29
description: Scopri come impostare i tipi di collegamento e gestire le dipendenze
  delle attività con Aspose.Tasks for Java in un tutorial passo-passo.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Come impostare i tipi di collegamento in Aspose.Tasks for Java
og_description: Scopri come impostare i tipi di collegamento e gestire le dipendenze
  delle attività con Aspose.Tasks for Java. Guida passo-passo per gli sviluppatori.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Come impostare i tipi di collegamento in Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Come impostare i tipi di collegamento in Aspose.Tasks for Java
url: /it/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare i tipi di collegamento in Aspose.Tasks per Java

## Introduzione
Se ti stai chiedendo **come impostare un collegamento** tra le attività mentre *gestisci le dipendenze delle attività* in un progetto, sei nel posto giusto. In questo tutorial ti guideremo nella creazione di un nuovo progetto, nell'aggiunta di attività e nella definizione del tipo di collegamento (Start‑to‑Start, Finish‑to‑Start, ecc.) utilizzando Aspose.Tasks per Java. Alla fine ti sentirai sicuro nel personalizzare le relazioni tra attività per soddisfare le esigenze di pianificazione del mondo reale e vedrai come l'API gestisce piani su larga scala con fino a 10.000 attività.

## Risposte rapide
- **Quale classe rappresenta una dipendenza?** `TaskLink` è l'oggetto principale che modella un collegamento tra due attività.  
- **Quale enum definisce il tipo di relazione?** `TaskLinkType` (ad esempio, `StartToStart`, `FinishToStart`).  
- **Posso leggere i tipi di collegamento esistenti?** Sì – itera `Project.getTaskLinks()` e chiama `getLinkType()`.  
- **Ho bisogno di una licenza per questo codice?** Una licenza temporanea funziona per i test; è necessaria una licenza completa per la produzione.  
- **È compatibile con Java 8+?** Assolutamente – Aspose.Tasks supporta Java 8 fino a Java 21, coprendo 13 versioni principali.

## Cos'è un collegamento di attività?
Un **collegamento di attività** modella una dipendenza tra due attività in un programma di progetto.  
Puoi creare, modificare o eliminare un `TaskLink` per riflettere le relazioni predecessore‑successore, consentendo al programmatore di calcolare automaticamente le date di inizio e fine.

## Perché usare i tipi di collegamento di Aspose.Tasks?
Aspose.Tasks supporta **oltre 30 formati di input e output** e può elaborare progetti contenenti **fino a 10.000 attività** senza caricare l'intero file in memoria. Questa capacità quantificata garantisce prestazioni rapide anche per piani su scala aziendale, e la libreria preserva tutte le funzionalità di Microsoft Project come campi personalizzati e assegnazioni di risorse.

## Prerequisiti
- **Ambiente di sviluppo Java** – JDK 8 o versioni successive installate e configurate.  
- **Libreria Aspose.Tasks** – Scarica l'ultimo JAR dal [download link](https://releases.aspose.com/tasks/java/).  
- **Directory dei documenti** – Crea una cartella sul tuo computer dove conserverai i file di progetto di esempio.

## Importare i pacchetti
Iniziamo importando le classi essenziali di Aspose.Tasks. Questo prepara l'IDE a riconoscere le chiamate API che utilizzeremo più avanti.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Come impostare i tipi di collegamento in Aspose.Tasks per Java?
Carica una nuova istanza di `Project`, aggiungi due attività e poi crea un `TaskLink` con il `TaskLinkType` desiderato. Questo modello a due passaggi ti consente di definire uno dei quattro tipi di dipendenza standard in una singola chiamata. `Project` rappresenta l'intero file di progetto e il suo programma. `Task` è un singolo elemento di lavoro all'interno del progetto. `TaskLink` collega un'attività predecessore a un'attività successore. `TaskLinkType` è un'enumerazione che specifica la relazione (Start‑to‑Start, Finish‑to‑Start, ecc.).

### Passo 1: impostare un tipo di collegamento
`TaskLink` rappresenta una dipendenza tra due attività, mentre `TaskLinkType` enumera i possibili tipi di relazione come `StartToStart`. In questo passaggio creiamo un nuovo progetto, aggiungiamo due attività e le colleghiamo utilizzando la relazione **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Consiglio:** Puoi sostituire `StartToStart` con `FinishToStart`, `StartToFinish` o `FinishToFinish` a seconda della dipendenza che devi **gestire le dipendenze delle attività**.

### Passo 2: ottenere un tipo di collegamento
`Project.getTaskLinks()` restituisce una collezione di tutti gli oggetti `TaskLink` nel programma. Iterando questa collezione puoi leggere il `TaskLinkType` di ciascun collegamento e verificare che la relazione corretta sia stata salvata.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

La console stamperà valori come `StartToStart`, `FinishToStart`, ecc., confermando il tipo di collegamento impostato in precedenza.

## Problemi comuni e soluzioni
- **NullPointerException durante l'aggiunta di collegamenti** – Assicurati che sia le attività predecessore che quelle successore siano aggiunte al progetto prima di creare un `TaskLink`.  
- **Tipo di collegamento errato dopo il salvataggio** – Chiama sempre `project.save("output.mpp")` (o un altro formato supportato) dopo aver impostato il tipo di collegamento per persistere le modifiche.  
- **Licenza non trovata** – Posiziona il file di licenza Aspose.Tasks nel classpath del progetto e caricalo con `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Domande frequenti

**D: Aspose.Tasks è compatibile con diversi ambienti Java?**  
R: Sì, Aspose.Tasks si integra con Java SE standard, Java EE e i kit di sviluppo Android senza dipendenze aggiuntive.

**D: Posso personalizzare i tipi di collegamento in base ai requisiti del mio progetto?**  
R: Assolutamente. L'enum `TaskLinkType` fornisce quattro tipi standard e puoi combinarli con valori di ritardo per modellare programmi complessi.

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks per Java?**  
R: Consulta la [documentazione di Aspose.Tasks per Java](https://reference.aspose.com/tasks/java/) per guide approfondite, riferimento API e esempi di codice.

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
R: Visita la [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/) per ottenere una licenza temporanea a scopo di test.

**D: Dove posso ottenere supporto per domande relative ad Aspose.Tasks?**  
R: Unisciti alla community di Aspose.Tasks sul [forum di supporto](https://forum.aspose.com/c/tasks/15) per assistenza e discussioni.

**D: Posso cambiare un tipo di collegamento dopo aver salvato il progetto?**  
R: Sì. Carica il progetto, recupera il `TaskLink`, chiama `setLinkType()` con il nuovo valore enum e salva nuovamente il progetto.

**D: Aspose.Tasks supporta la lettura di file Microsoft Project (MPP)?**  
R: Sì. Usa `new Project("file.mpp")` per caricare file MPP e lavorare con i loro collegamenti di attività proprio come nell'esempio XML sopra.

---

**Ultimo aggiornamento:** 2026-08-29  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Crea collegamento di attività cross-progetto in Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Imposta la data di inizio del progetto e gestisci attività padre e figlio in Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Carica file MPP Java - Gestisci le proprietà del progetto con Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}