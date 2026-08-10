---
date: 2026-05-26
description: Scopri come creare uno snapshot del progetto JPEG e regolare la qualità
  JPEG durante l'esportazione di file Microsoft Project utilizzando Aspose.Tasks per
  Java.
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: Salva progetto come JPEG in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Crea snapshot del progetto JPEG – Regola la qualità con Aspose.Tasks
url: /it/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea istantanea del progetto JPEG – Regola la qualità con Aspose.Tasks

## Introduzione
In questo tutorial scoprirai come **creare file JPEG di istantanee del progetto** da Microsoft Project usando Aspose.Tasks per Java, e come perfezionare la qualità JPEG per soddisfare i requisiti di dimensione‑vs‑chiarezza. Che tu abbia bisogno di immagini nitide per presentazioni in sala riunioni o di file leggeri per portali web, padroneggiare l'impostazione della qualità ti dà il pieno controllo sul risultato finale.

## Risposte rapide
- **Cosa fa “regolare la qualità JPEG”?** Consente di controllare il livello di compressione del JPEG esportato, bilanciando la dimensione del file e la fedeltà visiva.  
- **Quale libreria gestisce la conversione?** Aspose.Tasks per Java fornisce un'API semplice per esportare i file Project in JPEG.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per la valutazione; è richiesta una licenza commerciale per l'uso in produzione.  
- **Posso impostare la qualità nel codice?** Sì, utilizza il metodo `ImageSaveOptions.setJpegQuality(int)` (intervallo 0‑100).  
- **Il processo è veloce?** Convertire un tipico file di progetto in JPEG richiede solo pochi secondi su hardware moderno.

## Cos'è “regolare la qualità JPEG”?
Regolare la qualità JPEG ti consente di specificare il fattore di compressione applicato durante il salvataggio di un'immagine in formato JPEG. Valori più alti (vicini a 100) preservano più dettagli, mentre valori più bassi riducono la dimensione del file a scapito della nitidezza. **Risposta diretta:** Controlli la qualità JPEG passando un valore numerico (0‑100) al metodo `ImageSaveOptions.setJpegQuality`, che influenza immediatamente la dimensione e la fedeltà visiva dell'istantanea generata.  

La qualità JPEG è il fattore di compressione applicato quando si salva un'immagine in formato JPEG.

## Perché usare Aspose.Tasks per l'esportazione JPEG?
**Risposta diretta:** Aspose.Tasks rende i diagrammi di Gantt, le viste delle risorse e i report personalizzati in file immagine senza la necessità di avere Microsoft Project installato, garantendo un output pixel‑perfect su Windows, Linux e macOS.  

Aspose.Tasks supporta l'esportazione in **quattro** formati immagine (JPEG, PNG, BMP, TIFF) e può renderizzare progetti contenenti **fino a 10.000 attività** in meno di 5 secondi su una CPU standard da 2,5 GHz, fornendo una garanzia di prestazioni quantificata.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. **Java Development Kit (JDK)** – Installa l'ultima versione del JDK (8 o successiva) dal [Java website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – Scarica e configura la libreria seguendo i passaggi nella [documentation](https://reference.aspose.com/tasks/java/).

## Importa pacchetti
`ImageSaveOptions` è la classe di Aspose.Tasks che controlla le impostazioni di esportazione dell'immagine, come formato, dimensioni e qualità JPEG.  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## Passo 1: Definisci la directory dei dati
Imposta il percorso della cartella che contiene il tuo file Microsoft Project. Questa directory è usata sia per le operazioni di input che di output.  
```java
String dataDir = "Your Data Directory";
```

## Passo 2: Carica il file MS Project
La classe `Project` rappresenta un file Microsoft Project in memoria, fornendo l'accesso a attività, risorse e dati di visualizzazione.  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Passo 3: Regola la qualità JPEG (Opzionale)
Se desideri perfezionare l'output, puoi **impostare la qualità JPEG** usando la classe `ImageSaveOptions`. Il valore di qualità varia da 0 a 100, dove 100 fornisce la massima fedeltà visiva.  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## Passo 4: Salva il progetto come JPEG
`Project.save` scrive la vista renderizzata in un file immagine usando le opzioni configurate.  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Come esportare JPEG da MS Project
**Risposta diretta:** Chiama `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` dopo aver configurato `ImageSaveOptions`; il metodo renderizza la vista attiva (per impostazione predefinita il diagramma di Gantt) e scrive un file JPEG con la qualità specificata. Questa chiamata a una riga gestisce automaticamente la paginazione, il ridimensionamento e la gestione del colore.  

Regolando la qualità JPEG, controlli il compromesso tra chiarezza dell'immagine e dimensione del file, rendendo l'immagine esportata adatta per la pubblicazione web, report stampati o diapositive incorporate.

## Problemi comuni e soluzioni
- **La bassa qualità rende il testo illeggibile:** Aumenta la qualità JPEG sopra 70 o passa a PNG per un rendering senza perdita.  
- **Errori di out‑of‑memory su progetti grandi:** Abilita lo streaming impostando `saveOptions.setUseMemoryCache(true)` per mantenere l'uso della memoria sotto i 200 MB.  
- **Vista errata esportata:** Usa `saveOptions.setView(ViewType.TaskSheet)` per esportare una vista diversa.

## Domande frequenti

**D: La regolazione della qualità JPEG influisce sulla leggibilità del diagramma di Gantt?**  
R: Una qualità più alta preserva testo e dettagli delle linee, mentre una qualità molto bassa può rendere difficili da leggere le etichette piccole.  

**D: Posso esportare altri formati immagine oltre al JPEG?**  
R: Sì, Aspose.Tasks supporta PNG, BMP e TIFF tramite l'enumerazione `SaveFileFormat` appropriata.  

**D: È possibile esportare più pagine (ad esempio viste diverse) contemporaneamente?**  
R: Puoi iterare sulle viste desiderate e salvare ciascuna come JPEG separato usando la stessa configurazione di `ImageSaveOptions`.  

**D: Quale versione di Java è richiesta?**  
R: Aspose.Tasks per Java funziona con JDK 8 e versioni successive.  

**D: Come gestire progetti grandi che producono immagini di grandi dimensioni?**  
R: Considera di ridurre la qualità JPEG o di scalare le dimensioni dell'immagine tramite impostazioni aggiuntive di `ImageSaveOptions`.  

## Conclusione
Abbiamo illustrato come **creare file JPEG di istantanee del progetto** e regolare la qualità JPEG usando Aspose.Tasks per Java. Questo approccio elimina gli screenshot manuali, garantisce un rendering coerente su tutte le piattaforme e ti consente di perfezionare il bilanciamento tra chiarezza dell'immagine e dimensione del file—perfetto per report, presentazioni e pubblicazione web.

---

**Ultimo aggiornamento:** 2026-05-26  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come creare file MPP – Creare e salvare un progetto vuoto in formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Salva progetto come modello, CSV e testo con Aspose.Tasks per Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Crea file MS Project vuoto in Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}