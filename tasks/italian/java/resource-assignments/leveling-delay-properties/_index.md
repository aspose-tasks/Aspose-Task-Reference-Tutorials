---
date: 2026-06-05
description: Scopri come creare un'assegnazione di risorse con Aspose.Tasks per Java,
  aggiungere risorse a un progetto e gestire le proprietà di ritardo di livellamento.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Gestisci le proprietà di ritardo di livellamento per le assegnazioni di
  risorse in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Crea assegnazione di risorse con Aspose.Tasks per Java
url: /it/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea Assegnazione di Risorse con Aspose.Tasks per Java

In questa guida completa imparerai **how to create resource assignment aspotasks** utilizzando la libreria Aspose.Tasks per Java. Che tu stia costruendo un motore di pianificazione personalizzato, automatizzando aggiornamenti di progetto in blocco, o semplicemente abbia bisogno di manipolare i file Microsoft Project senza l'applicazione desktop, padroneggiare questi passaggi ti permette di mantenere i dati del progetto accurati e completamente controllabili.

## Risposte Rapide
- **What does “add resource to project” mean?** Crea una nuova voce di risorsa che può essere successivamente assegnata alle attività.  
- **Can I set a leveling delay after assignment?** Sì, utilizzando i campi `Asn.DELAY` o `Asn.LEVELING_DELAY`.  
- **Do I need a license to run this code?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza a pagamento per la produzione.  
- **Which Java version is supported?** Java 8 or later.  
- **Is this compatible with all MS Project file formats?** Aspose.Tasks supporta più di 12 formati—incluse .MPP, .XML, .XER, .CSV, .PDF e altri.

## Cos'è “add resource to project” in Aspose.Tasks?
Aggiungere una risorsa a un progetto significa creare un oggetto `Resource` all'interno del modello `Project`. Questo oggetto può essere successivamente collegato alle attività tramite `ResourceAssignment`, consentendo di monitorare lavoro, costi e impostazioni di leveling. Inserendo una risorsa fornisci allo scheduler qualcosa da allocare, e puoi successivamente interrogare o modificare le sue proprietà come disponibilità, tariffe e assegnazioni di calendario.

## Perché gestire le proprietà di ritardo di leveling?
Il ritardo di leveling indica allo scheduler di posticipare l'inizio di un'assegnazione sovraccarica, distribuendo il lavoro più uniformemente lungo la linea temporale. Configurando questo ritardo eviti date di inizio irrealistiche, riduci gli avvisi di sovraccarico e produci un programma che riflette le limitazioni delle risorse nel mondo reale. Regolare il ritardo ti offre anche un controllo dettagliato su quanta flessibilità il motore può inserire, aiutandoti a rispettare le scadenze del progetto mantenendo i limiti delle risorse.

## Come creare resource assignment aspotasks?
Carica il tuo oggetto `Project`, aggiungi un'attività, crea una risorsa e poi collegali insieme con un `ResourceAssignment`. Questo flusso end‑to‑end ti consente di costruire programmaticamente una struttura di progetto completa e controllare immediatamente il ritardo di leveling sull'assegnazione. Il processo dimostra il flusso di lavoro principale: inizializzazione del progetto, definizione dell'attività, creazione della risorsa, collegamento dell'assegnazione e infine l'applicazione di parametri di pianificazione come il ritardo di leveling.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): Assicurati di avere il Java JDK installato sul tuo sistema. Puoi scaricarlo e installarlo dal [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java Library: Scarica la libreria Aspose.Tasks per Java dalla [download page](https://releases.aspose.com/tasks/java/).

## Importa Pacchetti
Le seguenti importazioni includono le classi core di Aspose.Tasks necessarie per la manipolazione del progetto.  
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Come creare resource assignment aspotasks?
Carica il tuo oggetto `Project`, aggiungi un'attività, crea una risorsa e poi collegali insieme con un `ResourceAssignment`. Questo flusso end‑to‑end ti consente di costruire programmaticamente una struttura di progetto completa e controllare immediatamente il ritardo di leveling sull'assegnazione. Il processo dimostra il flusso di lavoro principale: inizializzazione del progetto, definizione dell'attività, creazione della risorsa, collegamento dell'assegnazione e infine l'applicazione di parametri di pianificazione come il ritardo di leveling.

## Passo 1: Crea un Oggetto Project
La classe `Project` è il contenitore di livello superiore di Aspose.Tasks che rappresenta un intero file di progetto in memoria. Istanziandola ottieni una base pulita per aggiungere attività, risorse e assegnazioni.
```java
Project prj = new Project();
```

## Passo 2: Crea un'Attività
La classe `Task` rappresenta un singolo elemento di lavoro nella pianificazione. Aggiungere un'attività dimostra **how to add task** programmaticamente e fornisce un obiettivo per la prossima assegnazione di risorsa.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Passo 3: Imposta Data di Inizio e Durata dell'Attività
Definisci quando l'attività inizia e quanto durerà. Le date di inizio corrette sono essenziali perché i calcoli di leveling le usano come base per qualsiasi ritardo che specifichi successivamente.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Passo 4: Aggiungi una Risorsa
Ora **add resource to project** creando una nuova voce `Resource`. La classe `Resource` è la rappresentazione di una persona, attrezzatura o materiale che può essere assegnato alle attività.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Passo 5: Crea un'Assegnazione di Risorsa
`ResourceAssignment` collega un `Task` e una `Resource`. Questa associazione ti consente di registrare lavoro, costo e dettagli di leveling per una risorsa specifica su un'attività specifica.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Passo 6: Imposta il Ritardo di Leveling
Configura il ritardo di leveling per l'assegnazione. Impostarlo a zero significa nessun ritardo aggiuntivo, ma puoi regolare il valore secondo necessità. Il campo `Asn.DELAY` contiene il ritardo in minuti; `Asn.LEVELING_DELAY` è un alias che funziona allo stesso modo.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Passo 7: Visualizza i Risultati
Stampa le proprietà importanti per verificare che tutto sia stato impostato correttamente. Questo passaggio ti aiuta a confermare che la risorsa, l'attività e i valori di ritardo siano esattamente quelli attesi prima di salvare il file.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Problemi Comuni e Suggerimenti
- **Pitfall:** Dimenticare di impostare la data di inizio dell'attività può far sì che l'assegnazione predefinisca l'inizio del progetto.  
- **Tip:** Utilizza `prj.getDuration(value, TimeUnitType.Day)` per controllare la granularità del ritardo.  
- **Tip:** Dopo aver aggiunto più risorse, chiama `prj.updateResourceAssignments()` per consentire allo scheduler di ricalcolare il leveling.  
- **Pro tip:** Per progetti di grandi dimensioni (oltre 10.000 attività) abilita `prj.setAutoCalculate(false)` prima degli aggiornamenti in blocco, quindi chiama `prj.calculate()` una volta alla fine per migliorare le prestazioni.

## Domande Frequenti

**Q: Posso usare Aspose.Tasks con altre librerie Java?**  
A: Sì, Aspose.Tasks si integra perfettamente con librerie come Jackson per la gestione di JSON o Apache POI per operazioni aggiuntive su fogli di calcolo, consentendoti di creare soluzioni di gestione progetti più ricche.

**Q: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?**  
A: Aspose.Tasks supporta più di 12 formati di file—incluse .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML e .MPP12—garantendo una modifica round‑trip senza interruzioni su tutte le principali versioni di Project.

**Q: Dove posso trovare supporto aggiuntivo per Aspose.Tasks?**  
A: Puoi trovare supporto e discussioni della community sul [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Posso provare Aspose.Tasks prima di acquistarlo?**  
A: Sì, una versione di prova completamente funzionale è disponibile dalla [releases page](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per la valutazione?**  
A: Richiedi una licenza temporanea dalla [temporary license page](https://purchase.aspose.com/temporary-license/) per eseguire la libreria senza restrizioni di valutazione.

**Last Updated:** 2026-06-05  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Tutorial Correlati

- [Crea Assegnazioni di Risorse in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Gestisci il Budget delle Assegnazioni Java usando Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Come interrompere l'Assegnazione e riprendere le Assegnazioni di Risorse in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}