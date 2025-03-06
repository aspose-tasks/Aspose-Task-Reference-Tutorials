---
title: Gestire le proprietà del ritardo di livellamento in Aspose.Tasks
linktitle: Gestire le proprietà del ritardo di livellamento per le assegnazioni di risorse in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come gestire le proprietà di ritardo del livellamento per le assegnazioni di risorse in Aspose.Tasks per Java con questo tutorial completo.
weight: 17
url: /it/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestire le proprietà del ritardo di livellamento in Aspose.Tasks

## introduzione
In questo tutorial, esamineremo il processo di gestione delle proprietà di ritardo del livellamento per le assegnazioni di risorse in Aspose.Tasks per Java. Aspose.Tasks è una potente libreria Java che ti consente di lavorare con i file di Microsoft Project senza richiedere l'installazione di Microsoft Project sul tuo sistema.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere Java JDK installato sul tuo sistema. È possibile scaricarlo e installarlo da[sito web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks per Java Library: scarica la libreria Aspose.Tasks per Java da[pagina di download](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari nel tuo progetto Java per utilizzare le funzionalità Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Passaggio 1: crea un oggetto di progetto
 Istanziare a`Project` oggetto:
```java
Project prj = new Project();
```
## Passaggio 2: crea un'attività
Aggiungi un'attività al progetto:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Passaggio 3: impostare la data di inizio e la durata dell'attività
Imposta la data di inizio e la durata dell'attività:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Passaggio 4: aggiungi una risorsa
Aggiungi una risorsa al progetto:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Passaggio 5: creare un'assegnazione di risorse
Creare un'assegnazione di risorse per l'attività e la risorsa:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Passaggio 6: impostare il ritardo di livellamento
Imposta il ritardo di livellamento per l'incarico:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Passaggio 7: visualizzare i risultati
Stampa il ritardo di livellamento e altre informazioni rilevanti:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Conclusione
In questo tutorial, abbiamo imparato come gestire le proprietà di ritardo del livellamento per le assegnazioni di risorse in Aspose.Tasks per Java. Seguendo questi passaggi, puoi gestire in modo efficiente le assegnazioni delle risorse nei tuoi progetti Java.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks con altre librerie Java?

R: Sì, Aspose.Tasks può essere integrato con altre librerie Java per migliorare le capacità di gestione dei progetti.

### D: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?

R: Sì, Aspose.Tasks supporta varie versioni dei file Microsoft Project, garantendo la compatibilità tra diversi ambienti.

### D: Dove posso trovare ulteriore supporto per Aspose.Tasks?

 R: Puoi trovare supporto e risorse su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### D: Posso provare Aspose.Tasks prima dell'acquisto?

 R: Sì, puoi ottenere una prova gratuita di Aspose.Tasks da[pagina delle uscite](https://releases.aspose.com/).

### D: Come posso ottenere una licenza temporanea per Aspose.Tasks?

 R: Puoi richiedere una licenza temporanea al[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/) a fini di valutazione.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
