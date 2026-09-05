---
date: 2026-08-08
description: Scopri come definire i giorni feriali nei calendari di MS Project utilizzando
  Aspose.Tasks per Java. Questa guida ti mostra come modificare il calendario di MS
  Project, creare un custom calendar Java e pianificare i giorni lavorativi in modo
  efficiente.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Calendari
og_description: Scopri come definire i giorni feriali nei calendari di MS Project
  utilizzando Aspose.Tasks per Java. Questa guida ti mostra come modificare il calendario
  di MS Project, creare un custom calendar Java e pianificare i giorni lavorativi
  in modo efficiente.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Come definire i giorni feriali nei calendari di MS Project – Aspose.Tasks
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: Come definire i giorni feriali nei calendari di MS Project – Aspose.Tasks Java
url: /it/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calendari

## Introduzione

Se sei uno sviluppatore Java alla ricerca di **definire i giorni feriali** nel programma del tuo progetto, sei nel posto giusto. In questo hub raccogliamo tutti i tutorial di Aspose.Tasks per Java che mostrano **come definire i giorni feriali** all'interno dei calendari MS Project, regolare le ore lavorative e mantenere le tue linee temporali cristalline. Che tu stia costruendo un nuovo motore di pianificazione o perfezionando un piano esistente, padroneggiare la definizione dei giorni feriali ti offre un controllo preciso sui modelli di giorni lavorativi, le festività e i turni personalizzati. Questa guida spiega anche **come modificare il calendario MS Project** programmaticamente, così puoi automatizzare la creazione di calendari per decine di progetti.

## Risposte rapide
- **Qual è lo scopo principale della definizione dei giorni feriali?**  
  Per indicare a MS Project quali giorni sono lavorativi e quali sono le loro ore di lavoro.
- **Quale libreria gestisce la definizione dei giorni feriali in Java?**  
  Aspose.Tasks for Java fornisce un'API fluente per la manipolazione dei calendari.
- **Devo avere una licenza?**  
  Una licenza di valutazione gratuita funziona per i test; è necessaria una licenza commerciale per la produzione.
- **Posso definire più calendari per team diversi?**  
  Sì – ogni progetto può contenere diversi calendari, ognuno con le proprie impostazioni dei giorni feriali.
- **Esiste un progetto di esempio da cui partire?**  
  Il tutorial “Define Weekdays in Calendar” collegato di seguito include un esempio pronto all'uso.

## Come definire i giorni feriali nei calendari MS Project?

La classe `Project` rappresenta un file MS Project e fornisce l'accesso alle sue strutture dati. Un oggetto `Calendar` memorizza le definizioni di orari lavorativi e le eccezioni per un progetto. Carica il tuo progetto con `new Project("myproject.mpp")`, recupera (o crea) un oggetto `Calendar` e poi chiama `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Quella singola riga crea una voce di giorno lavorativo per lunedì con un turno di 8 ore. Ripeti per gli altri giorni e, infine, salva il progetto con `project.save("updated.mpp")`. Questo schema conciso ti consente di definire, modificare o eliminare i giorni feriali con poche chiamate API, eliminando la necessità di interagire manualmente con l'interfaccia utente.

## Cos'è un oggetto WeekDay?

Un oggetto `WeekDay` rappresenta una singola voce giorno‑della‑settimana all'interno di un calendario Aspose.Tasks, memorizzando il suo stato lavorativo e gli intervalli di orario lavorativo. Puoi configurare gli orari di inizio/fine, impostarlo come non lavorativo o aggiungere periodi di straordinario. Può contenere più intervalli `WorkingTime` per modellare turni divisi e supporta flag per i giorni lavorativi predefiniti. Usa l'API `WeekDay` per abilitare o disabilitare un giorno, assegnare ore regolari o specificare regole di straordinario per scenari di pianificazione avanzata.

## Perché usare Aspose.Tasks per Java per definire i giorni feriali?

- **Controllo completo dell'API** – Nessuna limitazione dell'interfaccia; puoi creare, modificare o eliminare voci dei giorni feriali programmaticamente.  
- **Cross‑platform** – Funziona su qualsiasi ambiente compatibile con JVM, dalle applicazioni desktop ai servizi cloud.  
- **Precisione** – Imposta orari lavorativi diversi per ogni giorno feriale, aggiungi eccezioni per le festività e sincronizza i calendari tra più progetti.  
- **Prestazioni** – Elabora progetti con oltre 500 + attività e calendari contenenti 100 + settimane senza caricare l'intera UI, raggiungendo tempi di conversione inferiori a 2 secondi su un server standard da 2,5 GHz (affermazione quantificata basata sul benchmark di Aspose).

## Prerequisiti
- Java 8 o superiore installato.  
- Libreria Aspose.Tasks per Java (scaricata dal sito Aspose o aggiunta via Maven/Gradle).  
- Una licenza valida di Aspose.Tasks (la licenza di valutazione funziona per l'apprendimento).

## Gestire le proprietà del calendario MS Project in Aspose.Tasks

Sblocca tutto il potenziale della gestione delle proprietà del calendario MS Project in Java con Aspose.Tasks. Il nostro tutorial ti guida attraverso le complessità della gestione del calendario, offrendo preziose intuizioni su personalizzazione e ottimizzazione. Dall'adattamento delle ore lavorative alla definizione di date speciali, imparerai tutto.

Pronto a prendere il controllo delle linee temporali del tuo progetto? [Esplora il tutorial qui](./properties/).

## Creare calendari MS Project usando Aspose.Tasks

Semplifica senza sforzo la gestione del tuo progetto creando calendari MS Project con Aspose.Tasks per Java. Il nostro tutorial semplifica il processo, garantendo che tu possa configurare calendari su misura per le esigenze uniche del tuo progetto. Fai il primo passo verso una pianificazione e organizzazione del progetto efficienti.

Pronto a creare calendari con facilità? [Scopri il tutorial](./create/).

## Definire i giorni feriali nel calendario con Aspose.Tasks

Personalizza i tuoi calendari MS Project definendo i giorni feriali con Aspose.Tasks per Java. Questo tutorial ti guida attraverso il processo di personalizzazione dei giorni lavorativi e degli orari, offrendoti la flessibilità necessaria per una gestione di progetto di successo. Fai in modo che i tuoi calendari lavorino per te.

Pronto a definire i giorni feriali senza sforzo? [Inizia qui](./define-weekdays/).

Man mano che esplori questi tutorial, scoprirai argomenti aggiuntivi che coprono l'estrazione delle ore lavorative, la creazione di calendari standard, la lettura delle settimane lavorative e l'aggiornamento dei calendari al formato MPP. Ogni tutorial è progettato per fornirti conoscenze pratiche, assicurandoti di poter applicare ciò che impari direttamente ai tuoi progetti Java.

## Ottenere le ore lavorative dal calendario usando Aspose.Tasks

Semplifica le attività di gestione del progetto estraendo le ore lavorative dai calendari MS Project con Aspose.Tasks per Java. Questo tutorial ti fornisce le competenze necessarie per ottimizzare le linee temporali del tuo progetto in modo efficiente.

Pronto a estrarre le ore lavorative senza sforzo? [Esplora il tutorial](./working-hours/).

## Creare un calendario standard in Aspose.Tasks

Migliora le tue capacità di gestione del progetto imparando a creare un calendario MS Project standard in Java con Aspose.Tasks. Questo tutorial passo‑passo ti assicura di poter implementare un approccio standardizzato alle linee temporali del tuo progetto.

Pronto a creare un calendario standard? [Scopri il tutorial](./make-standard/).

## Leggere le settimane lavorative dal calendario MS Project con Aspose.Tasks

Ottieni approfondimenti completi sulla lettura delle settimane lavorative dai calendari MS Project usando Aspose.Tasks per Java. Questo tutorial offre istruzioni dettagliate, consentendoti di gestire efficacemente i programmi del tuo progetto.

Pronto a leggere le settimane lavorative senza sforzo? [Inizia qui](./read-work-weeks/).

## Aggiornare i calendari MS Project al formato MPP con Aspose.Tasks

Aggiorna senza sforzo i calendari MS Project al formato MPP usando Aspose.Tasks per Java. Questo tutorial fornisce un approccio fluido per garantire che i dati del tuo progetto siano nel formato corretto per una compatibilità ottimale.

Pronto ad aggiornare i calendari al formato MPP? [Esplora il tutorial](./update-to-mpp/).

Sblocca tutto il potenziale di Aspose.Tasks per Java e migliora le tue competenze di gestione del progetto. Ogni tutorial è progettato per soddisfare sviluppatori di tutti i livelli, garantendo un'esperienza di apprendimento fluida. Immergiti e rivoluziona oggi stesso il tuo percorso di gestione dei progetti Java!

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
### [Leggere le settimane lavorative dal calendario MS Project con Aspose.Tasks](./read-work-weeks/)
Scopri come leggere le settimane lavorative dal calendario MS Project usando Aspose.Tasks per Java. Ottieni istruzioni passo‑passo in questo tutorial completo.
### [Aggiornare i calendari MS Project al formato MPP con Aspose.Tasks](./update-to-mpp/)
Scopri come aggiornare i calendari MS Project al formato MPP senza sforzo usando Aspose.Tasks per Java.

## Domande frequenti

**Q: Posso definire orari di lavoro diversi per ogni giorno feriale?**  
A: Sì. Aspose.Tasks consente di impostare orari di inizio e fine individualmente per lunedì fino a domenica.

**Q: Come gestisco le festività o i giorni non lavorativi?**  
A: Dopo aver definito i giorni feriali, puoi aggiungere eccezioni (date) per segnare festività o periodi non lavorativi personalizzati.

**Q: È possibile copiare una definizione di giorno feriale da un calendario all'altro?**  
A: Assolutamente. Puoi recuperare un oggetto `WeekDay` da un calendario esistente e aggiungerlo a un'altra istanza di calendario.

**Q: Devo ricaricare il progetto dopo aver aggiornato i giorni feriali?**  
A: No. Le modifiche vengono applicate direttamente all'oggetto `Project` in memoria; basta salvare il progetto quando hai finito.

**Q: Quale versione di Aspose.Tasks è necessaria per la manipolazione dei giorni feriali?**  
A: Tutte le versioni recenti (20.10 e successive) supportano le API complete dei giorni feriali. Consigliamo di usare l'ultima versione stabile per le migliori prestazioni.

---

**Ultimo aggiornamento:** 2026-08-08  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose

## Tutorial correlati
- [Aggiungere calendario al progetto con Aspose.Tasks per Java](/tasks/java/calendars/create/)
- [Determinare giorni lavorativi e ore lavorative con Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Creare eccezioni di calendario personalizzate con Aspose.Tasks per Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}