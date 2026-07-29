---
date: 2026-07-29
description: Scopri come programmare i giorni non lavorativi creando un calendario
  di progetto con Aspose.Tasks for Java, definendo le eccezioni dei giorni feriali
  e gestendo i programmi delle festività.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Programmare giorni non lavorativi – Creare calendario di progetto Aspose
og_description: Programma i giorni non lavorativi utilizzando Aspose.Tasks for Java.
  Scopri come definire i giorni feriali, aggiungere eccezioni al calendario e gestire
  i programmi delle festività in modo efficiente.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Programmare giorni non lavorativi – Creare calendario di progetto Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Programmare giorni non lavorativi – Creare calendario di progetto Aspose
url: /it/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pianifica giorni non lavorativi – Crea calendario di progetto Aspose

### Introduzione
Quando è necessario **pianificare giorni non lavorativi** per un progetto, è fondamentale poter modellare festività, turni speciali o chiusure temporanee direttamente nel piano di progetto. Aspose.Tasks for Java ti offre il pieno controllo sulle definizioni del calendario, consentendoti di aggiungere eccezioni che rispecchiano i programmi del mondo reale. In questo tutorial percorreremo i passaggi esatti per definire i giorni della settimana per le eccezioni del calendario, così le tempistiche del tuo progetto rimarranno accurate e affidabili. Alla fine vedrai anche come questo si inserisce in una più ampia strategia di **pianificazione dei giorni non lavorativi** per qualsiasi progetto aziendale.

## Risposte rapide
- **Cosa significa “pianificare giorni non lavorativi”?**  
  Significa utilizzare Aspose.Tasks per creare un calendario che segna date specifiche come non lavorative, influenzando automaticamente le date delle attività.  
- **Ho bisogno di una licenza per eseguire l'esempio?**  
  Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quali IDE sono supportati?**  
  IntelliJ IDEA, Eclipse, NetBeans, o qualsiasi IDE che supporti Java 8+.  
- **Posso aggiungere più eccezioni allo stesso calendario?**  
  Sì – è possibile aggiungere quanti `CalendarException` oggetti necessari.  
- **In quali formati di file posso salvare il progetto?**  
  XML, MPP e diversi altri formati supportati da Aspose.Tasks.  

## Cos'è un calendario di progetto in Aspose.Tasks?
Il **calendario di progetto** è l'oggetto di livello superiore di Aspose.Tasks che definisce i giorni e le ore lavorative per un progetto. Influenza direttamente le date di inizio/fine delle attività, l'allocazione delle risorse e i calcoli complessivi del programma. Personalizzando un calendario, garantisci che il programma rispetti vincoli reali come le festività aziendali o le politiche di lavoro nei fine settimana.

## Perché definire i giorni della settimana per le eccezioni del calendario?
Definire eccezioni per i giorni della settimana garantisce che il motore del progetto tratti quei giorni come non lavorativi, impedendo che le attività vengano programmate automaticamente su di essi e mantenendo la linea temporale allineata ai vincoli reali come festività, finestre di manutenzione o schemi di turni speciali all'interno dell'organizzazione.

- **Tempistiche accurate:** Le attività non saranno collocate in giorni festivi o periodi di blackout.  
- **Pianificazione delle risorse:** Le risorse sono allocate solo nei giorni lavorativi validi, evitando il sovraccarico.  
- **Conformità:** I programmi seguono automaticamente le politiche organizzative o i calendari delle festività legali.  

## Pianificazione dei giorni non lavorativi con eccezioni del calendario
Quando gestisci una **pianificazione dei giorni non lavorativi**, di solito disponi di un elenco master di festività, finestre di manutenzione o altri periodi di blackout. Aggiungere tali date come oggetti `CalendarException` garantisce che ogni calcolo — sia esso un'analisi del percorso critico o il livellamento delle risorse — rispetti automaticamente questi vincoli. Questo approccio elimina le regolazioni manuali delle date e riduce il rischio di deriva del programma.

## Prerequisiti
1. **Java Development Kit (JDK)** – versione 8 o successiva.  
2. **Aspose.Tasks for Java** – scarica dalla pagina ufficiale [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse, NetBeans o qualsiasi editor compatibile con Java.  

## Come pianificare giorni non lavorativi usando le eccezioni del calendario

Carica il tuo progetto, crea un calendario personalizzato e aggiungi oggetti `CalendarException` che segnano i giorni della settimana desiderati come non lavorativi. L'intero processo può essere completato in pochi semplici passaggi, e il calendario risultante influenzerà automaticamente tutta la logica di pianificazione delle attività.

### Guida passo‑passo

### Passo 1: Importa i pacchetti richiesti
Abbiamo bisogno delle classi principali di Aspose.Tasks e del `GregorianCalendar` di Java per la gestione delle date.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Passo 2: Definisci la directory dei dati
Specifica dove verrà salvato il file di progetto generato.

```java
String dataDir = "Your Data Directory";
```

### Passo 3: Crea un'istanza di Project
`Project` è l'oggetto principale che contiene tutti i dati del progetto, incluse attività, risorse e calendari.

```java
Project project = new Project();
```

### Passo 4: Definisci un calendario
`Calendar` rappresenta un programma di tempi lavorativi e non lavorativi all'interno di un progetto.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Passo 5: Definisci l'eccezione per i giorni della settimana
`CalendarException` rappresenta un periodo contrassegnato come non lavorativo in un calendario.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Passo 6: Salva il progetto
Salva il progetto, includendo il calendario personalizzato e la sua eccezione, in un file XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Date di eccezione non applicate** | Assicurati che `setEnteredByOccurrences(false)` e i valori corretti di `FromDate/ToDate` siano impostati. |
| **Il file salvato è vuoto** | Verifica che `dataDir` punti a una cartella scrivibile e che il nome del file termini con `.xml`. |
| **Il calendario non è riflesso nella pianificazione delle attività** | Assegna il calendario alle attività o alle risorse usando `task.setCalendar(cal)` o `resource.setCalendar(cal)`. |

## Domande frequenti

**D: Posso definire più eccezioni per diversi giorni della settimana all'interno dello stesso calendario?**  
R: Sì. Aggiungi ulteriori oggetti `CalendarException` a `cal.getExceptions()` per ogni periodo o regola distinta.

**D: Aspose.Tasks per Java è compatibile con diversi IDE Java?**  
R: Assolutamente. La libreria funziona con IntelliJ IDEA, Eclipse, NetBeans e qualsiasi IDE che supporti progetti Java standard.

**D: Posso personalizzare tipi di eccezione diversi dalle eccezioni giornaliere?**  
R: Sì. Usa `CalendarExceptionType.Weekly`, `Monthly` o `Yearly` per soddisfare le tue esigenze di pianificazione.

**D: Come posso gestire le eccezioni in modo dinamico in base ai requisiti del progetto?**  
R: Crea gli oggetti eccezione programmaticamente — ad esempio, leggi le date delle festività da un database o file di configurazione e crea istanze `CalendarException` in un ciclo.

**D: È disponibile una versione di prova per Aspose.Tasks per Java?**  
R: Sì, puoi scaricare una prova gratuita dalla [pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).

## Conclusione
Seguendo questi passaggi ora sai come **pianificare giorni non lavorativi** creando un calendario di progetto e definendo eccezioni per i giorni della settimana che riflettano accuratamente le festività o i periodi speciali non lavorativi. Una corretta configurazione del calendario è essenziale per programmi realistici, l'allocazione delle risorse e il successo complessivo del progetto. Esplora ulteriormente collegando il calendario personalizzato alle attività o alle risorse e sperimentando altri tipi di eccezione per costruire una **pianificazione dei giorni non lavorativi** completa per qualsiasi progetto.

---

**Ultimo aggiornamento:** 2026-07-29  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose

## Tutorial correlati

- [Aggiungi calendario al progetto con Aspose.Tasks per Java](/tasks/java/calendars/create/)
- [Crea eccezione di calendario Aspose per Java](/tasks/java/calendar-exceptions/add-remove/)
- [Come impostare il calendario e definire i giorni della settimana in MS Project con Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}