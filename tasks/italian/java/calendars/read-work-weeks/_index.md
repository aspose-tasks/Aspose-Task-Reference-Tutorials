---
title: Leggi le settimane lavorative dal calendario di MS Project con Aspose.Tasks
linktitle: Leggi le settimane lavorative dal calendario con Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come leggere le settimane lavorative dal calendario di MS Project utilizzando Aspose.Tasks per Java. Ottieni istruzioni dettagliate in questo tutorial completo.
weight: 15
url: /it/java/calendars/read-work-weeks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi le settimane lavorative dal calendario di MS Project con Aspose.Tasks

## introduzione
In questo tutorial esploreremo come utilizzare Aspose.Tasks per Java per leggere le informazioni sulle settimane lavorative da un calendario di Microsoft Project. Aspose.Tasks è una potente libreria Java che ti consente di manipolare e gestire i documenti di Microsoft Project a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Tasks per la libreria Java scaricata e installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
Innanzitutto, importiamo i pacchetti necessari per iniziare con il nostro codice:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Passaggio 1: configura la directory dei dati
Imposta il percorso della directory in cui si trova il file MS Project:
```java
String dataDir = "Your Data Directory";
```
## Passaggio 2: crea l'istanza del progetto e accedi al calendario
Crea una nuova istanza della classe Project e accedi alla raccolta del calendario e delle settimane lavorative:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Passaggio 3: scorrere le settimane lavorative
Scorrere la raccolta delle settimane lavorative e visualizzarne le informazioni:
```java
for (WorkWeek workWeek : collection) {
    // Visualizza il nome della settimana lavorativa, le date da e a
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Accedi ai giorni della settimana e agli orari di lavoro
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Ulteriori tempi di lavorazione del processo, se necessari
    }
}
```
## Conclusione
In questo tutorial, abbiamo imparato come leggere le informazioni sulle settimane lavorative da un calendario di Microsoft Project utilizzando Aspose.Tasks per Java. Questa potente libreria consente una manipolazione fluida dei file di progetto, consentendo agli sviluppatori di automatizzare varie attività in modo efficiente.
## Domande frequenti
### Posso modificare le informazioni sulle settimane lavorative utilizzando Aspose.Tasks per Java?
Sì, Aspose.Tasks fornisce API per modificare, aggiungere o eliminare le settimane lavorative e le informazioni associate.
### Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?
Sì, Aspose.Tasks supporta varie versioni di file Microsoft Project, inclusi i formati MPP e XML.
### Posso integrare Aspose.Tasks con altri framework Java?
Assolutamente, Aspose.Tasks può essere perfettamente integrato con altri framework e librerie Java per funzionalità avanzate.
### È disponibile una versione di prova per Aspose.Tasks?
 Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.Tasks?
È possibile trovare supporto e assistenza sul forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
