---
title: Definire i giorni feriali nel calendario con Aspose.Tasks
linktitle: Definire i giorni feriali nel calendario con Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come definire i giorni feriali nel calendario di MS Project utilizzando Aspose.Tasks per Java. Personalizza facilmente giorni lavorativi e orari.
weight: 12
url: /it/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definire i giorni feriali nel calendario con Aspose.Tasks

## introduzione
In questo tutorial, esamineremo il processo di definizione dei giorni feriali in un calendario di MS Project utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente libreria Java che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. Puoi scaricarlo da[Sito web dell'Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) se non l'hai già fatto.
2.  Aspose.Tasks per Java Library: scarica e installa la libreria Aspose.Tasks per Java dal file[pagina di download](https://releases.aspose.com/tasks/java/). Seguire le istruzioni di installazione fornite nella documentazione.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari richiesti per lavorare con Aspose.Tasks nel tuo progetto Java:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Passaggio 1: crea un'istanza del progetto
Crea un'istanza di un oggetto Project, che rappresenta il file MS Project con cui lavorerai:
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Passaggio 2: definire il calendario
Crea una nuova istanza del calendario e aggiungila al progetto:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Passaggio 3: aggiungi giorni lavorativi
Definisci i giorni lavorativi aggiungendo dal lunedì al giovedì con orari predefiniti:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Passaggio 4: imposta un giorno lavorativo personalizzato
Definire sabato e domenica come giorni lavorativi:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Passaggio 5: impostare la giornata lavorativa breve
Imposta il venerdì come una giornata lavorativa breve con orari di lavoro personalizzati:
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
## Passaggio 6: salva il progetto
Salva il progetto modificato in un file XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Conclusione
Congratulazioni! Hai definito con successo i giorni feriali in un calendario di MS Project utilizzando Aspose.Tasks per Java. Ora puoi integrare questa funzionalità nelle tue applicazioni Java per manipolare i file MS Project a livello di codice.
## Domande frequenti
### Q1: posso definire giorni non lavorativi personalizzati utilizzando Aspose.Tasks per Java?
 R: Sì, puoi definire giorni non lavorativi personalizzati impostando il`DayWorking` proprietà a`false` per il rispettivo giorno della settimana.
### Q2: Come posso aggiungere festività al calendario?
 R: Puoi aggiungere festività creando istanze di`CalendarExceptions` specificando le date non lavorative.
### Q3: Aspose.Tasks è compatibile con diverse versioni dei file MS Project?
R: Sì, Aspose.Tasks supporta varie versioni di file MS Project, inclusi i formati MPP, MPT e XML.
### Q4: Posso modificare i calendari esistenti in un file MS Project?
R: Sì, puoi caricare un progetto esistente con calendari, apportare modifiche e quindi salvare le modifiche nel file originale.
### Q5: Aspose.Tasks fornisce supporto per attività ricorrenti?
R: Sì, Aspose.Tasks ti consente di lavorare con attività ricorrenti, inclusa la definizione dei loro modelli di ricorrenza e della loro durata.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
