---
date: 2026-02-28
description: Scopri come utilizzare Aspose.Tasks per Java per gestire i dati temporizzati
  delle attività, scarica la libreria, provala gratuitamente e semplifica il monitoraggio
  dei progetti.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come utilizzare Aspose.Tasks per gestire i dati temporizzati delle attività
  (Java)
url: /it/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare Aspose.Tasks per i dati temporizzati delle attività

## Introduzione
Se stai cercando **come usare Aspose** per tenere sotto controllo il tuo programma di progetto, sei nel posto giusto. Il tracciamento preciso dei dati temporizzati delle attività è una pietra angolare della gestione di progetto di successo, e Aspose.Tasks for Java ti fornisce gli strumenti necessari per automatizzare questo processo. In questo tutorial percorreremo un esempio completo, end‑to‑end, che ti mostra come utilizzare Aspose.Tasks per creare un progetto, assegnare risorse, impostare baseline e infine recuperare e visualizzare i dati temporizzati.

## Risposte rapide
- **Cosa significa “timephased data”?** Sono dati suddivisi per intervalli di tempo (giorni, settimane, mesi) che mostrano lavoro, costo o lavoro rimanente lungo la timeline del progetto.  
- **Quale libreria fornisce questa funzionalità?** Aspose.Tasks for Java.  
- **È necessaria una licenza per eseguire il campione?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o superiore.  
- **Posso esportare i risultati in Excel?** Sì – puoi iterare la collezione `TimephasedData` e scrivere i valori in qualsiasi formato ti serva.

## Che cos'è il dato temporizzato delle attività?
I dati temporizzati delle attività rappresentano la quantità di lavoro (o costo) programmata per un'attività durante ogni intervallo di tempo del calendario del progetto. Consentono di vedere come il lavoro è distribuito, individuare il sovraccarico e confrontare il progresso pianificato rispetto a quello reale.

## Perché usare Aspose.Tasks per gestire i dati temporizzati?
- **Controllo totale** – crea, modifica e interroga programmaticamente le informazioni temporizzate senza aprire Microsoft Project.  
- **Cross‑platform** – funziona su qualsiasi OS che supporta Java.  
- **Nessuna dipendenza COM** – ideale per l'automazione lato server.  
- **API ricca** – supporta baseline, contorni di lavoro e campi personalizzati fin da subito.

## Prerequisiti
- **Ambiente di sviluppo Java** – JDK 8+ installato e `JAVA_HOME` configurato.  
- **Libreria Aspose.Tasks for Java** – Scarica e includi la libreria Aspose.Tasks nel tuo progetto. Puoi trovare la libreria [qui](https://releases.aspose.com/tasks/java/).  
- **Directory dei documenti** – Una cartella sul tuo computer dove il file di progetto di esempio (`project.xml`) sarà letto e scritto.

## Importa pacchetti
Nel tuo progetto Java, importa le classi Aspose.Tasks necessarie:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Passo 1: Imposta la data di inizio del progetto
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Spiegazione:* Creiamo un'istanza `Project`, inizializziamo un `Calendar` alla data di inizio desiderata e lo assegniamo alla proprietà `START_DATE` del progetto.

## Passo 2: Definisci attività e risorsa
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Spiegazione:* Viene aggiunta una nuova attività chiamata **Task** sotto l'attività radice. Creiamo anche una risorsa chiamata **Rsc** e impostiamo le sue tariffe standard e di straordinario.

## Passo 3: Imposta la durata dell'attività
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Spiegazione:* L'attività è programmata per una durata di **6 giorni**.

## Passo 4: Assegna la risorsa all'attività
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Spiegazione:* La risorsa definita in precedenza è collegata all'attività tramite un `ResourceAssignment`.

## Passo 5: Configura l'assegnazione della risorsa
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Spiegazione:* Impostiamo le date di stop e resume dell'assegnazione (usando un valore segnaposto) e applichiamo un contorno di lavoro **Back‑Loaded**, che sposta più lavoro verso la fine dell'assegnazione.

## Passo 6: Imposta la baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Spiegazione:* Catturare una baseline ti consente di confrontare i valori pianificati rispetto a quelli reali in seguito.

## Passo 7: Aggiorna il completamento dell'attività
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Spiegazione:* L'attività è contrassegnata come **50 % completata**, il che influenzerà i calcoli del lavoro rimanente.

## Passo 8: Recupera i dati temporizzati
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Spiegazione:* Questa chiamata recupera il **lavoro rimanente** per l'assegnazione, suddiviso per gli intervalli di tempo del progetto.

## Passo 9: Visualizza i dati temporizzati
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Spiegazione:* Stampiamo semplicemente il numero di voci temporizzate e il valore della prima voce. In uno scenario reale itereresti l'elenco ed esporteresti i dati in un report o interfaccia utente.

## Problemi comuni e soluzioni
- **NullPointerException su `getTimephasedData`** – Assicurati che le date `START` e `FINISH` dell'assegnazione siano impostate prima di chiamare il metodo.  
- **Contorno di lavoro errato** – Verifica che il `WorkContourType` scelto corrisponda alla tua strategia di pianificazione; `BackLoaded` è solo una delle varie opzioni.  
- **La baseline non riflette le modifiche** – Ricorda di chiamare `project.setBaseline` *dopo* aver definito attività, risorse e assegnazioni.

## Domande frequenti
### Q: Posso usare Aspose.Tasks for Java in qualsiasi progetto Java?
A: Sì, Aspose.Tasks for Java è compatibile con qualsiasi progetto basato su Java.

### Q: Dove posso trovare supporto aggiuntivo per Aspose.Tasks for Java?
A: Visita il [Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto e discussioni.

### Q: È disponibile una versione di prova gratuita per Aspose.Tasks for Java?
A: Sì, puoi provare una versione di prova gratuita [qui](https://releases.aspose.com/).

### Q: Come posso ottenere una licenza temporanea per Aspose.Tasks for Java?
A: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Q: Dove posso acquistare Aspose.Tasks for Java?
A: Puoi acquistare Aspose.Tasks for Java [qui](https://purchase.aspose.com/buy).

---

**Ultimo aggiornamento:** 2026-02-28  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}