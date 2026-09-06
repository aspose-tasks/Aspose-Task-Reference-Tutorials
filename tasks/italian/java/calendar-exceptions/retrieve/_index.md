---
date: 2026-08-24
description: Scopri come recuperare le calendar exceptions java dai file MS Project
  e come leggere il calendario mpp utilizzando Aspose.Tasks per Java. Questo tutorial
  fornisce esempi di codice passo‑passo.
keywords:
- retrieve calendar exceptions java
- how to read mpp calendar
- Aspose.Tasks Java
- MS Project calendar API
lastmod: 2026-08-24
linktitle: Come recuperare le calendar exceptions java con Aspose.Tasks
og_description: Scopri come recuperare le calendar exceptions java dai file MS Project
  e come leggere il calendario mpp utilizzando Aspose.Tasks per Java. Questa guida
  passo‑passo ti aiuta ad aggiungere una gestione accurata del calendario alle tue
  app Java.
og_image_alt: Developer guide showing Java code to read calendar exceptions from an
  MS Project file
og_title: Come recuperare le calendar exceptions java con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-24'
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
In questo **asp tasks java tutorial** imparerai come recuperare le eccezioni del calendario da un file Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Le eccezioni del calendario rappresentano periodi non lavorativi come festività o regole personalizzate di orario di lavoro, e la possibilità di leggerle programmaticamente è essenziale per il livellamento delle risorse, la generazione di report e la logica di pianificazione personalizzata. Ti guideremo attraverso l’intero processo passo‑a‑passo, così potrai integrare questa funzionalità nelle tue applicazioni Java con sicurezza.

## Risposte rapide
- **Di cosa tratta questo tutorial?** Recuperare le eccezioni del calendario da un file MPP usando Aspose.Tasks per Java.  
- **Quanto tempo richiede l’implementazione?** Circa 10‑15 minuti per una configurazione di base.  
- **Prerequisiti?** JDK, Aspose.Tasks per Java e un IDE (IntelliJ IDEA o Eclipse).  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Versioni di Project supportate?** Tutti i principali formati MS Project (MPP, MPT, XML).

## Che cos’è l’asp tasks java tutorial?
L’**asp tasks java tutorial** spiega come utilizzare l’API Aspose.Tasks all’interno di progetti Java. Fornisce snippet di codice concreti, spiegazioni delle migliori pratiche e scenari reali affinché gli sviluppatori possano manipolare i file Project senza dover installare Microsoft Project. Seguendo un tutorial come questo, gli sviluppatori ottengono una comprensione chiara e pratica della struttura dell’API, dei pattern di utilizzo più comuni e di come integrare le sue funzionalità in applicazioni aziendali più ampie.

## Perché recuperare le eccezioni del calendario?
Recuperare le eccezioni del calendario ti consente di generare timeline di progetto accurate che rispettano festività e orari di lavoro personalizzati, di costruire strumenti di reporting che evidenziano i giorni non lavorativi e di sincronizzare i calendari di Project con sistemi esterni come ERP o piattaforme HR. Aspose.Tasks può leggere le eccezioni da **oltre 30** tipi di calendario e supporta **3 principali** formati di file MS Project (MPP, MPT, XML) senza caricare l’intero file in memoria, consentendo una gestione efficiente di progetti di centinaia di pagine.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. **Java Development Kit (JDK)** – Verifica di avere installato JDK 8 o versioni successive.  
2. **Aspose.Tasks per Java** – Scarica e installa Aspose.Tasks per Java dalla **[pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE)** – Puoi utilizzare qualsiasi IDE a tua scelta, come IntelliJ IDEA o Eclipse.

## Importare i pacchetti
Le istruzioni di importazione portano le classi Aspose.Tasks nel tuo file sorgente Java, permettendoti di lavorare con progetti, calendari ed eccezioni.

```java
import com.aspose.tasks.*;
import java.util.*;
```

## Passo 1: impostare la directory dei dati
Definisci una cartella che contiene il file Project da analizzare. L’uso di un percorso assoluto o di un percorso relativo alla cartella delle risorse del progetto evita `FileNotFoundException`.

```java
String dataDir = "C:/Projects/Data/";
```

> **Suggerimento:** Conserva i file Project in una cartella risorse dedicata e riferiscili con `Paths.get(...)` per percorsi indipendenti dalla piattaforma.

## Passo 2: caricare il file MS Project
La classe `Project` rappresenta un file MS Project e fornisce l’accesso ai suoi calendari, attività, risorse e altri dati del progetto. Carica il file Project in un oggetto `Project`. Questo oggetto rappresenta l’intero file MS Project in memoria e consente l’accesso a calendari, attività, risorse e altro ancora.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Passo 3: recuperare le eccezioni del calendario
Itera su ciascun calendario nel progetto e poi su ogni eccezione del calendario all’interno di quel calendario. Stampa le date di inizio e fine di ciascuna eccezione.

```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("Exception from " + calExc.getFromDate() + " to " + calExc.getToDate());
    }
}
```

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Nessun output stampato** | Il file Project non contiene eccezioni del calendario. | Verifica che il calendario in MS Project abbia eccezioni definite (ad es., festività). |
| **`NullPointerException`** | Il percorso `dataDir` è errato o il file non è stato trovato. | Controlla nuovamente il percorso della directory e assicurati che `project.mpp` esista. |
| **Discrepanza del fuso orario** | Le date sono visualizzate in UTC. | Usa `calExc.getFromDate().toLocalDateTime()` per convertire al fuso locale, se necessario. |

## Domande frequenti
### Aspose.Tasks può gestire versioni diverse di file MS Project?
Sì, Aspose.Tasks supporta **tutti i principali** formati MS Project, inclusi MPP, MPT e XML, per le versioni dal 2000 all’ultima release.

### È disponibile una versione di prova gratuita per Aspose.Tasks?
Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks dalla **[pagina di download della prova gratuita di Aspose](https://releases.aspose.com/)**.

### Dove posso trovare la documentazione per Aspose.Tasks per Java?
Puoi consultare la documentazione **[Riferimento API Java di Aspose.Tasks](https://reference.aspose.com/tasks/java/)**.

### Come posso ottenere supporto per Aspose.Tasks?
Puoi ottenere supporto dal forum della community **[forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15)**.

### Esiste un’opzione di licenza temporanea per Aspose.Tasks?
Sì, puoi ottenere licenze temporanee dalla **[pagina di acquisto licenza temporanea](https://purchase.aspose.com/temporary-license/)**.

**Domande aggiuntive**

**D:** *Posso modificare le eccezioni del calendario dopo averle recuperate?*  
**R:** Assolutamente. Usa `CalendarException.setFromDate()` e `setToDate()` per regolare le date, quindi salva il progetto con `project.save(...)`.

**D:** *Aspose.Tasks conserva i campi personalizzati sui calendari?*  
**R:** Sì, tutti i campi personalizzati e gli attributi estesi vengono mantenuti durante il caricamento e il salvataggio del progetto.

## Conclusione
In questo **asp tasks java tutorial** abbiamo imparato come recuperare le eccezioni del calendario da MS Project usando Aspose.Tasks per Java. Seguendo questi semplici passaggi, potrai integrare senza problemi questa funzionalità nelle tue applicazioni Java, abilitando funzionalità di pianificazione più ricche e analisi di progetto più accurate.

---

**Ultimo aggiornamento:** 2026-08-24  
**Testato con:** Aspose.Tasks per Java 24.11  
**Autore:** Aspose  








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

- [Crea eccezioni di calendario personalizzate con Aspose.Tasks per Java](/tasks/java/calendar-exceptions/)
- [Come usare Aspose.Tasks per recuperare le informazioni del calendario di MS Project](/tasks/java/project-file-operations/retrieve-calendar-info/)
- [Come leggere le settimane lavorative Java dal calendario di MS Project con Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}