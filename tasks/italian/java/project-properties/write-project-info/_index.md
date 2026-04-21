---
date: 2025-12-31
description: Impara come impostare la data di inizio del progetto, scrivere le informazioni
  del progetto e salvare il progetto come XML usando Aspose.Tasks per Java.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Imposta la data di inizio del progetto in MS Project usando Aspose.Tasks per
  Java
url: /it/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta la data di inizio del progetto in MS Project usando Aspose.Tasks per Java

## Introduzione
In questo tutorial scoprirai come **set project start date** e scrivere informazioni aggiuntive di MS Project con Aspose.Tasks per Java. Che tu stia automatizzando i piani di progetto, generando report o integrando i dati di Project in un sistema più ampio, controllare la data di inizio programmaticamente ti dà un controllo preciso sui tuoi tempi. Ti guideremo passo passo—dalla configurazione dell'ambiente al salvataggio del progetto aggiornato come file XML—così potrai iniziare a applicare subito queste tecniche.

## Risposte rapide
- **Qual è la classe principale per manipolare un progetto?** `Project` dalla libreria Aspose.Tasks.  
- **Come impostare la data di inizio del progetto?** Usa `project.set(Prj.START_DATE, <date>)`.  
- **Posso anche impostare la data di stato?** Sì, con `project.set(Prj.STATUS_DATE, <date>)`.  
- **Quale formato devo usare per esportare il progetto?** Salva come XML con `SaveFileFormat.Xml`.  
- **È necessaria una licenza per l'uso in produzione?** È necessaria una licenza valida di Aspose.Tasks per la piena funzionalità.

## Che cos'è **set project start date**?
Impostare la data di inizio del progetto definisce il giorno di calendario da cui iniziano tutte le attività programmate. È il punto di ancoraggio per calcoli come la durata delle attività, le dipendenze e i percorsi critici. Impostando questa data programmaticamente, garantisci coerenza tra più file di progetto ed elimini gli errori di inserimento manuale.

## Perché usare Aspose.Tasks per Java per scrivere informazioni di progetto?
- **Copertura completa dell'API:** Leggi, modifica e scrivi ogni proprietà di Project senza necessità di avere Microsoft Project installato.  
- **Cross‑platform:** Funziona su Windows, Linux e macOS.  
- **Pronto per l'automazione:** Ideale per elaborazioni batch, pipeline CI o servizi back‑end che generano piani di progetto al volo.  

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – qualsiasi versione recente (consigliata 8+).  
2. **Libreria Aspose.Tasks per Java** – scaricala da [here](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse o il tuo editor Java preferito.  

## Importa i pacchetti
Per prima cosa, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Passo 1: Configura la directory dei dati
Definisci la directory in cui verranno archiviati i dati del tuo progetto.
```java
String dataDir = "Your Data Directory";
```

## Passo 2: Crea un'istanza di Project
Inizializza una nuova istanza di Project.
```java
Project project = new Project();
```

## Passo 3: Imposta le proprietà delle informazioni del progetto
Qui impostiamo la **project start date**, la programmazione dall'inizio e la data di stato—coprendo le parole chiave primarie e secondarie *write project information* e *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Passo 4: Salva il progetto come XML
Infine, persisti il file di progetto aggiornato. Questo dimostra la parola chiave secondaria **save project as xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Incorrect start date** | Il mese del calendario è indicizzato a zero in Java. | Usa `Calendar.JULY` (o aggiungi 1 all'indice del mese) come mostrato. |
| **File not saved** | `dataDir` non esiste o non ha i permessi di scrittura. | Crea la directory in anticipo o scegli un percorso scrivibile. |
| **License warning** | L'esecuzione senza licenza aggiunge una filigrana. | Applica una licenza valida di Aspose.Tasks prima di creare l'oggetto `Project`. |

## FAQ
### Q: Posso usare Aspose.Tasks per Java per leggere i file MS Project?
A: Sì, Aspose.Tasks per Java offre funzionalità robuste sia per la lettura che per la scrittura dei file MS Project.  
### Q: Aspose.Tasks per Java è compatibile con diverse versioni di MS Project?
A: Assolutamente, Aspose.Tasks per Java supporta varie versioni di MS Project, garantendo la compatibilità con diversi formati di file.  
### Q: Ci sono limitazioni nella versione di prova di Aspose.Tasks per Java?
A: Sebbene la versione di prova ti permetta di esplorare le capacità della libreria, presenta alcune limitazioni come filigrane sui file di output.  
### Q: Come posso ottenere supporto per Aspose.Tasks per Java?
A: Puoi richiedere assistenza sul forum della community di Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).  
### Q: Posso acquistare una licenza temporanea per Aspose.Tasks per Java?
A: Sì, le licenze temporanee sono disponibili per un uso a breve termine. Puoi ottenerne una da [here](https://purchase.aspose.com/temporary-license/).  

## Conclusione
Ora hai imparato come **set project start date**, scrivere le informazioni essenziali del progetto e **save project as XML** usando Aspose.Tasks per Java. Questi blocchi fondamentali ti consentono di automatizzare i flussi di lavoro di gestione dei progetti, generare piani coerenti e integrare i dati di MS Project nelle tue applicazioni Java.

---

**Ultimo aggiornamento:** 2025-12-31  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}