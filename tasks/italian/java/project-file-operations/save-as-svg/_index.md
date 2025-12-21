---
date: 2025-12-21
description: Impara come creare SVG da file MPP in Java e salva il progetto come SVG
  usando la libreria Aspose.Tasks. Guida passo‑passo con esempi di codice.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come creare SVG da MPP in Java usando Aspose.Tasks
url: /it/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare SVG da MPP in Java

## Introduzione
In questo tutorial imparerai come **creare SVG da MPP** utilizzando Aspose.Tasks per Java. Convertire un file Microsoft Project (MPP) in grafica vettoriale scalabile (SVG) ti permette di incorporare diagrammi ad alta qualità e indipendenti dalla risoluzione direttamente nelle pagine web, nei report o nei cruscotti. Ti guideremo attraverso la configurazione necessaria, mostreremo il codice esatto di cui hai bisogno e spiegheremo ogni passaggio in modo che tu possa **salvare il progetto come SVG** nelle tue applicazioni.

## Risposte rapide
- **Cosa significa “creare SVG da MPP”?**  
  Converte un file Microsoft Project (.mpp) in un'immagine SVG che può essere visualizzata su qualsiasi browser senza perdita di qualità.  
- **Quale libreria gestisce la conversione?**  
  Aspose.Tasks per Java fornisce un metodo `save` a riga singola per eseguire la conversione.  
- **Ho bisogno di una licenza?**  
  È necessaria una licenza temporanea per uso commerciale; è disponibile una prova gratuita.  
- **Quali sono i prerequisiti?**  
  Java JDK 8+ e il JAR di Aspose.Tasks per Java.  
- **Quanto tempo richiede la conversione?**  
  Tipicamente meno di un secondo per file di progetto standard.

## Cos'è “creare SVG da MPP”?
Creare un SVG da un file MPP significa esportare la rappresentazione visiva di un programma di progetto — attività, linee temporali e risorse — nel formato Scalable Vector Graphics. SVG è basato su XML, leggero e si scala perfettamente su display ad alta risoluzione.

## Perché usare Aspose.Tasks per salvare il progetto come SVG?
- **Nessuna installazione di Microsoft Project richiesta** – la libreria funziona in modo indipendente.  
- **Fidelità completa** – grafici, barre Gantt e milestone mantengono i loro stili.  
- **Cross‑platform** – esegui il codice su Windows, Linux o macOS.  
- **Integrazione facile** – una chiamata API a riga singola si integra naturalmente nei pipeline Java esistenti.

## Prerequisiti
- **Java Development Kit (JDK)** – versione 8 o successiva. Scarica dal sito web di Oracle.  
- **Aspose.Tasks per Java** – ottieni la libreria dalla pagina di download ufficiale **[qui](https://releases.aspose.com/tasks/java/)**.  

## Importa pacchetti
Per prima cosa, importa le classi di cui avrai bisogno. Il blocco di import rimane invariato.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Passo 1: Definisci la directory dei dati
Specifica dove si trova il tuo file MPP di origine e dove verrà scritto l'SVG.

```java
String dataDir = "Your Data Directory";
```

> **Suggerimento:** Usa un percorso assoluto o un percorso relativo alla cartella delle risorse del tuo progetto per evitare `FileNotFoundException`.

## Passo 2: Carica il file MPP
Crea un'istanza `Project` caricando il file Microsoft Project esistente.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Questa riga legge *HomeMovePlan.mpp* dalla cartella definita in precedenza.

## Passo 3: Salva il progetto come SVG
Ora puoi **salvare il progetto come SVG** con un unico comando.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Il metodo scrive `project5.svg` nella stessa directory. L'SVG risultante può essere aperto in qualsiasi browser moderno o incorporato direttamente in HTML.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|-------|--------|-----|
| **File non trovato** | Percorso `dataDir` errato | Verifica che la stringa della directory termini con un separatore (`/` o `\\`). |
| **Output SVG vuoto** | Progetto caricato senza visualizzazioni | Assicurati che il file MPP contenga una vista Gantt prima di salvare. |
| **Eccezione di licenza** | Nessuna licenza valida applicata | Applica una licenza temporanea usando `License.setLicense("path/to/license.xml")` prima di chiamare `save`. |

## Domande frequenti

**D: Aspose.Tasks per Java è compatibile con tutte le versioni dei file Microsoft Project?**  
R: Sì, supporta i formati MPP, MPT e XML dalle versioni più vecchie alle ultime release di Project.

**D: Posso personalizzare l'aspetto dell'output SVG?**  
R: Assolutamente. Usa `SvgOptions` per impostare caratteri, colori e opzioni di layout prima di chiamare `save`.

**D: Aspose.Tasks per Java richiede una licenza per uso commerciale?**  
R: Sì, è necessaria una licenza valida per la produzione. Puoi ottenere una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.

**D: Posso provare Aspose.Tasks per Java prima di acquistare?**  
R: Sì, è disponibile una prova gratuita **[qui](https://purchase.aspose.com/buy)**.

**D: Dove posso ottenere supporto per Aspose.Tasks per Java?**  
R: Visita il forum della community **[qui](https://forum.aspose.com/c/tasks/15)** per fare domande e condividere feedback.

## Conclusione
Ora sai come **creare SVG da MPP** in Java e come **salvare il progetto come SVG** in modo efficiente usando Aspose.Tasks. Questa funzionalità ti consente di integrare visualizzazioni di progetto ricche in portali web, cruscotti di reporting o in qualsiasi luogo dove sono necessarie grafiche scalabili. Sperimenta con `SvgOptions` per perfezionare l'output, e avrai uno strumento potente nel tuo toolkit di sviluppo.

---

**Ultimo aggiornamento:** 2025-12-21  
**Testato con:** Aspose.Tasks per Java 24.10  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}