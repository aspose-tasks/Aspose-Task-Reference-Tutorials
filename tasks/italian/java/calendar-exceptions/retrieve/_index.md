---
date: 2026-11-19
description: Scopri come recuperare le calendar exceptions java dai file MS Project
  e come leggere il calendar mpp usando Aspose.Tasks per Java. Questo tutorial fornisce
  esempi di codice step‑by‑step.
images:
- /java/calendar-exceptions/retrieve/og-image.png
keywords:
- retrieve calendar exceptions java
- Aspose.Tasks for Java
- MS Project calendar API
- read MPP calendar
- Java project scheduling
lastmod: 2026-11-19
linktitle: Come recuperare le calendar exceptions java con Aspose.Tasks
og_description: Scopri come recuperare le calendar exceptions java dai file MS Project
  e leggere i calendar MPP usando Aspose.Tasks per Java. Questa guida ti mostra come
  aggiungere una gestione accurata del calendar nelle app Java.
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: Come recuperare le calendar exceptions java usando Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  headline: How to retrieve calendar exceptions java with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve calendar exceptions java from MS Project files
    and how to read mpp calendar using Aspose.Tasks for Java. This tutorial provides
    step‑by‑step code examples.
  name: How to retrieve calendar exceptions java with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
    text: '**Java Development Kit (JDK)** – Ensure you have JDK 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java** – Download and install Aspose.Tasks for Java
      from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
    text: '**Integrated Development Environment (IDE)** – You can use any IDE of your
      choice, such as IntelliJ IDEA or Eclipse.'
  type: HowTo
- questions:
  - answer: Retrieving calendar exceptions from an MPP file using Aspose.Tasks for
      Java.
    question: What does this tutorial cover?
  - answer: About 10‑15 minutes for a basic setup.
    question: How long does implementation take?
  - answer: JDK, Aspose.Tasks for Java, and an IDE (IntelliJ IDEA or Eclipse).
    question: Prerequisites?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: All major MS Project formats (MPP, MPT, XML).
    question: Supported Project versions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project scheduling
- calendar exceptions
- MS Project integration
- developer tutorial
title: Come recuperare le calendar exceptions java con Aspose.Tasks
url: /it/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come recuperare le eccezioni del calendario java con Aspose.Tasks

## Introduzione
In questo **asp tasks java tutorial** imparerai come recuperare le eccezioni del calendario da un file Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Le eccezioni del calendario rappresentano periodi non lavorativi come festività o regole personalizzate di orario di lavoro, e la capacità di leggerle programmaticamente è essenziale per il livellamento delle risorse, la generazione di report e la logica di pianificazione personalizzata. Ti guideremo attraverso l'intero processo passo dopo passo, così potrai integrare questa funzionalità nelle tue applicazioni Java con fiducia.

## Risposte rapide
- **Cosa copre questo tutorial?** Recuperare le eccezioni del calendario da un file MPP usando Aspose.Tasks per Java.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per una configurazione di base.  
- **Prerequisiti?** JDK, Aspose.Tasks per Java e un IDE (IntelliJ IDEA o Eclipse).  
- **È necessaria una licenza?** Una versione di prova è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Versioni di Project supportate?** Tutti i principali formati MS Project (MPP, MPT, XML).

## Che cos'è asp tasks java tutorial?
Il **asp tasks java tutorial** spiega come utilizzare l'API Aspose.Tasks all'interno di progetti Java. Fornisce snippet di codice concreti, spiegazioni delle migliori pratiche e scenari reali in modo che gli sviluppatori possano manipolare i file Project senza dover installare Microsoft Project. Seguendo un tutorial come questo, gli sviluppatori acquisiscono una comprensione pratica della struttura dell'API, dei pattern di utilizzo più comuni e di come integrare le sue funzionalità in applicazioni aziendali più ampie.

## Perché recuperare le eccezioni del calendario?
Recuperare le eccezioni del calendario ti consente di generare timeline di progetto accurate che rispettano festività e orari di lavoro personalizzati, creare strumenti di reporting che evidenziano i giorni non lavorativi e sincronizzare i calendari di Project con sistemi esterni come ERP o piattaforme HR. Aspose.Tasks può leggere le eccezioni da **oltre 30** tipi di calendario e supporta **3 principali** formati di file MS Project (MPP, MPT, XML) senza caricare l'intero file in memoria, consentendo una gestione efficiente di progetti di centinaia di pagine.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. **Java Development Kit (JDK)** – Verifica di avere installato JDK 8 o versioni successive.  
2. **Aspose.Tasks for Java** – Scarica e installa Aspose.Tasks for Java dalla **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE)** – Puoi utilizzare qualsiasi IDE a tua scelta, come IntelliJ IDEA o Eclipse.

Puoi anche ottenere Aspose.Tasks for Java dalla **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** se ti serve un promemoria più avanti nel tutorial.

## Come impostare la directory dei dati?
Definisci una cartella che contenga il file Project da analizzare. L'uso di un percorso assoluto o di un percorso relativo alla cartella delle risorse del tuo progetto evita `FileNotFoundException`. Conserva i file in una cartella `resources` dedicata e riferiscili con `Paths.get(...)` per mantenere il codice indipendente dalla piattaforma e evitare percorsi Windows hard‑coded.

## Importa pacchetti
Le istruzioni di importazione portano le classi Aspose.Tasks nel tuo file sorgente Java, consentendoti di lavorare con progetti, calendari ed eccezioni.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## Che cos'è la classe Project?
`Project` rappresenta un file MS Project caricato in memoria. È l'oggetto principale di Aspose.Tasks che ti dà accesso a calendari, attività, risorse e altri dati del progetto tramite un'API pulita e orientata agli oggetti. Utilizzando la classe `Project` puoi interrogare e manipolare ogni elemento di un progetto senza necessità di Microsoft Project installato, rendendola ideale per l'elaborazione lato server e la generazione automatica di report.

## Passo 1: imposta la tua directory dei dati
Definisci una cartella che contenga il file Project da analizzare. L'uso di un percorso assoluto o di un percorso relativo alla cartella delle risorse del tuo progetto evita `FileNotFoundException`.

```java
String dataDir = "C:/Projects/Data/";
```

> **Suggerimento professionale:** Conserva i file Project in una cartella `resources` dedicata e riferiscili con `Paths.get(...)` per percorsi indipendenti dalla piattaforma.

## Passo 2: carica il file MS Project
La classe `Project` rappresenta un file MS Project e fornisce accesso ai suoi calendari, attività, risorse e altri dati. Carica il file Project in un oggetto `Project`. Questo oggetto rappresenta l'intero file MS Project in memoria e fornisce accesso a calendari, attività, risorse e altro ancora.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Come recuperare le eccezioni del calendario da un progetto caricato?
Itera attraverso ogni calendario nel progetto e poi attraverso ogni eccezione di calendario all'interno di quel calendario. Stampa le date di inizio e fine di ciascuna eccezione. Questo ciclo a due livelli garantisce di catturare tutte le eccezioni, anche se un progetto contiene più calendari (standard, risorse o personalizzati). Esaminando ogni `CalendarException` puoi creare report personalizzati, regolare i programmi o esportare i dati verso altri sistemi.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## Problemi comuni e soluzioni
| Problema | Motivo | Correzione |
|----------|--------|------------|
| **Nessun output stampato** | Il file Project non contiene eccezioni del calendario. | Verifica che il calendario in MS Project abbia eccezioni definite (ad es., festività). |
| **`NullPointerException`** | Il percorso `dataDir` è errato o il file non è stato trovato. | Controlla nuovamente il percorso della directory e assicurati che `project.mpp` esista. |
| **Discrepanza di fuso orario** | Le date sono visualizzate in UTC. | Usa `calExc.getFromDate().toLocalDateTime()` per convertire al fuso locale, se necessario. |

## Domande frequenti
### Aspose.Tasks può gestire diverse versioni dei file MS Project?
Sì, Aspose.Tasks supporta **tutti i principali** formati MS Project, inclusi MPP, MPT e XML, per versioni dal 2000 all'ultima release.

### È disponibile una versione di prova gratuita per Aspose.Tasks?
Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks dalla **[Aspose free trial download page](https://releases.aspose.com/)**.

### Dove posso trovare la documentazione per Aspose.Tasks per Java?
Puoi consultare la documentazione **[Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/)**.

### Come posso ottenere supporto per Aspose.Tasks?
Puoi ottenere supporto dal forum della community **[Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)**.

### Esiste un'opzione per licenze temporanee per Aspose.Tasks?
Sì, puoi ottenere licenze temporanee dalla **[temporary license purchase page](https://purchase.aspose.com/temporary-license/)**.

**Domande aggiuntive**

**D:** *Posso modificare le eccezioni del calendario dopo averle recuperate?*  
**R:** Assolutamente. Usa `CalendarException.setFromDate()` e `setToDate()` per regolare le date, quindi salva il progetto con `project.save(...)`.

**D:** *Aspose.Tasks conserva i campi personalizzati sui calendari?*  
**R:** Sì, tutti i campi personalizzati e gli attributi estesi vengono mantenuti durante il caricamento e il salvataggio del progetto.

## Conclusione
In questo **asp tasks java tutorial** abbiamo imparato come recuperare le eccezioni del calendario da MS Project usando Aspose.Tasks per Java. Seguendo questi semplici passaggi, puoi integrare senza problemi questa funzionalità nelle tue applicazioni Java, abilitando funzionalità di pianificazione più ricche e analisi di progetto più accurate.

---

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  








```java
import com.aspose.tasks.*;
```

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

```java
Project project = new Project(dataDir + "project.mpp");
```

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

## Tutorial correlati

- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)
- [How to Use Aspose.Tasks to Retrieve MS Project Calendar Info](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [How to Read Workweeks Java from MS Project Calendar Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}