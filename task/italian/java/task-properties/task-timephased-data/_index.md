---
title: Dati rapportati alla scala cronologica delle attività in Aspose.Tasks
linktitle: Dati rapportati alla scala cronologica delle attività in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Esplora Aspose.Tasks per Java e la gestione dei dati rapportati alla scala cronologica delle attività principali. Scarica la libreria, goditi una prova gratuita e semplifica il monitoraggio del tuo progetto.
type: docs
weight: 34
url: /it/java/task-properties/task-timephased-data/
---
## introduzione
Nell'ambito della gestione dei progetti, il monitoraggio preciso dei dati delle attività rapportati alla scala cronologica è fondamentale per un'esecuzione efficiente del progetto. Aspose.Tasks per Java emerge come un potente strumento per semplificare questo processo, offrendo funzionalità robuste e flessibilità. Questo tutorial ti guiderà attraverso l'utilizzo di Aspose.Tasks per Java per gestire in modo efficace i dati delle attività rapportati alla scala cronologica.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Ambiente di sviluppo Java: assicurati di avere Java installato sul tuo sistema.
-  Aspose.Tasks per Java Library: scarica e includi la libreria Aspose.Tasks nel tuo progetto. Puoi trovare la biblioteca[Qui](https://releases.aspose.com/tasks/java/).
- Directory dei documenti: imposta una directory per i documenti del tuo progetto.
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari per Aspose.Tasks:
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
## Passaggio 1: imposta la data di inizio del progetto
```java
Project project = new Project(dataDir + "project.xml");
// Codice aggiuntivo per le importazioni di pacchetti
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Spiegazione: Inizializzare un oggetto calendario, impostare la data di inizio e applicarla al progetto.
## Passaggio 2: definire attività e risorse
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Spiegazione: creare un'attività e una risorsa, impostando le tariffe per standard e straordinari.
## Passaggio 3: imposta la durata dell'attività
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Spiegazione: definire la durata dell'attività (ad esempio, 6 giorni).
## Passaggio 4: assegnare la risorsa all'attività
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Spiegazione: Assegnare la risorsa all'attività.
## Passaggio 5: configurare l'assegnazione delle risorse
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Spiegazione: impostare parametri quali interruzione, ripresa e distribuzione del lavoro per l'assegnazione delle risorse.
## Passaggio 6: impostare la linea di base
```java
project.setBaseline(BaselineType.Baseline);
```
Spiegazione: stabilire una linea di base per il progetto.
## Passaggio 7: aggiorna il completamento dell'attività
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Spiegazione: indicare la percentuale di completamento dell'attività.
## Passaggio 8: recuperare i dati rapportati alla scala cronologica
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Spiegazione: Recuperare i dati rapportati alla scala cronologica per il lavoro rimanente dell'assegnazione.
## Passaggio 9: visualizzare i dati rapportati alla scala cronologica
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Codice aggiuntivo per visualizzare altri valori
```
Spiegazione: Emette e visualizza i dati rapportati alla scala cronologica.
## Conclusione
La gestione efficace dei dati delle attività rapportati alla scala cronologica è indispensabile per il successo del progetto. Aspose.Tasks per Java semplifica questo processo, fornendo un set completo di funzionalità. Seguendo questo tutorial, puoi integrare perfettamente Aspose.Tasks nel tuo progetto Java, garantendo un controllo preciso sulle tempistiche del progetto e sull'allocazione delle risorse.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per Java in qualsiasi progetto Java?
R: Sì, Aspose.Tasks per Java è compatibile con qualsiasi progetto basato su Java.
### D: Dove posso trovare ulteriore supporto per Aspose.Tasks per Java?
 R: Visita il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto e discussioni.
### D: È disponibile una prova gratuita per Aspose.Tasks per Java?
 R: Sì, puoi provare una prova gratuita[Qui](https://releases.aspose.com/).
### D: Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?
 R: Puoi acquisire una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso acquistare Aspose.Tasks per Java?
 R: È possibile acquistare Aspose.Tasks per Java[Qui](https://purchase.aspose.com/buy).