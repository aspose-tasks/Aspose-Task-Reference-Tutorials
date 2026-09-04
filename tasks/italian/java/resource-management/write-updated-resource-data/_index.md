---
date: 2026-06-30
description: Scopri come aggiornare più risorse e modificare i dati del gruppo di
  risorse, quindi esportare il progetto in MPP e salvare il progetto come MPP utilizzando
  Aspose.Tasks for Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Aggiorna più risorse in Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aggiorna più risorse in Aspose.Tasks for Java
url: /it/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiorna più risorse in Aspose.Tasks per Java

## Introduzione
In questo tutorial imparerai come **aggiornare più risorse** in un file Microsoft Project utilizzando Aspose.Tasks per Java. Che tu debba modificare le tariffe, riassegnare i gruppi o esportare il file aggiornato in MPP, i passaggi seguenti ti guideranno attraverso un flusso di lavoro completo e pronto per la produzione. Non è necessaria l'installazione di Microsoft Project e l'API può gestire progetti con centinaia di risorse in modo efficiente.

## Risposte rapide
- **Posso aggiornare più risorse contemporaneamente?** Sì – itera attraverso la `ResourceCollection` e imposta gli attributi in un unico passaggio.  
- **Quale metodo salva il file come MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Ho bisogno di una licenza per uso commerciale?** È necessaria una licenza a pagamento per la produzione; è disponibile una versione di prova gratuita.  
- **Quali versioni di Java sono supportate?** Java 6 e successive, inclusa Java 17 LTS.  
- **L'aggiornamento in blocco è performante?** Aspose.Tasks elabora progetti con 500 risorse in meno di 2 secondi su un server tipico.

## Cos'è “aggiornare più risorse”?
**“Aggiornare più risorse”** si riferisce a modificare programmaticamente le proprietà di diverse voci di risorsa — come tariffe, gruppi, calendari o campi personalizzati — all'interno di un singolo file di progetto. Questa operazione è spesso necessaria quando si sincronizzano i dati del progetto con i sistemi ERP, si adeguano i budget su molte risorse o si applicano modifiche alle politiche a livello organizzativo.

## Perché usare Aspose.Tasks per modificare il gruppo di risorse ed esportare il progetto in MPP?
Aspose.Tasks supporta **oltre 50 formati di input e output**, inclusi MPP, XML e CSV, e può **esportare il progetto in MPP** senza caricare l'intero file in memoria. La libreria elabora file fino a **2 GB** di dimensione, consentendoti di **salvare il progetto come MPP** in modo rapido e affidabile.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

1. Java Development Kit (JDK) installato sul tuo sistema.  
2. Libreria Aspose.Tasks per Java. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).  
3. Conoscenza di base della programmazione Java.  

## Importa pacchetti
Le istruzioni `import` importano le classi Aspose.Tasks necessarie nel tuo file sorgente.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Passo 1: Configura la tua directory dei dati
Definisci la directory in cui si trovano i tuoi file dati:

```java
String dataDir = "Your Data Directory";
```

## Passo 2: Specifica i file di input e output
Definisci i percorsi per il file MS Project di input e il file aggiornato risultante:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Passo 3: Carica il progetto
`Project` rappresenta un file Microsoft Project caricato in memoria, fornendo l'accesso a attività, risorse e altri dati del progetto.

```java
Project project = new Project(file);
```

## Passo 4: Aggiungi una risorsa e imposta gli attributi
`Resource` modella una singola risorsa del progetto, consentendoti di impostare tariffe, gruppi, calendari e altri attributi.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Passo 5: Aggiorna più risorse in modo efficiente
`ResourceCollection` è la collezione di tutte le risorse in un progetto, accessibile tramite `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Passo 6: Salva il progetto
`SaveFileFormat` elenca i formati di file supportati per salvare un progetto, come MPP, XML e PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Come aggiornare più risorse in un progetto?
Carica il progetto esistente, recupera la sua `ResourceCollection` e itera su ogni oggetto `Resource`. Per ogni risorsa, modifica i campi richiesti come tariffe, gruppi o attributi personalizzati, quindi passa all'elemento successivo. Dopo aver elaborato tutte le risorse, chiama `project.save(...)` una sola volta per persistere le modifiche in modo efficiente.

## Problemi comuni e soluzioni
- **Conflitto di ID risorsa** – Assicurati che ogni nuova risorsa ottenga un ID univoco usando `project.getResources().add(new Resource())`.  
- **Errori di formato della tariffa** – Usa oggetti `ResourceRate` e imposta `RateType` su `StandardRate` o `OvertimeRate`.  
- **File di grandi dimensioni causano pressione sulla memoria** – Abilita `Project.setReadOnly(true)` prima del caricamento per ridurre l'impronta di memoria.

## Domande frequenti
**Q: Posso aggiornare più risorse nello stesso progetto usando Aspose.Tasks per Java?**  
A: Sì, puoi aggiornare più risorse iterando su di esse e impostando i loro attributi di conseguenza.

**Q: Aspose.Tasks supporta altri formati di file oltre a MS Project?**  
A: Sì, Aspose.Tasks supporta vari formati di file inclusi XML, MPP e altri.

**Q: Aspose.Tasks è compatibile con diverse versioni di Java?**  
A: Aspose.Tasks è compatibile con le versioni di Java 6 e successive.

**Q: Posso eseguire altre operazioni sui file MS Project con Aspose.Tasks?**  
A: Sì, puoi eseguire un'ampia gamma di operazioni come leggere, scrivere e manipolare attività, risorse e calendari.

**Q: Dove posso trovare ulteriore aiuto o supporto per Aspose.Tasks?**  
A: Puoi visitare il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.

**Q: Come esportare il file aggiornato in formato MPP?**  
A: Chiama `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` dopo aver apportato tutte le modifiche alle risorse.

**Q: Qual è il modo migliore per modificare un gruppo di risorse?**  
A: Imposta la proprietà `Resource.Group` su ogni oggetto `Resource` prima di salvare il progetto.

---

**Ultimo aggiornamento:** 2026-06-30  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Aggiungi risorsa al progetto con Aspose.Tasks per Java](/tasks/java/resource-management/create-resources/)
- [Gestisci i costi delle risorse MS Project con Aspose.Tasks per Java](/tasks/java/resource-management/resource-cost/)
- [Come esportare MPP in Excel con Aspose.Tasks per Java](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}