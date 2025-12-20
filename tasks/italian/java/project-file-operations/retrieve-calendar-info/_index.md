---
date: 2025-12-20
description: Scopri come utilizzare Aspose.Tasks per estrarre i dettagli del calendario
  del progetto dai file Microsoft Project usando Java. Guida passo‑passo con esempi
  di codice.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come utilizzare Aspose.Tasks per recuperare le informazioni del calendario
  di MS Project
url: /it/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare Aspose.Tasks per recuperare le informazioni sul calendario di MS Project

## Introduzione
In questo tutorial, **scoprirai come utilizzare Aspose.Tasks** per recuperare programmaticamente le informazioni sul calendario dai file Microsoft Project. Accedere ai dati del calendario come giorni lavorativi, ore e eccezioni è essenziale quando è necessario **estrarre le informazioni del calendario del progetto** per report, integrazione o logica di pianificazione personalizzata. Seguiamo il processo passo dopo passo.

## Risposte rapide
- **Quale libreria utilizza questo tutorial?** Aspose.Tasks for Java.  
- **Quale parola chiave principale è trattata?** *how to use aspose.tasks*.  
- **Cosa puoi estrarre?** I calendari del progetto, inclusi giorni e ore lavorative.  
- **È necessaria una licenza?** È disponibile una versione di prova gratuita; è richiesta una licenza per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore.

## Perché estrarre le informazioni sul calendario del progetto?
I calendari del progetto determinano le date delle attività, le assegnazioni delle risorse e i calcoli complessivi della timeline. Estrarre questi dati ti permette di:
- Generare report personalizzati che riflettano i reali orari di lavoro.  
- Sincronizzare le timeline di Microsoft Project con sistemi esterni (ERP, BI, ecc.).  
- Eseguire analisi what‑if modificando programmaticamente le impostazioni del calendario.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Conoscenze di base della programmazione Java.  
- Java Development Kit (JDK) installato sul tuo sistema.  
- Libreria Aspose.Tasks for Java. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).

## Importa i pacchetti
Per prima cosa, importa le classi necessarie di Aspose.Tasks nel tuo progetto Java.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Passo 1: Imposta la directory dei dati
Definisci la cartella che contiene il tuo file *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Sostituisci `"Your Data Directory"` con il percorso assoluto della cartella in cui si trova **project.mpp**.

## Passo 2: Definisci le unità di tempo
Crea costanti che aiutino a convertire la rappresentazione interna del tempo in ore leggibili dall’uomo.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Questi valori sono espressi in microsecondi, che è il modo in cui Aspose.Tasks memorizza il tempo internamente.

## Passo 3: Crea l'istanza del progetto
Carica il file Microsoft Project in un oggetto `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Il costruttore `Project` analizza il file *.mpp* e rende tutti i dati del progetto, inclusi i calendari, accessibili tramite l'API.

## Passo 4: Recupera le informazioni sui calendari
Ottieni la collezione dei calendari definiti nel progetto.

```java
CalendarCollection alCals = project.getCalendars();
```

Un progetto può contenere più calendari (standard, risorse e personalizzati). Questa collezione ti dà accesso a ciascuno di essi.

## Passo 5: Itera sui calendari
Scorri ogni calendario, visualizza il suo UID, nome e i giorni lavorativi con le ore corrispondenti.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Il ciclo interno controlla ogni oggetto `WeekDay`. Se il giorno è contrassegnato come lavorativo, stampa il tipo di giorno (Monday, Tuesday, …) insieme alle ore lavorative calcolate.

## Passo 6: Visualizza il messaggio di completamento
Segnala che il processo di estrazione è terminato.

```java
System.out.println("Process completed Successfully");
```

## Conclusione
Seguendo questi passaggi, **ora sai come utilizzare Aspose.Tasks per estrarre le informazioni sul calendario del progetto** da un file MS Project usando Java. Puoi integrare questa logica in applicazioni più grandi, automatizzare i report o sincronizzare i programmi con altri sistemi aziendali.

## Domande frequenti

**Q: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
A: Sì, Aspose.Tasks supporta più piattaforme e linguaggi di programmazione, inclusi .NET, C++, Python e Java.

**Q: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
A: Sì, puoi scaricare una versione di prova gratuita da [qui](https://releases.aspose.com/).

**Q: Come posso ottenere supporto per Aspose.Tasks?**  
A: Puoi ottenere supporto dal forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**Q: Posso acquistare una licenza temporanea per Aspose.Tasks?**  
A: Sì, le licenze temporanee sono disponibili per l'acquisto [qui](https://purchase.aspose.com/temporary-license/).

**Q: Dove posso trovare la documentazione dettagliata per Aspose.Tasks?**  
A: Puoi consultare la documentazione [qui](https://reference.aspose.com/tasks/java/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}