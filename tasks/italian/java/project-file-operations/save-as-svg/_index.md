---
title: Converti MS Project in SVG in Java
linktitle: Salva come SVG in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Scopri come salvare i file di Microsoft Project come SVG in Java utilizzando la libreria Aspose.Tasks. Guida passo passo con esempi di codice.
weight: 18
url: /it/java/project-file-operations/save-as-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti MS Project in SVG in Java

## introduzione
Aspose.Tasks per Java è una potente libreria per lavorare con file di gestione dei progetti, consentendo agli sviluppatori di manipolare i dati del progetto, eseguire varie operazioni e generare report in modo efficiente. In questo tutorial esploreremo come salvare un progetto come SVG utilizzando Aspose.Tasks per Java. SVG (Scalable Vector Graphics) è un formato ampiamente utilizzato per visualizzare la grafica vettoriale sul Web, fornendo scalabilità e rendering di alta qualità.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
### Ambiente di sviluppo Java
Assicurati di avere Java Development Kit (JDK) installato sul tuo sistema. È possibile scaricare e installare JDK dal sito Web Oracle.
### Aspose.Tasks per la libreria Java
 Scaricare e installare la libreria Aspose.Tasks per Java dal sito Web. È possibile trovare il collegamento per il download nella documentazione fornita[Qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari nel tuo programma Java per lavorare con le funzionalità Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Ora suddividiamo l'esempio fornito in più passaggi:
## Passaggio 2: definire la directory dei dati
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"`con il percorso della directory in cui si trova il file di progetto.
## Passaggio 3: caricare il file di progetto
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Questo passaggio carica il file di progetto denominato "HomeMovePlan.mpp" dalla directory dei dati specificata.
## Passaggio 4: salva come SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Questo passaggio salva il progetto caricato in formato SVG con il nome "project5.svg" nella directory dei dati specificata.

## Conclusione
In questo tutorial, abbiamo imparato come salvare un progetto come SVG utilizzando Aspose.Tasks per Java. Seguendo i passaggi forniti, puoi convertire in modo efficiente i file di progetto in formato SVG, consentendo una perfetta integrazione con applicazioni basate sul Web o strumenti di visualizzazione.
## Domande frequenti
### Aspose.Tasks per Java è compatibile con tutte le versioni dei file Microsoft Project?
Sì, Aspose.Tasks per Java supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.
### Posso personalizzare l'aspetto dell'output SVG?
Sì, puoi personalizzare l'aspetto dell'output SVG modificando parametri quali caratteri, colori e configurazioni del layout.
### Aspose.Tasks per Java richiede una licenza per uso commerciale?
 Sì, è necessaria una licenza valida per l'uso commerciale di Aspose.Tasks per Java. È possibile ottenere una licenza dal sito Web[Qui](https://purchase.aspose.com/temporary-license/).
### Posso provare Aspose.Tasks per Java prima dell'acquisto?
 Sì, puoi richiedere una prova gratuita di Aspose.Tasks per Java dal sito web[Qui](https://purchase.aspose.com/buy) per valutarne le caratteristiche e le potenzialità.
### Dove posso ottenere supporto per Aspose.Tasks per Java?
 È possibile ottenere supporto per Aspose.Tasks per Java visitando il forum[Qui](https://forum.aspose.com/c/tasks/15), dove puoi porre domande e interagire con la community.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
