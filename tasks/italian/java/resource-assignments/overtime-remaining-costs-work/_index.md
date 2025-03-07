---
title: Monitorare gli straordinari, i costi rimanenti e il lavoro in Aspose.Tasks
linktitle: Monitorare gli straordinari, i costi rimanenti e il lavoro in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come monitorare gli straordinari, i costi rimanenti e lavorare su progetti Java utilizzando Aspose.Tasks. Semplici passaggi per una gestione efficace del progetto.
weight: 18
url: /it/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Monitorare gli straordinari, i costi rimanenti e il lavoro in Aspose.Tasks

## introduzione
In questo tutorial impareremo come utilizzare Aspose.Tasks per Java per monitorare gli straordinari, i costi rimanenti e lavorare in un progetto. Questo può essere prezioso per i project manager e i responsabili dei team per garantire che i progetti rimangano nei tempi previsti e nel rispetto del budget.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK): Aspose.Tasks per Java richiede Java SE 6 o successivo.
2.  Aspose.Tasks per Java Library: scarica e installa la libreria da[Qui](https://releases.aspose.com/tasks/java/).
3. Ambiente di sviluppo integrato (IDE): qualsiasi IDE Java come Eclipse, IntelliJ IDEA o NetBeans.

## Importa pacchetti
Inizia importando i pacchetti necessari nel tuo file Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Passaggio 1: impostare la directory dei dati
Definisci la directory in cui si trova il file di progetto:
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"` con il percorso del file di progetto.
## Passaggio 2: caricare il progetto
 Istanziare a`Project` oggetto e caricare il file di progetto:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Sostituire`"ResourceAssignmentOvertimes.mpp"` con il nome del file di progetto.
## Passaggio 3: ripetere le assegnazioni delle risorse
Passa in rassegna ogni assegnazione di risorse nel progetto:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Passaggio 4: stampare i costi e il lavoro degli straordinari
Recuperare e stampare i costi degli straordinari e lavorare per ogni assegnazione di risorse:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Passaggio 5: stampa dei costi e del lavoro rimanenti
Recupera e stampa i costi rimanenti e lavora per ogni assegnazione di risorse:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Passaggio 6: stampare i costi e il lavoro degli straordinari rimanenti
Recuperare e stampare i costi rimanenti degli straordinari e lavorare per ogni assegnazione di risorse:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Conclusione
Il monitoraggio degli straordinari, dei costi rimanenti e del lavoro in un progetto è fondamentale per una gestione di successo del progetto. Con Aspose.Tasks per Java, puoi facilmente accedere e tenere traccia di queste informazioni, assicurando che i tuoi progetti rispettino la pianificazione e il budget.
## Domande frequenti
### Posso utilizzare Aspose.Tasks per Java con altre librerie Java?
Sì, Aspose.Tasks per Java è compatibile con altre librerie e framework Java.
### Aspose.Tasks supporta diversi formati di file di progetto?
Sì, Aspose.Tasks supporta vari formati di file di progetto tra cui MPP, XML e altri.
### È disponibile una versione di prova?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso trovare supporto se riscontro problemi?
 È possibile visitare il forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15) per supporto.
### Come posso acquistare una licenza per Aspose.Tasks?
 Puoi acquistare una licenza da[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
