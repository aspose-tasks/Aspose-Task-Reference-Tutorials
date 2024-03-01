---
title: Leggere i dati rapportati alla scala cronologica per le risorse in Aspose.Tasks
linktitle: Leggere i dati rapportati alla scala cronologica per le risorse in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come estrarre i dati rapportati alla scala cronologica dalle risorse di MS Project utilizzando Aspose.Tasks per Java. Tutorial passo dopo passo.
type: docs
weight: 15
url: /it/java/resource-management/read-timephased-data/
---
## introduzione
In questo tutorial ti guideremo attraverso il processo di lettura dei dati rapportati alla scala cronologica per le risorse di MS Project utilizzando Aspose.Tasks per Java. Questa libreria fornisce potenti funzionalità per la gestione dei file di Microsoft Project a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. Puoi scaricarlo da[sito web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e seguire le istruzioni di installazione.
2.  Aspose.Tasks per Java Library: scarica la libreria Aspose.Tasks per Java da[pagina di download](https://releases.aspose.com/tasks/java/) e seguire le istruzioni di installazione fornite nella documentazione.

## Importa pacchetti
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Passaggio 1: configurare la directory dei dati
Innanzitutto, definisci la directory in cui si trova il tuo file MS Project.
```java
String dataDir = "Your Data Directory";
```
## Passaggio 2: leggere il file modello di MS Project
Specifica il nome del file modello di MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Passaggio 3: leggere il file di input come progetto
Leggere il file di input utilizzando Aspose.Tasks e caricarlo come oggetto progetto.
```java
Project project = new Project(dataDir + fileName);
```
## Passaggio 4: ottieni la risorsa in base all'ID
Recupera la risorsa desiderata dal progetto tramite il suo identificatore univoco (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Passaggio 5: stampare i dati rapportati alla scala cronologica per il lavoro sulle risorse
Stampare i dati rapportati alla scala cronologica per il lavoro delle risorse.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Passaggio 6: stampare i dati rapportati alla scala cronologica per il costo delle risorse
Stampare i dati rapportati alla scala cronologica per il costo delle risorse.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Conclusione
In questo tutorial, abbiamo imparato come leggere i dati rapportati alla scala cronologica per le risorse di MS Project utilizzando Aspose.Tasks per Java. Seguendo questi passaggi, puoi estrarre in modo efficiente informazioni preziose dai file di progetto a livello di codice.
## Domande frequenti
### Aspose.Tasks può gestire altri tipi di file di progetto oltre a Microsoft Project?
Sì, Aspose.Tasks supporta vari formati di file, inclusi MPP, XML e CSV.
### Aspose.Tasks è compatibile con diversi ambienti di sviluppo Java?
Sì, Aspose.Tasks è compatibile con tutti i principali IDE e framework Java.
### Posso manipolare i dati del progetto utilizzando Aspose.Tasks?
Assolutamente, Aspose.Tasks fornisce API estese per la creazione, la modifica e l'analisi dei dati del progetto.
### Aspose.Tasks è adatto a progetti di livello aziendale?
Sì, Aspose.Tasks è ampiamente utilizzato negli ambienti aziendali grazie alla sua affidabilità e scalabilità.
### Dove posso trovare supporto se riscontro problemi durante l'utilizzo di Aspose.Tasks?
 Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per l'assistenza da parte della comunità e del team di supporto.