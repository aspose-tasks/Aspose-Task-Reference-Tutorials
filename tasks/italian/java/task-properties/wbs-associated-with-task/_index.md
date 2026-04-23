---
date: 2026-03-03
description: Impara a rinumerare il WBS in Aspose.Tasks per Java, gestire la scomposizione
  del lavoro e personalizzare i codici WBS in modo efficiente con esempi passo‑passo.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come rinumerare il WBS in Aspose.Tasks per Java
url: /it/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come rinumerare WBS in Aspose.Tasks per Java

## Introduzione
Se hai bisogno di **come rinumerare WBS** in un file Microsoft Project usando Aspose.Tasks per Java, sei nel posto giusto. Questo tutorial ti guida attraverso la lettura dei codici WBS esistenti, la loro personalizzazione e poi la rinumerazione della gerarchia affinché il tuo progetto rimanga organizzato. Che tu stia pulendo un programma legacy o ne stia creando uno nuovo da zero, padroneggiare questi passaggi ti aiuterà a **gestire le strutture di scomposizione del lavoro** con fiducia.

## Risposte rapide
- **Cosa fa la rinumerazione del WBS?** Ricalcola la numerazione gerarchica delle attività per riflettere eventuali modifiche strutturali.  
- **Quale classe esegue la rinumerazione?** `Project.renumberWBSCode`.  
- **È necessaria una licenza per eseguire il codice?** È richiesta una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso personalizzare il formato WBS?** Sì—usa `Task.set(Tsk.WBS, "...")` per assegnare qualsiasi stringa desideri.  
- **Quali sono i prerequisiti principali?** Java JDK, la libreria Aspose.Tasks per Java e un file di progetto valido (.mpp).

## Che cos'è una Work Breakdown Structure (WBS)?
Una Work Breakdown Structure (WBS) è una rappresentazione gerarchica dei deliverable e delle attività di un progetto. Ogni attività riceve un codice (ad es., 1.2.3) che riflette la sua posizione nella gerarchia. La rinumerazione diventa essenziale quando le attività vengono aggiunte, rimosse o riordinate, garantendo che i codici rimangano logici e facili da leggere.

## Perché gestire la scomposizione del lavoro e personalizzare i codici WBS?
- **Chiarezza:** Codici WBS chiari facilitano gli stakeholder nell'individuare le attività.  
- **Reporting:** Molti strumenti di reporting si basano su una numerazione coerente.  
- **Flessibilità:** Codici personalizzati ti permettono di allineare la struttura del progetto agli standard interni.  

## Prerequisiti
Prima di immergerci nel codice, verifica di avere quanto segue:

- Java Development Kit (JDK) installato sulla tua macchina.  
- Libreria Aspose.Tasks per Java aggiunta al tuo progetto. Puoi ottenerla da [qui](https://releases.aspose.com/tasks/java/).  

## Importa i pacchetti
Assicurati di importare i pacchetti necessari per avviare il tuo progetto:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Leggi i codici WBS
Innanzitutto, leggeremo i codici WBS esistenti così potrai vedere con cosa stai lavorando.

### Passo 1: Carica il progetto
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Passo 2: Raccogli le attività
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Passo 3: Analizza e personalizza
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Il frammento sopra stampa il WBS corrente e il livello di ogni attività, quindi dimostra **personalizzare i codici wbs** assegnando una nuova stringa.

## Rinumerare i codici WBS delle attività
Ora rinumereremo effettivamente la gerarchia WBS.

### Passo 1: Carica il progetto (esempio di rinumerazione)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Passo 2: Seleziona tutte le attività
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Passo 3: Stampa i codici WBS iniziali
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Passo 4: Rinumerare i codici WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Passo 5: Stampa i codici WBS aggiornati
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Seguendo questi passaggi, potrai efficacemente **come rinumerare wbs** per qualsiasi insieme di attività nel tuo file di progetto.

## Problemi comuni e soluzioni
- **WBS non cambia dopo la chiamata `set`:** Assicurati di lavorare sull'istanza corretta dell'attività e che il progetto sia salvato dopo le modifiche.  
- **`renumberWBSCode` genera un'eccezione:** Verifica che l'elenco di ID corrisponda al numero di attività di livello superiore; altrimenti il metodo non può mappare correttamente i nuovi numeri.  
- **Valori WBS mancanti:** Alcune attività potrebbero avere un WBS `null` se sono state importate da un file che non ne definiva uno. Usa un valore di fallback prima di stampare.

## Domande frequenti

**Q: Dove posso trovare la documentazione per Aspose.Tasks per Java?**  
A: La documentazione è disponibile [qui](https://reference.aspose.com/tasks/java/).

**Q: Come posso scaricare Aspose.Tasks per Java?**  
A: Puoi scaricarlo [qui](https://releases.aspose.com/tasks/java/).

**Q: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?**  
A: Sì, puoi ottenere una prova gratuita [qui](https://releases.aspose.com/).

**Q: Dove posso ottenere supporto per Aspose.Tasks per Java?**  
A: Visita il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto.

**Q: Posso ottenere una licenza temporanea per Aspose.Tasks per Java?**  
A: Sì, ottieni una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**Q: Posso rinominare il formato WBS dopo la rinumerazione?**  
A: Assolutamente. Dopo aver chiamato `renumberWBSCode`, puoi iterare sulle attività e applicare `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` per adattarlo alle tue convenzioni di denominazione.

**Q: La rinumerazione influisce sulle dipendenze delle attività?**  
A: No. Il metodo aggiorna solo la stringa WBS; i collegamenti e i vincoli delle attività rimangono invariati.

**Ultimo aggiornamento:** 2026-03-03  
**Testato con:** Aspose.Tasks for Java 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}