---
date: 2026-08-03
description: Scopri come creare un calendario ms project, aggiungere il calendario
  a un progetto e salvare il progetto come XML utilizzando Aspose.Tasks per Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Aggiungi calendario al progetto usando Aspose.Tasks
og_description: Crea un calendario ms project in modo programmatico usando Aspose.Tasks
  per Java. Aggiungi calendari, personalizza i programmi e esporta in XML in pochi
  minuti.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Crea calendario ms project con Aspose.Tasks per Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Crea calendario ms project con Aspose.Tasks per Java
url: /it/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea calendario ms project con Aspose.Tasks per Java

## Introduzione
Nei moderni flussi di lavoro di project‑management, la possibilità di **creare un calendario ms project** programmaticamente può far risparmiare ore di modifica manuale. Aspose.Tasks per Java ti offre un'API pulita e type‑safe per manipolare i file Microsoft Project senza mai aprire il client desktop. In questo tutorial imparerai come aggiungere un calendario, come creare un calendario MS Project e come salvare il progetto come XML—tutto con poche righe di codice Java.

## Risposte rapide
- **Cosa significa “create ms project calendar”?**  
  Significa inserire una nuova definizione di orario di lavoro (calendario) in un file Microsoft Project tramite codice.  
- **Quale libreria gestisce questo?**  
  Aspose.Tasks per Java fornisce la classe `Calendar` e il contenitore `Project` per gestire i calendari.  
- **Ho bisogno di una licenza?**  
  Una licenza di valutazione temporanea funziona per i test; è necessaria una licenza completa per l'uso in produzione.  
- **Posso salvare il file come XML?**  
  Sì—usa `SaveFileFormat.Xml` per esportare il progetto come file XML.  
- **Quali sono i prerequisiti?**  
  Java JDK 8+ e il JAR di Aspose.Tasks per Java nel tuo classpath.

## Cos'è create ms project calendar?
Creare un calendario MS Project significa aggiungere programmaticamente una nuova definizione di calendario a un file Project, specificando i giorni lavorativi, le eccezioni e le ore di lavoro giornaliere, quindi assegnare quel calendario a attività, risorse o all'intero progetto affinché i calcoli di pianificazione rispettino il tempo di lavoro definito.

## Perché usare Aspose.Tasks per Java per aggiungere un calendario al progetto?
Dovresti usare Aspose.Tasks per Java perché fornisce un'API completamente type‑safe che funziona senza Microsoft Project installato, supporta tutte le principali versioni di Project (2007‑2021, coprendo più di 5 rilasci) e può esportare in XML, MPP e **10+** altri formati, consentendo la creazione automatizzata di calendari in blocco su qualsiasi server.

## Prerequisiti
- **Java Development Kit (JDK) 8 o più recente** installato e configurato.  
- **Aspose.Tasks for Java** library – scarica dal [sito ufficiale](https://releases.aspose.com/tasks/java/) e aggiungi il JAR al classpath del tuo progetto.  
- Un IDE o uno strumento di build (Maven/Gradle) a tua scelta.

## Guida passo‑passo

### Passo 1: importa il pacchetto Aspose.Tasks richiesto
Per prima cosa, porta le classi di Aspose.Tasks nello scope in modo da poter lavorare con progetti e calendari.

```java
import com.aspose.tasks.*;
```

### Passo 2: imposta il percorso della directory dei dati
Definisci dove verrà scritto il file di progetto generato. Sostituisci il segnaposto con un percorso assoluto o relativo sulla tua macchina.

```java
String dataDir = "Your Data Directory";
```

### Passo 3: crea una nuova istanza di Project
`Project` è la classe principale che rappresenta in memoria un file Microsoft Project.

```java
Project prj = new Project();
```

### Passo 4: definisci i calendari da aggiungere
`Calendar` definisce un programma con giorni lavorativi, eccezioni e orari di lavoro per un progetto.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Suggerimento professionale:** Dopo aver aggiunto un calendario, puoi personalizzare i suoi giorni lavorativi con `cal1.getWeekDays().add(...)` e impostare le ore di lavoro giornaliere usando `cal1.getBaseCalendar().setWorkingTime(...)`.

### Passo 5: salva il progetto (salva il progetto come XML)
`SaveFileFormat.Xml` indica ad Aspose.Tasks di scrivere il progetto in formato XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Passo 6: visualizza un messaggio di completamento
Fai sapere all'utente che l'operazione è terminata con successo.

```java
System.out.println("Process completed Successfully");
```

Seguendo questi sei passaggi concisi, hai aggiunto con successo **un calendario a un progetto** e salvato il risultato come file XML.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **`NullPointerException` on `prj.getCalendars()`** | L'oggetto Project non è stato inizializzato correttamente. | Assicurati che `new Project()` sia chiamato prima di accedere ai calendari. |
| **File not found when saving** | `dataDir` punta a una cartella inesistente. | Crea prima la directory o usa un percorso assoluto. |
| **Calendar name appears as “no info”** | Sono stati usati nomi segnaposto nel campione. | Sostituiscili con nomi significativi che riflettano il programma (ad es., “Calendario Festività USA”). |
| **Saved XML cannot be opened in MS Project** | Uso di una versione obsoleta di Aspose.Tasks. | Aggiorna all'ultima versione di Aspose.Tasks per Java. |

## Domande frequenti

**D: Aspose.Tasks può gestire calendari complessi con più eccezioni?**  
Sì – dopo aver aggiunto un calendario puoi definire eccezioni, ore di lavoro e giorni non lavorativi usando le classi `WeekDay` e `Exception`.

**D: È possibile assegnare il nuovo calendario a task specifici?**  
Assolutamente. Recupera un task tramite `prj.getRootTask().getChildren().add("Task Name")` e imposta `task.set(Tsk.CALENDAR, cal3);`.

**D: La libreria supporta il salvataggio in altri formati come MPP?**  
Sì. Sostituisci `SaveFileFormat.Xml` con `SaveFileFormat.Mpp` o `SaveFileFormat.P6` secondo necessità; Aspose.Tasks supporta **12** formati di output.

**D: Ho bisogno di una licenza per le build di sviluppo?**  
Una licenza di valutazione temporanea è sufficiente per i test; è necessaria una licenza completa per le distribuzioni in produzione.

**D: Dove posso ottenere aiuto se riscontro problemi?**  
Il forum della community di Aspose.Tasks è una risorsa eccellente: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2026-08-03  
**Testato con:** Aspose.Tasks for Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come definire i giorni della settimana nei calendari MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Come impostare il calendario del progetto Java con Aspose.Tasks](/tasks/java/calendars/properties/)
- [Crea eccezioni di calendario personalizzate con Aspose.Tasks per Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}