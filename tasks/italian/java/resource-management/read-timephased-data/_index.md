---
date: 2026-01-20
description: Scopri come ottenere una risorsa per ID ed estrarre i dati temporizzati
  dalle risorse di MS Project usando Aspose.Tasks per Java.
linktitle: Get resource by id and read timephased data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ottieni la risorsa per ID e leggi i dati temporizzati in Aspose.Tasks
url: /it/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recupera risorsa per ID e leggi i dati timephased in Aspose.Tasks

## Introduction
In questo tutorial, ti guideremo su **come ottenere una risorsa per ID** e leggere i dati timephased per le risorse di MS Project utilizzando Aspose.Tasks per Java. Che tu debba analizzare il carico di lavoro delle risorse o la distribuzione dei costi, estrarre queste informazioni programmaticamente consente di risparmiare innumerevoli ore manuali.

## Quick Answers
- **Qual è la classe principale per caricare un progetto?** `Project` da `com.aspose.tasks`.
- **Come trovo una risorsa specifica?** Usa `project.getResources().getByUid(resourceId)`.
- **Posso leggere sia i dati di lavoro che di costo?** Sì – chiama `resource.getTimephasedData` con il `TimephasedDataType` appropriato.
- **È necessaria una licenza per lo sviluppo?** Una licenza di valutazione gratuita funziona per i test; è necessaria una licenza completa per la produzione.
- **Quale versione di Java è supportata?** Aspose.Tasks per Java supporta JDK 8 e versioni successive.

## What is **get resource by id**?
`get resource by id` è una chiamata di metodo che recupera un oggetto `Resource` da un `Project` utilizzando l'identificatore univoco (UID) della risorsa. Questo UID è assegnato da Microsoft Project al momento della creazione della risorsa e rimane costante per tutta la durata del progetto.

## Why read timephased data?
I dati timephased suddividono il lavoro o il costo di una risorsa in intervalli di tempo discreti (giornalieri, settimanali, mensili). Questa granularità ti consente di:
- Generare report personalizzati sull'utilizzo delle risorse.
- Identificare le sovrallocazioni in anticipo.
- Alimentare i dati in strumenti di previsione o budgeting.

## Prerequisites
Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. **8 o successivo. Puoi scaricarlo dal [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e seguire le istruzioni di installazione.  
2. **Aspose.Tasks for Java Library** – Scarica la libreria Aspose.Tasks per Java dalla [download page](https://releases.aspose.com/tasks/java/) e segui le istruzioni di installazione fornite nella documentazione.  

## Import Packages
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Step 1: Set up Data Directory
Per prima cosa, definisci la directory in cui si trova il tuo file MS Project.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Read MS Project Template File
Specifica il nome del tuo file modello MS Project.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Step 3: Load the Project (java read project resources)
Leggi il file di input usando Aspose.Tasks e caricalo come oggetto `Project`.

```java
Project project = new Project(dataDir + fileName);
```

##= 1.

```java
Resource resource = project.getResources().getByUid(1);
```

## Step 5: Print Timephased Data for Resource Work
Stampa i dati timephased per il lavoro della risorsa.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Step 6: Print Timephased Data for Resource Cost
Stampa i dati timephased per il costo della risorsa.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Common Issues and Solutions
| Problema | Perché succedeose genera una build di produzione. | Carica il file di licenza con ` handle other types of project files apart from Microsoft Project?
Sì, Aspose.Tasks supporta vari formati di file, inclusi MPP, XML e CSV.

### Is Aspose.Tasks compatible with different Java development environments?
Sì, Aspose.Tasks è compatibile con tutti i principali IDE Java e framework.

### Can I manipulate project data using Aspose.Tasks?
Assolutamente, Aspose.Tasks fornisce API estese per creare, modificare e analizzare i dati del progetto.

### Is Aspose.Tasks suitable for enterprise‑level projects?
Sì, Aspose.Tasks è ampiamente usato in ambienti enterprise grazie alla sua affidabilità e scalabilità.

### Where can I find support if I encounter issues while using Aspose.Tasks?
Puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assistenza dalla community e dal team di supporto.

## Frequently Asked Questions

**Q: Come **estrarre i dati del progetto** per più risorse contemporaneamente?**  
A: Loop through `project.getResources()` and call `getTimephasedData` for each resource inside the loop.

**Q: Is there a way to change the time interval (e.g., daily → weekly)?**  
A: Yes, pass a `TimephasedDataType` such as `TimephasedDataType.ResourceWork` together with a `TimephasedData` collection that you can aggregate manually.

**Q: Can I export the timephased data to CSV?**  
A: After retrieving the data, write it to a CSV file using standard Java I/O (`FileWriter`/`BufferedWriter`).

**Q: Does Aspose.Tasks support reading project files created in newer MS Project versions?**  
A: The library is regularly updated to support the latest MPP formats; always use the latest Aspose.Tasks version.

**Q: What performance considerations are there for large projects?**  
A: Load the project once, reuse the `Project` instance, and avoid repeated calls to `getTimephasedData` for the same interval.

**Ultimo aggiornamento:** 2026-01-20  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}