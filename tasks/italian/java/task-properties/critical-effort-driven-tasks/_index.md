---
date: 2026-01-25
description: Scopri come utilizzare Aspose Tasks Java per la gestione delle attività,
  gestendo attività critiche e basate sullo sforzo nei tuoi progetti. Migliora i flussi
  di lavoro del progetto con questa guida.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – Gestisci attività critiche e basate sullo sforzo
url: /it/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java: Gestire attività critiche e basate sullo sforzo

Nella gestione moderna dei progetti, **aspose tasks java** ti offre la possibilità di identificare e controllare le attività critiche e basate sullo sforzo direttamente dal tuo codice Java. Che tu stia creando un pianificatore, uno strumento di reporting o una dashboard personalizzata, gestire correttamente queste proprietà delle attività può fare la differenza tra un progetto che rimane in carreggiata e uno che sfugge al controllo. In questo tutorial vedremo tutto ciò che devi sapere per lavorare con attività critiche e basate sullo sforzo usando Aspose Tasks Java.

## Risposte rapide
- **Cosa significa “critical”?** Un’attività il cui ritardo estenderà la data di fine del progetto.  
- **Cosa significa “effort‑driven”?** Un’attività che regola automaticamente la sua durata quando si modifica lo sforzo di lavoro.  
- **Quale libreria fornisce queste funzionalità?** Aspose Tasks Java.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per la valutazione; è richiesta una licenza per la produzione.  
- **Posso eseguirla su qualsiasi OS?** Sì – la libreria è indipendente dalla piattaforma (Windows, Linux, macOS).

## Cosa sono le attività critiche e basate sullo sforzo?
Le attività critiche sono quelle che fanno parte del percorso critico del progetto; qualsiasi slittamento influisce direttamente sul programma complessivo. Le attività basate sullo sforzo, invece, ricalcolano la loro durata in base alla quantità di lavoro assegnata, risultando ideali per risorse che possono fare straordinario o condividere lo sforzo tra più assegnazioni.

## Perché usare Aspose Tasks Java per questo?
- **API in stile .NET completa in Java** – Nessuna necessità di cambiare linguaggio.  
- **Alte prestazioni** – Funziona con file di progetto basati su XML di grandi dimensioni senza caricare l’intero file in memoria.  
- **Set di proprietà ricco** – Accesso a `IS_CRITICAL`, `IS_EFFORT_DRIVEN` e molte altre proprietà delle attività.  
- **Cross‑platform** – Esegui su qualsiasi ambiente compatibile con JVM.

## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:
- Libreria Aspose.Tasks per Java: scarica e installa la libreria dalla [documentazione di Aspose.Tasks per Java](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK): verifica di avere Java installato sul tuo sistema.
- Integrated Development Environment (IDE): utilizza il tuo IDE preferito per lo sviluppo Java.
- File di progetto: prepara un file di progetto in formato XML che userai per la dimostrazione.

## Importare i pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per sfruttare le funzionalità di Aspose.Tasks per Java:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### Passo 1: Raccogliere le attività con `ChildTasksCollector`
Crea un’istanza di `ChildTasksCollector` per raccogliere tutte le attività dall’attività radice usando `TaskUtils.apply`. Questo garantisce l’accesso a ogni attività all’interno del progetto.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Passo 2: Iterare sulle attività raccolte
Scorri tutte le attività raccolte con un ciclo `for`. Per ciascuna attività, determina se è basata sullo sforzo e critica, quindi stampa lo stato corrispondente.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

Seguendo questi passaggi, potrai gestire efficacemente le attività critiche e basate sullo sforzo nei tuoi progetti usando **aspose tasks java**.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| `NullPointerException` su `tsk.get(Tsk.IS_CRITICAL)` | L’attività non ha impostato la proprietà (ad es., un’attività riepilogativa). | Verifica `tsk.get(Tsk.TASK_TYPE)` prima di accedere al flag, oppure filtra le attività riepilogative. |
| File di progetto non trovato | Percorso `dataDir` errato o estensione del file mancante. | Usa `Paths.get(dataDir, "project.xml").toString()` e verifica che il file esista. |
| Licenza non applicata | La libreria è in modalità valutazione, limitando le funzionalità. | Carica il file di licenza con `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` prima di creare l’oggetto `Project`. |

## Domande frequenti
### D: Posso usare Aspose.Tasks per Java sia in ambienti Windows che Linux?
R: Sì, Aspose.Tasks per Java è indipendente dalla piattaforma e può essere utilizzato sia in ambienti Windows che Linux.

### D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?
R: Sì, puoi accedere a una versione di prova gratuita di Aspose.Tasks per Java [qui](https://releases.aspose.com/).

### D: Dove posso trovare supporto per Aspose.Tasks per Java?
R: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto della community e discussioni.

### D: Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?
R: Puoi acquisire una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### D: Dove posso acquistare Aspose.Tasks per Java?
R: Puoi acquistare Aspose.Tasks per Java dalla [pagina di acquisto](https://purchase.aspose.com/buy).

---

**Ultimo aggiornamento:** 2026-01-25  
**Testato con:** Aspose.Tasks Java 24.11 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}