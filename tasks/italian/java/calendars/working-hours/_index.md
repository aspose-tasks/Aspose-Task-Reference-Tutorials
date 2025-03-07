---
title: Ottieni l'orario di lavoro dal calendario utilizzando Aspose.Tasks
linktitle: Ottieni l'orario di lavoro dal calendario utilizzando Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Estrai facilmente gli orari di lavoro dai calendari di MS Project con Aspose.Tasks per Java. Semplifica le attività di gestione del progetto.
weight: 13
url: /it/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ottieni l'orario di lavoro dal calendario utilizzando Aspose.Tasks

## introduzione
Gestire i calendari di progetto ed estrarre le ore di lavoro è essenziale per una gestione efficace del progetto. Aspose.Tasks per Java fornisce funzionalità robuste per recuperare facilmente l'orario di lavoro dai calendari di MS Project. In questo tutorial ti guideremo attraverso il processo passo dopo passo.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per la libreria Java scaricata e aggiunta al tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
3. Conoscenza di base del linguaggio di programmazione Java.
## Importa pacchetti
Innanzitutto, importa i pacchetti necessari per lavorare con Aspose.Tasks per Java:
```java
import com.aspose.tasks.*;
```
## Passaggio 1: caricare il file di progetto
Inizia caricando il file MS Project:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Passaggio 2: recuperare le informazioni sulle attività e sul calendario
Estrai i dettagli dell'attività e del calendario dal progetto:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Passaggio 3: definire le date di inizio e fine
Imposta le date di inizio e fine per l'attività:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Passaggio 4: scorrere le date
Scorrere le date all'interno della durata dell'attività:
```java
java.util.Calendar tempDate = calStartDate;
```
## Passaggio 5: calcolare la durata
Calcola la durata in minuti, ore e giorni:
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
## Conclusione
In questo tutorial, abbiamo spiegato come recuperare l'orario di lavoro da un calendario di MS Project utilizzando Aspose.Tasks per Java. Seguendo questi passaggi, puoi gestire in modo efficiente le pianificazioni dei progetti e calcolare facilmente la durata delle attività.
## Domande frequenti
### D: Aspose.Tasks per Java può gestire strutture di progetto complesse?
R: Sì, Aspose.Tasks per Java fornisce un supporto completo per la gestione di strutture di progetto complesse, incluse attività, risorse e calendari.
### D: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?
R: Assolutamente, Aspose.Tasks per Java supporta varie versioni di MS Project, garantendo la compatibilità tra diversi ambienti.
### D: Posso personalizzare gli orari di lavoro e le festività nei calendari dei progetti?
R: Sì, puoi personalizzare facilmente l'orario di lavoro e le festività in base ai requisiti del tuo progetto utilizzando Aspose.Tasks per le API Java.
### D: Aspose.Tasks per Java offre supporto e documentazione?
R: Sì, Aspose.Tasks per Java fornisce un'ampia documentazione e forum di supporto dedicati per assistere gli sviluppatori nell'utilizzo efficace delle sue funzionalità.
### D: È disponibile una versione di prova per Aspose.Tasks per Java?
 R: Sì, puoi accedere a una versione di prova gratuita di Aspose.Tasks per Java da[Qui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
