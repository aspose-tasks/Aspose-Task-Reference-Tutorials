---
title: Gestisci in modo efficiente le proprietà di MS Project in Aspose.Tasks
linktitle: Gestisci le proprietà predefinite del progetto in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come gestire le proprietà predefinite di MS Project utilizzando Aspose.Tasks per Java. Semplifica il flusso di lavoro di gestione dei progetti senza sforzo.
weight: 11
url: /it/java/project-management/default-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestisci in modo efficiente le proprietà di MS Project in Aspose.Tasks

## introduzione
Stai cercando di semplificare il processo di gestione dei progetti con Aspose.Tasks per Java? La gestione delle proprietà predefinite nei file Microsoft Project può migliorare notevolmente l'efficienza. In questo tutorial, illustreremo istruzioni dettagliate su come gestire le proprietà predefinite di MS Project utilizzando Aspose.Tasks.
## Prerequisiti
Prima di approfondire il tutorial, assicurati di possedere i seguenti prerequisiti:
### 1. Kit di sviluppo Java (JDK)
   - Assicurati che JDK sia installato sul tuo sistema.
   -  Puoi scaricarlo da[Qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks per la libreria Java
   - Scarica e includi la libreria Aspose.Tasks per Java nel tuo progetto.
   -  Puoi scaricarlo da[sito web](https://releases.aspose.com/tasks/java/).
## Importa pacchetti
Innanzitutto, importa i pacchetti necessari nel tuo file Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Suddividiamo il processo in passaggi gestibili:
## Passaggio 1: caricare il file di progetto
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Passaggio 2: Visualizza le proprietà predefinite
```java
// Visualizza le proprietà predefinite
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Passaggio 3: imposta le proprietà predefinite
```java
// Imposta le proprietà predefinite
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
## Passaggio 4: salva il progetto in formato XML
```java
// Salva il progetto in formato XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Passaggio 5: Visualizza risultato
```java
// Visualizza il risultato della conversione.
System.out.println("Process completed Successfully");
```
Seguendo questi passaggi, puoi gestire in modo efficiente le proprietà predefinite di MS Project utilizzando Aspose.Tasks per Java.
## Conclusione
In questo tutorial, abbiamo imparato come gestire le proprietà predefinite di MS Project utilizzando Aspose.Tasks per Java. Utilizzando queste tecniche, puoi ottimizzare il flusso di lavoro di gestione dei progetti, migliorando la produttività e l'organizzazione.
## Domande frequenti
### Q1: posso utilizzare Aspose.Tasks con altri linguaggi di programmazione?
A1: Sì, Aspose.Tasks supporta vari linguaggi di programmazione come .NET, Python e Java.
### Q2: Aspose.Tasks è adatto sia per uso personale che aziendale?
A2: Assolutamente! Che tu stia gestendo piccoli progetti personali o iniziative aziendali su larga scala, Aspose.Tasks si rivolge a tutti.
### Q3: Aspose.Tasks offre assistenza clienti?
R3: Sì, puoi trovare assistenza e supporto della comunità su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Q4: Posso provare Aspose.Tasks prima dell'acquisto?
 A4: Certamente! Puoi usufruire di una prova gratuita da[sito web](https://releases.aspose.com/).
### Q5: Come posso ottenere una licenza temporanea per Aspose.Tasks?
 A5: Puoi ottenere una licenza temporanea da[pagina di acquisto](https://purchase.aspose.com/temporary-license/) a scopo di test e valutazione.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
