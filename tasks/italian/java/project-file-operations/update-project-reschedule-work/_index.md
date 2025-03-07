---
title: Aggiorna e riprogramma MS Project in Aspose.Tasks
linktitle: Aggiorna il progetto e riprogramma il lavoro non completato in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come aggiornare e riprogrammare i file MS Project a livello di codice utilizzando Aspose.Tasks per Java.
weight: 23
url: /it/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiorna e riprogramma MS Project in Aspose.Tasks

## introduzione
Microsoft Project è un software di gestione dei progetti ampiamente utilizzato che consente agli utenti di gestire attività, risorse e tempistiche in modo efficiente. Aspose.Tasks per Java fornisce un potente set di API per manipolare i file di Microsoft Project a livello di codice. In questo tutorial impareremo come aggiornare i file di MS Project e riprogrammare il lavoro non completato utilizzando Aspose.Tasks per Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Conoscenza di base del linguaggio di programmazione Java.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari nel tuo codice Java:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Passaggio 1: impostare il progetto
Inizializza un nuovo oggetto Progetto e definisci le attività al suo interno insieme alle relative durate e dipendenze.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Definire le attività e la loro durata
// ...
// Definire le dipendenze delle attività
// ...
// Salva lo stato iniziale del progetto
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Passaggio 2: aggiornare il lavoro del progetto
Aggiorna il lavoro del progetto per contrassegnarlo come completato fino a una determinata data.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Salvare il progetto aggiornato
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Passaggio 3: riprogrammare il lavoro non completato
Riprogrammare qualsiasi lavoro non completato per iniziare dopo una data specificata.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Salvare il progetto riprogrammato
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusione
In questo tutorial, abbiamo imparato come aggiornare i file di MS Project e riprogrammare il lavoro non completato utilizzando Aspose.Tasks per Java. Ciò può essere particolarmente utile negli scenari in cui le tempistiche del progetto necessitano di aggiustamenti in base ai progressi o al cambiamento delle priorità.

## Domande frequenti
### D: Aspose.Tasks per Java può gestire strutture di progetto complesse?
R: Sì, Aspose.Tasks per Java fornisce API robuste per gestire attività, dipendenze, risorse e altri elementi del progetto in modo efficiente.
### D: È disponibile una versione di prova per Aspose.Tasks per Java?
 R: Sì, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.Tasks per Java?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.
### D: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
 R: Sì, è possibile acquistare licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks per Java?
 R: Puoi fare riferimento alla documentazione[Qui](https://reference.aspose.com/tasks/java/) per guide complete e riferimenti API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
