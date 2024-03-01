---
title: Scrivi i dati delle risorse aggiornati in Aspose.Tasks
linktitle: Scrivi i dati delle risorse aggiornati in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come aggiornare facilmente i dati delle risorse nei file MS Project utilizzando Aspose.Tasks per Java.
type: docs
weight: 21
url: /it/java/resource-management/write-updated-resource-data/
---
## introduzione
In questo tutorial ti guideremo attraverso l'aggiornamento dei dati delle risorse di Microsoft Project utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente API Java che ti consente di manipolare i file di Microsoft Project senza richiedere l'installazione di Microsoft Project sul tuo sistema.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Conoscenza base della programmazione Java.

## Importa pacchetti

Innanzitutto, devi importare i pacchetti necessari per lavorare con Aspose.Tasks nel tuo codice Java. Aggiungi le seguenti istruzioni di importazione al tuo file Java:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Passaggio 1: configura la directory dei dati

Definisci la directory in cui si trovano i file di dati:

```java
String dataDir = "Your Data Directory";
```

## Passaggio 2: specificare i file di input e di output

Definire i percorsi per il file MS Project di input e il file aggiornato risultante:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // File di prova con un RSC da aggiornare
String resultFile = dataDir + "OutputMPP.mpp"; // File per scrivere il progetto di prova
```

## Passaggio 3: caricare il progetto

 Caricare il file MS Project in un file`Project` oggetto:

```java
Project project = new Project(file);
```

## Passaggio 4: aggiungi una risorsa e imposta gli attributi

Aggiungi una nuova risorsa al progetto e imposta i suoi attributi come tariffa standard, tariffa per gli straordinari e gruppo:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Passaggio 5: salva il progetto

Salva il progetto aggiornato con i dati della risorsa modificata:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusione

In questo tutorial, abbiamo dimostrato come aggiornare i dati delle risorse di MS Project utilizzando Aspose.Tasks per Java. Seguendo questi passaggi, puoi manipolare in modo efficiente le informazioni sulle risorse nei file MS Project a livello di codice.

## Domande frequenti

### Q1: posso aggiornare più risorse nello stesso progetto utilizzando Aspose.Tasks per Java?

R1: Sì, puoi aggiornare più risorse scorrendole e impostandone gli attributi di conseguenza.

### Q2: Aspose.Tasks supporta altri formati di file oltre a MS Project?

A2: Sì, Aspose.Tasks supporta vari formati di file tra cui XML, MPP e altro.

### Q3: Aspose.Tasks è compatibile con diverse versioni di Java?

A3: Aspose.Tasks è compatibile con le versioni Java 6 e successive.

### Q4: Posso eseguire altre operazioni sui file MS Project con Aspose.Tasks?

R4: Sì, puoi eseguire un'ampia gamma di operazioni come leggere, scrivere e manipolare attività, risorse e calendari.

### Q5: Dove posso trovare ulteriore aiuto o supporto per Aspose.Tasks?

 A5: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.
