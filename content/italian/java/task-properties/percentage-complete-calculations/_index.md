---
title: Calcoli percentuali di completamento per le attività in Aspose.Tasks
linktitle: Calcoli percentuali di completamento per le attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Esplora Aspose.Tasks per Java e semplifica il monitoraggio dell'avanzamento del progetto. Calcola facilmente le percentuali delle attività per una gestione efficiente dei progetti.
type: docs
weight: 25
url: /it/java/task-properties/percentage-complete-calculations/
---
## introduzione
Benvenuti nella nostra guida approfondita sulla padronanza dei calcoli della percentuale delle attività utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente libreria Java progettata per lavorare con file Microsoft Project, offrendo un robusto set di funzionalità per la gestione dei progetti. In questo tutorial ci concentreremo sui calcoli della percentuale di completamento, fornendoti le conoscenze per monitorare e analizzare in modo efficace l'avanzamento del progetto.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
- Ambiente di sviluppo Java: assicurati di avere Java installato sul tuo sistema.
-  Libreria Aspose.Tasks: scarica la libreria Aspose.Tasks per Java da[questo link](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
Iniziamo importando i pacchetti necessari per il tuo progetto Aspose.Tasks per Java. Includi il seguente snippet di codice nel tuo progetto:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Ora analizziamo ogni passaggio con spiegazioni dettagliate.
## Passaggio 1: importazione dei pacchetti
Nel primo passaggio, importiamo i pacchetti necessari per configurare il nostro progetto Aspose.Tasks.
## Passaggio 2: impostazione della directory dei documenti
 Definisci il percorso della directory dei documenti utilizzando il file`dataDir`variabile. Assicurati che il file Microsoft Project, come "Software Development.mpp", sia in questa directory.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
```
## Passaggio 3: caricamento del progetto
 Inizializzarne uno nuovo`Project` oggetto e caricare il file Microsoft Project nell'istanza del progetto.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Passaggio 4: recupero della raccolta attività
 Ottieni l'attività root del progetto e recupera i suoi figli come raccolta utilizzando`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Passo 5: Percentuale di stampa completata
Scorrere ciascuna attività nella raccolta e stampare Percentuale di completamento, Percentuale di lavoro completata e Percentuale fisica di completamento.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Ripeti questi passaggi per ogni attività del tuo progetto per ottenere informazioni dettagliate sullo stato di avanzamento di ciascuna.
## Conclusione
Congratulazioni! Hai padroneggiato con successo i calcoli della percentuale delle attività utilizzando Aspose.Tasks per Java. Questa potente libreria consente agli sviluppatori di gestire e analizzare l'avanzamento del progetto in modo efficiente.
## Domande frequenti
### D: Dove posso trovare la documentazione di Aspose.Tasks?
 La documentazione è disponibile[Qui](https://reference.aspose.com/tasks/java/).
### D: Come posso scaricare la libreria Aspose.Tasks per Java?
 Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/java/).
### D: È disponibile una prova gratuita?
Sì, puoi accedere a una prova gratuita[Qui](https://releases.aspose.com/).
### D: Dove posso ottenere supporto per Aspose.Tasks?
 Visita il forum di supporto[Qui](https://forum.aspose.com/c/tasks/15).
### D: Come posso ottenere una licenza temporanea?
 È possibile acquisire una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).