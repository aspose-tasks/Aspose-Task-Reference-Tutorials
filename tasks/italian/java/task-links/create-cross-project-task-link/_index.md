---
date: 2026-01-20
description: Scopri come collegare i progetti e collegare le attività tra progetti
  usando Aspose.Tasks per Java. Segui la guida passo‑passo per creare collegamenti
  di attività tra progetti.
linktitle: Create Cross-Project Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Come collegare i progetti: creare un collegamento di attività tra progetti
  in Aspose.Tasks'
url: /it/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come collegare i progetti: creare un collegamento di attività cross‑project in Aspose.Tasks

## Come collegare i progetti con Aspose.Tasks
Nell’attuale ambiente di gestione progetti ad alta velocità, sapere **come collegare i progetti** è fondamentale per mantenere più piani sincronizzati. Aspose.Tasks per Java offre un’API potente per creare collegamenti di attività cross‑project, consentendo di **collegare attività tra progetti** con poche righe di codice. In questo tutorial imparerai i passaggi esatti, vedrai gli snippet di codice richiesti e comprenderai perché questa tecnica può migliorare drasticamente la collaborazione tra i membri del team.

## Risposte rapide
- **Qual è il beneficio principale?** Sincronizzare senza soluzione di continuità gli elementi di lavoro dipendenti tra file di progetto separati.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (ultima versione).  
- **È necessaria una licenza?** È richiesta una licenza valida di Aspose.Tasks per l’uso in produzione.  
- **Quanti minuti per implementare?** Circa 10–15 minuti per un collegamento di base.  
- **Posso collegare attività tra formati di file diversi?** Sì – l’API supporta MPP, XML e altri formati.

## Prerequisiti
Prima di iniziare, assicurati di avere a disposizione quanto segue:

- Conoscenza pratica della programmazione Java.  
- Aspose.Tasks per Java installato. Puoi scaricarlo dalla [pagina di rilascio di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).  
- Comprensione di base dei concetti di gestione progetti, come dipendenze delle attività e attività riepilogo.

## Importare i pacchetti
Per prima cosa, importa le classi necessarie. Questo ti dà accesso alle funzionalità principali di Aspose.Tasks:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

## Passo 1: configurare l’ambiente
Assicurati che Java sia installato sulla tua macchina e che il JAR di Aspose.Tasks sia aggiunto al classpath del progetto. Questo passaggio è cruciale affinché il codice venga compilato senza errori.

## Passo 2: creare un’istanza di Project
Crea un nuovo oggetto `Project` che conterrà le attività e i collegamenti:

```java
Project project = new Project();
```

## Passo 3: aggiungere un’attività riepilogo
Un’attività riepilogo funge da contenitore per le attività che collegherai. Rende la struttura più chiara quando visualizzi il progetto in seguito:

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

## Passo 4: aggiungere un’attività esterna
Ora aggiungi un’attività esterna che punta a un’attività in un altro file di progetto. Questo è il lato “sorgente” del collegamento cross‑project:

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

## Passo 5: aggiungere un’attività locale
Crea l’attività locale che sarà collegata a quella esterna. Questo è il lato “destinazione” della relazione:

```java
Task t = summary.getChildren().add("Task");
```

## Passo 6: creare il collegamento di attività
Stabilisci il collegamento tra l’attività esterna e quella locale. Impostare `CrossProject` a `true` indica ad Aspose.Tasks che il collegamento attraversa due file di progetto diversi:

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

## Passo 7: visualizzare i risultati
Infine, stampa una semplice conferma così saprai che il processo è terminato senza eccezioni:

```java
System.out.println("Process completed Successfully");
```

## Perché collegare attività tra progetti?
Collegare attività tra progetti ti permette di:

- Mantenere gli elementi di lavoro dipendenti sincronizzati senza aggiornamenti manuali.  
- Ridurre la duplicazione di sforzi quando la stessa attività appare in più piani.  
- Fornire una fonte unica di verità per il monitoraggio delle milestone tra i team.  

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| Attività esterna non trovata | Verifica che il percorso `EXTERNAL_TASK_PROJECT` e `EXTERNAL_ID` siano corretti. |
| Tipo di collegamento non corrispondente | Assicurati che `TaskLinkType` corrisponda alla dipendenza desiderata (ad es., Fine‑a‑Inizio). |
| Eccezione di licenza | Installa una licenza valida di Aspose.Tasks prima di creare l’istanza di progetto. |

## Domande frequenti

**D: Posso collegare attività da più progetti esterni nello stesso task riepilogo?**  
R: Sì, è possibile collegare attività da diversi progetti esterni all’interno dello stesso task riepilogo, seguendo una procedura simile.

**D: Cosa succede se l’attività esterna nel progetto collegato viene modificata?**  
R: Qualsiasi modifica all’attività esterna verrà riflessa nell’attività collegata nel progetto corrente.

**D: È possibile creare collegamenti tra attività in formati di file diversi?**  
R: Sì, Aspose.Tasks per Java supporta il collegamento di attività tra progetti in vari formati di file.

**D: Posso scollegare le attività una volta collegate tra progetti?**  
R: Sì, è possibile scollegare le attività rimuovendo il collegamento tramite i metodi appropriati di Aspose.Tasks.

**D: Esistono limiti al numero di attività che possono essere collegate tra progetti?**  
R: Il numero di attività collegabili dipende dalle capacità e dalle limitazioni della tua licenza Aspose.Tasks.

## Conclusione
Ora sai **come collegare i progetti** e **come collegare attività tra progetti** usando Aspose.Tasks per Java. Creando collegamenti di attività cross‑project, abiliti una collaborazione più fluida, riduci lo sforzo di sincronizzazione manuale e mantieni i piani di progetto allineati. Sentiti libero di sperimentare con diversi tipi di collegamento ed esplorare ulteriori funzionalità di Aspose.Tasks per migliorare ulteriormente il tuo flusso di lavoro di gestione progetti.

---

**Ultimo aggiornamento:** 2026-01-20  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}