---
title: Lettura e scrittura della scala di velocità per le assegnazioni di risorse in Aspose.Tasks
linktitle: Lettura e scrittura della scala di velocità per le assegnazioni di risorse in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come gestire la scala tariffaria delle assegnazioni delle risorse in modo efficace in Aspose.Tasks per Java con questo tutorial completo.
type: docs
weight: 20
url: /it/java/resource-assignments/read-write-rate-scale/
---
## introduzione
In questo tutorial, approfondiremo la gestione della scala delle tariffe di assegnazione delle risorse utilizzando Aspose.Tasks per Java, una solida libreria per lavorare con i file di Microsoft Project a livello di codice. Seguendo questi passaggi sarai in grado di manipolare in modo efficace le impostazioni della scala tariffaria per le assegnazioni delle risorse nelle tue applicazioni Java.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Ambiente di sviluppo Java: assicurati di avere Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per Java Library: scarica e installa la libreria Aspose.Tasks per Java da[Qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari per lavorare con le funzionalità Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Passaggio 1: imposta il tuo progetto
Inizia configurando il tuo progetto Java e includi la libreria Aspose.Tasks nelle tue dipendenze.
## Passaggio 2: caricare il file di progetto
Carica il file di progetto con cui vuoi lavorare nella tua applicazione Java.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Passaggio 3: aggiungi un'attività
Aggiungi una nuova attività al tuo progetto.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Passaggio 4: definire le risorse
Definire le risorse materiali e non materiali e specificarne le tipologie.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Passaggio 5: assegnare le risorse all'attività
Assegnare le risorse definite in precedenza all'attività insieme ai relativi tipi di scala tariffaria.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Passaggio 6: salva il progetto
Salvare il progetto con le assegnazioni di risorse modificate.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Passaggio 7: recuperare le assegnazioni di risorse
Ricaricare il progetto salvato e recuperare le assegnazioni delle risorse per verificare le impostazioni della scala tariffaria.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Conclusione
La gestione della scala delle tariffe di assegnazione delle risorse in Aspose.Tasks per Java è fondamentale per una gestione efficace del progetto. Seguendo questa guida passo passo, puoi manipolare facilmente le impostazioni della scala di velocità per le assegnazioni delle risorse nelle tue applicazioni Java.
## Domande frequenti
### Q1: posso utilizzare Aspose.Tasks per Java con qualsiasi IDE Java?
R: Sì, Aspose.Tasks per Java è compatibile con tutti i principali IDE Java, inclusi IntelliJ IDEA, Eclipse e NetBeans.
### Q2: Aspose.Tasks supporta altri formati di file oltre a MPP?
R: Sì, Aspose.Tasks supporta vari formati di file, inclusi MPP, XML e HTML.
### Q3: Aspose.Tasks è adatto alla gestione di progetti a livello aziendale?
R: Assolutamente, Aspose.Tasks offre funzionalità complete per la gestione di progetti di qualsiasi scala, rendendolo adatto alla gestione di progetti a livello aziendale.
### Q4: Posso personalizzare ulteriormente le assegnazioni delle risorse oltre la scala tariffaria?
R: Sì, Aspose.Tasks offre funzionalità estese per personalizzare le assegnazioni delle risorse, inclusi aggiustamenti di costi, lavoro e durata.
### Q5: esiste un forum della community per il supporto di Aspose.Tasks?
 R: Sì, puoi trovare supporto e interagire con altri utenti sul forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).