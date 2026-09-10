---
date: 2026-09-09
description: Scopri come identificare le attività cross‑project utilizzando Aspose.Tasks
  per Java. Esplora l'integrazione senza interruzioni, la gestione efficiente e esempi
  reali.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identificare le attività cross‑project in Aspose.Tasks
og_description: Identificare le attività cross‑project in Aspose.Tasks per Java. Scopri
  come impostare la directory dei documenti, recuperare gli ID delle attività e gestire
  i progetti collegati in modo efficiente.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identificare le attività cross‑project in Aspose.Tasks – Guida Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identificare le attività cross‑project in Aspose.Tasks
url: /it/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identificare attività cross project in Aspose.Tasks

## Introduzione
In questo tutorial imparerai **come identificare attività cross project** con Aspose.Tasks per Java. Che tu gestisca un portafoglio di schedule interdipendenti o debba verificare dipendenze esterne, i passaggi seguenti mostrano come individuare le attività che fanno riferimento ad altri file di progetto, recuperare i loro identificatori e lavorare con esse programmaticamente.

## Risposte rapide
- **Cosa significa “identify cross project tasks”?** Significa individuare le attività che fanno riferimento o dipendono da attività in un altro file di progetto.  
- **Quale metodo stampa l'ID dell'attività?** Usa `externalTask.get(Tsk.ID)` per stampare l'ID dell'attività.  
- **Come impostare la directory del documento?** Assegna il percorso della cartella a una variabile `String` (ad es., `dataDir`).  
- **Quale proprietà recupera un'attività per UID?** Chiama `getChildren().getByUid(yourUid)`.  
- **È necessaria una licenza per l'uso in produzione?** Sì, è richiesta una licenza valida di Aspose.Tasks per le distribuzioni commerciali.

## Che cosa è “identify cross project tasks”?
Identificare attività cross‑project ti consente di tracciare le relazioni tra attività distribuite su più file Microsoft Project. Individuando le attività che fanno riferimento o dipendono da schedule esterni, puoi comprendere come gli elementi di lavoro interagiscono attraverso i confini dei progetti, evitare sforzi duplicati e mantenere cronologie accurate. Questa capacità è essenziale per portafogli su larga scala in cui le attività sono condivise o dipendono da schedule esterne.

## Perché usare Aspose.Tasks per Java?
Aspose.Tasks per Java supporta **oltre 50 formati di input e output** (inclusi MPP, MPX, XML e CSV) e può elaborare progetti con **fino a 10.000 attività** senza caricare l'intero file in memoria. La libreria funziona su qualsiasi piattaforma compatibile con JVM, non richiede l'installazione di Microsoft Project e offre pieno accesso API a ID, UID, ID esterni e metadati di collegamento.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Un ambiente di sviluppo Java funzionante (JDK 8 o superiore).  
- Aspose.Tasks per Java installato. Puoi scaricarlo **[qui](https://releases.aspose.com/tasks/java/)**.  
- Un file di licenza valido di Aspose.Tasks se prevedi di eseguire il codice in produzione.

## Importare i pacchetti
La classe `Project` rappresenta un file Microsoft Project, `Task` rappresenta un'attività individuale e `Tsk` fornisce le costanti dei campi attività.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Passo 1: impostare la directory del documento
La stringa `dataDir` contiene il percorso della cartella che contiene i tuoi file `.mpp`.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Passo 2: caricare il progetto esterno
`Project externalProject` carica il file di progetto esterno specificato per l'ispezione.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Passo 3: recuperare l'attività esterna per uid
`externalProject.getChildren().getByUid(uid)` recupera un'attività dalla collezione di attività del progetto esterno usando il suo identificatore unico.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Passo 4: stampare l'ID dell'attività (caso d'uso principale)
`externalTask.get(Tsk.ID)` restituisce l'ID interno assegnato da Aspose.Tasks per l'attività specificata.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Passo 5: stampare l'ID originale (esterno) dell'attività
`externalTask.get(Tsk.ExternalID)` recupera l'ID originale dell'attività così definito nel file di progetto sorgente.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Ripeti i passaggi precedenti per tutte le attività aggiuntive che devi monitorare tra i progetti.

## Problemi comuni e suggerimenti
- **Errori di percorso** – Assicurati che `dataDir` termini con il separatore di file appropriato (`/` o `\\`).  
- **UID non trovato** – Verifica che l'UID esista nel progetto esterno; usa `externalProject.getRootTask().getChildren().size()` per elencare gli UID disponibili.  
- **Eccezioni di licenza** – Una licenza mancante o non valida genererà un'eccezione di licenza a runtime.  
- **Progetti di grandi dimensioni** – Per progetti con più di 5.000 attività, considera l'uso di `ProjectReader` con il flag `LoadOptions` per lo streaming dei dati e ridurre il consumo di memoria.

## Domande frequenti

**Q: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
A: Sì, Aspose.Tasks supporta più linguaggi, tra cui Java, .NET e altri.

**Q: Dove posso trovare la documentazione dettagliata per Aspose.Tasks per Java?**  
A: Consulta la documentazione **[qui](https://reference.aspose.com/tasks/java/)**.

**Q: È disponibile una prova gratuita per Aspose.Tasks per Java?**  
A: Sì, puoi ottenere una prova gratuita **[qui](https://releases.aspose.com/)**.

**Q: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
A: Ottieni una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.

**Q: Hai bisogno di aiuto o hai domande specifiche?**  
A: Visita il forum di supporto di Aspose.Tasks **[qui](https://forum.aspose.com/c/tasks/15)**.

---

**Ultimo aggiornamento:** 2026-09-09  
**Testato con:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Autore:** Aspose

## Tutorial correlati

- [Creare dipendenze di attività di gestione progetti in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Impostare la data di inizio del progetto e gestire attività padre e figlio in Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Creare progetto MPP Java – Modificare l'avanzamento delle attività con Aspose.Tasks](/tasks/java/task-properties/change-progress/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}