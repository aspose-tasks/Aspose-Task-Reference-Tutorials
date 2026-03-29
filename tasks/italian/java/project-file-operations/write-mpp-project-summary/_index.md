---
date: 2026-03-29
description: Scopri come impostare le parole chiave e la data di creazione in un progetto
  MPP usando Aspose.Tasks per Java. Guida passo‑passo con esempi di codice.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come impostare le parole chiave nel riepilogo del progetto MPP con Aspose.Tasks
url: /it/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare le parole chiave nel riepilogo del progetto MPP con Aspose.Tasks

## Introduzione
In questo tutorial scoprirai **come impostare le parole chiave** e altre informazioni di riepilogo per un file di progetto MPP utilizzando Aspose.Tasks per Java. Che tu debba incorporare i dettagli dell'autore, i numeri di revisione o una data di creazione personalizzata, questa guida ti accompagna passo passo, completa di codice pronto da eseguire. Alla fine sarai in grado di impostare le parole chiave, impostare la data di creazione java e recuperare i dati dal file.

## Risposte rapide
- **Quale libreria è usata?** Aspose.Tasks for Java  
- **Scopo principale?** Set keywords, author info, and creation date in an MPP file  
- **Quanti passaggi di codice?** Three simple code blocks (initialize, save, read)  
- **È necessaria una licenza?** A free trial works for development; a commercial license is required for production  
- **Versione Java supportata?** Java 8 and higher  

## Cos'è “come impostare le parole chiave” in un file MPP?
Le parole chiave sono campi di metadati memorizzati all'interno di un file Microsoft Project (MPP). Aiutano a categorizzare i progetti, consentono ricerche rapide e forniscono informazioni contestuali per gli strumenti a valle. Aspose.Tasks espone la proprietà `Prj.KEYWORDS`, rendendo semplice scrivere o aggiornare questo valore programmaticamente.

## Perché usare Aspose.Tasks per Java per impostare parole chiave e data di creazione?
* **Compatibilità .MPP completa** – funziona con tutti i formati Project 2007‑2023.  
* **Nessuna installazione COM o Office richiesta** – puro Java, perfetto per ambienti server.  
* **API ricca** – oltre alle parole chiave è possibile impostare autore, revisione, commenti e date in una singola chiamata.  
* **Ottimizzato per le prestazioni** – lettura/scrittura veloce anche per file di progetto di grandi dimensioni.

## Prerequisiti
1. **Java Development Kit (JDK)** – JDK 8 o più recente installato.  
2. **Aspose.Tasks for Java** – download the latest JAR from [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, or any editor you prefer.

## Importare i pacchetti
Per prima cosa, importa le classi necessarie. Queste importazioni ti danno accesso all'oggetto `Project`, all'enumerazione `Prj` per i campi di riepilogo e all'enum `SaveFileFormat` per il salvataggio.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Passo 1: Configurare il progetto e definire le informazioni di riepilogo
Crea un'istanza `Project`, poi usa il metodo `set` per scrivere i metadati desiderati. Nota come **impostiamo le parole chiave** e **impostiamo la data di creazione java** usando un oggetto `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Passo 2: Salvare le informazioni di riepilogo del progetto
Dopo aver popolato i campi, persisti le modifiche. Qui salviamo il progetto come XML per una facile ispezione, ma è anche possibile salvare nuovamente in MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Passo 3: Leggere le informazioni di riepilogo del progetto
Per verificare che i metadati siano stati scritti correttamente, ricarica il file e leggi nuovamente ogni proprietà. Questo passo dimostra che **come impostare le parole chiave** funziona davvero end‑to‑end.

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | Il calendario non è stato impostato prima del salvataggio. | Assicurati di chiamare `project.set(Prj.CREATION_DATE, cal.getTime())` prima di `save()`. |
| **Keywords not appearing in Microsoft Project UI** | Il file è stato salvato come XML e aperto direttamente in Project. | Salva nuovamente in MPP (`SaveFileFormat.MPP`) o apri l'XML tramite *Import* in Project. |
| **Date values shifted by timezone** | Il `Date` di Java include informazioni sul fuso orario. | Usa `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` se ti servono date UTC. |

## Domande frequenti

**Q: Posso usare Aspose.Tasks per Java con altre librerie Java?**  
A: Sì, Aspose.Tasks per Java può essere integrato senza problemi con altre librerie Java per migliorare le capacità di gestione del progetto.

**Q: È disponibile una versione di prova per Aspose.Tasks per Java?**  
A: Sì, puoi scaricare una versione di prova gratuita da [here](https://releases.aspose.com/).

**Q: Con quale frequenza viene aggiornato Aspose.Tasks per Java?**  
A: Aspose.Tasks per Java viene aggiornato regolarmente per garantire la compatibilità con le ultime versioni di Java e dei file Microsoft Project.

**Q: Posso personalizzare ulteriormente le informazioni di riepilogo del progetto?**  
A: Assolutamente, Aspose.Tasks per Java offre ampie opzioni per personalizzare le informazioni di riepilogo del progetto secondo le tue esigenze specifiche.

**Q: Dove posso ottenere supporto per Aspose.Tasks per Java?**  
A: Puoi ottenere supporto dal forum della community di Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2026-03-29  
**Testato con:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}