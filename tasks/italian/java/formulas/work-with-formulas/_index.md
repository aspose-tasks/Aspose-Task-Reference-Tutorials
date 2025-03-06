---
title: Formule di MS Project con Aspose.Tasks per Java
linktitle: Lavorare con le formule in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come manipolare i file MS Project in Java utilizzando la libreria Aspose.Tasks. Crea, modifica e calcola gli attributi con facilità.
type: docs
weight: 11
url: /it/java/formulas/work-with-formulas/
---
## introduzione
In questo tutorial, approfondiremo il lavoro con le formule di MS Project utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente libreria che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di programmazione. Grazie alle sue funzionalità estese, puoi creare, leggere, modificare e convertire facilmente file di progetto in applicazioni Java.
## Prerequisiti
Prima di iniziare, assicurati di aver configurato i seguenti prerequisiti:
### Ambiente di sviluppo Java
Assicurati di avere un Java Development Kit (JDK) installato sul tuo sistema. È possibile scaricare e installare l'ultimo JDK dal sito Web Oracle.
### Libreria Aspose.Tasks
È necessario che la libreria Aspose.Tasks sia aggiunta al tuo progetto Java. È possibile scaricare la libreria da[Aspose.Tasks per la pagina di download di Java](https://releases.aspose.com/tasks/java/) e includilo nelle dipendenze del tuo progetto.

## Importa pacchetti
Prima di immergerti negli esempi, importa i pacchetti necessari nel tuo codice Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Suddividiamo l'esempio fornito in più passaggi:
## Passaggio 1: crea un progetto di prova con campo personalizzato
```java
Project project = CreateTestProjectWithCustomField();
```
 Innanzitutto, crea un progetto di prova con un campo personalizzato utilizzando il file`CreateTestProjectWithCustomField()` metodo. Questo metodo restituirà un oggetto Project che rappresenta il progetto appena creato.
## Passaggio 2: definire una definizione di attributo estesa
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Recupera la definizione dell'attributo esteso dal progetto e impostane l'alias e la formula. In questo esempio stiamo definendo un attributo per calcolare il numero di giorni dalla data di fine alla scadenza.
## Passaggio 3: imposta la scadenza per un'attività
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Crea un oggetto Calendario e imposta la data di scadenza. Quindi, recupera un'attività dal progetto e impostane la scadenza utilizzando l'oggetto Calendario.
## Passaggio 4: salva il progetto
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Infine, salva il progetto in un file con il nome e il formato specificati. In questo caso, lo salviamo come file MPP.

## Conclusione
In questo tutorial, abbiamo imparato come lavorare con le formule di MS Project utilizzando Aspose.Tasks per Java. Seguendo questi passaggi, puoi manipolare in modo efficace i file di progetto a livello di codice, aggiungendo campi personalizzati e calcolando attributi in base a formule.

## Domande frequenti
### D: Posso utilizzare Aspose.Tasks con altri linguaggi di programmazione?
R: Sì, Aspose.Tasks supporta vari linguaggi di programmazione tra cui Java, .NET e altri.
### D: È disponibile una prova gratuita per Aspose.Tasks?
 R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### D: Dove posso trovare la documentazione per Aspose.Tasks?
 R: È possibile trovare la documentazione per Aspose.Tasks[Qui](https://reference.aspose.com/tasks/java/).
### D: Come posso ottenere supporto per Aspose.Tasks?
 R: Per supporto, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### D: Ho bisogno di una licenza temporanea per utilizzare Aspose.Tasks?
R: Se hai bisogno di funzionalità aggiuntive, puoi ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).