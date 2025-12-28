---
date: 2025-12-28
description: Scopri come aggiungere attività e aggiornare i file MPP utilizzando Aspose.Tasks
  per Java, una libreria Java per la gestione dei progetti. Segui la nostra guida
  passo passo per creare attività in MPP e salvare il progetto come MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come aggiungere un'attività e aggiornare il file MPP in Aspose.Tasks
url: /it/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un'attività e aggiornare un file MPP in Aspose.Tasks

## Introduzione

## Risposte rapide
- **Cosa significa “how to add task” in questo contesto?** Si riferisce alla creazione programmatica di una nuova attività all'interno di un file Microsoft Project (MPP) esistente.  
- **Quale libreria gestisce l'operazione?** Aspose.Tasks for Java, una robusta libreria java per la gestione dei progetti.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso salvare il risultato come MPP?** Sì—usa `project.save(..., SaveFileFormat.Mpp)` per **salvare il progetto come mpp**.  
- **Quale versione di Java è richiesta?** Java 8 o successiva.

## Cos'è “how to add task” in un file MPP?
Aggiungere un'attività significa inserire un nuovo elemento di lavoro nella gerarchia del progetto, definendo le sue date di inizio/fine e salvando la modifica nel file MPP. Aspose.Tasks astrae i dettagli a basso livello del formato del file, permettendoti di concentrarti sulla logica di business.

## Perché usare Aspose.Tasks per Java?
- **Compatibilità completa** con i file Microsoft Project 2007‑2021.  
- **Nessuna installazione di COM o Office** richiesta—API Java pura.  
- **Set di funzionalità ricco**: collegamento attività, assegnazione risorse, campi personalizzati e altro.  
- **Alte prestazioni** per file di progetto di grandi dimensioni, rendendolo ideale per l'automazione lato server.

## Prerequisiti
1. **Ambiente di sviluppo Java** – JDK 8+ installato e configurato.  
2. **Aspose.Tasks for Java** – Scarica dalla [pagina di download](https://releases.aspose.com/tasks/java/).  
3. **Conoscenza di base di Java** – Familiarità con classi, oggetti e gestione delle date.  

## Importare i pacchetti
Per prima cosa, importa le classi necessarie. Questo ti dà accesso alla manipolazione del progetto, alle proprietà delle attività e alla gestione delle date.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Passo 1: Definire la directory dei dati
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con il percorso assoluto dove si trova il tuo file MPP di origine.

## Passo 2: Leggere il progetto esistente
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
Il costruttore `Project` carica **SampleMSP2010.mpp**, fornendoti un modello di oggetto manipolabile.

## Passo 3: Creare una nuova attività (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Questa riga **crea un'attività in mpp** aggiungendo un figlio chiamato *Task1* all'attività radice.

## Passo 4: Impostare le date di inizio e fine
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Qui definiamo la programmazione per l'attività appena aggiunta. Regola le date per farle corrispondere alla timeline del tuo progetto.

## Passo 5: Salvare il progetto (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Il progetto aggiornato, ora contenente la nuova attività, viene salvato come **AfterLinking.mpp**.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|----------|
| **File non trovato** | Verifica che `dataDir` termini con un separatore di percorso (`/` o `\\`) e che il nome del file sia corretto. |
| **Date errate** | Ricorda che i mesi di `Calendar` sono indicizzati da zero; `Calendar.JULY` è corretto per luglio. |
| **Eccezione di licenza** | Installa una licenza valida di Aspose.Tasks prima di chiamare qualsiasi API per evitare filigrane di valutazione. |

## FAQ
### D: Aspose.Tasks per Java può gestire strutture di progetto complesse?
R: Sì, Aspose.Tasks per Java offre funzionalità robuste per gestire strutture di progetto complesse in modo efficiente.  
### D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?
R: Sì, puoi scaricare una versione di prova gratuita dal [sito web](https://releases.aspose.com/).  
### D: Aspose.Tasks per Java supporta diverse versioni dei file Microsoft Project?
R: Assolutamente, Aspose.Tasks per Java supporta varie versioni dei file Microsoft Project, inclusi i formati MPP, MPT e XML.  
### D: Posso ottenere licenze temporanee per Aspose.Tasks per Java?
R: Sì, le licenze temporanee sono disponibili per scopi di test. Puoi ottenerle dalla [pagina delle licenze temporanee](https://purchase.aspose.com/temporary-license/).  
### D: Dove posso cercare aiuto o supporto riguardo Aspose.Tasks per Java?
R: Puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.

## Domande frequenti
**D: Come aggiungo più attività contemporaneamente?**  
R: Itera su una collezione di nomi di attività e ripeti il blocco “create task” all'interno del ciclo.

**D: Posso impostare campi personalizzati per la nuova attività?**  
R: Sì—usa `task.set(Tsk.CUSTOM_FIELD_x, value)` dove *x* è l'indice del campo.

**D: È possibile copiare un'attività esistente come modello?**  
R: Clona l'attività sorgente (`Task cloned = sourceTask.clone();`) e poi aggiungila al genitore desiderato.

**D: Cosa fare se devo aggiornare un'attività esistente invece di aggiungerne una nuova?**  
R: Recupera l'attività per ID (`Task existing = project.getRootTask().getChildren().getById(id);`) e modifica le sue proprietà.

**D: Aspose.Tasks supporta il salvataggio in altri formati come PDF o PNG?**  
R: Sì—usa `project.save("output.pdf", SaveFileFormat.Pdf);` o `SaveFileFormat.Png` per rappresentazioni visive.

---

**Ultimo aggiornamento:** 2025-12-28  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}