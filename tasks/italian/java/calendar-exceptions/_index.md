---
date: 2026-11-06
description: Crea facilmente eccezioni di calendario personalizzate, integra il calendario
  di MS Project e gestisci, definisci, elabora e recupera le eccezioni di calendario
  nei progetti Java con Aspose.Tasks. Ottimizza i flussi di lavoro del progetto per
  una gestione efficiente.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Eccezioni di calendario
og_description: Scopri come creare eccezioni di calendario in Java usando Aspose.Tasks.
  Gestisci i calendari di progetto, imposta giorni non lavorativi e modifica i calendari
  di MS Project in modo efficiente.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Crea eccezioni di calendario con Aspose.Tasks per Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Come creare eccezioni di calendario con Aspose.Tasks per Java
url: /it/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare eccezioni del calendario con Aspose.Tasks per Java

## Introduzione

`Aspose.Tasks` è una libreria Java che consente la creazione, manipolazione e conversione programmatica di file Microsoft Project. In questo tutorial imparerai a **creare eccezioni del calendario** — periodi non lavorativi personalizzati che sovrascrivono il calendario predefinito di un progetto. Un controllo preciso sui giorni lavorativi e non lavorativi è essenziale per previsioni accurate di programmazione, allocazione delle risorse e conformità alle festività regionali. Alla fine di questa guida saprai anche come **integrare un calendario MS Project** nella tua applicazione Java e recuperare o modificare le sue eccezioni.

## Risposte rapide
- **Cosa posso ottenere?** Creare, modificare e recuperare eccezioni di calendario personalizzate nei progetti Java.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (ultima versione stabile).  
- **È necessaria una licenza?** Sì, è necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso lavorare con file MS Project?** Assolutamente — è possibile importare, modificare ed esportare i dati del calendario di MS Project.  
- **È necessaria qualche configurazione speciale?** Basta aggiungere il JAR di Aspose.Tasks al classpath e importare le classi pertinenti.

## Come creare eccezioni di calendario personalizzate in Aspose.Tasks per Java?

Per creare eccezioni di calendario personalizzate in Aspose.Tasks per Java, carica il progetto di destinazione, recupera il suo Calendar, definisci le date di inizio e fine dell'eccezione con l'orario di lavoro desiderato, opzionalmente imposta un modello di ricorrenza, quindi salva il progetto. Questa sequenza aggiunge l'eccezione immediatamente e la persiste nel file .mpp.

La classe `Project` è l'oggetto principale di Aspose.Tasks che modella un intero file Microsoft Project. La classe `Project` rappresenta un file Microsoft Project e fornisce l'accesso al suo contenuto. L'oggetto `Calendar` definisce i periodi lavorativi e non lavorativi per il progetto. La classe `Calendar` è il contenitore di tutte le regole di orario di lavoro, incluse le eccezioni. Il metodo `addException()` aggiunge una nuova eccezione di calendario al calendario. `addException()` è un'API a chiamata singola che registra un periodo non lavorativo per l'intervallo di date specificato.

Carica il progetto di destinazione con `Project project = new Project("example.mpp")`, ottieni il suo oggetto `Calendar` e chiama `addException()` con l'intervallo di date e le impostazioni di orario desiderate. Questo modello a due passaggi crea una nuova eccezione istantaneamente e la persiste quando salvi il progetto. Per festività ricorrenti, configura il `RecurrencePattern` sull'eccezione prima di salvare.

Creare le eccezioni di calendario in questo modo ti consente di **impostare giorni non lavorativi** con precisione, sia che si tratti di chiusure occasionali sia di festività annuali. Dopo aver aggiunto l'eccezione, puoi chiamare `project.save("updated.mpp")` per scrivere le modifiche su disco.

### Panoramica dei passaggi
1. Carica il file del progetto.  
2. Recupera o crea un'istanza di `Calendar`.  
3. Definisci l'intervallo di date dell'eccezione e l'orario di lavoro.  
4. (Opzionale) Configura la ricorrenza per le festività annuali.  
5. Salva il progetto.

## Gestire le eccezioni del calendario in Aspose.Tasks
[Scopri come aggiungere e rimuovere le eccezioni del calendario in Aspose.Tasks per Java in modo efficiente](./add-remove/). Quando si tratta di gestione dei progetti, la flessibilità è fondamentale. Aspose.Tasks ti consente di gestire facilmente le eccezioni del calendario, permettendo aggiustamenti dinamici alle tempistiche del progetto. Questo tutorial fornisce una guida passo‑passo, assicurandoti di comprendere il processo in modo efficiente. Scopri come migliorare i flussi di lavoro della gestione dei progetti con facilità.

## Definire i giorni feriali per le eccezioni del calendario con Aspose.Tasks
[Padroneggia l'arte di definire i giorni feriali per le eccezioni del calendario nei progetti Java](./define-weekdays/) usando Aspose.Tasks. Una pianificazione accurata del progetto richiede un'attenzione meticolosa ai dettagli. Con Aspose.Tasks, puoi definire con precisione i giorni feriali per le eccezioni del calendario, garantendo che i tuoi progetti si allineino senza problemi a tempistiche specifiche. Questo tutorial ti fornisce le conoscenze per ottimizzare la pianificazione, offrendoti il controllo sulle tempistiche del progetto.

## Gestire le occorrenze nelle eccezioni del calendario usando Aspose.Tasks
[Gestire efficacemente le eccezioni del calendario nei progetti Java](./handle-occurrences/) con Aspose.Tasks per Java. La gestione dei progetti è un processo dinamico, spesso richiede aggiustamenti per tenere conto di eventi imprevisti. Aspose.Tasks ti consente di gestire efficacemente le eccezioni del calendario, offrendo un approccio semplificato alla gestione dei progetti. Impara l'arte di gestire le incertezze del progetto con facilità attraverso questo tutorial dettagliato.

## Recuperare le eccezioni del calendario con Aspose.Tasks
[Scopri come recuperare le eccezioni del calendario da MS Project usando Aspose.Tasks per Java](./retrieve/). Integra senza problemi le eccezioni del calendario nel tuo processo di gestione del progetto con Aspose.Tasks. Questo tutorial ti guida attraverso il processo passo‑passo di recupero delle eccezioni del calendario, garantendo un'integrazione fluida ed efficiente nei tuoi progetti. Sblocca il potere di Aspose.Tasks per migliorare le tue capacità di gestione del progetto.

## Come integrare il calendario MS Project con Aspose.Tasks?

Integrare un calendario MS Project con Aspose.Tasks comporta il caricamento del file .mpp sorgente usando la classe Project, l'accesso ai suoi oggetti Calendar predefiniti o personalizzati, la modifica o l'unione delle eccezioni secondo necessità, e quindi il salvataggio del progetto aggiornato. Questo ti consente di lavorare programmaticamente con i calendari MS Project senza interazione manuale dell'interfaccia utente.

La classe `Project` è l'oggetto principale di Aspose.Tasks che modella un intero file Microsoft Project. Importa un file MS Project esistente usando `new Project("source.mpp")`; la libreria carica automaticamente il suo calendario predefinito e le eventuali eccezioni personalizzate. Puoi quindi leggere, modificare o unire quelle eccezioni prima di salvare nuovamente il progetto su disco. Questo approccio ti consente di **modificare i dati del calendario MS Project** programmaticamente senza modifiche manuali nell'interfaccia di MS Project.

## Casi d'uso comuni
- **Pianificazione delle festività** – Definisci le festività nazionali come giorni non lavorativi in più progetti.  
- **Lavoro a turni** – Configura settimane lavorative personalizzate per team che operano con orari non standard.  
- **Controllo delle fasi di progetto** – Blocca periodi in cui non dovrebbe essere programmato alcun lavoro, come le finestre di manutenzione.  
- **Migrazione legacy** – Importa calendari da file MS Project più vecchi e regolali programmaticamente.

## Suggerimenti e migliori pratiche
- **Consiglio professionale:** Recupera sempre il calendario esistente prima di aggiungere nuove eccezioni per evitare duplicati.  
- **Avviso:** Modificare un calendario già assegnato alle attività può spostare le date delle attività; ricalcola il programma dopo le modifiche.  
- **Prestazioni:** Raggruppa più aggiornamenti di eccezioni in un'unica transazione per ridurre il carico I/O dei file. Aspose.Tasks elabora file fino a 1 GB mantenendo l'uso della memoria sotto 200 MB, e può gestire oltre 30 chiamate API correlate al calendario al secondo su hardware server tipico.

## Tutorial sulle eccezioni del calendario
### [Gestire le eccezioni del calendario in Aspose.Tasks](./add-remove/)
Scopri come aggiungere e rimuovere le eccezioni del calendario in Aspose.Tasks per Java in modo efficiente. Migliora i flussi di lavoro della gestione dei progetti senza sforzo.
### [Definire i giorni feriali per le eccezioni del calendario con Aspose.Tasks](./define-weekdays/)
Scopri come definire i giorni feriali per le eccezioni del calendario nei progetti Java usando Aspose.Tasks per una pianificazione accurata del progetto.
### [Gestire le occorrenze nelle eccezioni del calendario usando Aspose.Tasks](./handle-occurrences/)
Scopri come gestire efficacemente le eccezioni del calendario nei progetti Java con Aspose.Tasks per Java. Semplifica ora il tuo processo di gestione del progetto.
### [Recuperare le eccezioni del calendario con Aspose.Tasks](./retrieve/)
Scopri come recuperare le eccezioni del calendario da MS Project usando Aspose.Tasks per Java. Tutorial passo‑passo per un'integrazione senza soluzione di continuità.

## Domande frequenti

**D: Posso modificare le eccezioni del calendario dopo che un progetto è già stato pubblicato?**  
R: Sì. Usa le API add‑remove e define‑weekdays per aggiornare il calendario, quindi salva nuovamente il file del progetto.

**D: Aspose.Tasks supporta le eccezioni ricorrenti (ad esempio, ogni primo lunedì del mese)?**  
R: Assolutamente. Il tutorial “handle occurrences” spiega come impostare modelli ricorrenti.

**D: Come posso garantire che il mio calendario personalizzato sia utilizzato da tutte le attività del progetto?**  
R: Assegna il calendario al calendario predefinito del progetto o impostalo esplicitamente sulla proprietà `Calendar` di ogni attività.

**D: È possibile unire i calendari da più file MS Project?**  
R: Sì. Recupera ogni calendario, combina le loro eccezioni programmaticamente, quindi assegna il calendario unito al progetto di destinazione.

**D: Quale versione di Aspose.Tasks è necessaria per queste funzionalità?**  
R: Tutte le funzionalità sono disponibili nell'attuale versione stabile di Aspose.Tasks per Java (2025.x).

## Tutorial correlati

- [Creare calendario progetto Aspose – Definire i giorni feriali per le eccezioni del calendario](/tasks/java/calendar-exceptions/define-weekdays/)
- [Recuperare le eccezioni del calendario con Aspose.Tasks – tutorial java asp tasks](/tasks/java/calendar-exceptions/retrieve/)
- [Creare eccezione del calendario Aspose per Java](/tasks/java/calendar-exceptions/add-remove/)

**Ultimo aggiornamento:** 2026-11-06  
**Testato con:** Aspose.Tasks per Java 24.11  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}