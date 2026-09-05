---
date: 2026-08-08
description: Scopri come impostare il calendario di MS Project, definire le ore di
  lavoro giornaliere e aggiungere giorni lavorativi nel weekend utilizzando Aspose.Tasks
  per Java. Salva il progetto come XML in poche righe di codice.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Come impostare il calendario di MS Project e definire i giorni feriali
og_description: Imposta il calendario di MS Project, definisci i giorni feriali e
  aggiungi giorni lavorativi nel weekend utilizzando Aspose.Tasks per Java. Segui
  questo tutorial passo‑passo e salva come XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Imposta il calendario di MS Project con Aspose.Tasks – Guida Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Come impostare il calendario di MS Project e definire i giorni feriali
url: /it/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il calendario ms project e definire i giorni feriali

In questo tutorial imparerai **come impostare il calendario ms project** programmaticamente, definire i giorni feriali e configurare giorni lavorativi personalizzati utilizzando la libreria Aspose.Tasks per Java. Che tu stia costruendo un motore di pianificazione, integrando con sistemi ERP, o semplicemente abbia bisogno di generare un piano di progetto senza aprire Microsoft Project, i passaggi seguenti mostrano come creare un calendario, impostare le ore lavorative giornaliere e aggiungere giorni lavorativi nel fine settimana in poche righe di codice.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Tasks for Java.  
- **Posso aggiungere giorni lavorativi nel fine settimana?** Sì – basta contrassegnare sabato e domenica come giorni lavorativi.  
- **Come salvo il progetto?** Chiama `prj.save(..., SaveFileFormat.Xml)`.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per la valutazione; è necessaria una licenza per l'uso in produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore.

## Che cosa significa impostare il calendario ms project?
Impostare il calendario in MS Project determina quali giorni sono considerati giorni lavorativi, il numero di ore lavorative per giorno e eventuali eccezioni speciali come festività o chiusure aziendali. queste informazioni guidano la pianificazione delle attività, l'allocazione delle risorse e le tempistiche complessive del progetto, garantendo che i calcoli rispettino i reali schemi di lavoro dell'organizzazione.

## Perché usare Aspose.Tasks per la manipolazione del calendario?
Aspose.Tasks ti offre il controllo programmatico sui calendari senza avviare l'interfaccia di Microsoft Project. Funziona su qualsiasi sistema operativo che supporta Java, supporta più di 50 formati di input e output, e può elaborare progetti di centinaia di pagine senza caricare l'intero file in memoria, rendendolo ideale per l'automazione lato server.

## Prerequisiti
- **Java Development Kit (JDK) 8+** – scarica dal [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – ottieni l'ultimo JAR dalla [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- Un IDE o uno strumento di build (Maven/Gradle) per aggiungere il JAR di Aspose.Tasks al tuo classpath.

## Importa i pacchetti
Importa le classi che forniscono l'accesso a progetti, calendari e oggetti di tempo lavorativo.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guida passo‑passo

### Passo 1: crea un'istanza di progetto
Istanzia un oggetto `Project`, che rappresenta il file MS Project che manipolerai.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Passo 2: definisci un nuovo calendario
`Calendar` rappresenta un insieme di orari lavorativi, eccezioni e festività per un progetto.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Passo 3: aggiungi i giorni lavorativi standard (lunedì‑giovedì)
`WeekDay` definisce l'orario di lavoro per un giorno specifico della settimana.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Passo 4: aggiungi giorni lavorativi nel fine settimana
Se il tuo progetto si svolge nei fine settimana, aggiungi sabato e domenica come giorni lavorativi regolari. Questo dimostra **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Passo 5: imposta un giorno lavorativo corto personalizzato (venerdì)
Configura il venerdì con un turno mattutino (9 am‑12 pm) e un turno pomeridiano (1 pm‑4 pm) per illustrare **set daily working hours** e un giorno lavorativo corto personalizzato.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Passo 6: salva il progetto come XML
`SaveFileFormat` elenca i formati di file supportati durante il salvataggio di un progetto, come XML o MPP.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Working times not applied** | Assicurati che `setDayWorking(true)` sia chiamato su ogni `WeekDay` personalizzato. |
| **File not found when saving** | Verifica che `dataDir` punti a una cartella esistente e che l'applicazione abbia i permessi di scrittura. |
| **Calendar not reflected in tasks** | Assegna il calendario appena creato a risorse o attività usando `task.setCalendar(cal)`. |

## Domande frequenti

**Q: Posso definire giorni non lavorativi personalizzati usando Aspose.Tasks per Java?**  
A: Sì. Imposta la proprietà `DayWorking` a `false` per qualsiasi `WeekDay` che desideri trattare come giorno non lavorativo.

**Q: Come posso aggiungere festività o eccezioni aziendali?**  
A: Crea oggetti `CalendarException`, specifica le date delle eccezioni e aggiungili a `cal.getExceptions()`.

**Q: La libreria è compatibile con versioni più vecchie di MS Project?**  
A: Assolutamente. Aspose.Tasks supporta i formati MPP, MPT e XML su più versioni di Project.

**Q: Posso modificare un calendario esistente in un progetto importato?**  
A: Carica il progetto con `new Project("existing.mpp")`, recupera il calendario desiderato, apporta le modifiche e salva.

**Q: Aspose.Tasks gestisce anche le attività ricorrenti?**  
A: Sì, è possibile creare e modificare attività ricorrenti usando la classe `RecurringTask`.

## Conclusione
Ora sai **come impostare il calendario ms project**, definire i giorni feriali, aggiungere giorni lavorativi nel fine settimana e configurare un breve orario del venerdì — tutto con Aspose.Tasks per Java. Salva il risultato come XML e integra la logica del calendario in qualsiasi soluzione di gestione progetti basata su Java.

---

**Ultimo aggiornamento:** 2026-08-08  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose

## Tutorial correlati

- [Aggiungi calendario al progetto con Aspose.Tasks per Java](/tasks/java/calendars/create/)
- [Determina giorni lavorativi e ore lavorative con Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Aggiungi festività al calendario e salva come MPP con Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}