---
date: 2026-08-13
description: Scopri come aggiungere festività a un calendario, assegnare il calendario
  a un progetto e salvare il file MS Project come MPP usando Aspose.Tasks per Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Aggiorna il calendario al formato MPP in Aspose.Tasks
og_description: Aggiungi festività al calendario, assegnalo a un progetto e converti
  il programma in MPP usando Aspose.Tasks per Java. Scopri l'automazione passo‑passo.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Aggiungi festività al calendario e salva come MPP con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Aggiungi festività al calendario e salva come MPP con Aspose.Tasks
url: /it/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere festività al calendario e salvare come MPP con Aspose.Tasks

## Introduzione

Nella gestione moderna dei progetti è spesso necessario **add holidays to calendar** file, creare un **MS Project calendar** e poi condividere il programma nel formato nativo MPP. Che tu stia consolidando linee temporali da più fonti o migrando dati legacy, generare un calendario programmaticamente elimina gli errori manuali e accelera la consegna. Questo tutorial ti guida attraverso l'intero processo di creazione di un calendario in MS Project, personalizzandolo con le festività, **assign calendar to project**, e infine **convert project to MPP** usando l'Aspose.Tasks Java API.

## Risposte rapide

- **Qual è l'argomento di questo tutorial?** Aggiungere festività a un calendario, assegnarlo a un progetto e salvare il risultato come file MPP con Aspose.Tasks per Java.  
- **È necessaria una licenza?** Una prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o superiore (JDK 8+).  
- **Posso personalizzare il calendario?** Sì – è possibile aggiungere orari di lavoro, eccezioni e festività.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un calendario di base.  

## Che cos'è “create calendar MS Project”?

Creare un calendar MS Project significa definire i giorni lavorativi, le ore e le eccezioni che guidano la pianificazione delle attività all'interno di un file Microsoft Project. Usando Aspose.Tasks è possibile costruire programmaticamente questo calendario, impostare le festività e incorporarlo in un progetto senza aprire l'interfaccia di MS Project.

## Perché usare Aspose.Tasks per questo compito?

Dovresti usare Aspose.Tasks perché offre piena compatibilità Java, non è necessario Microsoft Office e consente di generare e salvare file MPP nativi direttamente dal codice. La libreria supporta tutte le funzionalità del calendario, funziona in qualsiasi ambiente server e elabora progetti fino a 10.000 attività in meno di un secondo.

## Prerequisiti

1. **Java Development Kit (JDK) 8+** – assicurati che `java -version` riporti 1.8 o superiore.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dal [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor tu preferisca.  
4. **Basic Java knowledge** – familiarità con classi, metodi e I/O di file.

## Come aggiungere festività al calendario

Per aggiungere festività crei un nuovo oggetto `Calendar`, recuperi la sua collezione `Exceptions` e aggiungi voci `DateException` per ogni data di festività. `DateException` rappresenta una singola data o intervallo non lavorativo in un calendario. Aspose.Tasks tratta quindi queste date come giorni non lavorativi, garantendo che le attività siano programmate intorno alle festività definite.

### Passo 1: importare i pacchetti richiesti

Per prima cosa, porta le classi Aspose.Tasks e le utility Java nello scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Passo 2: impostare la directory dei dati

Definisci dove risiederanno i tuoi file di modello di input e i file di output. Sostituisci il segnaposto con il percorso reale sul tuo computer.

```java
String dataDir = "Your Data Directory";
```

### Passo 3: definire i nomi dei file di input e output

Caricheremo un file MPP esistente (o un progetto vuoto) e scriveremo il risultato in un nuovo file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Passo 4: caricare il progetto e aggiungere un nuovo calendario

La classe `Project` rappresenta un file MS Project in memoria e fornisce l'accesso ai suoi calendari, attività e risorse.

Crea un'istanza `Project` dal file sorgente e aggiungi un calendario chiamato **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Passo 5: personalizzare il calendario (opzionale)

L'oggetto `Calendar` definisce i giorni lavorativi, le ore e le eccezioni per il programma di un progetto.

Se hai bisogno di orari di lavoro specifici, festività o eccezioni, chiama il tuo metodo di supporto. L'esempio utilizza `GetTestCalendar` come segnaposto.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Consiglio professionale:** puoi manipolare direttamente `cal1.getWeekDays()` per impostare le ore lavorative per ogni giorno della settimana, oppure usare `cal1.getExceptions()` per **add holidays to calendar**.

### Passo 6: assegnare il calendario al progetto

Indica al progetto di utilizzare il calendario appena creato per tutti i calcoli di pianificazione.

```java
project.set(Prj.CALENDAR, cal1);
```

### Passo 7: salvare il progetto come MPP

L'enumerazione `SaveFileFormat` specifica il formato di output, con `Mpp` che indica il formato nativo Microsoft Project.

Ora **convert project to MPP** salvandolo con l'opzione `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Passo 8: confermare il completamento riuscito

Un semplice messaggio sulla console ti informa che il processo è terminato senza errori.

```java
System.out.println("Process completed Successfully");
```

## Casi d'uso comuni

- **Automated schedule generation** per progetti ricorrenti (ad es., sprint settimanali).  
- **Migrating legacy CSV or Excel calendars** in un file MS Project completo di funzionalità.  
- **Server‑side reporting** dove un servizio web restituisce un file MPP su richiesta.  

## Risoluzione dei problemi e ostacoli comuni

| Problema | Causa | Soluzione |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` points to a non‑existent folder | Assicurati che la directory esista o creala programmaticamente. |
| Calendar not applied to tasks | Tasks still reference the default calendar | Dopo aver impostato `Prj.CALENDAR`, aggiorna anche `Task.CALENDAR` di ogni attività se era stato sovrascritto precedentemente. |
| Output file is 0 KB | Missing write permissions | Esegui la JVM con i permessi di file system appropriati o scegli un percorso scrivibile. |

## Domande frequenti

**Q: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?**  
A: Sì, Aspose.Tasks supporta tutti i formati di file Microsoft Project da Project 2007 a Project 2024, coprendo più di 10 versioni.

**Q: Posso personalizzare i calendari in base a requisiti specifici del progetto?**  
A: Assolutamente. Puoi definire i giorni lavorativi, impostare settimane lavorative personalizzate, aggiungere festività e persino creare più calendari all'interno di un unico file di progetto.

**Q: Aspose.Tasks per Java offre supporto per la risoluzione dei problemi e assistenza?**  
A: Sì, puoi ottenere aiuto dal forum della community di Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: È disponibile una prova gratuita per Aspose.Tasks per Java?**  
A: Sì, è disponibile una prova gratuita completamente funzionale [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?**  
A: Le licenze temporanee possono essere richieste tramite il sito Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-08-13  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Aggiungere calendario al progetto con Aspose.Tasks per Java](/tasks/java/calendars/create/)
- [Come definire i giorni della settimana nei calendari MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Creare eccezioni di calendario personalizzate con Aspose.Tasks per Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}