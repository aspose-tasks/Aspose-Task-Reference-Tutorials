---
date: 2026-01-31
description: Scopri come recuperare le eccezioni del calendario da MS Project usando
  Aspose.Tasks per Java e convertire l'UTC in orari locali. Questo tutorial di Aspose.Tasks
  per Java fornisce esempi di codice passo‑passo.
linktitle: Convert UTC to Local – Calendar Exceptions with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Converti UTC in locale – Eccezioni del calendario con Aspose.Tasks
url: /it/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperare le eccezioni del calendario con Aspose.Tasks – asp tasks java tutorial

## Introduction
In questo **asp tasks java tutorial** imparerai come recuperare le eccezioni del calendario da un file Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Le eccezioni del calendario rappresentano periodi non lavorativi come festività o regole personalizzate di orario di lavoro, e la possibilità di leggerle programmaticamente è essenziale per il livellamento delle risorse, la generazione di report e la logica di pianificazione personalizzata. Accedendo a queste eccezioni puoi anche **convertire UTC in locale** per calcoli di programmazione accurati. Ti guideremo passo‑passo, così potrai integrare questa funzionalità nelle tue applicazioni Java con fiducia.

## Quick Answers
- **What does this tutorial cover?** Recuperare le eccezioni del calendario da un file MPP usando Aspose.Tasks per Java.  
- **How long does implementation take?** Circa 10‑15 minuti per una configurazione di base.  
- **Prerequisites?** JDK, Aspose.Tasks per Java e un IDE (IntelliJ IDEA o Eclipse).  
- **Do I need a license?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Supported Project versions?** Tutti i principali formati di MS Project (MPP, MPT, XML).

## What is asp tasks java tutorial?
Un'interno di progetti Java. Fornisce snippet di codice concreti, spiegazioni delle migliori pratiche e scenari reali affinché gli sviluppatori possano manipolare i file Project senza dover installare Microsoft Project.

## Why retrieve calendar exceptions?
Comprendere le eccezioni del calendario ti permette di:
- Generare linee temporali di progetto accurate che rispett Creare strumenti di reporting personalizzati che evidenziano i giorni non lavorativi.
- **Convertire UTC in locale** quando si aggregano dati di programmazione tra regioni.
- Sincronizzare i calendari di Project con sistemi esterni (es. ERP, HR).

## Prerequisites
Prima di iniziare, assicurati di avere i seguenti requisiti:

1. **Java Development Kit (JDK)** – Verifica di avere installato JDK 8 o versioni successive.
2. **Aspose.Tasks for Java** – Scarica e installa Aspose.Tasks for Java da [qui](https://releases.aspose.com/tasks/java/).
3. **Integrated Development Environment (IDE)** – Puoi.

are con Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **Pro tip:** Usa un percorso assoluto o un percorso relativo alla cartella delle risorse del tuo progetto per evitare `FileNotFoundException`.

## Step 2: Load MS Project File
```java
Project project = new Project(dataDir + "project.mpp");
```

Questa riga inizializza un nuovo oggetto `Project` caricando il file MS Project specificato dal percorso.

## Step 3: Retrieve Calendar Exceptions
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

Qui, iteriamo su ogni calendario nel progetto e poi su ciascuna eccezione del calendario all'interno di quel calendario. Stampiamo le date di inizio e fine di ogni eccezione.

##Date` e `ToDate`, sono espressi in UTC per impostazione predefinita. Per lavorare mantenere intatti i blocchi di codice originali):

- Usa `java.time.ZoneId` per specificare il fuso orario di destinazione.  
- Chiama `toInstant().atZone(targetZone)` sugli oggetti `Date` restituiti da `getFromDate()` e `getToDate()`.

Applicare questa conversione ti consente di allineare i calendari di progetto con le ore lavorative locali dei membri del team, particolarmente utile per progetti multinazionali.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **No output printed** | Il file di progetto non contiene eccezioni del calendario. | Verifica che il calendario in MS Project abbia eccezioni definite (es. festività). |
| **`NullPointerException`** | Il percorso `dataDir` è errato o il file non è stato trovato. | Controlla nuovamente il percorso della directory e assicurati che `project.mpp` esista. |
| **Time zone mismatch** | Le date sono visualizzate in UTC. | Usa `calExc.getFromDate().toLocalDateTime()` per convertire in ora locale, se necessario. |

## Frequently Asked Questions supporta varie versioni di file MS Project, inclusi i formati MPP, MPT e XML.

### Is there a free trial available for Aspose.Tasks?
Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks da [qui](https://releases.aspose.com/).

### Where can I find documentation for Aspose.Tasks for Java?
Puoi consultare la documentazione [qui](https://reference.aspose.com/tasks/java/).

### How can I get support for Aspose.Tasks?
Puoi ottenere supporto dal forum della community [qui](https://forum.aspose.com/c/tasks/15).

### Is there an option for temporary licenses for Aspose.Tasks?
Sì, puoi ottenere licenze temporanee da [qui](https://purchase.aspose.com/temporary-license/).

**Additional Q&A**

**Q:** *Can I modify calendar exceptions after retrieving them?*  
**A:** Assolutamente. Usa `CalendarException.setFromDate()` e `setToDate()` per modificare le date, quindi salva il progetto con `project.save(...)`.

**Q:** *Does Aspose.Tasks preserve custom fields on calendars?*  
**A:** Sì, tutti i campi personalizzati e gli attributi estesi vengono mantenuti durante il caricamento e il salvataggio del progetto.

**Q:** *How do I convert the retrieved UTC dates to my local time conversione `ZoneId` e `ZonedDateTime` di Java agli oggetti `Date` restituiti dall'API. Questo garantisce che la programmazione rifletta le tue ore lavorative locali.

## Conclusion
In questo **asp tasks java tutorial** abbiamo imparato come recuperare le eccezioni del calendario da MS Project usando Aspose.Tasks per Java e come **convertire UTC in locale** per una programmazione accurata. Seguendo questi semplici passaggi, potrai integrare senza problemi questa funzionalità nelle tue applicazioni Java, abilitando funzionalità di pianificazione più ricche e analisi di progetto più precise.

---

**Last Updated:** 202624.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}