---
date: 2026-02-26
description: Scopri come salvare il progetto in PDF e generare un foglio delle attività
  usando Aspose.Tasks per Java. Esporta MPP in PDF rapidamente con questa guida passo‑passo.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salva progetto come PDF – Genera foglio attività con Aspose.Tasks per Java
url: /it/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva Progetto come PDF – Genera Foglio Attività in Aspose.Tasks

## Introduzione
In questa guida completa scoprirai come **salvare il progetto come PDF** e generare un foglio attività con Aspose.Tasks per Java. Che tu abbia bisogno di esportare un file MPP in PDF per le revisioni degli stakeholder o semplicemente di generare un foglio attività pulito per i report, questo tutorial ti accompagna passo passo, spiega perché ogni impostazione è importante e mostra il codice esatto da eseguire.

## Risposte Rapide
- **Cosa fa “save project as pdf”?** Converte un file Microsoft Project (MPP) in un documento PDF, formattandolo facoltativamente come foglio attività.  
- **Quale formato viene usato per un PDF foglio attività?** L'opzione `PresentationFormat.TaskSheet` in `PdfSaveOptions`.  
- **È necessaria una licenza per eseguire il codice?** È richiesta una licenza temporanea o completa per la produzione; una prova gratuita è sufficiente per la valutazione.  
- **Quali sono i prerequisiti principali?** Java JDK, la libreria Aspose.Tasks per Java e un file di progetto valido (es. *.mpp).  
- **Posso personalizzare il layout del PDF?** Sì, Aspose.Tasks offre molte proprietà `PdfSaveOptions` per lo stile e la configurazione della pagina.

## Cos'è “save project as pdf”?
Salvare un progetto come PDF trasforma i dati interni del progetto in un documento portatile e di sola lettura. È ideale per condividere piani, fogli attività o report di stato con stakeholder che non hanno Microsoft Project installato.

## Perché generare un foglio attività?
Un foglio attività presenta ogni attività in una vista tabellare, mostrando ID, nomi, date di inizio/fine e altri campi. Renderizzarlo in PDF garantisce una formattazione coerente su tutte le piattaforme e facilita la stampa o l'inserimento in altri documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – ultima versione installata e `java`/`javac` disponibili nel tuo PATH.  
2. **Aspose.Tasks for Java** – scarica la libreria dal sito ufficiale [qui](https://releases.aspose.com/tasks/java/).  
3. Un **file di progetto** valido (`*.mpp`) che desideri convertire, ad esempio `NewProductDev.mpp`.  

## Importa Pacchetti
Per prima cosa, importa le classi necessarie di Aspose.Tasks. Queste importazioni ti danno accesso alle opzioni di salvataggio PDF, ai formati di presentazione e all'oggetto core `Project`.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Guida Passo‑Passo

### Passo 1: Imposta la Directory del Documento
Definisci la cartella in cui si trova il file MPP di origine e dove verrà scritto il PDF generato. Funziona sia un percorso assoluto che relativo; assicurati solo che la cartella esista.

```java
String dataDir = "Your Document Directory";
```

### Passo 2: Carica il File di Progetto
Crea un'istanza `Project` caricando il file MPP esistente. Questo oggetto rappresenta l'intera struttura del progetto in memoria.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Passo 3: Configura le Opzioni di Salvataggio – Esporta MPP in PDF
Istanzia `PdfSaveOptions` e indica ad Aspose.Tasks che desideri che il PDF sia renderizzato come **foglio attività**. Questo è il passaggio chiave per il caso d'uso *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Passo 4: Salva il Progetto come Foglio Attività – Salva Progetto come PDF
Invoca il metodo `save` sull'oggetto `Project`, passando il nome del file di destinazione e le opzioni configurate. Questa azione **converte il file MPP in un PDF** formattato come foglio attività.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Passo 5: Verifica il Risultato
Naviga nella directory specificata (`dataDir`). Dovresti vedere `taskSheet.pdf` contenente un elenco ordinatamente formattato di tutte le attività. Aprilo con qualsiasi visualizzatore PDF per verificare che la conversione sia avvenuta con successo.

## Problemi Comuni e Soluzioni
- **FileNotFoundException** – Assicurati che `dataDir` termini con un separatore di percorso (`/` o `\\`) e che il nome del file MPP sia corretto.  
- **LicenseException** – Se visualizzi errori di licenza, applica una licenza temporanea o acquistata prima di chiamare qualsiasi API di Aspose.Tasks.  
- **Blank PDF** – Verifica che il progetto contenga effettivamente delle attività; un progetto vuoto produrrà un PDF vuoto.

## Domande Frequenti

**D: Aspose.Tasks è compatibile con tutte le versioni di Java?**  
R: Sì, Aspose.Tasks funziona con un'ampia gamma di versioni Java. Consulta la [documentazione](https://reference.aspose.com/tasks/java/) per i dettagli.

**D: Posso provare Aspose.Tasks prima di acquistarlo?**  
R: Assolutamente! Esplora la versione di prova gratuita [qui](https://releases.aspose.com/).

**D: Dove posso trovare supporto per Aspose.Tasks?**  
R: Unisciti alla community di Aspose.Tasks sul [forum](https://forum.aspose.com/c/tasks/15) per supporto e discussioni.

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
R: Ottieni la tua licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso acquistare Aspose.Tasks per Java?**  
R: Acquista Aspose.Tasks per Java [qui](https://purchase.aspose.com/buy).

## Conclusione
Seguendo questi passaggi hai imparato come **salvare il progetto come PDF**, in particolare generando un foglio attività, usando Aspose.Tasks per Java. Questa funzionalità ti consente di *esportare MPP in PDF* rapidamente, condividere snapshot di progetto leggibili e integrare i dati del progetto in flussi di lavoro di reporting più ampi.

---

**Ultimo Aggiornamento:** 2026-02-26  
**Testato Con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}