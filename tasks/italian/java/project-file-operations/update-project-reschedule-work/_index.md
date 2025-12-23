---
date: 2025-12-23
description: Scopri come aggiornare i file MS Project e riprogrammare il lavoro non
  completato usando Aspose.Tasks per Java. Vedi anche come salvare l'XML di MS Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aggiorna MS Project e riprogramma il lavoro con Aspose.Tasks
url: /it/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiorna MS Project e Riprogramma il Lavoro con Aspose.Tasks

## Introduzione
Microsoft Project è uno strumento di gestione progetti ampiamente utilizzato che aiuta i team a pianificare, monitorare e consegnare il lavoro in tempo. Quando i programmi cambiano, è spesso necessario **aggiornare MS Project** programmaticamente—segnare il lavoro come completato, spostare le attività rimanenti e mantenere la baseline del progetto accurata. Aspose.Tasks per Java fornisce un'API pulita e type‑safe per fare esattamente questo senza aprire l'interfaccia grafica. In questo tutorial vedrai come aggiornare un progetto, segnare il lavoro come terminato fino a una data specifica e poi **come riprogrammare MS Project** per il lavoro ancora in sospeso.

## Risposte Rapide
- **Cosa significa “aggiornare MS Project”?** Segna le attività come completate fino a una data specifica e scrive le modifiche nel file.  
- **Posso riprogrammare automaticamente il lavoro rimanente?** Sì—usa `rescheduleUncompletedWorkToStartAfter` per spostare le attività non finite in avanti.  
- **Quale formato di file viene salvato?** Gli esempi salvano il progetto come XML (`SaveFileFormat.Xml`).  
- **È necessaria una licenza per eseguire il codice?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quale versione di Java è richiesta?** JDK 8 o superiore.

## Cosa significa “aggiornare MS Project” nel codice?
Aggiornare un progetto significa modificare programmaticamente le date delle attività, le durate o le percentuali di completamento e persistere tali modifiche. Aspose.Tasks espone metodi come `updateProjectWorkAsComplete` che applicano le modifiche in base a una `Date` di riferimento fornita.

## Perché usare Aspose.Tasks per Java per aggiornare MS Project?
- **Nessuna dipendenza dall'interfaccia UI** – automatizza modifiche in blocco su molti file.  
- **Alta fedeltà** – la libreria preserva tutti i dati nativi di Project (risorse, calendari, campi personalizzati).  
- **Cross‑platform** – esegui lo stesso codice su Windows, Linux o macOS.  
- **Salva MS Project XML** – puoi esportare il progetto aggiornato nel formato XML ampiamente supportato per gli strumenti downstream.

## Prerequisiti
1. Java Development Kit (JDK) installato.  
2. Libreria Aspose.Tasks per Java – scaricala da [here](https://releases.aspose.com/tasks/java/).  
3. Familiarità di base con la sintassi Java e i concetti di programmazione orientata agli oggetti.

## Importa Pacchetti
First, import the necessary Aspose.Tasks classes and Java utilities:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Passo 1: Configura il Progetto
Create a new `Project` instance, define a few sample tasks, set their durations, and establish dependencies. Then persist the initial state so you can see the before‑and‑after effect.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Passo 2: Aggiorna il Lavoro del Progetto
Mark work as complete up to a specific cutoff date. This is the core of **update MS Project**—the API will adjust task progress and dates automatically.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Passo 3: Riprogramma il Lavoro Non Completato
After marking completed work, you often need to push the remaining tasks forward. The following call moves any unfinished work to start after the same cutoff date, effectively **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Problemi Comuni e Soluzioni
| Issue | Reason | Fix |
|-------|--------|-----|
| Le attività non mostrano le date aggiornate | Il progetto è stato salvato in un formato diverso (ad es., `.mpp`) | Usa `SaveFileFormat.Xml` per mantenere intatta la struttura XML. |
| `updateProjectWorkAsComplete` sembra non fare nulla | La data di riferimento è precedente all'inizio del progetto | Assicurati che la data del `Calendar` sia entro la timeline del progetto. |
| Le attività riprogrammate si sovrappongono | Nessun calendario o livellamento delle risorse applicato | Applica un calendario `Project` o usa `Task.setStart` manualmente dopo la riprogrammazione. |

## Domande Frequenti (Estese)

**D: Aspose.Tasks per Java può gestire strutture di progetto complesse?**  
R: Sì, Aspose.Tasks per Java fornisce API robuste per gestire attività, dipendenze, risorse e altri elementi del progetto in modo efficiente.

**D: È disponibile una versione di prova per Aspose.Tasks per Java?**  
R: Sì, puoi ottenere una prova gratuita da [here](https://releases.aspose.com/).

**D: Come posso ottenere supporto per Aspose.Tasks per Java?**  
R: Puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.

**D: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?**  
R: Sì, le licenze temporanee sono disponibili per l'acquisto [here](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks per Java?**  
R: Puoi consultare la documentazione [here](https://reference.aspose.com/tasks/java/) per guide complete e riferimenti API.

## Conclusione
In questo tutorial abbiamo percorso l'intero processo di **aggiornare MS Project** file, segnare il lavoro come completato e poi **come riprogrammare MS Project** le attività che rimangono incomplete. Salvando il progetto come XML mantieni la compatibilità con altri strumenti e conservi una chiara traccia delle modifiche. Usa questi pattern per automatizzare le regolazioni di programma in grandi portafogli, integrarle nei pipeline CI o creare dashboard di reporting personalizzati.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}