---
date: 2025-12-07
description: Impara come salvare il file di progetto, scrivere e leggere le formule
  di MS Project e aggiungere formule di campi personalizzati usando Aspose.Tasks per
  Java.
language: it
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salva il file di progetto e scrivi le formule di MS Project con Aspose.Tasks
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva il file di progetto e scrivi formule MS Project con Aspose.Tasks

## Introduzione
Nel campo della gestione dei progetti, la gestione efficace dei dati è fondamentale. Aspose.Tasks per Java è una soluzione robusta che facilita la manipolazione e l'estrazione di dati da file Microsoft Project. Una delle funzionalità più potenti che offre è la possibilità di scrivere e leggere formule MS Project. **Imparerai anche come *salvare il file di progetto* dopo aver applicato queste formule**, garantendo che le modifiche vengano conservate per future analisi. Questo tutorial ti guiderà attraverso il processo di utilizzo di questa funzionalità per migliorare le tue attività di gestione dei progetti.

## Risposte rapide
- **Cosa fa “salvare il file di progetto”?** Scrive tutte le modifiche in memoria in un file .mpp su disco.  
- **Posso aggiungere formule a campi personalizzati?** Sì – puoi creare un campo personalizzato e assegnare una formula come “doppio costo attività”.  
- **È necessaria una licenza per eseguire il codice?** Una prova gratuita è sufficiente per la valutazione; è necessaria una licenza commerciale per la produzione.  
- **Quale IDE funziona meglio?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, VS Code) compilerà l'esempio.  
- **L'API è compatibile con l'ultima versione di MS Project?** Aspose.Tasks supporta tutti i formati .mpp recenti.

## Cos'è “salvare il file di progetto” in Aspose.Tasks?
Salvare un file di progetto significa persistere lo stato corrente dell'oggetto `Project`—incluse attività, risorse e eventuali formule personalizzate—in un file Microsoft Project fisico (`.mpp`). Questa operazione è essenziale dopo aver modificato i dati, ad esempio aggiungendo un campo personalizzato o cambiando i costi delle attività.

## Perché aggiungere un campo personalizzato e creare una formula per campo personalizzato?
Aggiungere un campo personalizzato ti offre un contenitore flessibile per informazioni aggiuntive non coperte dai campi predefiniti. Associando una formula—come quella che **doppia il costo dell'attività**—automatizzi i calcoli, riduci gli errori manuali e mantieni i dati del tuo programma coerenti.

## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere i seguenti prerequisiti:

1. **Java Development Kit (JDK)** – Java 8 o superiore installato sulla tua macchina.  
2. **Aspose.Tasks per Java** – Scarica e installa da [qui](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Scegli il tuo IDE preferito per lo sviluppo Java (IntelliJ IDEA, Eclipse, VS Code, ecc.).  

## Importazione dei pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Passo 1: Configura la directory dei dati
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Definisci la cartella in cui risiedono i file MS Project. Qui caricherai il file sorgente e, successivamente, **salverai il file di progetto**.

## Passo 2: Carica il file di progetto
```java
Project project = new Project(dataDir + "project.mpp");
```
Carica il file Microsoft Project esistente in un oggetto `Project` così da poterne leggere o modificare il contenuto.

## Passo 3: Aggiungi campo personalizzato e crea formula per campo personalizzato
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
In questo passaggio **aggiungiamo il campo personalizzato** “Double Costs” e **creiamo la formula per campo personalizzato** che moltiplica il `[Cost]` dell’attività per 2, ottenendo così **doppio costo attività**. Il metodo `setFormula` incorpora il calcolo direttamente nel file di progetto.

## Passo 4: Aggiungi attività e imposta il costo
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Crea una nuova attività, quindi assegna un costo base di `100`. Quando il progetto verrà salvato, il campo personalizzato mostrerà automaticamente `200` grazie alla formula definita in precedenza.

## Passo 5: Salva il file di progetto
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Infine, **salva il file di progetto** con tutte le modifiche. Il metodo `save` scrive il progetto aggiornato, includendo il nuovo campo personalizzato e i valori calcolati, in `saved.mpp`.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Formula non applicata** | Campo personalizzato non aggiunto alla collezione `ExtendedAttributes` del progetto. | Assicurati che `project.getExtendedAttributes().add(attr);` venga eseguito prima del salvataggio. |
| **File non trovato** | Percorso `dataDir` errato. | Verifica che la stringa della directory termini con un separatore di percorso (`/` o `\\`). |
| **Il costo appare come 0** | Costo dell’attività non impostato prima del salvataggio. | Chiama `task.set(Tsk.COST, ...)` prima di `project.save`. |

## Domande frequenti
**D: Aspose.Tasks è compatibile con tutte le versioni di MS Project?**  
R: Sì, Aspose.Tasks supporta un'ampia gamma di versioni di MS Project, dai formati .mpp più vecchi alle ultime release.

**D: Posso integrare Aspose.Tasks nel mio progetto Java esistente?**  
R: Assolutamente. l'API è progettata per un'integrazione senza soluzione di continuità; basta aggiungere il JAR di Aspose.Tasks al classpath del progetto.

**D: Ci sono limitazioni sui tipi di formule che posso creare?**  
R: La libreria supporta la maggior parte della sintassi delle formule native di MS Project, includendo operazioni aritmetiche, logiche e funzioni integrate. Funzioni personalizzate complesse potrebbero richiedere soluzioni alternative.

**D: Aspose.Tasks supporta il deployment multi‑piattaforma?**  
R: Sì, la libreria gira su qualsiasi piattaforma che supporti Java, inclusi Windows, Linux e macOS.

**D: Come posso ottenere supporto tecnico per Aspose.Tasks?**  
R: Visita il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assistenza dalla community, o apri un ticket di supporto se possiedi una licenza commerciale.

## Conclusione
In questo tutorial abbiamo illustrato come **salvare il file di progetto**, **aggiungere un campo personalizzato** e **creare una formula per campo personalizzato** che **doppia il costo dell'attività** usando Aspose.Tasks per Java. Seguendo questi passaggi potrai automatizzare i calcoli, arricchire i dati del tuo progetto e garantire che tutte le modifiche vengano conservate per future report e analisi.

---

**Ultimo aggiornamento:** 2025-12-07  
**Testato con:** Aspose.Tasks per Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}