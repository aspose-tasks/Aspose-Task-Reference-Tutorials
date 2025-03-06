---
title: Interrompere e riprendere le assegnazioni di risorse in Aspose.Tasks
linktitle: Interrompere e riprendere le assegnazioni di risorse in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come gestire le assegnazioni delle risorse in modo efficace in Aspose.Tasks per Java con questo tutorial passo passo.
weight: 23
url: /it/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Interrompere e riprendere le assegnazioni di risorse in Aspose.Tasks

## introduzione
In questo tutorial impareremo come interrompere e riprendere le assegnazioni di risorse utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente API Java che consente agli sviluppatori di lavorare con file Microsoft Project senza che Microsoft Project sia installato sui propri sistemi. Suddivideremo il processo in passaggi gestibili per renderlo facile da seguire.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Tasks per la libreria Java scaricata. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
- Conoscenza di base della programmazione Java.
## Importa pacchetti
Innanzitutto, importiamo i pacchetti necessari nel nostro progetto Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Passaggio 1: caricare il file di progetto
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
// Carica il file di progetto
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 In questo passaggio, carichiamo il file di progetto in un file`Project` oggetto utilizzando il percorso del file.
## Passaggio 2: ripetere le assegnazioni delle risorse
```java
// Definire la data minima
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Scorrere le assegnazioni delle risorse
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Qui definiamo una data minima e iniziamo a scorrere ciascuna assegnazione di risorse nel progetto.
## Passaggio 3: controlla le date di fine e di ripresa
```java
    // Controlla la data di fine
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Controlla la data del curriculum
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
In questo passaggio controlliamo se le date di interruzione e di ripresa di ciascuna assegnazione di risorse sono precedenti alla data minima. Se lo sono, stampiamo "NA", altrimenti stampiamo le rispettive date.
## Conclusione
In questo tutorial, abbiamo imparato come interrompere e riprendere le assegnazioni di risorse in Aspose.Tasks per Java. Seguendo i passaggi forniti, puoi facilmente implementare questa funzionalità nei tuoi progetti Java.

## Domande frequenti
### Posso utilizzare Aspose.Tasks senza Microsoft Project installato?
Sì, Aspose.Tasks ti consente di lavorare con i file di Microsoft Project senza che sia necessario che Microsoft Project sia installato sul tuo sistema.
### Dove posso trovare ulteriore documentazione?
 Puoi trovare documentazione dettagliata[Qui](https://reference.aspose.com/tasks/java/).
### È disponibile una prova gratuita?
 Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto in caso di problemi?
Puoi ottenere supporto dalla comunità[Qui](https://forum.aspose.com/c/tasks/15).
### Posso acquistare una licenza temporanea?
 Sì, puoi acquistare una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
