---
date: 2026-02-05
description: Scopri come aggiungere festività a un calendario, assegnare il calendario
  a un progetto e salvare il file MS Project come MPP utilizzando Aspose.Tasks per
  Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aggiungi le festività al calendario e salva come MPP con Aspose.Tasks
url: /it/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere festività al calendario e salvare come MPP con Aspose.Tasks

## Introduzione

Nel project management moderno è spesso necessario **aggiungere festività al calendario**, creare un **MS Project calendar** e poi condividere il programma nel formato nativo MPP. Che tu stia consolidando linee temporali da più fonti o migrando dati legacy, generare un calendario in modo programmatico elimina errori manuali e accelera la consegna. Questo tutorial ti guida attraverso l’intero processo di creazione di un calendario in MS Project, personalizzandolo con festività, **assegnare il calendario al progetto**, e infine **convertire il progetto in MPP** usando l’Aspose.Tasks Java API.

## Risposte rapide
- **Di cosa tratta questo tutorial?** Aggiungere festività a un calendario, assegnarlo a un progetto e salvare il risultato come file MPP con Aspose.Tasks per Java.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quale versione di Java è necessaria?** Java 8 o superiore (JDK 8+).  
- **Posso personalizzare il calendario?** Sì – è possibile aggiungere orari di lavoro, eccezioni e festività.  
- **Quanto tempo richiede l’implementazione?** Circa 10‑15 minuti per un calendario di base.  

## Che cosa significa “create calendar MS Project”?

Creare un calendario MS Project significa definire programmaticamente i giorni lavorativi, le ore e le eccezioni che guidano la pianificazione delle attività all’interno di un file Microsoft Project. Utilizzando Aspose.Tasks è possibile **java create project calendar**, modificarlo e salvare le modifiche senza mai aprire l’interfaccia di Microsoft Project.

## Perché usare Aspose.Tasks per questo compito?

- **Compatibilità completa .NET/Java** – funziona su qualsiasi piattaforma che supporta Java.  
- **Nessun COM o installazione di Office necessaria** – ideale per l’automazione lato server e **automate schedule generation**.  
- **API ricca** – supporta ogni proprietà del calendario, inclusi set di lavoro personalizzati e festività.  
- **Output diretto in MPP** – è possibile **save project as MPP** senza conversioni intermedie.

## Prerequisiti

1. **Java Development Kit (JDK) 8+** – assicurati che `java -version` restituisca 1.8 o superiore.  
2. **Aspose.Tasks for Java** – scarica l’ultimo JAR dal [sito Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor tu preferisca.  
4. **Conoscenza di base di Java** – familiarità con classi, metodi e I/O di file.

## Come aggiungere festività al calendario

Di seguito percorriamo ogni passaggio, dalla configurazione dell’ambiente al salvataggio del file MPP finale. I blocchi di codice rimangono invariati rispetto al tutorial originale; le spiegazioni circostanti sono state ampliate per maggiore chiarezza.

### Passo 1: Importare i pacchetti richiesti

Per prima cosa, porta le classi Aspose.Tasks e le utility Java nello scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Passo 2: Configurare la directory dei dati

Definisci dove risiederanno i tuoi file modello di input e i file di output. Sostituisci il segnaposto con il percorso reale sul tuo computer.

```java
String dataDir = "Your Data Directory";
```

### Passo 3: Definire i nomi dei file di input e output

Caricheremo un file MPP esistente (o un progetto vuoto) e scriveremo il risultato in un nuovo file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Passo 4: Caricare il progetto e aggiungere un nuovo calendario

Crea un’istanza `Project` dal file sorgente e aggiungi un calendario denominato **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Passo 5: Personalizzare il calendario (opzionale)

Se ti servono orari di lavoro specifici, festività o eccezioni, chiama il tuo metodo di supporto. L’esempio utilizza `GetTestCalendar` come segnaposto.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Suggerimento professionale:** puoi manipolare direttamente `cal1.getWeekDays()` per impostare le ore lavorative per ciascun giorno della settimana, oppure usare `cal1.getExceptions()` per **add holidays to calendar**.

### Passo 6: Assegnare il calendario al progetto

Indica al progetto di utilizzare il calendario appena creato per tutti i calcoli di pianificazione.

```java
project.set(Prj.CALENDAR, cal1);
```

### Passo 7: Salvare il progetto come MPP

Ora **convert project to MPP** salvandolo con l’opzione `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Passo 8: Confermare il completamento con successo

Un semplice messaggio sulla console ti informa che il processo è terminato senza errori.

```java
System.out.println("Process completed Successfully");
```

## Casi d’uso comuni

- **Generazione automatica di schedule** per progetti ricorrenti (ad es. sprint settimanali).  
- **Migrazione di calendari legacy CSV o Excel** in un file MS Project completo di funzionalità.  
- **Reporting lato server** dove un servizio web restituisce un file MPP su richiesta.  

## Risoluzione dei problemi e ostacoli comuni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| `NullPointerException` su `project.save` | `dataDir` punta a una cartella inesistente | Verifica che la directory esista o creala programmaticamente. |
| Il calendario non viene applicato alle attività | Le attività continuano a fare riferimento al calendario predefinito | Dopo aver impostato `Prj.CALENDAR`, aggiorna anche `Task.CALENDAR` per ciascuna attività se era stato sovrascritto. |
| Il file di output è 0 KB | Permessi di scrittura mancanti | Esegui la JVM con i diritti di file system appropriati o scegli un percorso scrivibile. |

## Domande frequenti

**D: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?**  
R: Sì, Aspose.Tasks per Java supporta un’ampia gamma di versioni di MS Project, da Project 2007 fino all’ultima release, garantendo piena compatibilità.

**D: Posso personalizzare i calendari in base a requisiti specifici del progetto?**  
R: Assolutamente. È possibile definire giorni lavorativi, impostare set di lavoro personalizzati, aggiungere festività e persino creare più calendari all’interno dello stesso file di progetto.

**D: Aspose.Tasks per Java offre supporto per la risoluzione di problemi e assistenza?**  
R: Sì, puoi ottenere aiuto dalla community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?**  
R: Sì, una versione di prova completamente funzionale è disponibile [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?**  
R: Le licenze temporanee possono essere richieste tramite il sito Aspose [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-02-05  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}