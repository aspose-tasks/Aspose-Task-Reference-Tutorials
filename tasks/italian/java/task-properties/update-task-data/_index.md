---
date: 2026-03-03
description: Scopri come aggiornare i dati delle attività al formato MPP usando Aspose.Tasks
  per Java. Segui la nostra guida passo‑passo per una gestione efficiente del progetto.
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Aggiorna i dati del task al formato MPP
url: /it/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiorna i Dati delle Attività al Formato MPP in Aspose.Tasks

## Introduzione
Benvenuti alla nostra guida passo‑paso su **l'aggiornamento dei dati delle attività al formato MPP utilizzando Aspose.Tasks per Java**. In questo tutorial imparerete a manipolare i file di progetto in modo programmatico con *aspose tasks java*, dalla creazione di un'attività riepilogo alla conversione di un progetto XML in un file MPP. Alla fine sarete in grado di gestire le attività di progetto in modo efficiente e integrare la soluzione nelle vostre applicazioni Java.

## Risposte Rapide
- **Di cosa tratta questo tutorial?** Aggiornare i dati delle attività e salvare un progetto come MPP con Aspose.Tasks per Java.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per l'uso in produzione; è disponibile una versione di prova gratuita.  
- **Quale IDE è consigliato?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, VS Code) funzionerà.  
- **Posso convertire XML in MPP?** Sì – l'esempio carica un progetto XML e lo salva come MPP.  
- **Quante attività vengono create?** L'esempio crea un'attività principale, un'attività riepilogo e dieci attività aggiuntive.

## Che cos'è Aspose.Tasks per Java?
Aspose.Tasks per Java è una potente API che consente agli sviluppatori di leggere, scrivere e modificare file Microsoft Project (MPP, XML e altri) senza la necessità di avere Microsoft Project installato. Supporta la manipolazione completa a livello di progetto, inclusa la creazione di attività, la gestione dei vincoli e la conversione dei formati di file.

## Perché utilizzare Aspose.Tasks Java per la gestione dei progetti?
- **Controllo totale** sulle proprietà delle attività come data di inizio, durata e vincoli.  
- **Conversione fluida** tra XML e MPP, consentendo l'integrazione con pipeline di dati di progetto esistenti.  
- **Nessuna interop COM** – puro Java, ideale per ambienti cross‑platform.  
- **Alte prestazioni** per file di progetto di grandi dimensioni, rendendolo adatto a soluzioni su scala enterprise.

## Prerequisiti
Prima di immergerci nel tutorial, assicuratevi di avere i seguenti prerequisiti:
- Aspose.Tasks per Java: Verificate di aver installato la libreria Aspose.Tasks. Potete scaricarla dalla [pagina di rilascio](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Assicuratevi di avere Java installato sul vostro sistema.
- Integrated Development Environment (IDE): Utilizzate l'IDE di vostra scelta per lo sviluppo Java.

## Importare i Pacchetti
Iniziate importando i pacchetti necessari nel vostro progetto Java. Il frammento seguente dimostra come importare i pacchetti:

```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```

## Come Creare un'Attività Riepilogo
Un'attività riepilogo raggruppa le sotto‑attività correlate, fornendo una vista ad alto livello dei pacchetti di lavoro. Nel codice sottostante creiamo un'attività riepilogo e colleghiamo la prima attività come suo figlio.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## Come Impostare la Data di Inizio per un'Attività
Impostare la data di inizio è fondamentale per una pianificazione accurata. L'esempio utilizza un'istanza `Calendar` per definire l'inizio del progetto e la assegna all'attività.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## Come Convertire XML in MPP
L'API può leggere un file di progetto XML e salvarlo direttamente come file MPP, facilitando la migrazione da formati legacy.

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## Come Impostare la Scadenza e Aggiungere Note all'Attività
Le scadenze aiutano a mantenere le attività in linea, mentre le note forniscono contesto ai membri del team.

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## Come Configurare i Vincoli dell'Attività e Aggiornare la Durata dell'Attività
Vincoli come *Finish No Later Than* guidano il programmatore. Potete anche modificare il formato della durata per riflettere i giorni stimati.

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## Come Creare Attività Aggiuntive (Gestione delle Attività di Progetto)
Il ciclo qui sotto dimostra come generare più attività in modo programmatico, una necessità comune quando si importano dati in blocco.

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## Come Salvare il Progetto (Esportazione in MPP)
Infine, persistete le modifiche salvando il progetto come file MPP.

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

Seguendo questi passaggi, avete aggiornato con successo **i dati delle attività al formato MPP utilizzando aspose tasks java**. Ora disponete di una solida base per gestire le attività di progetto, creare attività riepilogo, impostare le date di inizio e convertire progetti XML in MPP.

## Conclusione
Congratulazioni! Avete completato una guida completa sull'aggiornamento dei dati delle attività in formato MPP utilizzando Aspose.Tasks per Java. Questa potente libreria semplifica le attività di gestione dei progetti, rendendola uno strumento prezioso per gli sviluppatori Java che devono **gestire le attività di progetto** in modo programmatico.

## Domande Frequenti

### Q: Dove posso trovare la documentazione di Aspose.Tasks per Java?
A: La documentazione è disponibile [qui](https://reference.aspose.com/tasks/java/).

### Q: Come posso scaricare Aspose.Tasks per Java?
A: Potete scaricarlo dalla [pagina di rilascio](https://releases.aspose.com/tasks/java/).

### Q: È disponibile una versione di prova gratuita?
A: Sì, potete accedere alla versione di prova gratuita [qui](https://releases.aspose.com/).

### Q: Dove posso ottenere supporto per Aspose.Tasks per Java?
A: Visitate il forum di supporto [qui](https://forum.aspose.com/c/tasks/15).

### Q: Offrite licenze temporanee per scopi di test?
A: Sì, potete ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-03-03  
**Testato con:** Aspose.Tasks per Java 24.11 (latest)  
**Autore:** Aspose  

---