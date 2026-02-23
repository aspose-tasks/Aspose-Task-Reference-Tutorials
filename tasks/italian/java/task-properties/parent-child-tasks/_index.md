---
date: 2026-02-23
description: Scopri come impostare la data di inizio del progetto, impostare la durata
  delle attività e salvare il progetto come MPP utilizzando Aspose.Tasks per Java.
  Gestisci in modo efficiente le attività padre e figlio.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Imposta la data di inizio del progetto e gestisci le attività padre e figlio
  in Aspose.Tasks
url: /it/java/task-properties/parent-child-tasks/
weight: 24
---

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta la Data di Inizio del Progetto e Gestisci le Attività Padre e Figlio in Aspose.Tasks

## Introduzione
L'organizzazione efficace delle attività è la spina dorsale di una gestione di progetto di successo, e **impostare correttamente la data di inizio del progetto** è il primo passo verso un calendario ben strutturato. In questo tutorial vedrai come **impostare la data di inizio del progetto**, configurare le durate delle attività e gestire le relazioni padre‑figlio usando Aspose.Tasks per Java. Alla fine, sarai pronto a **salvare il progetto come MPP**, aggiornare le percentuali di completamento delle attività e personalizzare le proprietà delle attività per adattarle a qualsiasi scenario reale.

## Risposte Rapide
- **Come imposto la data di inizio del progetto?** Usa `proj.set(Prj.START_DATE, startDate);` dopo aver inizializzato l'oggetto `Project`.  
- **Posso aggiungere attività figlio sotto un'attività padre?** Sì – chiama `parentTask.getChildren().add("Child Task")`.  
- **In quale formato Aspose.Tasks salva il file?** Usa `SaveFileFormat.Mpp` per **salvare il progetto come MPP**.  
- **Come aggiorno il completamento di un'attività?** Imposta `Tsk.PERCENT_COMPLETE` sull'oggetto attività.  
- **Dove posso ottenere una licenza temporanea?** Visita la pagina della licenza temporanea collegata nelle FAQ.

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza di base della programmazione Java.  
- Libreria Aspose.Tasks per Java installata. Puoi scaricarla [qui](https://releases.aspose.com/tasks/java/).  
- Un ambiente di sviluppo integrato (IDE) Java configurato sul tuo sistema.

## Importa Pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java. Questi pacchetti facilitano l'integrazione fluida con le funzionalità di Aspose.Tasks per Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Passo 1: Imposta la Data di Inizio del Progetto
Inizia impostando la data di inizio del progetto e altri parametri rilevanti.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Passo 2: Aggiungi Attività Padre (Task 1)
Crea un'attività padre denominata "Task 1" e configura le sue proprietà, inclusa **set task duration**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Passo 3: Aggiungi Attività Padre (Task 2) con Attività Figlio
Ora, aggiungi un altro attività padre denominata "Task 2" e includi le attività figlio (Task 3 e Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Passo 4: Configura le Attività Figlio
Specifica le date di inizio, le durate e i vincoli per Task 3 e Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Passo 5: Aggiorna la Percentuale di Completamento dell'Attività
Regola la percentuale di completamento per Task 3 e Task 4 – questo è il modo per **aggiornare il completamento dell'attività**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Passo 6: Salva il Progetto
Infine, **salva il progetto come MPP** con le modifiche applicate.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Questa guida passo‑passo dimostra come gestire efficacemente le attività padre e figlio usando Aspose.Tasks per Java. Sperimenta con diverse configurazioni per soddisfare i requisiti del tuo progetto.

## Perché Personalizzare le Proprietà dell'Attività?
Personalizzare le proprietà dell'attività, come date di inizio, durate, vincoli e percentuali di completamento, ti offre un controllo granulare sul comportamento del calendario. Che tu debba allineare le attività alla disponibilità delle risorse o far rispettare regole aziendali, Aspose.Tasks ti consente di **personalizzare le proprietà dell'attività** programmaticamente.

## Problemi Comuni e Soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Start date not applied** | Assicurati di chiamare `proj.set(Prj.START_DATE, …)` **dopo** aver creato l'oggetto `Project` e prima di aggiungere le attività. |
| **Child tasks inherit wrong constraints** | Imposta esplicitamente `ConstraintType` e `ConstraintDate` per ciascun figlio, come mostrato nel Passo 4. |
| **Saved file cannot be opened in MS Project** | Verifica di utilizzare l'ultima versione di Aspose.Tasks e di salvare con `SaveFileFormat.Mpp`. |
| **Percentage not reflecting in UI** | Dopo aver impostato `Tsk.PERCENT_COMPLETE`, chiama `proj.calculateTaskSchedule()` se hai bisogno di ricalcolare le date. |

## FAQ
### Aspose.Tasks per Java è compatibile con diversi formati di file di progetto?
Sì, Aspose.Tasks per Java supporta vari formati di file di progetto, inclusi MPP e XML.

### Posso personalizzare le proprietà dell'attività oltre a quanto coperto in questo tutorial?
Assolutamente! Aspose.Tasks per Java offre ampie opzioni di personalizzazione per le proprietà delle attività.

### Esiste un forum della community per Aspose.Tasks dove posso chiedere supporto?
Sì, puoi visitare il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto della community.

### Come posso ottenere una licenza temporanea per Aspose.Tasks per Java?
Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Dove posso trovare la documentazione completa per Aspose.Tasks per Java?
La documentazione è disponibile [qui](https://reference.aspose.com/tasks/java/).

**Additional Q&A**

**Q: Come ottengo programmaticamente una licenza temporanea?**  
A: Carica il file di licenza temporanea usando `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Posso cambiare l'unità di durata predefinita dell'attività?**  
A: Sì – modifica l'argomento `TimeUnitType` in `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: Quale versione di Aspose.Tasks è necessaria per usare `SaveFileFormat.Mpp`?**  
A: Tutte le versioni recenti (2022‑2026) supportano il salvataggio come MPP; controlla le note di rilascio per eventuali modifiche breaking.

**Ultimo aggiornamento:** 2026-02-23  
**Testato con:** Aspose.Tasks per Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}