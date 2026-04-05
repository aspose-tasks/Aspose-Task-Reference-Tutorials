---
date: 2026-02-26
description: Scopri come suddividere le attività con Aspose.Tasks per Java – la guida
  definitiva su come suddividere le attività, impostare il calendario del progetto
  e creare l'assegnazione delle risorse.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come suddividere le attività in Aspose.Tasks
url: /it/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come dividere le attività in Aspose.Tasks

## Introduzione
Se stai cercando **come dividere le attività** in un progetto basato su Java, sei nel posto giusto. Aspose.Tasks per Java ti offre un modo pulito e programmatico per suddividere un'attività a lungo termine in parti più piccole e gestibili, il che aiuta con il livellamento delle risorse, la reportistica accurata e scadenze di progetto più strette. In questo tutorial percorreremo l'intero processo—dalla configurazione del calendario del progetto alla creazione di un'assegnazione di risorsa e infine alla divisione dell'attività in più segmenti.

## Risposte rapide
- **Cos'è la divisione delle attività?** Suddividere un'unica attività in diversi intervalli più piccoli mantenendo la sua durata totale.  
- **Perché dividere le attività in Java?** Consente un'allocazione precisa delle risorse e un migliore monitoraggio dell'avanzamento.  
- **Quale libreria aiuta?** Aspose.Tasks for Java fornisce metodi integrati per la divisione e la suddivisione temporale.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza per la produzione.  
- **Quale versione di Java è supportata?** La libreria funziona con Java 8 e versioni successive.

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti pronti:
- Java Development Kit (JDK) installato sulla tua macchina.  
- Libreria Aspose.Tasks per Java scaricata e aggiunta al tuo progetto. Puoi scaricarla dalla [documentazione di Aspose.Tasks per Java](https://reference.aspose.com/tasks/java/).

## Importa i pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Passo 1: Crea un nuovo progetto
Inizia creando un nuovo progetto utilizzando la libreria Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Passo 2: Imposta il calendario del progetto
Impostare il **calendario del progetto** definisce i giorni lavorativi, le festività e la linea temporale complessiva del tuo programma. Questo passaggio è essenziale per calcoli temporali accurati.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Passo 3: Aggiungi un'attività radice
Ogni progetto ha bisogno di un contenitore radice. Aggiungere un'attività radice ti offre un punto a cui collegare tutte le attività successive.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Passo 4: Aggiungi una nuova attività da dividere
Crea l'attività che intendi dividere. Qui impostiamo una durata di tre giorni come esempio.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Passo 5: Crea un'assegnazione di risorsa
Un'**assegnazione di risorsa** collega una risorsa (o un segnaposto) all'attività. Questo è necessario prima di generare i dati temporali.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Passo 6: Genera dati temporali
I dati temporali rappresentano come il lavoro è distribuito sulla durata dell'attività. Generarli prepara l'attività alla divisione.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Passo 7: Dividi l'attività
Ora **dividiamo l'attività in parti**. In questo esempio dividiamo l'attività di tre giorni in tre segmenti di un giorno ciascuno.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Perché dividere le attività?
Dividere le attività ti offre un controllo più granulare su:
- **Livellamento delle risorse:** Assegna risorse diverse a ciascun segmento.
- **Monitoraggio dell'avanzamento:** Aggiorna lo stato su base per segmento.
- **Reportistica:** Genera diagrammi di Gantt e report più dettagliati.

## Problemi comuni e soluzioni
- **Dati del calendario mancanti:** Assicurati di chiamare `timephasedDataFromTaskDuration` prima di dividere.  
- **Segmenti a durata zero:** Verifica che ogni intervallo diviso abbia una durata diversa da zero; altrimenti la libreria lo ignorerà.  
- **Eccezioni di licenza:** L'esecuzione senza una licenza valida può aggiungere una filigrana ai file esportati.

## Domande frequenti
### Posso dividere le attività con durate diverse?
Sì, puoi regolare la durata di ogni parte per soddisfare i requisiti del tuo progetto.

### Aspose.Tasks per Java è compatibile con tutte le versioni di Java?
Aspose.Tasks per Java è progettato per funzionare senza problemi con Java 8 e versioni successive, garantendo ampia compatibilità.

### Posso usare Aspose.Tasks per Java gratuitamente?
Aspose.Tasks per Java offre una versione di prova gratuita, che ti permette di esplorare le sue funzionalità prima di effettuare un acquisto.

### Come posso ottenere supporto per Aspose.Tasks per Java?
Visita il [forum di supporto di Aspose.Tasks per Java](https://forum.aspose.com/c/tasks/15) per ricevere assistenza e connetterti con la community.

### Ho bisogno di una licenza temporanea per Aspose.Tasks per Java?
Puoi ottenere una licenza temporanea da [questo link](https://purchase.aspose.com/temporary-license/) per scopi di test e valutazione.

---

**Ultimo aggiornamento:** 2026-02-26  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}