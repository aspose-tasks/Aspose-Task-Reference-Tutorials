---
title: Eseguire il rendering dell'utilizzo delle risorse e della visualizzazione foglio in Aspose.Tasks
linktitle: Eseguire il rendering dell'utilizzo delle risorse e della visualizzazione foglio in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come eseguire il rendering dell'utilizzo delle risorse di MS Project e delle visualizzazioni dei fogli in Aspose.Tasks per Java. Segui la nostra guida passo passo per generare report PDF dettagliati senza sforzo.
type: docs
weight: 16
url: /it/java/resource-management/render-resource-usage-sheet-view/
---
## introduzione
In questo tutorial impareremo come utilizzare Aspose.Tasks per Java per eseguire il rendering dell'utilizzo delle risorse e delle visualizzazioni dei fogli di MS Project. Aspose.Tasks è una potente libreria Java che consente agli sviluppatori di lavorare con file Microsoft Project senza la necessità di installare Microsoft Project.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti installati e configurati:
1. Java Development Kit (JDK): assicurati di avere Java Development Kit installato sul tuo sistema. È possibile scaricare e installare la versione più recente di JDK dal sito Web Oracle.
2.  Aspose.Tasks per Java: scarica e installa la libreria Aspose.Tasks per Java dal file[pagina di download](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Passaggio 1: leggere il progetto sorgente
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
// Leggi il progetto sorgente
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
In questo passaggio specifichiamo il percorso del file di progetto sorgente (`ResourceUsageView.mpp` ) e utilizzare il file`Project` lezione per leggerlo.
## Passaggio 2: definire le opzioni di salvataggio con le impostazioni di scala temporale richieste
```java
// Definire SaveOptions con le impostazioni TimeScale richieste come Giorni
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Qui definiamo il`SaveOptions` con il richiesto`TimeScale` impostazioni. In questo esempio impostiamo il file`TimeScale` di oggi.
## Passaggio 3: impostare il formato della presentazione su ResourceUsage
```java
// Imposta il formato Presentazione su ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Impostiamo il formato di presentazione su`ResourceUsage`, indicando che vogliamo eseguire il rendering della vista Utilizzo risorse.
## Passaggio 4: salva il progetto
```java
// Salva il progetto
project.save(dataDir + days, options);
```
Infine, salviamo il progetto con le opzioni specificate. In questo esempio, il file di output verrà salvato come`result_days.pdf`.
## Passaggio 5: visualizzazioni di rendering per altre impostazioni di scala temporale
Ripetere i passaggi da 2 a 4 per eseguire il rendering delle viste con impostazioni TimeScale diverse (ThirdsOfMonths e Months).
```java
// Configura le impostazioni della scala temporale su ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Salva il progetto
project.save(thirds, options);
// Configura le impostazioni della scala cronologica su Mesi
options.setTimescale(Timescale.Months);
// Salva il progetto
project.save(dataDir + months, options);
```
 Assicurati di cambiare il file`Timescale` impostazioni di conseguenza per ciascuna vista.

## Conclusione
In questo tutorial, abbiamo esplorato come utilizzare Aspose.Tasks per Java per eseguire il rendering dell'utilizzo delle risorse e delle visualizzazioni dei fogli di MS Project. Seguendo i passaggi sopra descritti, puoi generare in modo efficiente queste visualizzazioni in formato PDF, facilitando una migliore visualizzazione e analisi dei dati del tuo progetto.
## Domande frequenti
### Aspose.Tasks può eseguire il rendering di altre visualizzazioni oltre all'utilizzo delle risorse e al foglio?
Aspose.Tasks supporta il rendering di varie visualizzazioni come diagramma di Gantt, utilizzo attività e visualizzazioni calendario, tra le altre.
### Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?
Sì, Aspose.Tasks supporta un'ampia gamma di formati di file di Microsoft Project, inclusi i formati MPP, MPT e XML.
### Posso personalizzare l'aspetto delle viste renderizzate utilizzando Aspose.Tasks?
Assolutamente! Aspose.Tasks fornisce ampie opzioni per personalizzare l'aspetto e il layout delle viste renderizzate in base alle proprie esigenze specifiche.
### Aspose.Tasks richiede che Microsoft Project sia installato sul sistema?
No, Aspose.Tasks è una libreria autonoma e non richiede l'installazione di Microsoft Project per il suo funzionamento.
### Il supporto tecnico è disponibile per gli utenti Aspose.Tasks?
 Sì, gli utenti di Aspose.Tasks possono avvalersi del supporto tecnico tramite il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).