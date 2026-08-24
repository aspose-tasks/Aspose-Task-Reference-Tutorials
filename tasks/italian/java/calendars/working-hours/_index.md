---
date: 2026-08-24
description: Scopri come aggiungere il calendario delle festività, determinare i giorni
  lavorativi e calcolare la durata delle attività estraendo le ore lavorative dai
  calendari di MS Project usando Aspose.Tasks for Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Come aggiungere il calendario delle festività e determinare i giorni lavorativi
og_description: Scopri come aggiungere il calendario delle festività, determinare
  i giorni lavorativi e calcolare la durata delle attività estraendo le ore lavorative
  dai calendari di MS Project usando Aspose.Tasks for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Come aggiungere il calendario delle festività e determinare i giorni lavorativi
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Come aggiungere il calendario delle festività e determinare i giorni lavorativi
url: /it/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere un calendario delle festività e determinare i giorni lavorativi

Gestire i calendari di progetto è una parte fondamentale della pianificazione di progetto di successo. In questo tutorial **aggiungerai un calendario delle festività**, **determinerai i giorni lavorativi** per qualsiasi attività e **estrarrai le ore lavorative** da un calendario MS Project utilizzando Aspose.Tasks per Java. Alla fine della guida sarai in grado di **calcolare la durata dell'attività**, personalizzare le ore lavorative e caricare in modo affidabile un **file MPP** per recuperare i dati necessari — tutto senza installare Microsoft Project.

## Risposte rapide
- **Cosa significa “determine working days”?** Significa identificare quali date del calendario sono considerate giorni lavorativi per una determinata attività.  
- **Quale libreria dovrei usare?** Aspose.Tasks for Java fornisce un'API completa per lavorare con file MS Project.  
- **Quanto tempo richiede l'implementazione?** Tipicamente 10–15 minuti per un'estrazione di base.  
- **È necessaria una licenza?** È disponibile una prova gratuita; è richiesta una licenza commerciale per l'uso in produzione.  
- **Posso personalizzare le ore lavorative?** Sì – è possibile modificare i calendari, aggiungere festività e impostare intervalli di lavoro personalizzati.  

## Cos'è “determine working days”?
**Determine working days** significa interrogare un calendario di progetto per scoprire quali date sono contrassegnate come giorni lavorativi rispetto ai giorni non lavorativi (fine settimana, festività o eccezioni personalizzate). Questa informazione è essenziale per un calcolo accurato della **calculate task duration** perché solo i giorni lavorativi contribuiscono al tempo trascorso di un'attività.

## Perché usare Aspose.Tasks per recuperare le ore lavorative?
Aspose.Tasks ti consente di leggere i file MS Project senza avere Microsoft Project installato, permettendo l'automazione su qualsiasi piattaforma. Fornisce anche elaborazione ad alte prestazioni, supporto esteso di formati e documentazione dettagliata.  

- **Full calendar support** – i calendari predefiniti, delle risorse e delle attività sono tutti accessibili.  
- **High performance** – può elaborare progetti contenenti **10,000+ tasks in under 2 seconds** su una CPU standard da 2.5 GHz.  
- **Extensive format coverage** – supporta **50+ input and output formats**, inclusi MPP, MPX, XML e Primavera.  
- **Comprehensive documentation** – esempi di codice, riferimento API e forum della community sono tutti disponibili.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – versione 8 o superiore.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR da [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Conoscenze di base di programmazione Java.  

## Importa pacchetti
La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file MS Project in memoria. Importa lo spazio dei nomi richiesto prima di iniziare:

Importa pacchetti

```java
import com.aspose.tasks.*;
```

## Come caricare un file MPP con Aspose.Tasks?
La classe `Project` carica un file MS Project e fornisce l'accesso ai suoi dati. Carica il file di progetto con una singola riga di codice; non è necessaria alcuna interfaccia UI o interop COM. Questo passaggio semplice ti dà pieno accesso a calendari, attività e risorse.

Caricamento di un file MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Recupera informazioni su attività e calendario
`Task` rappresenta un'attività di progetto, e `Calendar` definisce le sue regole di orario di lavoro. Seleziona l'attività che desideri analizzare e ottieni il calendario associato. L'oggetto `Task` fornisce i metodi `getStart()` e `getFinish()`, mentre l'oggetto `Calendar` espone le definizioni del tempo di lavoro.

Recupero di attività e calendario

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definisci le date di inizio e fine
Gli oggetti `Date` specificano la finestra temporale per l'analisi del calendario. Imposta la finestra temporale per cui desideri **determine working days**. Utilizzare le date di inizio e fine dell'attività garantisce di valutare solo il periodo rilevante.

Definizione delle date

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Itera attraverso le date
Un ciclo `for` può iterare su ogni giorno nell'intervallo di date. Scorri ogni data nella durata dell'attività. Questo ciclo ti consentirà di **customize working hours** in seguito, se necessario, ed è la base per calcolare il tempo di lavoro totale.

Iterazione delle date

```java
java.util.Calendar tempDate = calStartDate;
```

## Calcola la durata
`Duration` aggrega il tempo totale di lavoro calcolato dall'iterazione. Durante l'iterazione verifichi se ogni giorno è un giorno lavorativo, sommi le ore lavorative e infine calcoli la durata dell'attività in minuti, ore e giorni. Questo dimostra come **calculate working days** e **calculate task duration** programmaticamente.

Calcolo della durata

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Come personalizzare le ore lavorative e le festività
Puoi modificare gli intervalli di orario di lavoro del calendario e aggiungere eccezioni come le festività. Usa `taskCalendar.addWorkingTime()` per impostare nuovi periodi di lavoro e `taskCalendar.addException()` per inserire una festività. Questo è utile quando l'orario predefinito 9‑5 non corrisponde alle politiche della tua organizzazione.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Task returns `null` for calendar** | Assicurati che l'attività abbia effettivamente un calendario assegnato; altrimenti eredita il calendario predefinito del progetto. |
| **Incorrect duration because of holidays** | Verifica che le festività siano definite nel calendario dell'attività o nel calendario base del progetto. |
| **Time zone mismatch** | Usa `java.util.TimeZone` per allineare il fuso orario del calendario con il tuo sistema, se necessario. |

## Domande frequenti
### Q: Aspose.Tasks for Java può gestire strutture di progetto complesse?
A: Sì, Aspose.Tasks for Java fornisce un supporto completo per gestire strutture di progetto complesse, incluse attività, risorse e calendari.

### Q: Aspose.Tasks for Java è compatibile con diverse versioni di MS Project?
A: Assolutamente, Aspose.Tasks for Java supporta varie versioni di MS Project, garantendo compatibilità su diversi ambienti.

### Q: Posso personalizzare le ore lavorative e le festività nei calendari di progetto?
A: Sì, puoi facilmente personalizzare le ore lavorative e le festività secondo i requisiti del tuo progetto usando le API di Aspose.Tasks for Java.

### Q: Aspose.Tasks for Java offre supporto e documentazione?
A: Sì, Aspose.Tasks for Java fornisce una documentazione estesa e forum di supporto dedicati per assistere gli sviluppatori nell'utilizzo delle sue funzionalità.

### Q: È disponibile una versione di prova per Aspose.Tasks for Java?
A: Sì, puoi accedere a una versione di prova gratuita di Aspose.Tasks for Java dalla [pagina di rilascio di Aspose](https://releases.aspose.com/).

## Conclusione
In questa guida abbiamo dimostrato come **add holidays calendar**, **determine working days**, **retrieve working hours** e **calculate task duration** da un calendario MS Project usando Aspose.Tasks per Java. Seguendo i passaggi sopra potrai automatizzare l'analisi dei programmi, personalizzare i calendari e mantenere i piani di progetto accurati e aggiornati. Ora disponi degli strumenti per **read MS Project** dati, **load an MPP file**, e eseguire calcoli precisi della durata senza la necessità di Microsoft Project.

---

**Ultimo aggiornamento:** 2026-08-24  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose

## Tutorial correlati

- [Aggiungi calendario al progetto con Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Aggiungi festività al calendario e salva come MPP con Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Crea eccezioni di calendario personalizzate con Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}