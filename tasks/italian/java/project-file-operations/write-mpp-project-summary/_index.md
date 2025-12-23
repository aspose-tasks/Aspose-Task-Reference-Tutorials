---
date: 2025-12-23
description: Scopri come creare un riepilogo MPP e aggiornare l'autore del progetto
  usando Aspose.Tasks per Java. Imposta e recupera le informazioni del progetto senza
  sforzo.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come creare un riepilogo MPP e aggiornare l'autore del progetto con Aspose.Tasks
url: /it/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Scrivi il riepilogo del progetto MPP in Aspose.Tasks

## Introduzione
In questo tutorial, **creerai** informazioni di riepilogo MPP per un file Microsoft Project e imparerai a **aggiornare i dettagli dell'autore del progetto** utilizzando la libreria Aspose.Tasks per Java. Che tu stia costruendo uno strumento di gestione dei progetti o automatizzando la generazione di report, controllare le proprietà di riepilogo in modo programmatico fa risparmiare tempo e garantisce coerenza nei tuoi progetti.

## Risposte rapide
- **Che cosa significa “creare riepilogo MPP”?** Significa impostare le proprietà di alto livello del progetto (autore, revisione, parole‑chiave, ecc.) che compaiono nella finestra di dialogo Informazioni riepilogo progetto di Microsoft Project.  
- **Quale libreria gestisce questo?** Aspose.Tasks per Java fornisce un'API fluida per leggere e scrivere queste proprietà.  
- **Ho bisogno di una licenza?** È disponibile una versione di prova gratuita, ma è necessaria una licenza commerciale per l'uso in produzione.  
- **Posso anche cambiare l'autore dopo che il file è stato salvato?** Sì – puoi **aggiornare l'autore del progetto** chiamando `project.set(Prj.AUTHOR, "New Author")` e quindi risalvare il file.  
- **Quali formati di file sono supportati?** Sia MPP che XML (SaveFileFormat.Xml) sono pienamente supportati.

## Cos'è creare riepilogo MPP?
Creare un riepilogo MPP consiste nel popolare i metadati del progetto—autore, numero di revisione, parole‑chiave, commenti, data di creazione e data di stampa. questi metadati sono memorizzati all'interno del record Informazioni riepilogo progetto e vengono visualizzati nella sezione **File → Info** di Microsoft Project.

## Perché aggiornare l'autore del progetto?
Mantenere le informazioni sull'**autore del progetto** accurate è essenziale per le tracce di audit, la collaborazione e la generazione di report. Quando più membri del team contribuiscono, potresti dover **aggiornare l'autore del progetto** per riflettere le modifiche più recenti o attribuire correttamente il lavoro.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK) installato sulla tua macchina.  
2. Aspose.Tasks per Java – scaricalo da [qui](https://releases.aspose.com/tasks/java/).  
3. Un IDE come IntelliJ IDEA, Eclipse o NetBeans.

## Importa i pacchetti
Innanzitutto, importa i pacchetti necessari nella tua classe Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Passo 1: Configura il progetto e definisci le informazioni di riepilogo
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
Nel codice sopra **creiamo** i campi di riepilogo MPP come autore, revisione e parole‑chiave. Puoi anche **aggiornare l'autore del progetto** in seguito chiamando `project.set(Prj.AUTHOR, "New Name")`.

## Passo 2: Salva le informazioni di riepilogo del progetto
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Il salvataggio del progetto persiste tutti i dati di riepilogo appena definiti.

## Passo 3: Leggi le informazioni di riepilogo del progetto
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Questo frammento dimostra come **leggere** le informazioni di riepilogo, confermando che l'operazione di **creare riepilogo MPP** è riuscita.

## Problemi comuni e soluzioni
- **Valori nulli dopo la lettura:** Assicurati che il progetto sia stato salvato correttamente prima di ricaricarlo. Controlla i percorsi dei file e i permessi.  
- **Differenze di formattazione della data:** `project.get(Prj.CREATION_DATE)` restituisce un `java.util.Date`. Usa `SimpleDateFormat` se hai bisogno di un formato di visualizzazione personalizzato.  
- **Licenza non impostata:** Senza una licenza valida, Aspose.Tasks funziona in modalità di valutazione e può inserire una filigrana. Registra la tua licenza all'inizio del codice.

## Domande frequenti
**Q: Posso usare Aspose.Tasks per Java con altre librerie Java?**  
A: Sì, Aspose.Tasks per Java può essere integrato senza problemi con altre librerie Java per potenziare le tue capacità di gestione dei progetti.

**Q: È disponibile una versione di prova per Aspose.Tasks per Java?**  
A: Sì, puoi scaricare una versione di prova gratuita da [qui](https://releases.aspose.com/).

**Q: Con quale frequenza viene aggiornato Aspose.Tasks per Java?**  
A: Aspose.Tasks per Java viene aggiornato regolarmente per garantire la compatibilità con le versioni più recenti di Java e dei file Microsoft Project.

**Q: Posso personalizzare ulteriormente le informazioni di riepilogo del progetto?**  
A: Assolutamente, Aspose.Tasks per Java offre ampie opzioni per personalizzare le informazioni di riepilogo del progetto secondo le tue esigenze specifiche.

**Q: Dove posso ottenere supporto per Aspose.Tasks per Java?**  
A: Puoi ottenere supporto dal forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

## Conclusione
In questo tutorial ti abbiamo mostrato come **creare dati di riepilogo MPP**, **aggiornare l'autore del progetto** e verificare tali modifiche usando Aspose.Tasks per Java. Automatizzando questi passaggi ottieni il pieno controllo sui metadati del progetto, rendendo le tue applicazioni più robuste e i tuoi report più accurati.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}