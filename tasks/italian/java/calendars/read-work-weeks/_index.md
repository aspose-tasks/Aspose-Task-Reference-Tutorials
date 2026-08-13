---
date: 2026-08-13
description: Scopri come leggere le settimane lavorative da un calendario MS Project
  utilizzando Aspose.Tasks per Java. Segui la guida passo‑passo con esempi di codice
  e suggerimenti per la risoluzione dei problemi.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Leggi le settimane lavorative dal calendario con Aspose.Tasks
og_description: Come leggere le settimane lavorative da un calendario MS Project utilizzando
  Aspose.Tasks per Java. Segui il tutorial conciso con i passaggi di configurazione,
  snippet di codice e suggerimenti per la risoluzione dei problemi.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Come leggere le settimane lavorative dal calendario MS con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Come leggere le settimane lavorative dal calendario MS con Aspose.Tasks
url: /it/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere le settimane lavorative dal calendario MS con Aspose.Tasks

## Introduzione
Nella presente tutorial **imparerai a leggere le settimane lavorative** da un calendario Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Che tu stia creando un cruscotto di reporting, sincronizzando i programmi con un sistema ERP, o automatizzando l'estrazione dei dati per l'analisi, l'accesso programmatico alle definizioni delle settimane lavorative salva innumerevoli ore manuali. Aspose.Tasks supporta **50+ formati di input e output** e può elaborare file di progetto di centinaia di pagine senza caricare l'intero file in memoria, offrendoti sia flessibilità che prestazioni.

## Risposte rapide
- **Cosa significa “leggere le settimane lavorative”?** Si riferisce all'estrazione delle definizioni delle settimane lavorative (date e regole di orario giornaliero) da un file Project tramite codice Java.  
- **Quale libreria è necessaria?** Aspose.Tasks for Java (disponibile versione di prova gratuita).  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova funziona per i test; è necessaria una licenza commerciale per le distribuzioni in produzione.  
- **Quali formati di file sono supportati?** Sia i file *.mpp* che i file Project XML sono gestiti, oltre a 50+ altri formati per import/export.  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti una volta configurata la libreria.

## Cos'è una settimana lavorativa in MS Project?
Una settimana lavorativa definisce le regole del calendario che determinano quando le risorse sono disponibili durante un periodo specifico. Include una data di inizio, una data di fine e intervalli di orario di lavoro giornalieri (ad es., 9 am–5 pm). In MS Project, ogni calendario può contenere più settimane lavorative, consentendo di modellare festività, turni o programmi stagionali.

## Come Aspose.Tasks legge le settimane lavorative da un calendario?
Aspose.Tasks espone la `WorkWeekCollection` di un oggetto `Calendar`. Creando un'istanza `Project`, selezionando il calendario desiderato (per UID o nome) e iterando sulla sua `WorkWeekCollection`, è possibile recuperare l'etichetta di ogni settimana lavorativa, l'intervallo di date effettive e gli slot giornalieri dettagliati di orario di lavoro. L'API gestisce tutte le conversioni data‑ora e rispetta automaticamente le impostazioni del fuso orario del progetto.

## Perché leggere le settimane lavorative in Java da un calendario Microsoft Project?
Leggere le settimane lavorative in modo programmatico elimina il copia‑incolla manuale, garantisce che i sistemi a valle (ERP, HR, reporting) utilizzino le stesse regole di programmazione e assicura coerenza tra più progetti. L'automazione riduce anche gli errori umani e velocizza le pipeline di integrazione, soprattutto quando è necessario elaborare decine di file di progetto ogni notte.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

1. **Java Development Kit (JDK)** – versione 8 o successiva installata.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dal sito ufficiale: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Un **file Project di esempio** (`ReadWorkWeeksInformation.mpp`) posizionato in una cartella nota sul tuo computer.

## Importa i pacchetti
Per prima cosa, importa le classi di cui avremo bisogno per interagire con i calendari e le settimane lavorative:

`Project` rappresenta un file Microsoft Project, `Calendar` fornisce i suoi calendari, `WorkWeek` definisce una settimana lavorativa e `WeekDay` rappresenta un giorno.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Passo 1: imposta la tua directory dei dati
Definisci la cartella che contiene il file `.mpp`. Sostituisci il segnaposto con il percorso reale sul tuo computer:

```java
String dataDir = "Your Data Directory";
```

## Passo 2: crea un'istanza di Project e accedi al calendario
La classe `Project` rappresenta un file Microsoft Project e fornisce l'accesso alle sue strutture dati, inclusi calendari, attività e risorse.  
Istanzia un oggetto `Project`, scegli il calendario desiderato (per UID) e ottieni la sua `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Suggerimento:** Se non sei sicuro dell'UID del calendario, itera su `project.getCalendars()` e stampa prima il nome e l'UID di ogni calendario.

## Passo 3: itera attraverso le settimane lavorative
La classe `WorkWeek` incapsula una definizione di settimana lavorativa, contenendo le date di inizio/fine e le impostazioni di orario giornaliero.  
Scorri ogni `WorkWeek` per visualizzare il suo nome, le date di inizio/fine e gli orari di lavoro giornalieri:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Cosa vedrai:** La console stampa l'etichetta di ogni settimana lavorativa (ad es., “Standard”), il suo intervallo di date effettive, e puoi approfondire le ore di lavoro esatte per ogni giorno.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| `NullPointerException` durante l'accesso a `calendar` | UID errato o il calendario non esiste | Verifica l'UID con `project.getCalendars().size()` e elenca prima i calendari disponibili. |
| Nessun output per le settimane lavorative | Il calendario selezionato non ha settimane lavorative personalizzate (usa quelle predefinite) | Usa il calendario predefinito (`project.getDefaultCalendar()`) o crea una settimana lavorativa programmaticamente. |
| Il formato della data sembra strano | `System.out.println` utilizza il formato predefinito di `java.util.Date` | Applica un `SimpleDateFormat` per formattare le date secondo necessità. |

## Domande frequenti
**Q: Posso modificare le informazioni delle settimane lavorative usando Aspose.Tasks per Java?**  
A: Sì. L'API fornisce `addWorkWeek()`, `removeWorkWeek()` e i setter delle proprietà per cambiare nomi, date e orari di lavoro.

**Q: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?**  
A: Assolutamente. Supporta file MPP da Project 98 fino alle ultime versioni, così come i file Project XML.

**Q: Posso integrare Aspose.Tasks con altri framework Java?**  
A: Sì. La libreria è pure Java, quindi può essere usata insieme a Spring, Jakarta EE o qualsiasi altro framework.

**Q: È disponibile una versione di prova per Aspose.Tasks?**  
A: Sì, puoi scaricare una prova gratuita di 30 giorni dal sito ufficiale: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Dove posso trovare supporto per Aspose.Tasks?**  
A: Il forum della community Aspose è il posto migliore: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2026-08-13  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Aggiungi calendario al progetto con Aspose.Tasks per Java](/tasks/java/calendars/create/)
- [Recupera le eccezioni del calendario con Aspose.Tasks – tutorial java di asp tasks](/tasks/java/calendar-exceptions/retrieve/)
- [Come impostare il calendario e definire i giorni della settimana in MS Project con Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}