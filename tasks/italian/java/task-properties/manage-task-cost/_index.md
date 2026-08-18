---
date: 2026-02-20
description: Scopri come calcolare la varianza dei costi di progetto e gestire i costi
  delle attività in Java usando Aspose.Tasks. Segui la nostra guida passo‑passo per
  impostare i costi e controllare i budget.
linktitle: Manage Task Costs in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Calcola la varianza dei costi del progetto con Aspose.Tasks per Java
url: /it/java/task-properties/manage-task-cost/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calcolare la Varianza dei Costi del Progetto con Aspose.Tasks

## Introduzione
In questo tutorial completo scoprirai **come calcolare la varianza dei costi del progetto** e gestire in modo efficiente i costi delle attività all'interno delle tue applicazioni Java con Aspose.Tasks. Che tu stia monitorando un piccolo progetto interno o un'ampia implementazione aziendale, comprendere la varianza dei costi ti aiuta a mantenere i budget sotto controllo e a individuare i superamenti in anticipo.

## Risposte Rapide
- **Che cos'è la varianza dei costi?** La differenza tra il costo pianificato (fisso) e il costo reale (rimanente).  
- **Quale metodo API imposta il costo di un'attività?** `task.set(Tsk.COST, BigDecimal.valueOf(...))`.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.  
- **Posso recuperare i dati sui costi a livello di progetto?** Sì, accedendo alle proprietà di costo dell'attività radice.  
- **Quale versione di Java è supportata?** Aspose.Tasks funziona con Java 8 e versioni successive.

## Che cosa significa “calcolare la varianza dei costi del progetto”?
Calcolare la varianza dei costi del progetto significa confrontare il **costo fisso** che hai originariamente pianificato per un'attività o per l'intero progetto con il **costo rimanente** che riflette il lavoro ancora da svolgere. La varianza ti indica se sei sotto o sopra il budget, consentendo aggiustamenti proattivi.

## Perché usare Aspose.Tasks per calcolare la varianza dei costi del progetto?
- **API Java completa, senza dipendenze .NET** – nessuna libreria nativa richiesta.  
- **Ricche proprietà di gestione dei costi** (`COST`, `FIXED_COST`, `REMAINING_COST`, `COST_VARIANCE`).  
- **Facile integrazione** con progetti Maven/Gradle esistenti.  
- **Report accurati** che possono essere esportati in file MS Project®.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – Java 8 o successiva installata.  
2. **Libreria Aspose.Tasks per Java** – scaricala dal sito ufficiale **[qui](https://releases.aspose.com/tasks/java/)**.  
3. Un IDE o uno strumento di build (IntelliJ, Eclipse, Maven, Gradle) per compilare ed eseguire il codice di esempio.

## Importare i Pacchetti
Aggiungi le classi necessarie di Aspose.Tasks al tuo file sorgente Java così da poter lavorare con progetti e attività.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Import Aspose.Tasks classes
```

## Guida Passo‑Passo

### Passo 1: Configurare il Progetto
Per prima cosa, crea una nuova istanza `Project` e indica una cartella dove potrai salvare i file generati.

```java
// Set the path to your document directory
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project();
```

### Passo 2: Aggiungere una Nuova Attività
Aggiungi un'attività sotto l'attività radice. Qui assegneremo i costi.

```java
// Add a new task to the root task
Task task = project.getRootTask().getChildren().add("Task");
```

### Passo 3: Impostare il Costo dell'Attività – **come impostare il costo**
Assegna un costo pianificato all'attività. In uno scenario reale questo potrebbe provenire da un foglio di calcolo di budgeting.

```java
// Set the task cost to 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```

### Passo 4: Recuperare e Visualizzare le Informazioni sui Costi – **come gestire i costi**
Ora leggeremo le varie proprietà di costo, inclusa la varianza di costo calcolata.

```java
// Retrieve and print task information
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Retrieve and print project-level cost information
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```

**Ciò che vedrai:**  
- `Remaining Cost` riflette il lavoro ancora da completare.  
- `Fixed Cost` è la baseline che hai impostato (800 in questo esempio).  
- `Cost Variance` è calcolata automaticamente come **Fixed – Remaining**.  
- Gli stessi valori sono disponibili a livello di progetto (attività radice), permettendoti di **calcolare la varianza dei costi del progetto** per tutte le attività.

### Passo 5: Ripetere per Attività Aggiuntive (Opzionale)
Se il tuo progetto ha più fasi, ripeti i Passi 2‑4 per ogni attività. Sommare le varianze individuali ti fornisce la varianza complessiva dei costi del progetto.

## Problemi Comuni e Soluzioni
| Problema | Perché accade | Soluzione |
|----------|---------------|-----------|
| `NullPointerException` quando si accede alle proprietà dell'attività | L'attività non è stata aggiunta alla gerarchia del progetto. | Assicurati di chiamare `project.getRootTask().getChildren().add(...)` prima di impostare i costi. |
| I valori dei costi appaiono come `0` | Uso di `int` invece di `BigDecimal`. | Usa sempre `BigDecimal.valueOf(...)` come mostrato. |
| Varianza inattesa (negativa) | `REMAINING_COST` supera `FIXED_COST`. | Verifica di aggiornare il costo rimanente man mano che il lavoro avanza. |

## Domande Frequenti

**D: Dove posso trovare la documentazione per Aspose.Tasks per Java?**  
R: Puoi accedere alla documentazione **[qui](https://reference.aspose.com/tasks/java/)**.

**D: Come posso scaricare la libreria Aspose.Tasks per Java?**  
R: Scarica la libreria **[qui](https://releases.aspose.com/tasks/java/)**.

**D: Dove posso acquistare Aspose.Tasks per Java?**  
R: Puoi acquistarla **[qui](https://purchase.aspose.com/buy)**.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?**  
R: Sì, puoi ottenere una prova gratuita **[qui](https://releases.aspose.com/)**.

**D: Dove posso richiedere supporto per Aspose.Tasks per Java?**  
R: Visita il forum di supporto **[qui](https://forum.aspose.com/c/tasks/15)**.

---

**Ultimo aggiornamento:** 2026-02-20  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}