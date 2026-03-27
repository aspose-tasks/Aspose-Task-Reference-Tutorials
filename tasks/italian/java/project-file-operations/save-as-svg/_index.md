---
date: 2026-03-27
description: Scopri come esportare MPP in SVG in Java con Aspose.Tasks. Guida passo
  passo, esempi di codice e consigli per salvare rapidamente un progetto in SVG.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come esportare MPP in SVG in Java usando Aspose.Tasks
url: /it/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come esportare MPP in SVG in Java

## Esportazione di MPP in SVG – Introduzione
In questo tutorial imparerai come **esportare MPP in SVG** utilizzando Aspose.Tasks per Java. Convertire un file Microsoft Project (MPP) in un'immagine Scalable Vector Graphics (SVG) ti consente di incorporare diagrammi ad alta qualità e indipendenti dalla risoluzione direttamente nelle pagine web, nei report o nei cruscotti. Ti guideremo attraverso la configurazione necessaria, mostreremo il codice esatto di cui hai bisogno e spiegheremo ogni passaggio così potrai **salvare il progetto come SVG** nelle tue applicazioni.

## Risposte rapide
- **Cosa significa “export MPP to SVG”?**  
  Converte un file Microsoft Project (.mpp) in un'immagine SVG che può essere visualizzata su qualsiasi browser senza perdita di qualità.  
- **Quale libreria gestisce la conversione?**  
  Aspose.Tasks per Java fornisce un metodo `save` a riga singola per eseguire la conversione.  
- **Ho bisogno di una licenza?**  
  È necessaria una licenza temporanea per uso commerciale; è disponibile una prova gratuita.  
- **Quali sono i prerequisiti?**  
  Java JDK 8+ e il JAR di Aspose.Tasks per Java.  
- **Quanto tempo richiede la conversione?**  
  Tipicamente meno di un secondo per file di progetto standard.

## Cos'è “export MPP to SVG”?
Esportare MPP in SVG significa prendere la rappresentazione visiva di un programma di progetto—attività, linee temporali e risorse—e scriverla in un file SVG. SVG è basato su XML, leggero e si scala perfettamente su display ad alta risoluzione.

## Perché esportare MPP in SVG con Aspose.Tasks?
- **Nessuna installazione di Microsoft Project richiesta** – la libreria funziona in modo indipendente.  
- **Fedele al 100%** – grafici, barre Gantt e milestone mantengono i loro stili.  
- **Cross‑platform** – esegui il codice su Windows, Linux o macOS.  
- **API a una riga** – una singola chiamata salva il progetto come SVG, integrandosi naturalmente nei pipeline Java esistenti.

## Prerequisiti
- **Java Development Kit (JDK)** – versione 8 o successiva. Scarica dal sito web di Oracle.  
- **Aspose.Tasks per Java** – ottieni la libreria dalla pagina di download ufficiale **[qui](https://releases.aspose.com/tasks/java/)**.  

## Importa pacchetti
First, import the classes you’ll need. The import block remains unchanged.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Passo 1: Definisci la directory dei dati
Specify where your source MPP file lives and where the SVG will be written.

```java
String dataDir = "Your Data Directory";
```

> **Suggerimento professionale:** Usa un percorso assoluto o un percorso relativo alla cartella delle risorse del tuo progetto per evitare `FileNotFoundException`.

## Passo 2: Carica il file MPP
Create a `Project` instance by loading the existing Microsoft Project file.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Questa riga legge *HomeMovePlan.mpp* dalla cartella che hai definito in precedenza.

## Passo 3: Salva il progetto come SVG
Now you can **export MPP to SVG** with a single command.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Il metodo scrive `project5.svg` nella stessa directory. L'SVG risultante può essere aperto in qualsiasi browser moderno o incorporato direttamente in HTML.

## Casi d'uso comuni
- **Dashboard di progetto** – incorpora grafici Gantt live nei portali web senza richiedere al cliente di installare Microsoft Project.  
- **Reportistica automatizzata** – genera immagini SVG al volo per report PDF o HTML.  
- **Collaborazione cross‑team** – condividi un calendario visivo con gli stakeholder che hanno solo bisogno di un browser per visualizzarlo.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **File non trovato** | Percorso `dataDir` errato | Verifica che la stringa della directory termini con un separatore (`/` o `\\`). |
| **Output SVG vuoto** | Progetto caricato senza viste | Assicurati che il file MPP contenga una vista Gantt prima di salvare. |
| **Eccezione di licenza** | Nessuna licenza valida applicata | Applica una licenza temporanea usando `License.setLicense("path/to/license.xml")` prima di chiamare `save`. |

## Domande frequenti

**Q: Aspose.Tasks per Java è compatibile con tutte le versioni dei file Microsoft Project?**  
A: Sì, supporta i formati MPP, MPT e XML dalle versioni più vecchie fino alle ultime release di Project.

**Q: Posso personalizzare l'aspetto dell'output SVG?**  
A: Assolutamente. Usa `SvgOptions` per impostare caratteri, colori e opzioni di layout prima di chiamare `save`.

**Q: Aspose.Tasks per Java richiede una licenza per uso commerciale?**  
A: Sì, è necessaria una licenza valida per la produzione. Puoi ottenere una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.

**Q: Posso provare Aspose.Tasks per Java prima di acquistarlo?**  
A: Sì, è disponibile una prova gratuita **[qui](https://purchase.aspose.com/buy)**.

**Q: Dove posso ottenere supporto per Aspose.Tasks per Java?**  
A: Visita il forum della community **[qui](https://forum.aspose.com/c/tasks/15)** per porre domande e condividere feedback.

## Conclusione
Ora sai come **esportare MPP in SVG** in Java e **salvare il progetto come SVG** in modo efficiente usando Aspose.Tasks. Questa funzionalità ti consente di integrare visualizzazioni di progetto ricche in portali web, dashboard di reporting o in qualsiasi contesto in cui siano necessarie grafiche scalabili. Sperimenta con `SvgOptions` per perfezionare l'output e avrai uno strumento potente nel tuo toolkit di sviluppo.

---

**Ultimo aggiornamento:** 2026-03-27  
**Testato con:** Aspose.Tasks per Java 24.10  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}