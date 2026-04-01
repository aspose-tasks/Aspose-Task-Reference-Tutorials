---
date: 2026-04-01
description: Scopri come salvare XML, impostare l'anno fiscale e convertire MPP in
  XML usando Aspose.Tasks per Java. Guida passo passo con esempi di codice.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: Come salvare XML e gestire l'anno fiscale in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come salvare XML e gestire l'anno fiscale in Aspose.Tasks
url: /it/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come salvare XML e gestire l'anno fiscale in Aspose.Tasks

## Introduzione
Se hai bisogno di **how to save xml** file generati dai dati di Microsoft Project, Aspose.Tasks per Java ti offre un modo semplice e senza licenza per farlo. In questo tutorial vedremo come caricare un file MPP, visualizzare le informazioni sull'anno fiscale, impostare le proprietà dell'anno fiscale e infine **how to save xml** l'output. Vedrai anche come **how to set fiscal** i dettagli e **how to convert mpp** i file senza mai aprire Microsoft Project.

## Risposte rapide
- **Cosa significa “manage fiscal year” in Aspose.Tasks?** Consente di definire il mese di inizio dell'anno fiscale e abilitare la numerazione dell'anno fiscale per un progetto.  
- **Come impostare il mese di inizio dell'anno fiscale?** Usa la proprietà `Prj.FY_START_DATE` con un valore enum `Month` (ad es., `Month.JULY`).  
- **Posso caricare un file MPP?** Sì, basta creare un'istanza `Project` con il percorso del file *.mpp*.  
- **Come convertire MPP in XML?** Chiama `project.save(..., SaveFileFormat.Xml)` dopo aver impostato le proprietà desiderate.  
- **È necessaria una licenza?** È disponibile una versione di prova gratuita; per l'uso in produzione è richiesta una licenza commerciale.  

## Cos'è “gestire l'anno fiscale” nei file di progetto?
Gestire l'anno fiscale significa configurare il calendario che il tuo progetto utilizza per la rendicontazione finanziaria. Ciò include impostare il mese di inizio dell'anno fiscale e, facoltativamente, abilitare la numerazione dell'anno fiscale, che influisce su come le date vengono calcolate e visualizzate nei report.

## Perché usare Aspose.Tasks per la gestione dell'anno fiscale?
- **Nessun Microsoft Project richiesto** – lavora con i file di progetto direttamente in Java.  
- **Controllo completo** – imposta l'inizio dell'anno fiscale, abilita la numerazione e converti i formati programmaticamente.  
- **API robusta** – gestione affidabile di file MPP di grandi dimensioni ed esportazione XML senza problemi.  

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.  
2. Aspose.Tasks per Java JAR – scaricalo da [here](https://releases.aspose.com/tasks/java/) e aggiungilo al classpath del tuo progetto.

## Importare i pacchetti
Per iniziare, importa le classi necessarie nel tuo file sorgente Java:
```java
import com.aspose.tasks.*;
```

## Come caricare un file MPP e visualizzare le informazioni sull'anno fiscale
Di seguito suddividiamo il processo in passaggi chiari e numerati.

### Passo 1: Caricare il file di progetto
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Qui **load an MPP file** (`project.mpp`) dalla directory specificata. Questo è il primo passo in qualsiasi manipolazione relativa all'anno fiscale.

### Passo 2: Visualizzare le proprietà dell'anno fiscale
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
Le proprietà `Prj.FY_START_DATE` e `Prj.FISCAL_YEAR_START` ti consentono di **display fiscal year** i dettagli, rispondendo alla domanda “qual è la configurazione fiscale corrente?”.

### Passo 3: Impostare l'inizio dell'anno fiscale e abilitare la numerazione
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
In questo passo **how to set fiscal** le impostazioni:
- `Month.JULY` definisce il mese di inizio dell'anno fiscale.  
- `NullableBool(true)` attiva la numerazione dell'anno fiscale.  
- Infine, il progetto è **converted MPP to XML** usando `SaveFileFormat.Xml`.

### Passo 4: Confermare l'operazione
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Un semplice messaggio sulla console conferma che l'anno fiscale è stato configurato e il file salvato.

## Perché è importante
Salvare il progetto come XML ti fornisce una rappresentazione portabile, basata su testo, che può essere facilmente analizzata, gestita con il versionamento o integrata con altri sistemi. Quando le impostazioni dell'anno fiscale sono corrette, i report finanziari e i dashboard a valle saranno allineati ai periodi contabili della tua organizzazione.

## Casi d'uso comuni
- **Reporting finanziario** – Allinea i programmi di progetto a un calendario fiscale prima di esportare verso strumenti BI.  
- **Migrazione dati** – Converti file *.mpp* legacy in XML per l'importazione in piattaforme di gestione progetti basate su cloud.  
- **Audit automatizzati** – Verifica programmaticamente che ogni progetto utilizzi il corretto mese di inizio fiscale.

## Suggerimenti per la risoluzione dei problemi e ostacoli comuni
| Problema | Soluzione |
|----------|-----------|
| **Valore del mese errato** | Assicurati di usare l'enum `Month` (ad esempio, `Month.JANUARY`). |
| **File non trovato** | Verifica che `dataDir` punti alla cartella corretta e che il nome del file corrisponda. |
| **Salvataggio fallito** | Controlla i permessi di scrittura sulla directory di destinazione e che `SaveFileFormat` sia supportato. |
| **Anno fiscale non riflesso nell'XML** | Dopo il salvataggio, apri l'XML e conferma che i nodi `<FiscalYearStart>` e `<FiscalYearNumbering>` contengano i valori attesi. |

## Domande frequenti

**Q: Posso usare Aspose.Tasks per Java per manipolare altre proprietà del progetto?**  
A: Sì, Aspose.Tasks fornisce funzionalità complete per gestire varie proprietà del progetto oltre alle impostazioni dell'anno fiscale.

**Q: Aspose.Tasks per Java è compatibile con diversi formati di file di progetto?**  
A: Sì, supporta un'ampia gamma di formati inclusi MPP, XML e altri.

**Q: Come posso ottenere supporto se incontro problemi usando Aspose.Tasks per Java?**  
A: Puoi chiedere assistenza alla community di Aspose.Tasks sul [forum](https://forum.aspose.com/c/tasks/15) o contattare direttamente il loro team di supporto.

**Q: Aspose.Tasks offre una versione di prova gratuita?**  
A: Sì, puoi accedere alla versione di prova gratuita di Aspose.Tasks da [here](https://releases.aspose.com/).

**Q: Dove posso acquistare una licenza per Aspose.Tasks per Java?**  
A: Puoi acquistare una licenza per Aspose.Tasks per Java da [here](https://purchase.aspose.com/buy).

## Conclusione
Gestire le proprietà dell'anno fiscale in Aspose.Tasks per Java è semplice. Seguendo i passaggi sopra potrai **how to save xml**, **load mpp file**, **display fiscal year**, **set fiscal year** e **convert mpp to xml** con fiducia. Usa queste tecniche per mantenere i programmi di progetto allineati al calendario finanziario della tua organizzazione e per creare rappresentazioni XML portabili per l'elaborazione a valle.

---

**Ultimo aggiornamento:** 2026-04-01  
**Testato con:** Aspose.Tasks per Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}