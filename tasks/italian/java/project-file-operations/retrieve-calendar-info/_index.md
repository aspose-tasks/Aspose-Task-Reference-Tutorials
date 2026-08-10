---
date: 2026-03-27
description: Impara a usare Aspose e Aspose.Tasks per estrarre i dettagli del calendario
  del progetto dai file Microsoft Project usando Java. Guida passo‑passo con esempi
  di codice.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come usare Aspose.Tasks per recuperare le informazioni del calendario di MS
  Project
url: /it/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare Aspose.Tasks per recuperare le informazioni sul calendario di MS Project

## Introduzione
In questo tutorial, **scoprirai come usare Aspose.Tasks** per recuperare programmaticamente le informazioni sul calendario dai file Microsoft Project. Accedere ai dati del calendario, come giorni lavorativi, ore e eccezioni, è fondamentale quando è necessario **estrarre il calendario del progetto** per report, integrazioni o logiche di pianificazione personalizzate. Seguiamo il processo passo dopo passo, e vedrai esattamente **come usare Aspose** per estrarre questi dati da un file *.mpp*.

## Risposte rapide
- **Quale libreria utilizza questo tutorial?** Aspose.Tasks per Java.  
- **Qual è la parola chiave principale trattata?** *how to use aspose*.  
- **Cosa puoi estrarre?** Calendari del progetto, inclusi giorni e ore lavorative.  
- **È necessaria una licenza?** È disponibile una versione di prova gratuita; è necessaria una licenza per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore.

## Cos’è Aspose.Tasks e perché usarlo?
Aspose.Tasks è una potente API Java che consente agli sviluppatori di leggere, scrivere e manipolare file Microsoft Project senza necessitare di Microsoft Project stesso. Utilizzando Aspose.Tasks puoi **estrarre le informazioni sul calendario**, automatizzare i calcoli di pianificazione e integrare i dati del progetto con altri sistemi aziendali, tutto con puro codice Java.

## Perché estrarre le informazioni sul calendario del progetto?
- Generare report personalizzati che riflettano i reali orari di lavoro.  
- Sincronizzare le tempistiche di Microsoft Project con sistemi esterni (ERP, BI, ecc.).  
- Eseguire analisi *what‑if* modificando le impostazioni del calendario in modo programmatico.  
- **Estrarre i dati del calendario di MS Project** per la migrazione verso altri strumenti di pianificazione.

## Prerequisiti
- Conoscenza di base della programmazione Java.  
- Java Development Kit (JDK) installato sul tuo sistema.  
- Libreria Aspose.Tasks per Java. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).

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
Crea costanti che aiutano a convertire la rappresentazione temporale interna in ore leggibili dall'uomo.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Questi valori sono espressi in microsecondi, che è il modo in cui Aspose.Tasks memorizza il tempo internamente.

## Passo 3: Crea l’istanza del progetto
Carica il file Microsoft Project in un oggetto `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Il costruttore `Project` analizza il file *.mpp* e rende tutti i dati del progetto, inclusi i calendari, accessibili tramite l’API.

## Passo 4: Recupera le informazioni sui calendari
Ottieni la collezione di calendari definiti nel progetto.

```java
CalendarCollection alCals = project.getCalendars();
```

Un progetto può contenere più calendari (standard, risorse e personalizzati). Questa collezione ti dà accesso a ciascuno di essi.

## Passo 5: Itera attraverso i calendari
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

Il ciclo interno verifica ogni oggetto `WeekDay`. Se il giorno è contrassegnato come lavorativo, stampa il tipo di giorno (Monday, Tuesday, …) insieme alle ore lavorative calcolate.

## Passo 6: Visualizza il messaggio di completamento
Segnala che il processo di estrazione è terminato.

```java
System.out.println("Process completed Successfully");
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **No calendars returned** | Il file di progetto potrebbe non contenere calendari personalizzati. | Verifica che il *.mpp* definisca effettivamente dei calendari o aprilo in Microsoft Project per confermare. |
| **Incorrect working hours** | Le costanti di conversione del tempo sono sbagliate per una versione diversa di Project. | Regola `OneSec`, `OneMin`, `OneHour` se utilizzi una versione più recente di Aspose.Tasks che modifica l'unità di tempo interna. |
| **`NullPointerException` on `cal.getName()`** | Alcuni oggetti calendario potrebbero essere null. | Aggiungi un controllo null prima di accedere alle proprietà (già mostrato). |

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
R: Sì, Aspose.Tasks supporta più piattaforme e linguaggi di programmazione, tra cui .NET, C++, Python e Java.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
R: Sì, puoi scaricare una versione di prova gratuita da [qui](https://releases.aspose.com/).

**D: Come posso ottenere supporto per Aspose.Tasks?**  
R: Puoi ottenere supporto dal forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**D: Posso acquistare una licenza temporanea per Aspose.Tasks?**  
R: Sì, le licenze temporanee sono disponibili per l'acquisto [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks?**  
R: Puoi consultare la documentazione [qui](https://reference.aspose.com/tasks/java/).

## Conclusione
Seguendo questi passaggi, **ora sai come utilizzare Aspose.Tasks per estrarre le informazioni sul calendario di un file MS Project** usando Java. Puoi integrare questa logica in applicazioni più grandi, automatizzare la generazione di report o sincronizzare i programmi con altri sistemi aziendali. Ricorda, padroneggiare **come usare aspose** apre la porta a numerosi scenari avanzati di automazione nella gestione dei progetti.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}