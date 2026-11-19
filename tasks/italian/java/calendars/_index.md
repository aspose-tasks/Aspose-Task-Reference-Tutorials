---
date: 2026-11-19
description: Scopri come creare un calendario personalizzato Java usando Aspose.Tasks.
  Questa guida ti mostra come definire i giorni lavorativi, impostare le ore di lavoro
  e modificare i calendari di MS Project programmaticamente.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Calendari
og_description: Scopri come creare un calendario personalizzato Java con Aspose.Tasks.
  Padroneggia la definizione dei giorni lavorativi, l'impostazione delle ore di lavoro
  e la modifica efficiente dei calendari di MS Project.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Come creare un calendario personalizzato Java con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Come creare un calendario personalizzato Java con Aspose.Tasks
url: /it/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calendari

## Introduzione

Se sei uno sviluppatore Java che desidera **creare soluzioni di calendario personalizzate Java**, sei nel posto giusto. Questo hub raccoglie tutti i tutorial di Aspose.Tasks per Java che mostrano come **definire i giorni lavorativi in MS Project**, **impostare le ore lavorative in MS Project**, e regolare programmaticamente le impostazioni del calendario. Che tu stia costruendo un nuovo motore di pianificazione o estendendo un piano esistente, padroneggiare queste API ti offre un controllo preciso sui modelli di giorni lavorativi, festività e turni personalizzati—senza mai aprire l'interfaccia UI di MS Project.

## Risposte rapide
- **Qual è lo scopo principale della definizione dei giorni feriali?**  
  Indicare a MS Project quali giorni sono lavorativi e quali sono le loro ore di lavoro.  
- **Quale libreria gestisce la definizione dei giorni feriali in Java?**  
  Aspose.Tasks for Java fornisce un'API fluida per la manipolazione del calendario.  
- **Ho bisogno di una licenza?**  
  Una licenza di valutazione gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso definire più calendari per team diversi?**  
  Sì – ogni progetto può contenere diversi calendari, ciascuno con le proprie impostazioni dei giorni feriali.  
- **Esiste un progetto di esempio da cui partire?**  
  Il tutorial “Define Weekdays in Calendar” collegato di seguito include un esempio pronto all'uso.

## Come creare un calendario personalizzato Java?

Carica un progetto, crea o recupera un calendario, aggiungi le definizioni dei giorni feriali e salva il file—tutto in poche chiamate API. Questo approccio elimina i passaggi manuali dell'interfaccia UI, ti consente di automatizzare la creazione dei calendari in decine di progetti e garantisce modelli di giorni lavorativi coerenti in tutta l'organizzazione.

## Cos'è la classe Project?

La classe `Project` è l'oggetto centrale per caricare, modificare e salvare i file MS Project. Contiene collezioni di attività, risorse e calendari, esponendo metodi che ti permettono di leggere e modificare ogni aspetto di un progetto in modo programmatico. Utilizzando questa classe, puoi accedere alla collezione di calendari di un progetto, regolare gli orari di lavoro e persistere le modifiche in un file MPP o XML.

## Come definire i giorni feriali nei calendari MS Project?

La classe `Project` rappresenta un file MS Project e fornisce l'accesso alle sue strutture dati. Un oggetto `Calendar` memorizza le definizioni di orario di lavoro e le eccezioni per un progetto. Carica il tuo progetto con `new Project("myproject.mpp")`, recupera (o crea) un oggetto `Calendar`, e poi chiama `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Quella singola riga crea una voce di giorno lavorativo per lunedì con un turno di 8 ore. Ripeti per gli altri giorni e infine salva il progetto con `project.save("updated.mpp")`. Questo schema conciso ti consente di definire, modificare o eliminare i giorni feriali con poche chiamate API, eliminando la necessità di interagire manualmente con l'interfaccia UI.

## Cos'è un oggetto WeekDay?

Un oggetto `WeekDay` rappresenta una singola voce di giorno della settimana all'interno di un calendario. Memorizza se il giorno è lavorativo, gli intervalli di orario di lavoro per quel giorno e flag per il comportamento predefinito. Puoi collegare uno o più intervalli `WorkingTime` per modellare turni divisi, impostare il giorno come non lavorativo o ereditare le impostazioni predefinite dal calendario padre.

## Come definire i giorni lavorativi in MS Project?

Definisci i giorni lavorativi aggiungendo oggetti `WeekDay` alla collezione `WeekDays` di un calendario. Ogni `WeekDay` specifica se il giorno è lavorativo e gli intervalli di tempo considerati ore di lavoro. Ad esempio, per rendere il sabato una mezza giornata, aggiungi un `WeekDay` con un unico `WorkingTime` dalle 10:00 alle 14:00. L'API aggiorna automaticamente i calcoli del programma del progetto.

## Come impostare le ore lavorative in MS Project?

Imposta le ore lavorative creando uno o più intervalli `WorkingTime` per ciascun `WeekDay`. Un `WorkingTime` richiede valori di ora di inizio, minuto di inizio, ora di fine e minuto di fine. Puoi assegnare più intervalli a un singolo giorno per modellare turni divisi (ad esempio, 08:00‑12:00 e 13:00‑17:00). Dopo aver configurato tutti i giorni feriali, chiama `project.save(...)` per persistere le modifiche.

## Perché usare Aspose.Tasks per Java per definire i giorni feriali?

- **Controllo completo dell'API** – Nessuna limitazione dell'interfaccia UI; puoi creare, modificare o eliminare voci dei giorni feriali in modo programmatico.  
- **Cross‑platform** – Funziona su qualsiasi ambiente compatibile con JVM, dalle applicazioni desktop ai servizi cloud.  
- **Precisione** – Imposta orari di lavoro diversi per ogni giorno feriale, aggiungi eccezioni per le festività e sincronizza i calendari tra più progetti.  
- **Prestazioni** – Elabora progetti con oltre 500 attività e calendari contenenti più di 100 settimane senza caricare l'intera UI, raggiungendo tempi di conversione inferiori a 2 secondi su un server standard da 2,5 GHz (affermazione quantificata basata sul benchmark Aspose).  
- **Ampio supporto di formati** – Aspose.Tasks supporta oltre 30 API correlate ai calendari e può importare/esportare più di 20 formati di file, consentendo un'integrazione fluida con le pipeline di dati di progetto esistenti.

## Prerequisiti
- Java 8 o versione successiva installata.  
- Libreria Aspose.Tasks per Java (scaricata dal sito Aspose o aggiunta tramite Maven/Gradle).  
- Una licenza valida di Aspose.Tasks (la licenza di valutazione è sufficiente per l'apprendimento).  

## Gestire le proprietà del calendario MS Project in Aspose.Tasks

Sblocca tutto il potenziale della gestione delle proprietà del calendario MS Project in Java con Aspose.Tasks. Il nostro tutorial ti guida attraverso le complessità della gestione del calendario, offrendo preziose intuizioni su personalizzazione e ottimizzazione. Dall'adattamento delle ore lavorative alla definizione di date speciali, imparerai tutto.

Pronto a prendere il controllo delle tempistiche del tuo progetto? [Esplora il tutorial qui](./properties/).

## Creare calendari MS Project usando Aspose.Tasks

Semplifica senza sforzo la gestione del tuo progetto creando calendari MS Project con Aspose.Tasks per Java. Il nostro tutorial semplifica il processo, garantendo che tu possa configurare calendari su misura per le esigenze uniche del tuo progetto. Fai il primo passo verso una pianificazione e organizzazione del progetto efficiente.

Pronto a creare calendari con facilità? [Scopri il tutorial](./create/).

## Definire i giorni feriali nel calendario con Aspose.Tasks

Personalizza i tuoi calendari MS Project definendo i giorni feriali con Aspose.Tasks per Java. Questo tutorial ti guida nel processo di personalizzazione dei giorni lavorativi e degli orari, offrendoti la flessibilità necessaria per una gestione di progetto di successo. Fai sì che i tuoi calendari lavorino per te.

Pronto a definire i giorni feriali senza sforzo? [Inizia qui](./define-weekdays/).

Mentre esplori questi tutorial, scoprirai argomenti aggiuntivi che coprono l'estrazione delle ore lavorative, la creazione di calendari standard, la lettura delle settimane di lavoro e l'aggiornamento dei calendari al formato MPP. Ogni tutorial è stato realizzato per fornirti conoscenze pratiche, assicurandoti di poter applicare direttamente ciò che impari ai tuoi progetti Java.

## Ottenere le ore lavorative dal calendario usando Aspose.Tasks

Semplifica le attività di gestione del progetto estraendo le ore lavorative dai calendari MS Project con Aspose.Tasks per Java. Questo tutorial ti fornisce le competenze necessarie per ottimizzare efficacemente le tempistiche del tuo progetto.

Pronto a estrarre le ore lavorative senza sforzo? [Esplora il tutorial](./working-hours/).

## Creare un calendario standard in Aspose.Tasks

Migliora le tue capacità di gestione del progetto imparando a creare un calendario MS Project standard in Java con Aspose.Tasks. Questo tutorial passo‑passo ti assicura di poter implementare un approccio standardizzato alle tempistiche del tuo progetto.

Pronto a creare un calendario standard? [Scopri il tutorial](./make-standard/).

## Leggere le settimane di lavoro dal calendario MS Project con Aspose.Tasks

Ottieni approfondimenti completi sulla lettura delle settimane di lavoro dai calendari MS Project usando Aspose.Tasks per Java. Questo tutorial offre istruzioni dettagliate, consentendoti di gestire efficacemente i programmi del tuo progetto.

Pronto a leggere le settimane di lavoro senza sforzo? [Inizia qui](./read-work-weeks/).

## Aggiornare i calendari MS Project al formato MPP con Aspose.Tasks

Aggiorna senza sforzo i calendari MS Project al formato MPP usando Aspose.Tasks per Java. Questo tutorial fornisce un approccio fluido per garantire che i dati del tuo progetto siano nel formato corretto per una compatibilità ottimale.

Pronto ad aggiornare i calendari al formato MPP? [Esplora il tutorial](./update-to-mpp/).

Sblocca tutto il potenziale di Aspose.Tasks per Java e eleva le tue competenze di gestione del progetto. Ogni tutorial è progettato per soddisfare sviluppatori di tutti i livelli, garantendo un'esperienza di apprendimento fluida. Immergiti e rivoluziona il tuo percorso di gestione dei progetti Java oggi!

## Tutorial sui calendari
### [Gestire le proprietà del calendario MS Project in Aspose.Tasks](./properties/)
Scopri come gestire le proprietà del calendario MS Project in Java usando Aspose.Tasks. Questo fornisce una guida passo‑passo per i calendari all'interno delle tue applicazioni Java.
### [Creare calendari MS Project usando Aspose.Tasks](./create/)
Scopri come creare calendari MS Project usando Aspose.Tasks per Java. Semplifica la gestione del progetto con facilità.
### [Definire i giorni feriali nel calendario con Aspose.Tasks](./define-weekdays/)
Scopri come definire i giorni feriali nel calendario MS Project usando Aspose.Tasks per Java. Personalizza i giorni lavorativi e gli orari senza sforzo.
### [Ottenere le ore lavorative dal calendario usando Aspose.Tasks](./working-hours/)
Estrai le ore lavorative dai calendari MS Project facilmente con Aspose.Tasks per Java. Semplifica le attività di gestione del progetto.
### [Creare un calendario standard in Aspose.Tasks](./make-standard/)
Scopri come creare un calendario MS Project standard in Java usando Aspose.Tasks. Potenzia le tue capacità di gestione del progetto con questo tutorial passo‑passo.
### [Leggere le settimane di lavoro dal calendario MS Project con Aspose.Tasks](./read-work-weeks/)
Scopri come leggere le settimane di lavoro dal calendario MS Project usando Aspose.Tasks per Java. Ottieni istruzioni passo‑passo in questo tutorial completo.
### [Aggiornare i calendari MS Project al formato MPP senza sforzo usando Aspose.Tasks per Java](./update-to-mpp/)
Scopri come aggiornare i calendari MS Project al formato MPP senza sforzo usando Aspose.Tasks per Java.

## Domande frequenti

**D: Posso definire ore lavorative diverse per ogni giorno feriale?**  
Sì. Aspose.Tasks ti consente di impostare orari di inizio e fine individualmente per ciascun giorno da lunedì a domenica.

**D: Come gestisco le festività o i giorni non lavorativi?**  
Dopo aver definito i giorni feriali, puoi aggiungere eccezioni (date) per contrassegnare le festività o periodi non lavorativi personalizzati.

**D: È possibile copiare una definizione di giorno feriale da un calendario a un altro?**  
Assolutamente. Puoi recuperare un oggetto `WeekDay` da un calendario esistente e aggiungerlo a un'altra istanza di calendario.

**D: Devo ricaricare il progetto dopo aver aggiornato i giorni feriali?**  
No. Le modifiche sono applicate direttamente all'oggetto `Project` in memoria; basta salvare il progetto quando hai finito.

**D: Quale versione di Aspose.Tasks è necessaria per la manipolazione dei giorni feriali?**  
Tutte le versioni recenti (20.10 e successive) supportano le API complete per i giorni feriali. Consigliamo di utilizzare l'ultima versione stabile per le migliori prestazioni.

---

**Last Updated:** 2026-11-19  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutorial correlati

- [Aggiungere calendario al progetto con Aspose.Tasks per Java](/tasks/java/calendars/create/)
- [Determinare giorni lavorativi e ore lavorative con Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Creare eccezioni di calendario personalizzate con Aspose.Tasks per Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}