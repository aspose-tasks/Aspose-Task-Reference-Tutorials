---
date: 2026-02-23
description: Scopri come gestire gli straordinari nelle attività di progetto usando
  Aspose.Tasks per Java, incluso come calcolare il costo degli straordinari e semplificare
  il monitoraggio delle risorse.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come gestire gli straordinari nelle attività con Aspose.Tasks
url: /it/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come gestire gli straordinari nelle attività con Aspose.Tasks

## Introduction
Se stai cercando **come gestire gli straordinari** in un file Microsoft Project, sei nel posto giusto. In questo tutorial ti mostreremo come Aspose.Tasks per Java ti consente di leggere, modificare e segnalare le proprietà relative agli straordinari di ogni attività, così da mantenere il tuo programma e il budget accurati.  

## Quick Answers
- **Cosa significa “overtime” in un progetto?** Ore di lavoro aggiuntive oltre la capacità regolare di una risorsa.  
- **Quale classe API fornisce i dati sugli straordinari?** `Task` con la collezione di campi `Tsk` (ad es., `Tsk.OVERTIME_COST`).  
- **È necessaria una licenza per eseguire il campione?** Sì, è richiesta una licenza temporanea o completa di Aspose.Tasks per l'uso in produzione.  
- **Posso calcolare automaticamente il costo degli straordinari?** Assolutamente – recupera `Tsk.OVERTIME_COST` e applica la tua logica di tariffa dei costi.  
- **È compatibile con Java 17?** Sì, Aspose.Tasks per Java supporta Java 8 e versioni successive.

## What is Overtime Management in Project Tasks?
La gestione degli straordinari significa tenere traccia del lavoro aggiuntivo e del costo che si verifica quando le risorse superano il loro normale orario di lavoro. Catturare accuratamente questi dati ti aiuta a prevedere i budget, regolare i programmi e segnalare lo stato realistico del progetto.

## Why Use Aspose.Tasks for Overtime?
* **Nessun Microsoft Project necessario** – lavora direttamente con file .MPP.  
* **Accesso completo ai campi degli straordinari** – costi, lavoro e valori di percentuale completata sono esposti tramite l'enumerazione `Tsk`.  
* **Controllo programmatico** – puoi leggere, modificare o calcolare il costo degli straordinari senza passaggi manuali dell'interfaccia utente.

## Prerequisites
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti in ordine:
- Ambiente di sviluppo Java: assicurati di avere un ambiente di sviluppo Java configurato sulla tua macchina.  
- Aspose.Tasks per Java: scarica e installa la libreria Aspose.Tasks. Puoi trovare la libreria e la sua documentazione [qui](https://reference.aspose.com/tasks/java/).  
- File di progetto: prepara un file di progetto (ad es., TaskOvertimes.mpp) da utilizzare durante il tutorial.

## Import Packages
Nel tuo progetto Java, importa i pacchetti Aspose.Tasks necessari per sfruttare le sue funzionalità. Aggiungi le seguenti istruzioni di importazione:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Create a New Project
Passo 1: Crea un nuovo progetto
Creare un nuovo progetto (o caricare uno esistente) è il primo passo per qualsiasi analisi. Questo soddisfa anche la keyword secondaria **create new project**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Step 2: Iterate Through Tasks and Print Overtime Details
Passo 2: Itera attraverso le attività e stampa i dettagli degli straordinari
Ora percorreremo ogni attività di livello superiore, mostreremo le sue informazioni sugli straordinari e dimostreremo come **calcolare il costo degli straordinari** leggendo il campo `OVERTIME_COST`.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **Suggerimento:** Il valore `OVERTIME_COST` è già calcolato da Aspose.Tasks in base al tasso di straordinario della risorsa. Se hai bisogno di un calcolo personalizzato, moltiplica `OVERTIME_WORK` per il tuo tasso e aggiorna il campo con `tsk.set(Tsk.OVERTIME_COST, yourValue);`.

## Common Issues and Solutions
| Problema | Soluzione |
|----------|-----------|
| **Valori null per i campi degli straordinari** | Assicurati che il file .MPP di origine contenga effettivamente dati sugli straordinari; altrimenti i campi restituiscono `null`. |
| **Costo errato dopo la modifica** | Dopo aver modificato il lavoro o il costo degli straordinari, chiama `project.save()` per persistere le modifiche. |
| **Licenza non trovata** | Posiziona il tuo file `Aspose.Tasks.lic` nella radice del progetto o imposta la licenza programmaticamente prima di caricare il progetto. |

## Frequently Asked Questions

**D: Aspose.Tasks è adatto per la gestione di progetti su larga scala?**  
R: Sì, Aspose.Tasks è progettato per gestire progetti di varie dimensioni, da piccole iniziative a programmi grandi e complessi.

**D: Posso integrare Aspose.Tasks con altri framework Java?**  
R: Assolutamente! Aspose.Tasks si integra perfettamente con Spring, Jakarta EE e altri ecosistemi Java, migliorandone la versatilità.

**D: Ci sono considerazioni di licenza per l'uso di Aspose.Tasks?**  
R: Sì, puoi trovare i dettagli della licenza e ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso cercare assistenza o discutere domande relative ad Aspose.Tasks?**  
R: Visita il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per interagire con la community e richiedere supporto.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
R: Sì, puoi accedere alla versione di prova gratuita [qui](https://releases.aspose.com/).

**D: Come calcolo il costo degli straordinari per una risorsa specifica?**  
R: Recupera il tasso di straordinario della risorsa, moltiplicalo per `OVERTIME_WORK` (in ore) e imposta il risultato su `OVERTIME_COST` se hai bisogno di un calcolo personalizzato.

## Conclusion
Aspose.Tasks per Java semplifica **come gestire gli straordinari** nelle attività di progetto, offrendo agli sviluppatori accesso programmatico diretto a costi, lavoro e metriche di avanzamento degli straordinari. Seguendo questa guida puoi caricare un progetto, leggere i dettagli degli straordinari, regolare le percentuali e persino calcolare costi personalizzati degli straordinari — tutto senza aprire Microsoft Project.

---

**Ultimo aggiornamento:** 2026-02-23  
**Testato con:** Aspose.Tasks for Java (ultima versione)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}