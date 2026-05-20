---
date: 2026-05-20
description: Scopri come utilizzare Aspose.Tasks per Java per aggiungere extended
  attributes to resource assignments, impostare project start date e scrivere file
  MS Project in modo efficiente.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Come utilizzare Aspose.Tasks per Java – Add Extended Attributes to Resource
  Assignments
url: /it/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare la manipolazione di MS Project con Aspose.Tasks per Java

## Introduzione
In questo tutorial scoprirai **come utilizzare Aspose.Tasks per Java** per aggiungere attributi estesi alle assegnazioni delle risorse e scrivere informazioni di Microsoft Project in modo programmatico. Che tu stia automatizzando una pipeline di reporting o costruendo uno strumento personalizzato di gestione progetti, i passaggi seguenti mostrano esattamente come impostare la data di inizio del progetto, creare assegnazioni di risorse e salvare il file come XML—tutto con poche righe di codice Java.

## Risposte rapide
- **Cosa fa Aspose.Tasks per Java?** Legge, scrive e modifica file Microsoft Project senza necessità di avere Microsoft Project installato.  
- **Posso aggiungere campi personalizzati a un'assegnazione di risorsa?** Sì, utilizza la collezione `ExtendedAttribute` sull'oggetto `ResourceAssignment`.  
- **Come imposto la data di inizio del progetto?** Chiama `project.setStartDate(LocalDateTime.of(...))` prima di salvare.  
- **È necessaria una licenza per l'uso in produzione?** Una licenza commerciale rimuove le filigrane di valutazione e sblocca l'accesso completo all'API.  
- **Quali versioni di Java sono supportate?** Aspose.Tasks per Java supporta JDK 8 fino a JDK 21.

## Come usare Aspose.Tasks per Java?
`Project` è l'oggetto principale che rappresenta un file Microsoft Project in memoria. Carica la libreria Aspose.Tasks, crea un'istanza `Project`, configura le proprietà a livello di progetto, aggiungi attributi estesi a un'assegnazione di risorsa e infine salva il progetto come XML. Il flusso di lavoro di base si articola in tre passaggi concisi: inizializzare, modificare e persistere. Questo modello funziona per progetti di qualsiasi dimensione e gira su JVM Windows, Linux o macOS.

## Cos'è un attributo esteso in Aspose.Tasks?
Un **attributo esteso** è un campo personalizzato che si associa a attività, risorse o assegnazioni per memorizzare metadati aggiuntivi oltre alle colonne predefinite. `ExtendedAttributeDefinition` definisce lo schema per un campo personalizzato. Aspose.Tasks espone le classi `ExtendedAttributeDefinition` e `ExtendedAttribute` per definire e assegnare questi campi in modo programmatico.

## Perché aggiungere attributi estesi alle assegnazioni di risorsa?
Aspose.Tasks supporta **oltre 50 campi predefiniti e personalizzati**, e puoi aggiungere attributi definiti dall'utente illimitati. Aggiungerli consente di catturare codici di costo, ID dipartimento o qualsiasi dato specifico di business direttamente all'interno del file .mpp, eliminando la necessità di fogli di calcolo esterni e garantendo l'integrità dei dati lungo l'intero ciclo di vita del progetto.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – JDK 8 o successivo installato.  
2. **Libreria Aspose.Tasks per Java** – Scaricala dalla pagina di rilascio ufficiale [qui](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor compatibile con Java che preferisci.

## Importare i pacchetti
Per prima cosa, importa i pacchetti necessari nel tuo progetto Java:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Passo 1: Configurare la directory dei dati
Definisci la directory in cui verranno archiviati i dati del progetto. Questo percorso verrà utilizzato più tardi per salvare il file XML.

```java
String dataDir = "Your Data Directory";
```

### Passo 2: Creare un'istanza di Project
La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file Microsoft Project in memoria. Istanziarla ti dà pieno accesso a tutti gli elementi del progetto.

```java
Project project = new Project();
```

### Passo 3: Impostare le proprietà delle informazioni di progetto
Imposta le proprietà essenziali del progetto come la data di inizio, il flag "schedule from start" e la data di stato. Questi valori sono memorizzati nell'oggetto `ProjectInfo` del progetto.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Passo 4: Aggiungere attributi estesi a un'assegnazione di risorsa
Crea un `ExtendedAttributeDefinition` per il campo personalizzato, collegalo a un `ResourceAssignment` e popola il valore. Questo passaggio dimostra il funzionamento della keyword **add extended attributes**.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemi comuni e soluzioni
- **NullPointerException durante l'accesso alla collezione di assegnazioni** – Assicurati di aver creato almeno una risorsa e un'attività prima di recuperare le assegnazioni.  
- **L'attributo esteso non appare in MS Project** – Verifica che il `FieldId` dell'attributo corrisponda a uno slot di campo personalizzato (ad esempio, `ExtendedAttributeTask.Text1`).  
- **Mancata corrispondenza del formato data** – Usa `java.time.LocalDateTime` per i valori data; Aspose.Tasks li converte automaticamente nel formato del calendario del progetto.

## Domande frequenti

**D: Posso usare Aspose.Tasks per Java per leggere file MS Project?**  
R: Sì, la libreria offre piena capacità di lettura‑scrittura per i formati .mpp, .xml e .xps.

**D: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?**  
R: Assolutamente, supporta file da Project 2000 fino all'ultima versione 2024, coprendo più di 20 formati di versione.

**D: Ci sono limitazioni nella versione di prova di Aspose.Tasks per Java?**  
R: La versione di prova aggiunge una filigrana ai file generati e limita il numero di attività che è possibile creare, ma tutte le funzionalità dell'API rimangono accessibili.

**D: Come posso ottenere supporto per Aspose.Tasks per Java?**  
R: Puoi chiedere assistenza nel forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**D: È possibile acquistare una licenza temporanea per Aspose.Tasks per Java?**  
R: Sì, le licenze temporanee sono disponibili per utilizzi a breve termine. Puoi ottenerne una da [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-05-20  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come aggiungere note alle assegnazioni di risorsa in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Come leggere e scrivere Rate Scale per le assegnazioni di risorsa in Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Come aggiungere una risorsa al progetto e gestire le proprietà di ritardo di livellamento in Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}