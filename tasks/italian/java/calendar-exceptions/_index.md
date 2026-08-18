---
date: 2026-08-18
description: Crea facilmente eccezioni personalizzate del calendario, integra il calendario
  di MS Project e gestisci, definisci, manipola e recupera le eccezioni del calendario
  nei progetti Java con Aspose.Tasks. Ottimizza i flussi di lavoro del progetto per
  una gestione efficiente.
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: Eccezioni del calendario
og_description: Scopri come creare eccezioni del calendario, gestire il calendario
  del progetto e impostare giorni non lavorativi in Java usando Aspose.Tasks. Guida
  rapida per gli sviluppatori.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Come creare eccezioni del calendario con Aspose.Tasks per Java
schemas:
- author: Aspose
  dateModified: '2026-08-18'
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
title: Come creare eccezioni del calendario con Aspose.Tasks per Java
url: /it/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare eccezioni del calendario con Aspose.Tasks per Java

## Introduzione

`Aspose.Tasks` è una libreria Java che consente la creazione, manipolazione e conversione programmatica di file Microsoft Project. In questo tutorial imparerai a **creare eccezioni del calendario**—periodi personalizzati non lavorativi che sovrascrivono il calendario predefinito di un progetto. Un controllo preciso sui giorni lavorativi e non lavorativi è essenziale per previsioni di programmazione accurate, allocazione delle risorse e conformità alle festività regionali. Alla fine di questa guida saprai anche come **integrare un calendario MS Project** nella tua applicazione Java e recuperare o modificare le sue eccezioni.

## Risposte rapide
- **Cosa posso ottenere?** Creare, modificare e recuperare eccezioni personalizzate del calendario in progetti Java.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (ultima versione stabile).  
- **È necessaria una licenza?** Sì, è richiesta una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso lavorare con file MS Project?** Assolutamente – è possibile importare, modificare ed esportare i dati del calendario di MS Project.  
- **È necessaria qualche configurazione speciale?** Basta aggiungere il JAR di Aspose.Tasks al classpath e importare le classi rilevanti.

## Come creare eccezioni personalizzate del calendario in Aspose.Tasks per Java?

La classe `Project` rappresenta un file Microsoft Project e fornisce l'accesso al suo contenuto. L'oggetto `Calendar` definisce i periodi lavorativi e non lavorativi per il progetto. Il metodo `addException()` aggiunge una nuova eccezione del calendario al calendario.

Carica il progetto target con `Project project = new Project("example.mpp")`, ottieni il suo oggetto `Calendar` e chiama `addException()` con l'intervallo di date desiderato e le impostazioni di orario di lavoro. Questo modello a due passaggi crea immediatamente una nuova eccezione e la persiste quando salvi il progetto. Per festività ricorrenti, configura il `RecurrencePattern` sull'eccezione prima di salvare.

Creare eccezioni del calendario in questo modo ti consente di **impostare giorni non lavorativi** con precisione, sia che si tratti di chiusure occasionali sia di festività annuali. Dopo aver aggiunto l'eccezione, puoi chiamare `project.save("updated.mpp")` per scrivere le modifiche su disco.

### Panoramica dei passaggi
1. Carica il file del progetto.  
2. Recupera o crea un'istanza di `Calendar`.  
3. Definisci l'intervallo di date e l'orario di lavoro dell'eccezione.  
4. (Opzionale) Configura la ricorrenza per le festività annuali.  
5. Salva il progetto.

## Gestire le eccezioni del calendario in Aspose.Tasks
[Learn how to add and remove calendar exceptions in Aspose.Tasks for Java efficiently](./add-remove/). When it comes to project management, flexibility is key. Aspose.Tasks empowers you to effortlessly manage calendar exceptions, allowing for dynamic adjustments to project timelines. This tutorial provides a step‑by‑step guide, ensuring you grasp the process efficiently. Discover how to enhance your project management workflows with ease.

## Definire i giorni feriali per le eccezioni del calendario con Aspose.Tasks
[Master the art of defining weekdays for calendar exceptions in Java projects](./define-weekdays/) using Aspose.Tasks. Accurate project scheduling requires meticulous attention to detail. With Aspose.Tasks, you can precisely define weekdays for calendar exceptions, ensuring your projects align with specific timelines seamlessly. This tutorial equips you with the knowledge to optimize scheduling, giving you control over project timelines.

## Gestire le occorrenze nelle eccezioni del calendario usando Aspose.Tasks
[Effectively handle calendar exceptions in Java projects](./handle-occurrences/) with Aspose.Tasks for Java. Project management is a dynamic process, often requiring adjustments to account for unforeseen occurrences. Aspose.Tasks empowers you to handle calendar exceptions effectively, providing a streamlined approach to project management. Learn the art of managing project uncertainties with ease through this detailed tutorial.

## Recuperare le eccezioni del calendario con Aspose.Tasks
[Learn how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java](./retrieve/). Seamlessly integrate calendar exceptions into your project management process with Aspose.Tasks. This tutorial guides you through the step‑by‑step process of retrieving calendar exceptions, ensuring a smooth and efficient integration into your projects. Unlock the power of Aspose.Tasks to enhance your project management capabilities.

## Come integrare il calendario MS Project con Aspose.Tasks?

La classe `Project` carica un file Microsoft Project, esponendo i suoi calendari e altri dati del progetto. Importa un file MS Project esistente usando `new Project("source.mpp")`; la libreria carica automaticamente il suo calendario predefinito e le eventuali eccezioni personalizzate. Puoi quindi leggere, modificare o unire tali eccezioni prima di salvare nuovamente il progetto su disco. Questo approccio ti consente di **modificare i dati del calendario MS Project** programmaticamente senza interventi manuali nell'interfaccia di MS Project.

## Casi d'uso comuni
- **Pianificazione delle festività** – Definisci le festività nazionali come giorni non lavorativi su più progetti.  
- **Lavoro a turni** – Configura settimane lavorative personalizzate per team che operano con orari non standard.  
- **Controllo delle fasi di progetto** – Blocca periodi in cui non deve essere programmato alcun lavoro, come finestre di manutenzione.  
- **Migrazione legacy** – Importa calendari da file MS Project più vecchi e regolali programmaticamente.

## Suggerimenti e migliori pratiche
- **Pro tip:** Recupera sempre il calendario esistente prima di aggiungere nuove eccezioni per evitare duplicati.  
- **Warning:** Modificare un calendario già assegnato alle attività può spostare le date delle attività; ricalcola il programma dopo le modifiche.  
- **Performance:** Raggruppa più aggiornamenti di eccezioni in un'unica transazione per ridurre il carico I/O del file. Aspose.Tasks elabora file fino a 500 MB senza caricare l'intero documento in memoria, gestendo oltre 50 chiamate API correlate al calendario al secondo su hardware server tipico.

## Tutorial sulle eccezioni del calendario
### [Gestire le eccezioni del calendario in Aspose.Tasks](./add-remove/)
Learn how to add and remove calendar exceptions in Aspose.Tasks for Java efficiently. Enhance project management workflows effortlessly.
### [Definire i giorni feriali per le eccezioni del calendario con Aspose.Tasks](./define-weekdays/)
Learn how to define weekdays for calendar exceptions in Java projects using Aspose.Tasks for accurate project scheduling.
### [Gestire le occorrenze nelle eccezioni del calendario usando Aspose.Tasks](./handle-occurrences/)
Learn how to handle calendar exceptions effectively in Java projects with Aspose.Tasks for Java. Streamline your project management process now.
### [Recuperare le eccezioni del calendario con Aspose.Tasks](./retrieve/)
Learn how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java. Step-by-step tutorial for seamless integration.

## Domande frequenti

**Q: Posso modificare le eccezioni del calendario dopo che un progetto è già stato pubblicato?**  
A: Sì. Usa le API add‑remove e define‑weekdays per aggiornare il calendario, quindi salva nuovamente il file di progetto.

**Q: Aspose.Tasks supporta le eccezioni ricorrenti (ad esempio, ogni primo lunedì del mese)?**  
A: Assolutamente. Il tutorial “handle occurrences” spiega come impostare i modelli ricorrenti.

**Q: Come posso garantire che il mio calendario personalizzato sia usato da tutte le attività nel progetto?**  
A: Assegna il calendario al calendario predefinito del progetto o impostalo esplicitamente su ogni attività tramite la proprietà `Calendar`.

**Q: È possibile unire i calendari da più file MS Project?**  
A: Sì. Recupera ogni calendario, combina le loro eccezioni programmaticamente, quindi assegna il calendario unito al progetto di destinazione.

**Q: Quale versione di Aspose.Tasks è necessaria per queste funzionalità?**  
A: Tutte le funzionalità sono disponibili nell'attuale versione stabile di Aspose.Tasks per Java (2025.x).

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Tutorial correlati

- [Crea calendario di progetto Aspose – Definisci i giorni feriali per le eccezioni del calendario](/tasks/java/calendar-exceptions/define-weekdays/)
- [Recupera le eccezioni del calendario con Aspose.Tasks – tutorial java asp tasks](/tasks/java/calendar-exceptions/retrieve/)
- [Crea eccezione del calendario Aspose per Java](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}