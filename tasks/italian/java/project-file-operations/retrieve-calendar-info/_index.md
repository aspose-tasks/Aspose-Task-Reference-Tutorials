---
title: Recupera le informazioni sul calendario di MS Project in Aspose.Tasks
linktitle: Recupera le informazioni del calendario in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come recuperare le informazioni del calendario di MS Project utilizzando Aspose.Tasks per Java. Guida passo passo per accedere ai dettagli del calendario in modo programmatico.
type: docs
weight: 14
url: /it/java/project-file-operations/retrieve-calendar-info/
---
## introduzione
In questo tutorial esploreremo come recuperare le informazioni del calendario dai file di Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Aspose.Tasks fornisce potenti funzionalità per manipolare i dati del progetto, incluso l'accesso ai dettagli del calendario come giorni e ore lavorative.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza base della programmazione Java.
- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Tasks per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari nel tuo codice Java per utilizzare le funzionalità Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Ora suddividiamo l'esempio fornito in più passaggi per una migliore comprensione.
## Passaggio 1: imposta la directory dei dati
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"` con il percorso della directory dei file di progetto.
## Passaggio 2: definire le unità di tempo
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Queste costanti rappresentano le unità di tempo in microsecondi.
## Passaggio 3: crea l'istanza del progetto
```java
Project project = new Project(dataDir + "project.mpp");
```
 Questa riga crea un'istanza di`Project` classe, inizializzandola con il percorso del file di progetto (`project.mpp`).
## Passaggio 4: recuperare le informazioni sui calendari
```java
CalendarCollection alCals = project.getCalendars();
```
Qui recuperiamo una raccolta di calendari presenti nel file di progetto.
## Passaggio 5: scorrere i calendari
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Informazioni sul calendario
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Ripetere i giorni feriali
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Tempo in millisecondi
            double time = ts / (OneHour); // Converti in ore
            if (wd.getDayWorking()) {
                // Visualizza i giorni e le ore lavorative
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Questo ciclo scorre ciascun calendario e ne stampa l'UID, il nome e i giorni lavorativi con i rispettivi orari lavorativi.
## Passaggio 6: Visualizza il messaggio di completamento
```java
System.out.println("Process completed Successfully");
```
Infine, viene visualizzato un messaggio che indica il completamento del processo.
## Conclusione
In questo tutorial, abbiamo imparato come recuperare le informazioni del calendario dai file MS Project utilizzando Aspose.Tasks per Java. Seguendo questi passaggi è possibile accedere e manipolare in modo efficiente i dati di progetto nelle applicazioni Java.

## Domande frequenti
### D: Posso utilizzare Aspose.Tasks con altri linguaggi di programmazione?
R: Sì, Aspose.Tasks supporta più piattaforme e linguaggi di programmazione, inclusi .NET, C++, Python e Java.
### D: È disponibile una prova gratuita per Aspose.Tasks?
 R: Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.Tasks?
R: Puoi ottenere supporto dal forum della community Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
### D: Posso acquistare una licenza temporanea per Aspose.Tasks?
 R: Sì, è possibile acquistare licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks?
 R: Puoi fare riferimento alla documentazione[Qui](https://reference.aspose.com/tasks/java/).