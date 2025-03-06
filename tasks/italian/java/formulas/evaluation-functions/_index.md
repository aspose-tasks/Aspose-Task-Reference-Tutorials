---
title: Supporta le funzioni di valutazione nelle formule Aspose.Tasks
linktitle: Supporta le funzioni di valutazione nelle formule Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come supportare la valutazione delle funzioni di MS Project nelle formule Aspose.Tasks utilizzando Java. Aumenta la tua produttività con Aspose.Tasks.
weight: 10
url: /it/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Supporta le funzioni di valutazione nelle formule Aspose.Tasks


## introduzione
Aspose.Tasks per Java è una potente libreria che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice. Una delle sue caratteristiche principali è la capacità di supportare la valutazione delle funzioni di MS Project all'interno delle formule Aspose.Tasks. Questa funzionalità consente agli utenti di eseguire calcoli e analisi complessi direttamente all'interno delle loro applicazioni Java.
## Prerequisiti
Prima di iniziare con l'integrazione delle funzioni di MS Project nelle formule Aspose.Tasks, assicurati di avere quanto segue:
1. Ambiente di sviluppo Java: assicurati di avere Java installato sul tuo sistema insieme a un IDE compatibile per lo sviluppo Java come IntelliJ IDEA o Eclipse.
2.  Aspose.Tasks per Java Library: scarica e includi la libreria Aspose.Tasks per Java nel tuo progetto Java. Puoi scaricarlo da[Aspose.Tasks per la pagina di download di Java](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
Per iniziare, importa i pacchetti necessari nella tua classe Java per utilizzare le funzionalità Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## Passaggio 1: crea un nuovo oggetto di progetto
 Per prima cosa, creane uno nuovo`Project`oggetto con cui lavorare:
```java
Project project = new Project();
```
Questo inizializza un nuovo progetto vuoto.
## Passaggio 2: definire un attributo esteso per le attività
Successivamente, definire un attributo esteso per le attività. Questo attributo conterrà i dati personalizzati associati alle attività:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Qui creiamo un attributo esteso di tipo`Number` con il nome "Sine" per le attività.
## Passaggio 3: aggiungi l'attributo esteso al progetto
Aggiungi la definizione dell'attributo esteso all'elenco degli attributi estesi del progetto:
```java
project.getExtendedAttributes().add(attr);
```
Ciò aggiunge l'attributo personalizzato al progetto.
## Passaggio 4: crea una nuova attività
Ora creiamo una nuova attività all'interno del progetto:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Ciò aggiunge una nuova attività denominata "Attività" al progetto.
## Passaggio 5: associare l'attributo esteso all'attività
Associa l'attributo esteso creato in precedenza all'attività:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
Questo associa l'attributo esteso "Sine" all'attività.

## Conclusione
In conclusione, l'integrazione delle funzioni di MS Project nelle formule Aspose.Tasks in Java è un processo semplice. Seguendo i passaggi forniti, puoi utilizzare in modo efficace le potenti funzionalità di Aspose.Tasks per Java per manipolare e analizzare i file di Microsoft Project a livello di codice.
## Domande frequenti
### D: Aspose.Tasks per Java può gestire formule complesse di MS Project?
R: Sì, Aspose.Tasks per Java supporta la valutazione di un'ampia gamma di funzioni di MS Project, consentendo calcoli complessi all'interno delle applicazioni Java.
### D: Aspose.Tasks per Java è compatibile con diverse versioni dei file Microsoft Project?
R: Sì, Aspose.Tasks per Java supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.
### D: Posso provare Aspose.Tasks per Java prima dell'acquisto?
 R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per Java dal sito web[Qui](https://purchase.aspose.com/buy).
### D: Come posso ottenere supporto per Aspose.Tasks per Java?
R: Puoi ottenere supporto dal forum della community Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
### D: È disponibile una licenza temporanea per Aspose.Tasks per Java?
 R: Sì, puoi ottenere una licenza temporanea a scopo di test dal sito Web Aspose[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
