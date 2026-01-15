---
date: 2026-01-15
description: Scopri come aggiungere una risorsa al progetto, aggiornare i dati della
  risorsa e salvare il progetto come MPP usando Aspose.Tasks per Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aggiungi risorsa al progetto usando Aspose.Tasks per Java
url: /it/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere una risorsa al progetto usando Aspose.Tasks per Java

## Introduzione
In questo tutorial pratico scoprirai **how to add resource to project** programmaticamente con l'API Java di Aspose.Tasks. Vedremo come caricare un file XML di MS Project esistente, inserire una nuova risorsa, aggiornare le sue proprietà e infine **save project as MPP**. Alla fine avrai un modello chiaro e ripetibile da inserire in qualsiasi strumento di reporting o automazione basato su Java.

## Risposte rapide
- **Cosa significa “add resource to project”?** Crea una nuova voce di risorsa (persone, attrezzature, materiale) all'interno di un file Microsoft Project.  
- **Quale libreria gestisce questo?** Aspose.Tasks per Java – non è necessario avere Microsoft Project installato.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso convertire XML in MPP?** Sì – carica il file XML e **save project as MPP** usando `project.save(...)`.  
- **Quale versione di Java è richiesta?** Java 6 o successiva (Java 8+ consigliata).

## Che cosa è “add resource to project”?
Aggiungere una risorsa a un progetto significa inserire una nuova riga nella tabella Risorse di un file MS Project. Questa riga memorizza dettagli come nome, tariffe dei costi, gruppo e campi personalizzati a cui i task possono fare riferimento in seguito.

## Perché usare Aspose.Tasks per Java?
- **Nessuna dipendenza da Microsoft Project** – funziona su qualsiasi OS o server CI.  
- **Fedele al 100%** – conserva tutte le funzionalità native di Project durante la conversione tra formati.  
- **API ricca** – consente di leggere, scrivere e manipolare task, risorse, calendari e altro.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. Java Development Kit (JDK) 8 o più recente installato.  
2. Libreria Aspose.Tasks per Java – scaricala da [qui](https://releases.aspose.com/tasks/java/).  
3. Familiarità di base con la sintassi Java e la configurazione di progetti Maven/Gradle.

## Importare i pacchetti
Aggiungi le classi Aspose.Tasks necessarie al tuo file sorgente Java:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Passo 1: Configura la tua directory dati
Definisci dove risiederanno i file XML di origine e i file MPP risultanti:

```java
String dataDir = "Your Data Directory";
```

## Passo 2: Specifica i file di input e output
Indica il file XML che desideri convertire (**converti XML in MPP**) e il file MPP di destinazione che conterrà la nuova risorsa:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Passo 3: Carica il progetto
Crea un oggetto `Project` dalla sorgente XML:

```java
Project project = new Project(file);
```

## Passo 4: Aggiungi una risorsa e imposta gli attributi
Qui è dove **add resource to project** e configuriamo le sue tariffe e il gruppo:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Consiglio professionale:* Puoi ripetere la chiamata `add` all'interno di un ciclo per **aggiornare più risorse** in un'unica esecuzione.

## Passo 5: Salva il progetto
Infine, **save project as MPP** per persistere le modifiche:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusione
Hai appena imparato **how to add resource to project**, aggiornato le sue proprietà e **save project as MPP** usando Aspose.Tasks per Java. Questo approccio è ideale per pipeline di reporting automatizzate, importazioni di risorse in blocco o qualsiasi scenario in cui è necessario manipolare file MS Project senza l'applicazione desktop.

## Domande frequenti

**Q1: Posso aggiornare più risorse nello stesso progetto usando Aspose.Tasks per Java?**  
A: Sì, itera su `project.getResources()` o chiama `add` ripetutamente, impostando i campi di ciascuna risorsa secondo necessità.

**Q2: Aspose.Tasks supporta altri formati di file oltre a MS Project?**  
A: Assolutamente – XML, MPP, MPX, Primavera e molti altri sono tutti supportati.

**Q3: Aspose.Tasks è compatibile con diverse versioni di Java?**  
A: La libreria funziona con Java 6 e versioni successive; Java 8+ è fortemente consigliata per le migliori prestazioni.

**Q4: Posso eseguire altre operazioni sui file MS Project con Aspose.Tasks?**  
A: Sì, puoi leggere/scrivere task, calendari, assegnazioni, campi personalizzati e persino generare report.

**Q5: Dove posso trovare ulteriore aiuto o supporto per Aspose.Tasks?**  
A: Visita il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assistenza della community e supporto ufficiale.

---

**Ultimo aggiornamento:** 2026-01-15  
**Testato con:** Aspose.Tasks per Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}