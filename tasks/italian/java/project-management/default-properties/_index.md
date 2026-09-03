---
date: 2026-05-31
description: Scopri come caricare un file MPP in Java e gestire le proprietà del progetto
  con Aspose.Tasks, inclusa l'impostazione delle proprietà predefinite e la conversione
  dei formati.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Gestisci le proprietà predefinite del progetto in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Carica file MPP in Java – Gestisci le proprietà del progetto con Aspose.Tasks
url: /it/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Carica file MPP Java – Gestisci le proprietà del progetto con Aspose.Tasks

## Introduzione
Se hai bisogno di **load MPP file Java** progetti e di gestire programmaticamente le proprietà predefinite del progetto, Aspose.Tasks per Java lo rende semplice. In questo tutorial percorreremo l’intero processo — dal caricamento di un file Microsoft Project esistente alla personalizzazione delle impostazioni predefinite di attività e risorse, fino al salvataggio del progetto aggiornato. Alla fine avrai un modello chiaro e riutilizzabile da inserire in qualsiasi soluzione di gestione progetti basata su Java.

## Risposte rapide
- **Cosa significa “load MPP file Java”?** Significa leggere un file Microsoft Project (.mpp) usando codice Java tramite Aspose.Tasks.  
- **Quale libreria gestisce questo?** Aspose.Tasks for Java fornisce un'API completa per la manipolazione dei progetti.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per l'uso in produzione.  
- **Posso modificare le date di inizio predefinite delle attività?** Sì—usa `Prj.DEFAULT_START_TIME` e le proprietà correlate per impostare i valori predefiniti.  
- **Quali formati di output sono supportati?** Oltre al formato MPP nativo, è possibile salvare in XML, PDF, HTML e oltre 20 altri formati.

## Che cos'è “load MPP file Java”?
Caricare un file MPP in Java significa utilizzare una libreria per analizzare il formato binario di Microsoft Project, esponendo i suoi oggetti (attività, risorse, calendari) come classi Java. Questo ti consente di leggere, modificare e salvare i dati del progetto senza mai aprire Microsoft Project stesso.

## Perché usare Aspose.Tasks per Java?
Aspose.Tasks ti permette di gestire le proprietà del progetto senza un'installazione di Microsoft Project, supporta **50+ formati di input e output**, e può elaborare progetti con **fino a 10.000 attività** mantenendo l'uso della memoria sotto i 200 MB. Funziona su qualsiasi OS che supporti un JDK, rendendolo ideale per l'automazione lato server.

## Prerequisiti
Prima di immergerci, assicurati di avere quanto segue:

### 1. Java Development Kit (JDK)
- Installa JDK 11 o successivo.  
- Puoi scaricarlo da [qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### 2. Libreria Aspose.Tasks per Java
- Scarica l'ultimo JAR di Aspose.Tasks e aggiungilo al classpath del tuo progetto.  
- Ottienilo dal [sito web](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Le istruzioni di importazione portano le classi essenziali di Aspose.Tasks nel tuo file sorgente Java.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Come caricare file MPP Java e impostare le proprietà predefinite?
La classe `Project` rappresenta un file Microsoft Project e fornisce l'accesso a attività, risorse e impostazioni. Carica il progetto, ispeziona le impostazioni predefinite, modificale e salva il risultato — il tutto in poche righe semplici. Questo approccio ti dà il pieno controllo sui valori predefiniti di pianificazione, impostazioni del calendario e regole di accumulo dei costi, consentendoti di applicare standard di progetto coerenti a tutti i file generati.

### Passo 1: Carica file di progetto
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Passo 2: Visualizza proprietà predefinite
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Passo 3: Imposta proprietà predefinite
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Passo 4: Salva progetto in formato XML
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Passo 5: Visualizza risultato
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

Seguendo questi passaggi hai **loaded an MPP file in Java**, ispezionato le impostazioni predefinite, personalizzato le stesse e salvato il progetto aggiornato.

## Problemi comuni e consigli
- **File not found** – Verifica che `dataDir` termini con un separatore di percorso (`/` o `\\`).  
- **License not applied** – Se vedi una filigrana di prova, aggiungi il tuo file di licenza prima di caricare il progetto: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Date handling** – Usa `java.util.Calendar` o la più recente API `java.time` (converti in `java.util.Date` prima di assegnare).

## Domande frequenti

**Q: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
A: Sì, Aspose.Tasks è disponibile anche per .NET, Python e altre piattaforme.

**Q: Aspose.Tasks è adatto sia per uso personale che aziendale?**  
A: Assolutamente! Scala da piccoli progetti personali a grandi portafogli aziendali.

**Q: Aspose.Tasks offre supporto clienti?**  
A: Sì, puoi trovare assistenza e supporto della community sul [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Posso provare Aspose.Tasks prima di acquistarlo?**  
A: Certo! Puoi usufruire di una prova gratuita dal [sito web](https://releases.aspose.com/).

**Q: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
A: Puoi ottenere una licenza temporanea dalla [pagina di acquisto](https://purchase.aspose.com/temporary-license/) per scopi di test e valutazione.

## Conclusione
In questo tutorial abbiamo coperto come **load MPP file Java** progetti, leggere e modificare le loro proprietà predefinite e salvare le modifiche usando Aspose.Tasks per Java. Incorporare queste tecniche nelle tue applicazioni ti aiuterà ad automatizzare le attività di gestione progetti, a imporre valori predefiniti coerenti e a ridurre lo sforzo manuale.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Imposta data di inizio del progetto in MS Project usando Aspose.Tasks per Java](/tasks/java/project-properties/write-project-info/)
- [Come impostare il calendario del progetto con Aspose.Tasks per Java](/tasks/java/calendars/properties/)
- [Come creare file MPP – Crea e salva progetto vuoto in formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}