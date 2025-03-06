---
title: Scrivere e leggere le formule di MS Project in Aspose.Tasks
linktitle: Scrivere e leggere formule in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Impara a scrivere e leggere le formule di MS Project in modo efficiente con Aspose.Tasks per Java. Migliora le tue capacità di gestione dei progetti.
weight: 12
url: /it/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Scrivere e leggere le formule di MS Project in Aspose.Tasks

## introduzione
Nell’ambito della gestione dei progetti, la gestione efficace dei dati è fondamentale. Aspose.Tasks per Java è una soluzione robusta che facilita la manipolazione e l'estrazione dei dati dai file Microsoft Project. Una potente funzionalità che offre è la capacità di scrivere e leggere formule di MS Project. Questo tutorial ti guiderà attraverso il processo di sfruttamento di questa funzionalità per migliorare le attività di gestione del progetto.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema.
2.  Aspose.Tasks per Java: Scarica e installa Aspose.Tasks per Java da[Qui](https://releases.aspose.com/tasks/java/).
3. Ambiente di sviluppo integrato (IDE): scegli il tuo IDE preferito per lo sviluppo Java.

## Importazione di pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Passaggio 1: impostare la directory dei dati
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
```
In questo passaggio, definisci la directory in cui si trovano i file MS Project.
## Passaggio 2: caricare il file di progetto
```java
Project project = new Project(dataDir + "project.mpp");
```
Qui, carica il file MS Project in un file`Project` oggetto da manipolare.
## Passaggio 3: definire la formula personalizzata
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
Questo passaggio prevede la creazione di un campo personalizzato con una formula che raddoppia il costo dell'attività.
## Passaggio 4: aggiungi attività e imposta il costo
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Qui viene aggiunta una nuova attività e il suo costo è impostato su 100.
## Passaggio 5: salva il file di progetto
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Infine, salva il file di progetto modificato.

## Conclusione
In questo tutorial, abbiamo esplorato come scrivere e leggere le formule di MS Project utilizzando Aspose.Tasks per Java. Seguendo questi passaggi è possibile manipolare in modo efficiente i dati del progetto per soddisfare i propri requisiti specifici.
## Domande frequenti
### Aspose.Tasks è compatibile con tutte le versioni di MS Project?
Aspose.Tasks offre compatibilità con varie versioni di MS Project, garantendo flessibilità agli utenti.
### Posso integrare Aspose.Tasks nel mio progetto Java esistente?
Assolutamente! Aspose.Tasks fornisce una perfetta integrazione con i progetti Java attraverso il semplice utilizzo dell'API.
### Ci sono limitazioni ai tipi di formule che posso creare?
Con Aspose.Tasks, hai un'ampia flessibilità nella creazione di formule personalizzate su misura per le esigenze del tuo progetto.
### Aspose.Tasks supporta la distribuzione multipiattaforma?
Sì, Aspose.Tasks supporta la distribuzione su più piattaforme, migliorandone la versatilità.
### Come posso ottenere supporto tecnico per Aspose.Tasks?
 Per assistenza tecnica e supporto comunitario, visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
