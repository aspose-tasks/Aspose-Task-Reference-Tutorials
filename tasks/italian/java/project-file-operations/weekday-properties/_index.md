---
date: 2026-03-29
description: Scopri come modificare i giorni per mese e gestire altre proprietà dei
  giorni della settimana in Aspose.Tasks per Java. Personalizza le date di inizio
  settimana, modifica il calendario del progetto e salva il progetto in XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Modifica i giorni per mese con le proprietà Weekday di Aspose.Tasks
url: /it/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifica i giorni per mese con le proprietà dei giorni della settimana di Aspose.Tasks

## Introduzione
Aspose.Tasks for Java ti consente di **modificare i giorni per mese** e di regolare finemente altre impostazioni dei giorni della settimana senza la necessità di avere Microsoft Project installato. Che tu stia allineando il calendario di un progetto a un mese fiscale non standard o semplicemente abbia bisogno di modificare il giorno di inizio settimana, questo tutorial ti guida attraverso gli scenari più comuni — recuperare il giorno di inizio settimana corrente, personalizzare la data di inizio settimana, modificare il calendario del progetto e salvare il progetto come XML.

## Risposte rapide
- **Posso modificare il numero di giorni per mese?** Sì, utilizza `Prj.DAYS_PER_MONTH` sull'oggetto `Project`.  
- **Come posso personalizzare la data di inizio settimana?** Imposta `Prj.WEEK_START_DAY` su un valore `DayType` (ad es., `DayType.Monday`).  
- **Quale formato posso usare per esportare il progetto?** L'esempio salva il file come XML con `SaveFileFormat.Xml`.  
- **È necessaria una licenza per l'uso in produzione?** È necessaria una licenza valida di Aspose.Tasks per le distribuzioni non‑di valutazione.  
- **Quali IDE sono supportati?** Qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans funziona.

## Cos'è “cambiare i giorni per mese” in Aspose.Tasks?
Modificare i giorni per mese significa aggiornare la proprietà `Prj.DAYS_PER_MONTH` di un'istanza `Project`. Questa proprietà indica al motore quanti giorni lavorativi considerare in ogni mese, influenzando direttamente la programmazione delle attività e i calcoli dei costi.

## Perché modificare le proprietà del calendario del progetto?
Personalizzare il calendario del progetto — come impostare un giorno di inizio settimana diverso o modificare i minuti per giorno — ti aiuta a:

- Allineare i programmi con le settimane lavorative regionali.  
- Modellare schemi di lavoro non standard (ad es., settimane di 4 giorni).  
- Garantire report accurati per i contratti che utilizzano calendari personalizzati.

## Prerequisiti
- **Java Development Kit (JDK)** – Installa l'ultima versione del JDK da Oracle.  
- **Aspose.Tasks for Java library** – Scaricala dal sito ufficiale [qui](https://releases.aspose.com/tasks/java/).  
- **IDE di tua scelta** – IntelliJ IDEA, Eclipse o NetBeans.

## Importa pacchetti
Per prima cosa, importa le classi essenziali di Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Passo 1: Carica il file di progetto
Questo carica un file Microsoft Project esistente (`project.mpp`) dalla cartella specificata.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Passo 2: Visualizza le proprietà dei giorni della settimana
Qui recuperiamo e stampiamo le impostazioni attuali dei giorni della settimana, inclusi il **giorno di inizio settimana** e i **giorni per mese**.

```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```

## Passo 3: Impostazione delle proprietà dei giorni della settimana
In questo passo **modifichiamo i giorni per mese** a 24, impostiamo la settimana per iniziare il lunedì e regolare i minuti per giorno/settimana. Questo dimostra come **modificare il calendario del progetto** programmaticamente.

```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```

## Passo 4: Salva il progetto
Il progetto modificato viene salvato utilizzando il formato **save project as XML**, utile per l'integrazione con altri strumenti o per l'archiviazione sotto controllo di versione.

```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```

## Passo 5: Visualizza il risultato
Una semplice conferma che le operazioni sono terminate senza errori.

```java
System.out.println("Process completed Successfully");
```

## Come personalizzare la data di inizio settimana
Se la tua organizzazione utilizza un calendario che inizia la domenica, sostituisci `DayType.Monday` con `DayType.Sunday`. Viene utilizzata la stessa proprietà (`Prj.WEEK_START_DAY`), rendendo la modifica semplice.

## Come recuperare il giorno di inizio settimana
Puoi chiamare `project.get(Prj.WEEK_START_DAY)` in qualsiasi momento per **recuperare il giorno di inizio settimana**, come mostrato nel Passo 2.

## Come modificare il calendario del progetto
Oltre al giorno di inizio settimana, puoi anche regolare `Prj.MINUTES_PER_DAY` e `Prj.MINUTES_PER_WEEK` per riflettere ore lavorative personalizzate o schemi di turno.

## Problemi comuni e soluzioni
- **Valore del tipo di giorno errato** – Assicurati di utilizzare l'enumerazione `DayType` (ad es., `DayType.Monday`).  
- **Errori nel percorso del file** – Verifica che `dataDir` termini con il separatore di file appropriato (`/` o `\`).  
- **Licenza non impostata** – Se visualizzi avvisi di licenza, registra la tua licenza Aspose.Tasks prima di creare l'oggetto `Project`.

## Domande frequenti

**Q: Aspose.Tasks for Java può gestire strutture di progetto complesse?**  
A: Sì, Aspose.Tasks for Java fornisce un supporto completo per gestire strutture di progetto complesse con facilità.

**Q: Aspose.Tasks for Java è compatibile con diverse versioni dei file Microsoft Project?**  
A: Assolutamente, Aspose.Tasks for Java supporta varie versioni dei file Microsoft Project, garantendo la compatibilità su più piattaforme.

**Q: Posso integrare Aspose.Tasks for Java nelle mie applicazioni Java esistenti?**  
A: Sì, Aspose.Tasks for Java offre capacità di integrazione senza soluzione di continuità, consentendoti di potenziare le tue applicazioni Java con potenti funzionalità di gestione dei progetti.

**Q: Aspose.Tasks for Java fornisce documentazione e supporto?**  
A: Sì, puoi accedere a una documentazione estesa e al supporto della community per Aspose.Tasks for Java sul loro [sito web](https://releases.aspose.com/).

**Q: È disponibile una versione di prova gratuita per Aspose.Tasks for Java?**  
A: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks for Java dal loro [sito web](https://reference.aspose.com/tasks/java/) per esplorare le funzionalità prima di effettuare un acquisto.

---

**Ultimo aggiornamento:** 2026-03-29  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}