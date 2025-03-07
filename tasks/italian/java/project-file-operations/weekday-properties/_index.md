---
title: Proprietà dei giorni feriali in Aspose.Tasks
linktitle: Proprietà dei giorni feriali in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Impara a gestire le proprietà dei giorni feriali in modo efficiente in Aspose.Tasks per Java. Personalizza facilmente le date di inizio settimana, i giorni del mese e altro ancora.
weight: 25
url: /it/java/project-file-operations/weekday-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proprietà dei giorni feriali in Aspose.Tasks

## introduzione
Aspose.Tasks per Java è una potente API che consente agli sviluppatori Java di lavorare con file Microsoft Project senza che Microsoft Project sia installato sul computer. Una delle sue funzionalità chiave è la gestione delle proprietà dei giorni feriali, consentendo agli utenti di personalizzare le date di inizio settimana, i giorni al mese, i minuti al giorno e i minuti alla settimana. Questo tutorial fornirà una guida dettagliata su come utilizzare queste funzionalità in modo efficace.
## Prerequisiti
Prima di immergerti in Aspose.Tasks per Java, assicurati di avere i seguenti prerequisiti:
### Kit di sviluppo Java (JDK)
Assicurati di avere JDK installato sul tuo sistema. È possibile scaricare e installare l'ultimo JDK dal sito Web Oracle.
### Aspose.Tasks per la libreria Java
 Scaricare e installare la libreria Aspose.Tasks per Java dal sito Web. È possibile accedere al collegamento per il download[Qui](https://releases.aspose.com/tasks/java/).
### Ambiente di sviluppo integrato (IDE)
Scegli un IDE di tua preferenza per lo sviluppo Java. Le scelte più popolari includono IntelliJ IDEA, Eclipse o NetBeans.
## Importa pacchetti
Per iniziare, importa i pacchetti Aspose.Tasks necessari nel tuo progetto Java. Ecco come:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Ora suddividiamo l'esempio fornito in più passaggi per una migliore comprensione.
## Passaggio 1: caricare il file di progetto
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Questo passaggio prevede il caricamento di un file di progetto denominato "project.mpp" dalla directory dei dati specificata.
## Passaggio 2: Visualizza le proprietà dei giorni feriali
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Qui recuperiamo e stampiamo le proprietà della data di inizio settimana, dei giorni al mese, dei minuti al giorno e dei minuti alla settimana del progetto caricato.
## Passaggio 3: impostazione delle proprietà dei giorni feriali
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Questo passaggio prevede la creazione di una nuova istanza del progetto e l'impostazione di proprietà personalizzate dei giorni feriali come il giorno di inizio settimana, i giorni al mese, i minuti al giorno e i minuti alla settimana.
## Passaggio 4: salva il progetto
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Infine, salviamo il progetto modificato con le proprietà aggiornate dei giorni feriali come file XML.
## Passaggio 5: Visualizza risultato
```java
System.out.println("Process completed Successfully");
```
Questo passaggio conferma il corretto completamento del processo.
## Conclusione
Padroneggiare le proprietà dei giorni feriali in Aspose.Tasks per Java è fondamentale per una gestione efficace del progetto. Seguendo questo tutorial, hai imparato come manipolare e personalizzare facilmente le proprietà dei giorni feriali. Esplora ulteriore documentazione ed esempi per migliorare le tue capacità di gestione dei progetti.
## Domande frequenti
### D: Aspose.Tasks per Java può gestire strutture di progetto complesse?
R: Sì, Aspose.Tasks per Java fornisce un supporto completo per gestire facilmente strutture di progetto complesse.
### D: Aspose.Tasks per Java è compatibile con diverse versioni dei file Microsoft Project?
R: Assolutamente, Aspose.Tasks per Java supporta varie versioni di file Microsoft Project, garantendo la compatibilità tra piattaforme.
### D: Posso integrare Aspose.Tasks per Java nelle mie applicazioni Java esistenti?
R: Sì, Aspose.Tasks per Java offre funzionalità di integrazione perfetta, che ti consentono di migliorare le tue applicazioni Java con potenti funzionalità di gestione dei progetti.
### D: Aspose.Tasks per Java fornisce documentazione e supporto?
 R: Sì, puoi accedere a un'ampia documentazione e al supporto della community per Aspose.Tasks per Java sul loro sito[sito web](https://releases.aspose.com/).
### D: È disponibile una prova gratuita per Aspose.Tasks per Java?
R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per Java dal loro[sito web](https://reference.aspose.com/tasks/java/) per esplorarne le funzionalità prima di effettuare un acquisto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
