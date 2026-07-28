---
date: 2026-02-05
description: Impara a leggere le settimane di lavoro Java da un calendario di Microsoft
  Project usando Aspose.Tasks. Segui la guida passo passo con esempi di codice completi.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come leggere le settimane lavorative in Java dal calendario di MS Project con
  Aspose.Tasks
url: /it/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere le settimane lavorative Java dal calendario MS Project Aspose.Tasks

## Introduzione
In questo tutorial **imparerai come leggere le settimane lavorative Java** da un calendario Microsoft Project utilizzando la libreria Aspose.Tasks. Che tu stia costruendo uno strumento di reporting, sincronizzando i programmi o automatizzando l'estrazione dei dati di progetto, la possibilità di accedere programmaticamente alle definizioni delle settimane lavorative fa risparmiare innumerevoli ore manuali. Ti guideremo attraverso la configurazione necessaria, ti mostreremo il codice esatto per recuperare i dettagli delle settimane lavorative e spiegheremo ogni passaggio in modo che tu possa adattare la soluzione ai tuoi progetti.

## Risposte rapide
- **Cosa significa “read workweeks java”?** Si riferisce all'estrazione delle definizioni delle settimane lavorative da un file Project usando codice Java.  
- **Quale libreria è necessaria?** Aspose.Tasks for Java (disponibile versione di prova gratuita).  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Quali formati di file sono supportati?** Sono gestiti sia i file *.mpp* sia i file Project XML.  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti una volta configurata la libreria.

## Come leggere le settimane lavorative Java da un calendario Microsoft Project
Leggere le settimane lavorative in Java significa utilizzare l'API Aspose.Tasks per accedere alla `WorkWeekCollection` di un oggetto calendario all'interno di un file Microsoft Project. Ogni `WorkWeek` contiene le date di inizio/fine e le definizioni dei tempi di lavoro giornalieri che determinano come le risorse sono programmate.

## Perché leggere le settimane lavorative Java da un calendario Microsoft Project?
- **Automazione:** Elimina il copia‑incolla manuale dei dati di programmazione.  
- **Integrazione:** Fornisci le informazioni sulle settimane lavorative a ERP, HR o sistemi di reporting personalizzati.  
- **Coerenza:** Assicura che tutti gli strumenti a valle rispettino le stesse regole del calendario definite nel file Project.

## Prerequisiti
Prima di immergerci nel codice, assicurati di avere:

1. **Java Development Kit (JDK)** – versione 8 o successiva installata.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dal sito ufficiale: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Un **file Project di esempio** (`ReadWorkWeeksInformation.mpp`) posizionato in una cartella nota.

## Importare i pacchetti
Per prima cosa, importa le classi di cui avremo bisogno per interagire con i calendari e le settimane lavorative:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Passo 1: Configura la tua directory dei dati
Definisci la cartella che contiene il file `.mpp`. Sostituisci il segnaposto con il percorso reale sul tuo computer:

```java
String dataDir = "Your Data Directory";
```

## Passo 2: Crea un'istanza Project e accedi al calendario
Istanzia un oggetto `Project`, scegli il calendario desiderato (per UID) e ottieni la sua `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Suggerimento professionale:** Se non sei sicuro dell'UID del calendario, puoi iterare su `project.getCalendars()` e stampare il nome e l'UID di ciascun calendario.

## Passo 3: Itera attraverso le settimane lavorative
Scorri ogni `WorkWeek` per visualizzare il suo nome, le date di inizio/fine e gli orari di lavoro giornalieri:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Ciò che vedrai:** La console stampa l'etichetta di ogni settimana lavorativa (ad es., “Standard”), il suo intervallo di date effettive, e puoi approfondire le ore di lavoro esatte per ogni giorno.

## Problemi comuni e soluzioni
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | UID errato o il calendario non esiste | Verifica l'UID con `project.getCalendars().size()` e elenca prima i calendari disponibili. |
| No output for work weeks | Il calendario selezionato non ha settimane lavorative personalizzate (usa quelle predefinite) | Usa il calendario predefinito (`project.getDefaultCalendar()`) o crea una settimana lavorativa programmaticamente. |
| Date format looks odd | `System.out.println` uses default `java.util.Date` format | Applica un `SimpleDateFormat` per formattare le date secondo necessità. |

## Domande frequenti

**D: Posso modificare le informazioni delle settimane lavorative usando Aspose.Tasks for Java?**  
R: Sì. L'API fornisce metodi come `addWorkWeek()`, `removeWorkWeek()` e setter delle proprietà per cambiare nomi, date e orari di lavoro.

**D: Aspose.Tasks è compatibile con diverse versioni di file Microsoft Project?**  
R: Assolutamente. Supporta file MPP da Project 98 fino alle versioni più recenti, così come i file Project XML.

**D: Posso integrare Aspose.Tasks con altri framework Java?**  
R: Sì. La libreria è pure Java, quindi può essere usata insieme a Spring, Jakarta EE o qualsiasi altro framework.

**D: È disponibile una versione di prova per Aspose.Tasks?**  
R: Sì, puoi scaricare una prova gratuita di 30 giorni dal sito ufficiale: [Aspose.Tasks trial](https://releases.aspose.com/).

**D: Dove posso trovare supporto per Aspose.Tasks?**  
R: Il forum della community Aspose è il posto migliore: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusione
Ora hai padroneggiato **come leggere le settimane lavorative Java** usando Aspose.Tasks. Seguendo i passaggi sopra puoi estrarre programmaticamente le definizioni delle settimane lavorative da qualsiasi calendario MS Project, integrare quei dati nelle tue applicazioni e automatizzare i flussi di lavoro legati alla programmazione. Sentiti libero di sperimentare creando o aggiornando le settimane lavorative—Aspose.Tasks lo rende semplice.

---

**Ultimo aggiornamento:** 2026-02-05  
**Testato con:** Aspose.Tasks for Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}