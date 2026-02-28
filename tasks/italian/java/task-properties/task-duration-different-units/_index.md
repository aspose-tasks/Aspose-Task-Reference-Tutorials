---
date: 2026-02-28
description: Scopri come ottenere la durata in minuti, giorni, ore, settimane e mesi
  utilizzando Aspose.Tasks per Java. Guida dettagliata con esempi di codice.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come ottenere la durata in unità diverse con Aspose.Tasks
url: /it/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come Ottenere la Durata in Diverse Unità con Aspose.Tasks

## Introduzione
Comprendere **come ottenere la durata** delle attività è una parte fondamentale di qualsiasi flusso di lavoro di gestione dei progetti. Che tu abbia bisogno di minuti per un tracciamento dettagliato o di mesi per una pianificazione di alto livello, Aspose.Tasks per Java rende la conversione semplice. In questo tutorial ti guideremo nel recuperare la durata di un'attività in minuti, giorni, ore, settimane e mesi, spiegando perché ogni unità può essere utile nei progetti reali.

## Risposte Rapide
- **Cosa significa “how to get duration”?** È il processo di estrazione dell’intervallo di tempo di un'attività e della sua conversione nell'unità necessaria.  
- **Quale metodo API esegue la conversione?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **È necessaria una licenza per eseguire il codice?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso convertire in unità personalizzate?** È possibile concatenare conversioni o utilizzare `TimeSpan` per calcoli personalizzati.  
- **Il codice è compatibile con Java 17?** Sì, Aspose.Tasks supporta Java 8 e versioni successive.

## Cos'è “how to get duration” in Aspose.Tasks?
Aspose.Tasks memorizza la lunghezza di un'attività come oggetto `Duration`. Chiamando il metodo `convert` e specificando un `TimeUnitType` (Minute, Hour, Day, Week, Month), è possibile recuperare lo stesso valore sottostante espresso nell'unità desiderata. Questa flessibilità consente di generare report, eseguire calcoli o fornire dati ad altri sistemi senza operazioni matematiche manuali.

## Perché usare Aspose.Tasks per la conversione della durata?
- **Precisione:** Gestisce automaticamente le eccezioni del calendario, gli orari di lavoro e i calendari non standard.  
- **Prestazioni:** La conversione in una singola riga evita cicli o parsing personalizzati.  
- **Portabilità:** Funziona allo stesso modo su ambienti Windows, Linux e macOS.  
- **Integrazione:** Si integra perfettamente nelle applicazioni Java esistenti che già utilizzano Aspose.Tasks.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere:

- Java Development Kit (JDK) installato
- Libreria Aspose.Tasks per Java. Puoi scaricarla [qui](https://releases.aspose.com/tasks/java/)
- Una conoscenza di base della programmazione Java

## Importa Pacchetti
Nel tuo progetto Java, includi la libreria Aspose.Tasks. Aggiungi la seguente istruzione di importazione all'inizio del tuo codice:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Passo 1: Configura il Tuo Progetto
Crea un nuovo progetto Java nel tuo IDE preferito (IntelliJ, Eclipse, VS Code, ecc.) e aggiungi il JAR di Aspose.Tasks al classpath del progetto. Questo garantisce che le classi sopra siano disponibili al momento della compilazione.

## Passo 2: Leggi il Modello di Progetto
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

Sostituisci `"Your Document Directory"` con la cartella reale che contiene il tuo file di progetto `.xml` o `.mpp`.

## Passo 3: Recupera un'Attività
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

La chiamata `getById(1)` recupera l'attività il cui ID è 1. Modifica l'ID per puntare a un'attività diversa nel tuo file.

## Passo 4: Durata in Minuti – Come ottenere la durata in minuti?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

La variabile `mins` ora contiene la lunghezza dell'attività espressa in minuti.

## Passo 5: Durata in Giorni – Come ottenere la durata in giorni?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

Usa questo valore quando ti serve una granularità a livello di giorno per report o allocazione delle risorse.

## Passo 6: Durata in Ore – Come ottenere la durata in ore?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

Le ore sono utili per i fogli di presenza o quando vuoi suddividere una giornata in turni di lavoro.

## Passo 7: Durata in Settimane – Come ottenere la durata in settimane?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

Le settimane sono spesso usate nei diagrammi di Gantt di alto livello o nella pianificazione dei traguardi.

## Passo 8: Durata in Mesi – Come ottenere la durata in mesi?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

Le durate a livello di mese aiutano quando allinei le fasi del progetto con i periodi fiscali.

## Problemi Comuni e Soluzioni
| Sintomo | Causa Probabile | Soluzione |
|---------|-----------------|-----------|
| `NullPointerException` on `task` | ID attività errato o figli mancanti | Verifica che l'ID dell'attività esista usando `project.getRootTask().getChildren()` |
| Unexpected values (e.g., 0) | Il progetto utilizza un calendario personalizzato con giorni non lavorativi | Assicurati che il calendario del progetto sia definito correttamente o usa `project.getCalendar()` per ispezionarlo |
| Conversion returns fractional weeks | Le settimane sono calcolate in base alla durata predefinita della settimana del progetto (di solito 5 giorni) | Moltiplica per 5 se ti servono settimane di calendario, oppure regola le impostazioni del calendario |

## Domande Frequenti
### Q: Posso usare Aspose.Tasks per Java con qualsiasi IDE Java?
A: Sì, Aspose.Tasks per Java è compatibile con qualsiasi ambiente di sviluppo integrato (IDE) Java.

### Q: Come posso ottenere l'ID di un'attività in un file Microsoft Project?
A: Puoi ispezionare manualmente il file di progetto o chiamare `project.getRootTask().getChildren()` e iterare sulla collezione per leggere l'`ID` di ciascuna attività.

### Q: Aspose.Tasks è adatto per gestire progetti su larga scala?
A: Assolutamente. Aspose.Tasks è progettato per elaborare in modo efficiente progetti con migliaia di attività e risorse.

### Q: Dove posso trovare ulteriore documentazione?
A: Visita la [documentazione](https://reference.aspose.com/tasks/java/) per riferimenti API completi, esempi di codice e guide alle migliori pratiche.

### Q: Posso provare Aspose.Tasks per Java prima di acquistarlo?
A: Sì, puoi esplorare una [versione di prova gratuita](https://releases.aspose.com/) per valutare le sue funzionalità.

---

**Ultimo aggiornamento:** 2026-02-28  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}