---
date: 2026-01-13
description: Scopri come calcolare la percentuale delle risorse in Java con Aspose.Tasks,
  incluso come ottenere la percentuale di lavoro completato per le risorse di MS Project.
  Guida passo passo con esempi di codice.
linktitle: Perform Percentage Calculations for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: calcolare la percentuale delle risorse in Java usando Aspose.Tasks
url: /it/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# calcolare la percentuale delle risorse java con Aspose.Tasks

## Introduction
Benvenuti! In questo tutorial imparerete **come calcolare la percentuale delle risorse java** utilizzando la libreria Aspose.Tasks per Java. Vi guideremo nell'estrazione del *percent work complete* per ogni risorsa in un file Microsoft Project, spiegheremo perché questa metrica è importante e vi mostreremo il codice esatto di cui avete bisogno. Alla fine, sarete in grado di integrare i calcoli della percentuale delle risorse in qualsiasi soluzione di gestione progetti basata su Java.

## Quick Answers
- **What does “resource percentage” mean?** È la percentuale di lavoro che una risorsa ha completato rispetto al totale del lavoro assegnato.  
- **Which API call returns this value?** `Rsc.PERCENT_WORK_COMPLETE` tramite la classe `Resource`.  
- **Do I need a license?** È necessaria una licenza temporanea o completa di Aspose.Tasks per l'uso in produzione.  
- **Can I use this with other Java frameworks?** Sì – l'API funziona con Spring, Hibernate e progetti Java standard.  
- **What version of Aspose.Tasks is needed?** Qualsiasi versione recente che supporti l'enumerazione `Rsc` (ad es., 24.x).

## What is calculate resource percentage java?
Calcolare la percentuale delle risorse in Java significa leggere programmaticamente un file Microsoft Project e determinare quanto lavoro ha terminato ciascuna risorsa. queste informazioni aiutano i project manager a prevedere le tempistiche, bilanciare i carichi di lavoro e identificare i colli di bottiglia.

## Why get percent work complete?
- **Progress tracking:** Visualizzare a colpo d'occhio quali membri del team sono in linea con il programma.  
- **Capacity planning:** Regolare le future assegnazioni basandosi sulle prestazioni reali.  
- **Reporting:** Generare report di stato accurati per gli stakeholder senza calcoli manuali.

## Prerequisites
### Java Development Environment
Assicurati di avere installato il Java Development Kit (JDK). Puoi scaricare il JDK da [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks Library
Scarica e aggiungi la libreria Aspose.Tasks al tuo progetto da [here](https://releases.aspose.com/tasks/java/) e segui le istruzioni di installazione fornite nella documentazione [here](https://reference.aspose.com/tasks/java/).

## Import Packages
Before we start coding, let's import the necessary packages required for this tutorial:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Step 1: Set up Project File Path
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con la cartella che contiene il tuo file Microsoft Project.

## Step 2: Load the Project
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Questo carica il file **Software Development.mpp** dalla directory specificata.

## Step 3: Iterate Through Resources
```java
for (Resource res : prj.getResources()) {
```
Eseguiamo un ciclo su ogni risorsa definita nel progetto.

## Step 4: Check Resource Name and Get Percent Work Complete
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Il codice verifica innanzitutto che la risorsa abbia un nome e poi stampa il valore **percent work complete** per quella risorsa.

## Common Issues and Solutions
- **NullPointerException** – Assicurati che il percorso del file di progetto sia corretto e che il file venga caricato senza errori.  
- **Incorrect percentages** – Verifica che la risorsa abbia effettivamente lavoro assegnato; altrimenti la percentuale sarà `0`.  
- **License errors** – Usa una licenza valida di Aspose.Tasks o una licenza di valutazione temporanea per evitare restrizioni a runtime.

## Frequently Asked Questions (Original)

### Can I use Aspose.Tasks for Java with other Java frameworks?
Sì, Aspose.Tasks per Java è compatibile con vari framework Java come Spring, Hibernate e altri.

### Does Aspose.Tasks support all versions of Microsoft Project files?
Aspose.Tasks fornisce supporto per tutte le versioni dei file Microsoft Project, inclusi MPP, MPT, XML e altri.

### Can I manipulate project schedules using Aspose.Tasks?
Assolutamente, Aspose.Tasks offre funzionalità complete per manipolare i piani di progetto, inclusi task, risorse, calendari e altro.

### Is there a community forum for Aspose.Tasks support?
Sì, puoi trovare assistenza e interagire con altri utenti sul forum della community di Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

### Does Aspose.Tasks offer temporary licenses for evaluation purposes?
Sì, puoi ottenere una licenza temporanea per la valutazione da [here](https://purchase.aspose.com/temporary-license/).

## Additional FAQ

**Q: How do I format the output to show percentages with a % sign?**  
A: Retrieve the numeric value with `res.get(Rsc.PERCENT_WORK_COMPLETE)` and format it using `String.format("%.2f%%", value)`.

**Q: Can I filter resources to only show those with less than 50 % complete?**  
A: Yes, add an `if` condition checking `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` before printing.

**Q: Is it possible to write the percentages back to the Project file?**  
A: The `Rsc.PERCENT_WORK_COMPLETE` field is read‑only; you would need to adjust task assignments instead.

**Q: Does this work with Project Online (cloud) files?**  
A: You must first download the .mpp file locally; Aspose.Tasks works with the file format, not the cloud service directly.

## Conclusion
In this guide we demonstrated **how to calculate resource percentage java** using Aspose.Tasks, focusing on retrieving the *percent work complete* for each resource. By following the steps above, you can embed precise resource‑percentage analytics into your Java applications, giving you better visibility into project health and resource utilization.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}