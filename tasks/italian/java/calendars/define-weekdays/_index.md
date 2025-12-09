---
date: 2025-12-02
description: Scopri come impostare il calendario, definire i giorni feriali in MS Project
  e impostare giorni lavorativi personalizzati usando Aspose.Tasks per Java. Salva
  il progetto come XML con poche righe di codice.
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come impostare il calendario e definire i giorni della settimana in MS Project
  con Aspose.Tasks
url: /it/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il calendario e definire i giorni della settimana in MS Project con Aspose.Tasks

## Introduzione
In questo tutorial scoprirai **come impostare il calendario** programmaticamente e definire i giorni della settimana in un file Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Che tu debba creare una settimana lavorativa standard, aggiungere giorni lavorativi nel weekend o configurare un orario ridotto per il venerdì, questa guida ti accompagna passo passo—dalla creazione del progetto al salvataggio del file in formato XML.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Tasks for Java  
- **Posso aggiungere giorni lavorativi nel weekend?** Sì – basta aggiungere sabato e domenica come giorni lavorativi.  
- **Come salvo il progetto?** Usa `prj.save(..., SaveFileFormat.Xml)`.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per la valutazione; è necessaria una licenza per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o superiore.

## Che cosa significa “impostare il calendario” nel contesto di MS Project?
Impostare un calendario in MS Project significa definire quali giorni sono lavorativi, le ore di lavoro giornaliere e eventuali eccezioni come le festività. Questo calendario guida la pianificazione delle attività, l'allocazione delle risorse e le tempistiche complessive del progetto.

## Perché usare Aspose.Tasks per la manipolazione del calendario?
- **Controllo completo** – crea, modifica o elimina i calendari programmaticamente senza aprire l'interfaccia.  
- **Cross‑platform** – funziona su qualsiasi OS che supporta Java.  
- **Supporta tutti i formati di file** – MPP, MPT e XML, così puoi *salvare il progetto come XML* per una facile integrazione con altri sistemi.  
- **Nessuna dipendenza COM** – a differenza della libreria Microsoft Project Interop.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK) 8+** – scarica dal [sito Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – ottieni l'ultima JAR dalla [pagina di download Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Un IDE o uno strumento di build (Maven/Gradle) per aggiungere la JAR di Aspose.Tasks al classpath del tuo progetto.

## Importa i pacchetti
Per prima cosa, importa le classi di cui avrai bisogno. Queste importazioni ti danno accesso a oggetti progetto, calendario e orari di lavoro.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guida passo‑passo

### Passo 1: Crea un'istanza di Project
Crea un nuovo oggetto `Project`. Questo oggetto rappresenta il file MS Project che stai modificando.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Passo 2: Definisci un nuovo calendario
Aggiungi un nuovo calendario al progetto. Assegnargli un nome chiaro aiuta quando hai più calendari.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Passo 3: Aggiungi giorni lavorativi standard (Lunedì‑Giovedì)
Usa l'aiuto integrato `WeekDay.createDefaultWorkingDay` per impostare l'orario predefinito 9 am‑5 pm per la settimana lavorativa principale.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Passo 4: Aggiungi giorni lavorativi nel weekend
Se il tuo progetto opera nei weekend, aggiungi semplicemente sabato e domenica come giorni lavorativi regolari. Questo dimostra **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Passo 5: Imposta un giorno lavorativo corto personalizzato (Venerdì)
Qui **set custom working days** per il venerdì: un turno mattutino (9 am‑12 pm) e un turno pomeridiano (1 pm‑4 pm).

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

### Passo 6: Salva il progetto come XML
Infine, persisti le modifiche. L'opzione `SaveFileFormat.Xml` ti permette di **save project as XML**, utile per l'integrazione con altri strumenti.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Working times not applied** | Ensure `setDayWorking(true)` is called on the custom `WeekDay`. |
| **File not found when saving** | Verify that `dataDir` points to an existing folder and that your application has write permissions. |
| **Calendar not reflected in tasks** | Assign the newly created calendar to resources or tasks using `task.setCalendar(cal)`. |

## Domande frequenti

**D: Posso definire giorni non lavorativi personalizzati usando Aspose.Tasks per Java?**  
R: Sì. Imposta la proprietà `DayWorking` a `false` per qualsiasi `WeekDay` che desideri trattare come giorno non lavorativo.

**D: Come posso aggiungere festività o eccezioni aziendali?**  
R: Crea oggetti `CalendarException`, specifica le date di eccezione e aggiungili a `cal.getExceptions()`.

**D: La libreria è compatibile con versioni più vecchie di MS Project?**  
R: Assolutamente. Aspose.Tasks supporta i formati MPP, MPT e XML su più versioni di Project.

**D: Posso modificare un calendario esistente in un progetto importato?**  
R: Carica il progetto con `new Project("existing.mpp")`, recupera il calendario desiderato, apporta le modifiche e salva.

**D: Aspose.Tasks gestisce anche le attività ricorrenti?**  
R: Sì, puoi creare e modificare attività ricorrenti usando la classe `RecurringTask`.

## Conclusione
Ora sai **come impostare il calendario**, **definire i giorni della settimana in MS Project**, aggiungere giorni lavorativi nel weekend e creare un orario ridotto per il venerdì—tutto con Aspose.Tasks per Java. Salva il risultato come XML e integra la logica del calendario in qualsiasi soluzione di gestione progetti basata su Java.

---

**Ultimo aggiornamento:** 2025-12-02  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}