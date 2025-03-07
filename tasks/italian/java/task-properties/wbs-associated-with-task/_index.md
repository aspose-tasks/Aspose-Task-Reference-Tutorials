---
title: WBS associato all'attività in Aspose.Tasks
linktitle: WBS associato all'attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Padroneggia la WBS con Aspose.Tasks per Java impara a leggere e rinumerare i codici WBS delle attività. Aumenta l'efficienza della gestione dei progetti!
weight: 36
url: /it/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS associato all'attività in Aspose.Tasks

## introduzione
Benvenuti nel mondo della gestione dei progetti con Aspose.Tasks per Java! In questo tutorial, approfondiremo le complessità della Work Breakdown Structure (WBS) associata alle attività utilizzando Aspose.Tasks per Java. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida ti aiuterà a esplorare gli elementi essenziali per gestire i codici WBS in modo efficiente.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo computer.
-  Aspose.Tasks per la libreria Java scaricata e aggiunta al tuo progetto. Puoi ottenerlo da[Qui](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
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
Iniziamo leggendo i codici WBS associati alle attività. Segui questi passi:
## Passaggio 1: caricare il progetto
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Passaggio 2: raccogli attività
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Passaggio 3: analizza e personalizza
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Questo frammento legge e personalizza i codici WBS associati alle attività nel tuo progetto.
## Rinumera i codici WBS delle attività
Esploriamo ora la rinumerazione dei codici WBS per le attività:
## Passaggio 1: caricare il progetto
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Passaggio 2: seleziona Tutte le attività
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Passaggio 3: output dei codici WBS iniziali
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Passaggio 4: rinumerare i codici WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Passaggio 5: output dei codici WBS aggiornati
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Seguendo questi passaggi, rinumererai in modo efficace i codici WBS per le attività nel tuo progetto.
## Conclusione
Congratulazioni! Hai imparato con successo come lavorare con i codici WBS utilizzando Aspose.Tasks per Java. Questa conoscenza ti consentirà di gestire e personalizzare in modo efficiente la gerarchia delle attività del tuo progetto.
## Domande frequenti
### D: Dove posso trovare la documentazione per Aspose.Tasks per Java?
 R: La documentazione è disponibile[Qui](https://reference.aspose.com/tasks/java/).
### D: Come posso scaricare Aspose.Tasks per Java?
 R: Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/java/).
### D: È disponibile una prova gratuita per Aspose.Tasks per Java?
 R: Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).
### D: Dove posso ottenere supporto per Aspose.Tasks per Java?
 R: Visita il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto.
### D: Posso ottenere una licenza temporanea per Aspose.Tasks per Java?
 R: Sì, ottieni una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
