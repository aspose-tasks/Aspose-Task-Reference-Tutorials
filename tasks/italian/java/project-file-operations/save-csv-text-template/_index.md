---
date: 2025-12-21
description: Scopri come salvare il progetto come modello, esportare MPP in CSV e
  convertire MPP in testo utilizzando Aspose.Tasks per Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Salva progetto come modello, CSV e testo con Aspose.Tasks per Java
url: /it/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva progetto come modello, CSV e testo con Aspise.Tasks

## Introduction
In questo tutorial, scoprirai **come salvare un progetto come modello** e anche come esportare i tuoi file Microsoft Project (MPP) in formati CSV e plain‑text utilizzando la libreria Aspose.Tasks per Java. Che tu abbia bisogno di creare un modello di progetto riutilizzabile, generare report CSV per l'analisi, o produrre semplici estratti di testo per l'integrazione, questi passaggi ti guideranno attraverso il processo in modo rapido ed efficiente.

## Quick Answers
- **Posso esportare MPP in CSV?** Sì – usa `project.save(..., SaveFileFormat.CSV)`.  
- **Come esportare testo?** Salva con `SaveFileFormat.TEXT`.  
- **Cosa fa “save project as template”?** Crea un file `.mpt` che rimuove i valori reali e di baseline, pronto per il riutilizzo.  
- **È necessaria una licenza?** È disponibile una versione di prova; per la produzione è richiesta una licenza commerciale.  
- **Quale versione di Java è necessaria?** Java 8+ è supportata.

## What is “save project as template”?
Salvare un progetto come modello (`.mpt`) cattura la struttura, la gerarchia delle attività e le assegnazioni delle risorse, rimuovendo le date di inizio/fine effettive e i dati di baseline. Questo rende il modello ideale per riutilizzare un layout di progetto standard in più nuovi progetti.

## Why use Aspose.Tasks for Java?
Aspose.Tasks ti consente di manipolare i file Microsoft Project senza dover installare Microsoft Project stesso. Supporta **come esportare MPP**, **come esportare testo** e **convertire MPP in CSV**, tutto da codice Java puro, perfetto per l'automazione lato server, pipeline CI o utility desktop.

## Prerequisites
Prima di iniziare, assicurati di avere:

1. Java Development Kit (JDK) 8 o superiore installato.  
2. La libreria Aspose.Tasks per Java aggiunta al tuo progetto. Scaricala da [here](https://releases.aspose.com/tasks/java/).  
3. Una conoscenza di base della sintassi Java e della configurazione di progetti Maven/Gradle.

## Import Packages
Per prima cosa, importa le classi necessarie nel tuo file sorgente Java:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Save Project as CSV (Export MPP to CSV)
Esportare un file MPP in CSV è utile per l'analisi dei dati in Excel o strumenti BI.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Save Project as Text (How to Export Text)
Se hai bisogno di una rappresentazione plain‑text di attività, risorse o assegnazioni, salva il progetto come file di testo.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as Text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Save Project as Template (Create Project Template Java)
Creare un modello riutilizzabile rimuove le date effettive e le baseline, lasciando uno scheletro pulito per i nuovi progetti.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Set Template Options
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Step 3: Save as Template
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Common Issues & Tips
- **File non trovato:** Assicurati che il percorso a `YourProject.mpp` sia corretto o utilizza un percorso assoluto.  
- **Eccezioni di licenza:** Senza una licenza valida, la libreria funziona in modalità di valutazione e può aggiungere filigrane. Applica la tua licenza all'inizio del codice (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Progetti di grandi dimensioni:** Per file MPP molto grandi, considera di aumentare la dimensione dell'heap JVM (`-Xmx2g`) per evitare `OutOfMemoryError`.

## Conclusion
Abbiamo coperto **come salvare un progetto come modello**, così come **esportare MPP in CSV** e **convertire MPP in testo** utilizzando Aspose.Tasks per Java. Queste funzionalità ti consentono di automatizzare la gestione dei dati di progetto, generare modelli riutilizzabili e integrare le informazioni di progetto in altri sistemi, il tutto senza la necessità di installare Microsoft Project.

## FAQ's
### Q: Aspose.Tasks per Java può gestire file di progetto complessi?
A: Assolutamente! Aspose.Tasks per Java può gestire progetti di diversa complessità con facilità, fornendo un supporto completo per i formati di file Microsoft Project.  
### Q: È disponibile una versione di prova per Aspose.Tasks per Java?
A: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per Java da [here](https://releases.aspose.com/).  
### Q: Dove posso trovare supporto per Aspose.Tasks per Java?
A: Puoi visitare il [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda riguardante Aspose.Tasks per Java.  
### Q: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
A: Sì, puoi acquistare una licenza temporanea da [here](https://purchase.aspose.com/temporary-license/), che ti permette di valutare il pieno potenziale della libreria.  
### Q: Aspose.Tasks per Java è compatibile con diversi sistemi operativi?
A: Sì, Aspose.Tasks per Java è compatibile con vari sistemi operativi, inclusi Windows, macOS e Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose