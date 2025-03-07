---
title: Padroneggiare le proprietà delle attività in Aspose.Tasks
linktitle: Leggere e scrivere proprietà generali delle attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Esplora la potenza di Aspose.Tasks per Java nella gestione delle proprietà delle attività senza sforzo. Leggi e scrivi con facilità utilizzando la nostra guida passo passo.
weight: 26
url: /it/java/task-properties/read-write-general-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare le proprietà delle attività in Aspose.Tasks

## introduzione
Sblocca tutto il potenziale della gestione delle attività in Java con Aspose.Tasks. In questa guida completa, approfondiremo la lettura e la scrittura delle proprietà generali delle attività utilizzando Aspose.Tasks per Java. Che tu sia uno sviluppatore esperto o un principiante, questo tutorial ti fornirà le competenze per manipolare le proprietà delle attività senza sforzo.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Tasks per la libreria Java scaricata e configurata. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/tasks/java/).
- Un editor di codice come IntelliJ IDEA o Eclipse.
## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Questo passaggio garantisce l'accesso alle funzionalità Aspose.Tasks. Ecco uno snippet per guidarti:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Lettura delle proprietà generali delle attività
## Passaggio 1: crea un'attività
Inizia creando un'attività nel tuo progetto. Ciò comporta l'impostazione del nome dell'attività, della data di inizio e di altri dettagli rilevanti. Ecco un esempio:
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## Passaggio 2: leggere le proprietà dell'attività
Ora che hai creato un'attività, recuperiamo e visualizziamo le sue proprietà generali. Il seguente frammento di codice realizza ciò:
```java
// Lettura delle proprietà generali delle attività
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## Scrittura delle proprietà generali delle attività
## Passaggio 3: caricare il progetto e creare un raccoglitore
 Per scrivere proprietà generali, caricare un progetto esistente e impostare a`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## Passaggio 4: analisi e visualizzazione delle proprietà
Infine, analizza le attività raccolte e visualizza le loro proprietà:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
Congratulazioni! Hai letto e scritto con successo le proprietà generali delle attività utilizzando Aspose.Tasks per Java.
## Conclusione
In questo tutorial, abbiamo esplorato i passaggi fondamentali per manipolare le proprietà dell'attività senza problemi con Aspose.Tasks per Java. Padroneggiando queste tecniche, puoi migliorare le tue capacità di sviluppo Java e semplificare la gestione delle attività nei tuoi progetti.
## Domande frequenti
### Aspose.Tasks è compatibile con Java 11?
Sì, Aspose.Tasks è compatibile con Java 11 e versioni successive.
### Posso utilizzare Aspose.Tasks per progetti commerciali?
 Assolutamente! Aspose.Tasks è un potente strumento sia per progetti personali che commerciali. Visita[Qui](https://purchase.aspose.com/buy) per esplorare le opzioni di licenza.
### Come posso ottenere una licenza temporanea a scopo di test?
 Ottieni una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) per test e valutazioni.
### Dove posso trovare il supporto della community per Aspose.Tasks?
 Partecipa alla discussione della community su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assistenza e collaborazione.
### Sono disponibili progetti di esempio come riferimento?
 Esplora la sezione degli esempi della documentazione[Qui](https://reference.aspose.com/tasks/java/) per progetti di esempio e frammenti di codice.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
