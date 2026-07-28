---
date: 2026-02-05
description: Scopri come determinare i giorni lavorativi e calcolare la durata delle
  attività estraendo le ore lavorative dai calendari di MS Project utilizzando Aspose.Tasks
  per Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Determinare i giorni lavorativi e le ore lavorative con Aspose.Tasks
url: /it/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Determinare i giorni lavorativi e le ore lavorative con Aspose.Tasks

## Introduzione
Gestire i calendari di progetto è una parte fondamentale della pianificazione di progetto di successo. In questo tutorial **determinerai i giorni lavorativi** per qualsiasi attività e **estrarrai le ore lavorative** da un calendario MS Project usando Aspose.Tasks per Java. Alla fine della guida sarai in grado di **calcolare la durata dell'attività**, personalizzare le ore lavorative e caricare in modo affidabile un **file MPP** per recuperare i dati di cui hai bisogno. Vedrai anche come **leggere i file MS Project** senza avere Microsoft Project installato, rendendo l'automazione possibile su qualsiasi piattaforma.

## Risposte rapide
- **Cosa significa “determinare i giorni lavorativi”?** Significa identificare quali date del calendario sono considerate giorni lavorativi per una determinata attività.  
- **Quale libreria devo usare?** Aspose.Tasks per Java fornisce un'API completa per lavorare con i file MS Project.  
- **Quanto tempo richiede l'implementazione?** Tipicamente 10–15 minuti per un'estrazione di base.  
- **Ho bisogno di una licenza?** È disponibile una versione di prova gratuita; è necessaria una licenza commerciale per l'uso in produzione.  
- **Posso personalizzare le ore lavorative?** Sì – puoi modificare i calendari, aggiungere festività e impostare intervalli di orario di lavoro personalizzati.  

## Cos'è “determinare i giorni lavorativi”?
Quando un'attività è programmata, il calendario di progetto definisce quali giorni sono giorni lavorativi e quali sono non lavorativi (weekend, festività). Determinare i giorni lavorativi significa interrogare quel calendario per sapere esattamente quando può avvenire il lavoro, il che è essenziale per calcoli accurati di **calcolare la durata dell'attività**.

## Perché usare Aspose.Tasks per recuperare le ore lavorative?
- **Nessun Microsoft Project richiesto** – puoi leggere i file MS Project direttamente dal codice Java.  
- **Supporto completo del calendario** – include calendari predefiniti, di risorse e di attività.  
- **Alte prestazioni** – elabora rapidamente progetti di grandi dimensioni.  
- **Documentazione estesa** – esempi e riferimento API sono prontamente disponibili.

## Prerequisiti
1. **Java Development Kit (JDK)** – versione 8 o superiore.  
2. **Aspose.Tasks per Java** – scarica l'ultimo JAR da [qui](https://releases.aspose.com/tasks/java/).  
3. Conoscenze di base di programmazione Java.

## Importare i pacchetti
Per prima cosa, importa lo spazio dei nomi principale di Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Come caricare un file MPP con Aspose.Tasks?
Caricare il file di progetto è il primo passo verso qualsiasi analisi del calendario. L'API ti consente di **caricare un file MPP** in una singola riga di codice, senza la necessità dell'interfaccia di MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Recuperare le informazioni su attività e calendario
Scegli l'attività che vuoi analizzare e ottieni il suo calendario associato. Qui è dove **recuperiamo le ore lavorative** per l'attività:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definire le date di inizio e fine
Imposta la finestra temporale per la quale vuoi **determinare i giorni lavorativi**. Utilizzare le date di inizio e fine dell'attività garantisce di valutare solo il periodo pertinente.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterare attraverso le date
Scorri ogni data nella durata dell'attività. Questo ciclo ci aiuterà a **personalizzare le ore lavorative** in seguito, se necessario:

```java
java.util.Calendar tempDate = calStartDate;
```

## Calcolare la durata
Durante l'iterazione verifichiamo se ogni giorno è un giorno lavorativo, sommiamo le ore lavorative e infine calcoliamo la durata dell'attività in minuti, ore e giorni. Questo passaggio dimostra come **calcolare i giorni lavorativi** e **calcolare la durata dell'attività** programmaticamente.

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
Aspose.Tasks ti consente di modificare gli intervalli di orario di lavoro del calendario e aggiungere eccezioni come le festività. Puoi chiamare `taskCalendar.addWorkingTime()` o `taskCalendar.addException()` per adattare il programma alle politiche della tua organizzazione. Questo è utile quando l'orario predefinito 9‑5 non corrisponde alla realtà.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **L'attività restituisce `null` per il calendario** | Assicurati che l'attività abbia effettivamente un calendario assegnato; altrimenti eredita il calendario predefinito del progetto. |
| **Durata errata a causa delle festività** | Verifica che le festività siano definite nel calendario dell'attività o nel calendario base del progetto. |
| **Discrepanza del fuso orario** | Usa `java.util.TimeZone` per allineare il fuso orario del calendario con il tuo sistema, se necessario. |

## Domande frequenti
### Q: Aspose.Tasks per Java può gestire strutture di progetto complesse?
A: Sì, Aspose.Tasks per Java fornisce un supporto completo per gestire strutture di progetto complesse, incluse attività, risorse e calendari.

### Q: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?
A: Assolutamente, Aspose.Tasks per Java supporta varie versioni di MS Project, garantendo la compatibilità su diversi ambienti.

### Q: Posso personalizzare le ore lavorative e le festività nei calendari di progetto?
A: Sì, puoi facilmente personalizzare le ore lavorative e le festività in base ai requisiti del tuo progetto usando le API di Aspose.Tasks per Java.

### Q: Aspose.Tasks per Java offre supporto e documentazione?
A: Sì, Aspose.Tasks per Java fornisce una documentazione estesa e forum di supporto dedicati per assistere gli sviluppatori nell'utilizzo efficace delle sue funzionalità.

### Q: È disponibile una versione di prova per Aspose.Tasks per Java?
A: Sì, puoi accedere a una versione di prova gratuita di Aspose.Tasks per Java da [qui](https://releases.aspose.com/).

## Conclusione
In questa guida abbiamo dimostrato come **determinare i giorni lavorativi**, **recuperare le ore lavorative** e **calcolare la durata dell'attività** da un calendario MS Project usando Aspose.Tasks per Java. Seguendo i passaggi sopra potrai automatizzare l'analisi dei programmi, personalizzare i calendari e mantenere i piani di progetto accurati e aggiornati. Ora hai gli strumenti per **leggere i dati MS Project**, **caricare un file MPP** e eseguire calcoli precisi della durata senza la necessità di Microsoft Project.

---

**Ultimo aggiornamento:** 2026-02-05  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}