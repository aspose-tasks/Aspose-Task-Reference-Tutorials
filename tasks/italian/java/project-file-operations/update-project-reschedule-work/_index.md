---
date: 2026-03-29
description: Scopri come riprogrammare il lavoro non completato, aggiornare il lavoro
  di progetto e salvare i file MS Project in formato XML utilizzando Aspose.Tasks
  per Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Riprogrammare il lavoro non completato e aggiornare i file MS Project con Aspose.Tasks
url: /it/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Riprogrammare il lavoro non completato e aggiornare i file MS Project con Aspose.Tasks

## Introduzione
Microsoft Project è uno strumento di gestione progetti ampiamente utilizzato che aiuta i team a pianificare le attività, assegnare risorse e monitorare le tempistiche. Aspose.Tasks per Java offre agli sviluppatori un'API ricca per manipolare i file Microsoft Project in modo programmatico. In questo tutorial imparerai come **aggiornare il lavoro del progetto**, **riprogrammare il lavoro non completato** e **salvare il file MS Project** in formato XML utilizzando Aspose.Tasks per Java.

## Risposte rapide
- **Cosa significa “riprogrammare il lavoro non completato”?** Sposta qualsiasi lavoro rimanente delle attività per iniziare dopo una data scelta, mantenendo intatte le parti completate.  
- **Quale metodo segna il lavoro come completato?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Come posso persistere le modifiche?** Usa `project.save(<path>, SaveFileFormat.Xml)`.  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza valida di Aspose.Tasks per l'uso commerciale.  
- **Quale versione di Java è supportata?** Java 8 e successive sono pienamente supportate.

## Cos'è “riprogrammare il lavoro non completato”?
Riprogrammare il lavoro non completato regola le date di inizio di tutte le attività che non sono ancora terminate, spostandole per iniziare dopo una data di cut‑off specificata. Questo è utile quando la tempistica di un progetto cambia a causa di ritardi o modifiche dell'ambito.

## Perché usare Aspose.Tasks per aggiornare il lavoro del progetto e riprogrammare le attività?
- **Controllo dettagliato:** Imposta direttamente le percentuali di completamento del lavoro e le date.  
- **Nessuna interfaccia UI richiesta:** Automatizza aggiornamenti massivi su molti file di progetto.  
- **Cross‑platform:** Funziona su qualsiasi sistema che esegue Java.  
- **Preserva l'integrità dei dati:** Tutte le dipendenze, i vincoli e le risorse rimangono coerenti.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.  
2. Libreria Aspose.Tasks per Java. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/java/).  
3. Conoscenza di base del linguaggio di programmazione Java.

## Importare i pacchetti
Per prima cosa, importa i pacchetti necessari nel tuo codice Java:
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

## Passo 1: Configurare il progetto
Inizializza un nuovo oggetto `Project`, definisci le attività, imposta le durate e stabilisci le dipendenze. Questo crea il progetto di base che successivamente aggiorneremo e riprogrammareremo.
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

## Passo 2: Aggiornare il lavoro del progetto
Segna il lavoro come completato fino a una data specifica. Questo passo dimostra l'operazione **aggiornare il lavoro del progetto**, che è spesso la prima azione prima di riprogrammare.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Passo 3: Riprogrammare il lavoro non completato
Ora spostiamo qualsiasi lavoro rimanente (non completato) in modo che inizi dopo la stessa data di cut‑off. Questa è la funzionalità principale di **riprogrammare il lavoro non completato**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusione
In questo tutorial, abbiamo illustrato come **aggiornare il lavoro del progetto**, **riprogrammare il lavoro non completato** e **salvare il file MS Project** in XML utilizzando Aspose.Tasks per Java. Queste funzionalità sono essenziali quando le tempistiche di progetto devono essere adeguate in base ai progressi reali o alle priorità aziendali in evoluzione.

## FAQ
### Q: Aspose.Tasks per Java può gestire strutture di progetto complesse?
A: Sì, Aspose.Tasks per Java fornisce API robuste per gestire attività, dipendenze, risorse e altri elementi del progetto in modo efficiente.
### Q: È disponibile una versione di prova per Aspose.Tasks per Java?
A: Sì, è possibile ottenere una versione di prova gratuita da [qui](https://releases.aspose.com/).
### Q: Come posso ottenere supporto per Aspose.Tasks per Java?
A: Puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda.
### Q: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
A: Sì, le licenze temporanee sono disponibili per l'acquisto [qui](https://purchase.aspose.com/temporary-license/).
### Q: Dove posso trovare la documentazione dettagliata per Aspose.Tasks per Java?
A: Puoi consultare la documentazione [qui](https://reference.aspose.com/tasks/java/) per guide complete e riferimenti API.

## Domande frequenti aggiuntive

**Q: Come posso garantire che il file salvato sia compatibile con versioni precedenti di Microsoft Project?**  
A: Salva il progetto usando `SaveFileFormat.Xml`; XML è ampiamente supportato nelle varie versioni di Project.

**Q: Posso riprogrammare solo un sottoinsieme di attività invece dell'intero progetto?**  
A: Sì, puoi iterare sulle attività specifiche e chiamare `task.setStart(date)` dopo aver calcolato la nuova data di inizio.

**Q: Cosa succede alle assegnazioni delle risorse quando riprogrammo il lavoro non completato?**  
A: Le assegnazioni delle risorse vengono spostate automaticamente per corrispondere alle nuove date di inizio delle attività, preservando la logica di allocazione.

**Q: È possibile annullare programmaticamente un'operazione di riprogrammazione?**  
A: Puoi ricaricare il file di progetto originale (o un backup) per ripristinare le modifiche.

**Q: Aspose.Tasks supporta il salvataggio in altri formati come .mpp?**  
A: Assolutamente. Usa `SaveFileFormat.MPP` per salvare nel formato nativo di Microsoft Project.

---

**Ultimo aggiornamento:** 2026-03-29  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}