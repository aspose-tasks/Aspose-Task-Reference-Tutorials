---
date: 2025-12-03
description: Scopri come creare un calendario MS Project, convertire un progetto in
  MPP e salvare il progetto MPP senza sforzo usando Aspose.Tasks per Java.
language: it
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Crea calendario MS Project e salva come MPP con Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creare un calendario MS Project e salvarlo come MPP con Aspose.Tasks

## Introduzione

Nella gestione moderna dei progetti è spesso necessario **creare file calendario MS Project** e poi condividerli nel formato nativo MPP. Che tu stia consolidando programmi da più fonti o migrando dati legacy, la capacità di generare un calendario programmaticamente fa risparmiare tempo ed elimina errori manuali. Questo tutorial ti guida attraverso l’intero processo di creazione di un calendario in MS Project, personalizzazione e infine **convertire il progetto in MPP** usando l’API Aspose.Tasks per Java.

## Risposte rapide
- **Cosa copre questo tutorial?** Creare un calendario in MS Project e salvarlo come file MPP con Aspose.Tasks per Java.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quale versione di Java è necessaria?** Java 8 o superiore (JDK 8+).  
- **Posso personalizzare il calendario?** Sì – è possibile aggiungere orari di lavoro, eccezioni e festività.  
- **Quanto tempo richiede l’implementazione?** Circa 10‑15 minuti per un calendario di base.

## Che cosa significa “creare calendario MS Project”?

Creare un calendario MS Project significa definire programmaticamente i giorni lavorativi, le ore e le eccezioni che guidano la pianificazione delle attività all’interno di un file Microsoft Project. Utilizzando Aspose.Tasks è possibile costruire, modificare e persistere questi calendari senza mai aprire l’interfaccia di Microsoft Project.

## Perché usare Aspose.Tasks per questo compito?

- **Compatibilità completa .NET/Java** – funziona su qualsiasi piattaforma che supporta Java.  
- **Nessun COM o installazione di Office necessaria** – ideale per l’automazione lato server.  
- **API ricca** – supporta ogni proprietà del calendario, incluse settimane lavorative personalizzate e festività.  
- **Output diretto MPP** – è possibile **salvare il progetto in MPP** senza conversioni intermedie.

## Prerequisiti

1. **Java Development Kit (JDK) 8+** – assicurati che `java -version` riporti 1.8 o superiore.  
2. **Aspose.Tasks per Java** – scarica l’ultimo JAR dal [sito Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor tu preferisca.  
4. **Conoscenza di base di Java** – familiarità con classi, metodi e I/O di file.

## Guida passo‑passo

### Passo 1: Importare i pacchetti richiesti

Per prima cosa, porta le classi Aspose.Tasks e le utility Java nello scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Passo 2: Configurare la directory dei dati

Definisci dove risiederanno i file modello di input e i file di output. Sostituisci il segnaposto con il percorso reale sulla tua macchina.

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

Crea un’istanza `Project` dal file sorgente e aggiungi un calendario chiamato **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Passo 5: Personalizzare il calendario (opzionale)

Se ti servono orari di lavoro specifici, festività o eccezioni, chiama il tuo metodo di supporto. L’esempio usa `GetTestCalendar` come segnaposto.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Suggerimento:** Puoi manipolare direttamente `cal1.getWeekDays()` per impostare le ore lavorative per ciascun giorno della settimana.

### Passo 6: Assegnare il calendario al progetto

Indica al progetto di utilizzare il calendario appena creato per tutti i calcoli di pianificazione.

```java
project.set(Prj.CALENDAR, cal1);
```

### Passo 7: Salvare il progetto come MPP

Ora **converti il progetto in MPP** salvandolo con l’opzione `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Passo 8: Confermare il completamento

Un semplice messaggio sulla console ti informa che il processo è terminato senza errori.

```java
System.out.println("Process completed Successfully");
```

## Casi d’uso comuni

- **Generazione automatica di schedule** per progetti ricorrenti (es. sprint settimanali).  
- **Migrazione di calendari legacy CSV o Excel** in un file MS Project completo.  
- **Reporting lato server** dove un servizio web restituisce un file MPP su richiesta.  

## Risoluzione dei problemi e ostacoli comuni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| `NullPointerException` su `project.save` | `dataDir` punta a una cartella inesistente | Verifica che la directory esista o creala programmaticamente. |
| Calendario non applicato alle attività | Le attività continuano a fare riferimento al calendario predefinito | Dopo aver impostato `Prj.CALENDAR`, aggiorna anche `Task.CALENDAR` per ogni attività se era stato sovrascritto. |
| Il file di output è 0 KB | Mancano i permessi di scrittura | Esegui la JVM con i diritti di file system appropriati o scegli un percorso scrivibile. |

## Domande frequenti

**D: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?**  
R: Sì, Aspose.Tasks per Java supporta un’ampia gamma di versioni di MS Project, da Project 2007 fino all’ultima release, garantendo piena compatibilità.

**D: Posso personalizzare i calendari secondo requisiti specifici del progetto?**  
R: Assolutamente. È possibile definire giorni lavorativi, impostare settimane lavorative personalizzate, aggiungere festività e persino creare più calendari all’interno dello stesso file di progetto.

**D: Aspose.Tasks per Java offre supporto per la risoluzione dei problemi?**  
R: Sì, puoi ottenere assistenza dal forum della community Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?**  
R: Sì, una versione di prova completamente funzionale è disponibile [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?**  
R: Le licenze temporanee possono essere richieste tramite il sito Aspose [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2025-12-03  
**Testato con:** Aspose.Tasks per Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}