---
title: Scrivi il riepilogo del progetto MPP in Aspose.Tasks
linktitle: Scrivi il riepilogo del progetto MPP in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come scrivere riepiloghi di progetti MPP in Java utilizzando Aspose.Tasks. Imposta e recupera le informazioni sul progetto senza sforzo.
weight: 27
url: /it/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Scrivi il riepilogo del progetto MPP in Aspose.Tasks

## introduzione
In questo tutorial impareremo come utilizzare Aspose.Tasks per Java per scrivere riepiloghi del progetto MPP. Aspose.Tasks è una potente libreria Java per lavorare con i file Microsoft Project. Seguendo i passaggi descritti di seguito, sarai in grado di impostare e recuperare varie informazioni di riepilogo su un progetto utilizzando questa libreria.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2.  Aspose.Tasks per Java: scarica e installa la libreria Aspose.Tasks per Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Ambiente di sviluppo integrato (IDE): scegli il tuo IDE preferito per lo sviluppo Java, come IntelliJ IDEA, Eclipse o NetBeans.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari nella tua classe Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Passaggio 1: impostare il progetto e definire le informazioni di riepilogo
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
//Inizializza un nuovo oggetto Progetto con il percorso del file di progetto
Project project = new Project(dataDir + "project.mpp");
// Imposta informazioni di riepilogo sul progetto
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Imposta la data di creazione del progetto
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Imposta le parole chiave per il progetto
project.set(Prj.KEYWORDS, "MPP Aspose");
// Imposta la data dell'ultima stampa del progetto
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Passaggio 2: salvare le informazioni di riepilogo del progetto
```java
// Salva nuovamente il progetto in formato MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Visualizza un messaggio di successo
System.out.println("Process completed Successfully");
```
## Passaggio 3: leggere le informazioni di riepilogo del progetto
```java
// Lettura delle informazioni di riepilogo del progetto
project = new Project(dataDir + "MppAspose.xml");
// Stampa autore del progetto
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Stampa l'ultimo autore del progetto
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Stampa il numero di revisione del progetto
System.out.println("Revision: " + project.get(Prj.REVISION));
// Stampa le parole chiave del progetto
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Stampa commenti del progetto
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Stampa la data di creazione del progetto
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Stampa le parole chiave del progetto (di nuovo)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Stampa l'ultima data stampata del progetto
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Conclusione
In questo tutorial, abbiamo spiegato come scrivere riepiloghi di progetti MPP utilizzando Aspose.Tasks per Java. Seguendo questi passaggi, puoi impostare e recuperare in modo efficiente varie informazioni di riepilogo sui file di progetto. Aspose.Tasks semplifica il processo di lavoro con i file Microsoft Project nelle applicazioni Java, offrendo funzionalità robuste e facilità d'uso.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per Java con altre librerie Java?
R: Sì, Aspose.Tasks per Java può essere perfettamente integrato con altre librerie Java per migliorare le capacità di gestione dei progetti.
### D: È disponibile una versione di prova per Aspose.Tasks per Java?
 R: Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Con quale frequenza viene aggiornato Aspose.Tasks per Java?
R: Aspose.Tasks per Java viene regolarmente aggiornato per garantire la compatibilità con le ultime versioni dei file Java e Microsoft Project.
### D: Posso personalizzare ulteriormente le informazioni di riepilogo del progetto?
R: Assolutamente, Aspose.Tasks per Java fornisce ampie opzioni per personalizzare le informazioni di riepilogo del progetto in base ai requisiti specifici.
### D: Dove posso ottenere supporto per Aspose.Tasks per Java?
R: Puoi ottenere supporto dal forum della community Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
