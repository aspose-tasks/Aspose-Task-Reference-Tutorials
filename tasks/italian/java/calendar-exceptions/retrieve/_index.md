---
title: Recupera le eccezioni del calendario con Aspose.Tasks
linktitle: Recupera le eccezioni del calendario con Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come recuperare le eccezioni del calendario da MS Project utilizzando Aspose.Tasks per Java. Tutorial passo passo per un'integrazione perfetta.
weight: 13
url: /it/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recupera le eccezioni del calendario con Aspose.Tasks

## introduzione
In questo tutorial esploreremo come recuperare le eccezioni del calendario da MS Project utilizzando la libreria Aspose.Tasks per Java. Aspose.Tasks è un potente strumento che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice. Ti guideremo attraverso il processo passo dopo passo, suddividendo ogni esempio in più passaggi per una facile comprensione.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2.  Aspose.Tasks per Java: Scarica e installa Aspose.Tasks per Java da[Qui](https://releases.aspose.com/tasks/java/).
3. Ambiente di sviluppo integrato (IDE): puoi utilizzare qualsiasi IDE di tua scelta, come IntelliJ IDEA o Eclipse.

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari per lavorare con Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Passaggio 1: configura la directory dei dati
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Data Directory";
```
 Assicurarsi di sostituire`"Your Data Directory"` con il percorso della directory contenente il file MS Project.
## Passaggio 2: caricare il file MS Project
```java
Project project = new Project(dataDir + "project.mpp");
```
 Questa riga inizializza un nuovo file`Project` oggetto caricando il file MS Project specificato dal percorso.
## Passaggio 3: recuperare le eccezioni del calendario
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Qui, iteriamo attraverso ogni calendario nel progetto e poi attraverso ogni eccezione di calendario all'interno di quel calendario. Stampiamo le date di inizio e di fine di ciascuna eccezione.

## Conclusione
In questo tutorial, abbiamo imparato come recuperare le eccezioni del calendario da MS Project utilizzando Aspose.Tasks per Java. Seguendo questi semplici passaggi, puoi integrare perfettamente questa funzionalità nelle tue applicazioni Java.
## Domande frequenti
### Aspose.Tasks può gestire diverse versioni dei file MS Project?
Sì, Aspose.Tasks supporta varie versioni di file MS Project, inclusi i formati MPP, MPT e XML.
### È disponibile una prova gratuita per Aspose.Tasks?
 Sì, puoi scaricare una prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Tasks per Java?
 Puoi fare riferimento alla documentazione[Qui](https://reference.aspose.com/tasks/java/).
### Come posso ottenere supporto per Aspose.Tasks?
 Puoi ottenere supporto dal forum della community[Qui](https://forum.aspose.com/c/tasks/15).
### Esiste un'opzione per licenze temporanee per Aspose.Tasks?
 Sì, puoi ottenere licenze temporanee da[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
