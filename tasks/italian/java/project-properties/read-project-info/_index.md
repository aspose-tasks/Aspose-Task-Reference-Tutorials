---
date: 2026-04-24
description: Impara a leggere le informazioni del progetto, incluso il programma dall'inizio,
  utilizzando Aspose.Tasks per Java. Scopri come estrarre rapidamente le proprietà
  del progetto in Java.
keywords:
- how to read project
- Aspose.Tasks Java
- read project properties
linktitle: Leggi le informazioni del progetto con Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come leggere le informazioni di progetto da Microsoft Project con Aspose.Tasks
  per Java
url: /it/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere le informazioni di progetto da Microsoft Project con Aspose.Tasks per Java

## Introduzione
If you need to **how to read project** details such as start dates, finish dates, or calendar settings directly from a Microsoft Project file, Aspose.Tasks for Java gives you a clean, code‑first approach. In this tutorial you’ll see exactly **how to read project** metadata, understand the **project schedule from start**, and learn to pull other key properties—all within a few lines of Java code.

## Risposte rapide
- **Cosa fa Aspose.Tasks per Java?** Consente l'accesso programmatico ai file Microsoft Project (MPP, XML, ecc.) senza che Microsoft Project sia installato.  
- **Quale proprietà indica se il programma è basato sull'inizio?** `Prj.SCHEDULE_FROM_START` – true significa programma dall'inizio, false significa dal termine.  
- **Posso estrarre le proprietà del progetto in Java?** Sì, è possibile leggere la data di inizio, la data di fine, la data corrente, la data di stato e il nome del calendario.  
- **È necessaria una licenza per lo sviluppo?** Una licenza temporanea gratuita funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o superiore con il JAR di Aspose.Tasks nel classpath.  
- **Esiste un modo per caricare il file in modalità sola lettura?** Sì—usa `new Project(filePath, new LoadOptions())` e imposta `ReadOnly` su true per ridurre l'uso di memoria.

## Perché usare Aspose.Tasks per Java per leggere le informazioni di progetto?
Leggere i dati di progetto direttamente da un file MPP consente di automatizzare i report, alimentare dashboard o integrare i programmi di progetto nella logica aziendale personalizzata senza passaggi di esportazione manuali. Aspose.Tasks gestisce tutte le versioni di Microsoft Project, offrendo una soluzione affidabile e indipendente dalla versione che funziona su qualsiasi piattaforma che supporta Java.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Ambiente di sviluppo Java** – JDK 8 o più recente installato e configurato.  
2. **Aspose.Tasks per Java** – Scarica l'ultima libreria dal [sito web](https://releases.aspose.com/tasks/java/).  

## Importa pacchetti
Per interagire con i file di progetto, importa lo spazio dei nomi principale di Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Guida passo‑passo

### Passo 1: Definisci la directory dei dati
Imposta la cartella che contiene il tuo file `.mpp`. Sostituisci il segnaposto con il percorso reale sul tuo computer.

```java
String dataDir = "Your Data Directory";
```

### Passo 2: Carica il file di progetto
Crea un'istanza `Project` caricando il file Microsoft Project che desideri esaminare.

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### Passo 3: Determina la base del programma di progetto
Verifica se il programma è calcolato dalla data di inizio del progetto o dalla data di fine. Questo è il fulcro di **come leggere le informazioni di programmazione del progetto**.

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **Consiglio professionale:** `Prj.SCHEDULE_FROM_START` restituisce un Boolean; `true` significa *programma del progetto dall'inizio*.

### Passo 4: Recupera ulteriori informazioni sul programma di progetto
Oltre alle date di inizio/fine, spesso è necessario la data corrente, la data di stato e il calendario associato al progetto. Questo dimostra **leggere le proprietà del progetto in Java** in azione.

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| `NullPointerException` su `project.get(Prj.CALENDAR)` | Il file di progetto manca di un calendario predefinito. | Assicurati che il file MPP definisca un calendario o gestisci i controlli `null`. |
| Date stampate come `null` | File di progetto corrotto o campi data mancanti. | Convalida il file sorgente in Microsoft Project prima dell'elaborazione. |
| Errore di compilazione: `cannot find symbol Prj` | JAR di Aspose.Tasks non presente nel classpath. | Aggiungi `aspose-tasks-xx.jar` al percorso di build del tuo progetto. |

## Domande frequenti

### D: Posso usare Aspose.Tasks per Java con qualsiasi versione dei file Microsoft Project?
**R:** Sì, Aspose.Tasks per Java supporta varie versioni dei file Microsoft Project, inclusi i formati MPP e XML.

### D: Aspose.Tasks per Java è compatibile con tutti gli ambienti di sviluppo Java?
**R:** Aspose.Tasks per Java è compatibile con la maggior parte degli ambienti di sviluppo Java, garantendo flessibilità nell'integrazione.

### D: Aspose.Tasks per Java offre supporto per manipolare i dati di progetto oltre alla lettura delle informazioni?
**R:** Assolutamente, Aspose.Tasks per Java offre funzionalità estese per manipolare i dati di progetto, inclusi modifica, salvataggio ed esportazione.

### D: Posso automatizzare l'estrazione delle informazioni di progetto usando Aspose.Tasks per Java?
**R:** Sì, Aspose.Tasks per Java consente l'automazione tramite la sua API completa, permettendo processi semplificati per l'estrazione e l'analisi dei dati.

### D: Esiste un forum della community o un canale di supporto disponibile per gli utenti di Aspose.Tasks per Java?
**R:** Sì, puoi trovare risorse utili e interagire con la community sul [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### D: Come leggo le proprietà del progetto in Java senza caricare l'intero albero delle attività?
**R:** Usa il metodo `Project.get` con i valori di enumerazione `Prj` richiesti; questo recupera solo i metadati richiesti, mantenendo basso l'uso di memoria.

### D: Qual è il modo migliore per gestire file MPP di grandi dimensioni durante l'estrazione delle proprietà?
**R:** Carica il progetto in modalità *sola lettura* (`new Project(filePath, LoadOptions)`) e interroga solo le proprietà necessarie per evitare un elevato consumo di memoria.

## Conclusione
Seguendo questa guida ora sai **come leggere le informazioni di progetto** come l'origine del programma, le date e i dettagli del calendario usando Aspose.Tasks per Java. Incorporare questi snippet nelle tue applicazioni consente report automatizzati, dashboard personalizzate e decisioni più intelligenti senza interazione manuale con Microsoft Project.

---

**Ultimo aggiornamento:** 2026-04-24  
**Testato con:** Aspose.Tasks for Java 24.10  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}