---
date: 2025-12-18
description: Scopri come creare una vista in Aspose.Tasks per Java, inclusa la modalità
  di salvataggio della vista del progetto e l'impostazione delle proprietà della vista.
  Migliora l'efficienza della gestione dei progetti con viste personalizzate di MS Project
  su misura.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Come creare una vista: viste personalizzate di MS Project in Aspose.Tasks'
url: /it/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare visualizzazioni: Visualizzazioni personalizzate di MS Project in Aspose.Tasks

## Introduzione
Se stai cercando **come creare visualizzazione** che corrisponda alle esigenze uniche di reporting del tuo progetto, sei nel posto giusto. Nella gestione dei progetti, la personalizzazione delle visualizzazioni può migliorare notevolmente la chiarezza e l'efficienza nella gestione di attività e risorse. **Aspose.Tasks for Java** ti fornisce un'API ricca per **add custom view java**‑style solutions, consentendoti di modellare le visualizzazioni di MS Project esattamente come desideri. In questo tutorial ti guideremo passo dopo passo, dalla configurazione di un progetto al salvataggio della visualizzazione del progetto.

## Risposte rapide
- **Qual è lo scopo principale?** Creare e mantenere una visualizzazione personalizzata di MS Project utilizzando Aspose.Tasks for Java.  
- **Quale classe crea una visualizzazione?** `GanttChartView` (o altri tipi di visualizzazione).  
- **Come faccio a far apparire la visualizzazione nel menu?** Imposta `view.setShowInMenu(true)`.  
- **Come posso salvare la visualizzazione con il progetto?** Usa `MPPSaveOptions` con `setWriteViewData(true)`.  
- **Ho bisogno di una licenza?** Sì, è necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:

### Ambiente di sviluppo Java
Assicurati di avere Java installato sul tuo sistema.

### Aspose.Tasks per Java
Scarica e installa Aspose.Tasks per Java da [qui](https://releases.aspose.com/tasks/java/).

## Importa pacchetti
Per prima cosa, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Passo 1: Configura il progetto
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Passo 2: Crea visualizzazione
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Passo 3: Personalizza le proprietà della visualizzazione *(imposta proprietà visualizzazione)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### Come mostrare il menu della visualizzazione
La chiamata `view.setShowInMenu(true)` garantisce che la visualizzazione appena creata appaia nel **menu visualizzazioni** di MS Project, offrendo agli utenti finali un accesso rapido.

## Passo 4: Regola le impostazioni della visualizzazione
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Passo 5: Aggiungi visualizzazione al progetto *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Passo 6: Salva progetto *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Perché è importante salvare la visualizzazione del progetto
Impostando `options.setWriteViewData(true)` si indica ad Aspose.Tasks di **salvare le informazioni della visualizzazione del progetto** all'interno del file MPP, in modo che la visualizzazione personalizzata persista tra le sessioni.

## Passo 7: Verifica le proprietà della visualizzazione
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Casi d'uso comuni
- **Report per stakeholder:** Crea una visualizzazione che mostri solo le milestone di alto livello e le attività critiche.  
- **Allocazione risorse:** Crea una visualizzazione che elenchi le risorse insieme alle attività assegnate per verifiche rapide della capacità.  
- **Documenti pronti per la stampa:** Regola le impostazioni di pagina (come nel Passo 4) per generare snapshot di progetto stampabili.

## Suggerimenti per la risoluzione dei problemi
- **Visualizzazione non appare nel menu:** Verifica che `view.setShowInMenu(true)` sia chiamato prima del salvataggio.  
- **Colonne mancanti nella stampa:** Assicurati che `setFirstColumnsCount` corrisponda alle colonne necessarie e che `setPrintFirstColumnsCountOnAllPages(true)` sia abilitato.  
- **Eccezioni di licenza:** Se incontri errori di licenza, conferma che un file di licenza valido di Aspose.Tasks sia caricato prima di creare l'oggetto `Project`.

## Domande frequenti
### Q1: Posso personalizzare le visualizzazioni oltre i diagrammi di Gantt?
A: Sì, Aspose.Tasks per Java offre la flessibilità di personalizzare vari tipi di visualizzazioni oltre i diagrammi di Gantt, inclusi tabelle e grafici.

### Q2: Aspose.Tasks per Java è adatto a progetti su larga scala?
A: Assolutamente. La libreria è progettata per gestire progetti di qualsiasi dimensione, offrendo prestazioni robuste e una gestione efficiente della memoria.

### Q3: Aspose.Tasks per Java supporta l'esportazione delle visualizzazioni in diversi formati?
A: Sì, è possibile esportare le visualizzazioni in PDF, XLSX, HTML e altri formati, garantendo una condivisione fluida tra le piattaforme.

### Q4: Posso automatizzare la creazione di visualizzazioni personalizzate usando Aspose.Tasks per Java?
A: Certamente. L'API consente una piena automazione, permettendoti di generare e gestire programmaticamente visualizzazioni personalizzate.

### Q5: Esiste un forum della community per il supporto di Aspose.Tasks per Java?
A: Sì, puoi trovare assistenza e interagire con altri utenti nel [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per domande e discussioni relative a Java.

---

**Ultimo aggiornamento:** 2025-12-18  
**Testato con:** Aspose.Tasks for Java 24.12  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}