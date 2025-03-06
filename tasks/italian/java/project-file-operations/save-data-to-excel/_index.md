---
title: Salva i dati di MS Project in Excel in Aspose.Tasks
linktitle: Salvare i dati in Excel in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come salvare i dati di Microsoft Project in file Excel utilizzando Aspose.Tasks per Java. Facile integrazione per gli sviluppatori Java.
weight: 19
url: /it/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva i dati di MS Project in Excel in Aspose.Tasks

## introduzione
Aspose.Tasks per Java è una potente libreria che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice. In questo tutorial, ti guideremo passo dopo passo attraverso il processo di salvataggio dei dati da un file di progetto a un file Excel.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema. È possibile scaricare e installare la versione più recente di JDK dal sito Web Oracle.
2.  Aspose.Tasks per Java Library: scarica la libreria Aspose.Tasks per Java da[Link per scaricare](https://releases.aspose.com/tasks/java/) e includilo nel tuo progetto Java.

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari nel tuo codice Java per lavorare con Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Suddividiamo l'esempio fornito in più passaggi:
## Passaggio 1: definire il percorso della directory dei dati
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"`con il percorso della directory dei dati in cui si trova il file di progetto.
## Passaggio 2: caricare il file di progetto
```java
Project project = new Project(dataDir + "project5.mpp");
```
Questa riga di codice carica il file di progetto denominato "project5.mpp" dalla directory dei dati specificata.
## Passaggio 3: salva il progetto come XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Ecco, il`save` viene utilizzato per salvare il file di progetto caricato come file Excel con il nome "project1.xlsx" nella stessa directory dei dati. Precisiamo il`SaveFileFormat.Xlsx` parametro per salvarlo in formato XLSX.

## Conclusione
In questo tutorial, abbiamo imparato come salvare i dati da un file Microsoft Project in un file Excel utilizzando Aspose.Tasks per Java. Seguendo i passaggi forniti, puoi integrare perfettamente questa funzionalità nelle tue applicazioni Java.
## Domande frequenti
### Posso utilizzare Aspose.Tasks per Java per manipolare i dati del progetto a livello di codice?
Sì, Aspose.Tasks per Java fornisce funzionalità estese per manipolare i dati di progetto, inclusa la lettura, la scrittura e la modifica dei file di progetto.
### È disponibile una prova gratuita per Aspose.Tasks per Java?
 Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per Java da[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Tasks per Java?
È possibile trovare la documentazione per Aspose.Tasks per Java[Qui](https://reference.aspose.com/tasks/java/).
### Come posso ottenere supporto per eventuali problemi o domande relative a Aspose.Tasks per Java?
 È possibile ottenere supporto visitando il forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
### Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
 Sì, puoi acquistare una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
