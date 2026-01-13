---
date: 2026-01-13
description: Scopri come iterare le risorse non radice nei file Microsoft Project
  utilizzando Aspose.Tasks per Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Iterare le risorse non radice con Aspose.Tasks per Java
url: /it/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Iterare le risorse non‑radice con Aspose.Tasks per Java

## Introduzione
Aspose.Tasks for Java è una libreria potente che offre agli sviluppatori un modo pulito e orientato agli oggetti per lavorare con i file Microsoft Project. In questo tutorial imparerai **come iterare le risorse non‑radice** così potrai leggere, modificare o analizzare i dati delle risorse senza dover gestire il segnaposto radice. Che tu stia costruendo uno strumento di reporting, uno script di migrazione o un pianificatore personalizzato, padroneggiare questa tecnica renderà il tuo codice più preciso ed efficiente.

## Risposte rapide
- **Cosa significa “risorsa non‑radice”?** Una risorsa che non è il segnaposto predefinito “Project” (il nodo radice).  
- **Perché filtrare la risorsa radice?** La radice non contiene dati di pianificazione utili e può ingombrare i report.  
- **Quale classe di Aspose.Tasks fornisce la collezione di risorse?** `Project.getResources()`.  
- **È necessaria una licenza per questo codice?** Una prova gratuita funziona per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso usarlo con Java 17?** Sì – Aspose.Tasks supporta Java 8 e versioni successive.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

1. **Java Development Kit (JDK)** – Installa l'ultima JDK dal [sito Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Libreria Aspose.Tasks per Java** – Scarica l'ultimo JAR dalla [pagina di download](https://releases.aspose.com/tasks/java/).  

## Importa i pacchetti
Nel tuo progetto Java, importa le classi Aspose.Tasks necessarie:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Passo 1: Configura la directory dei dati
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con il percorso assoluto dove risiedono i tuoi file `.mpp`.

## Passo 2: Carica il file di progetto
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Questo crea un'istanza `Project` caricando **ResourceCosts.mpp** dalla cartella specificata.

## Passo 3: Itera le risorse non‑radice
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Il ciclo attraversa ogni oggetto `Resource` nel progetto. Il controllo `isRoot()` salta la risorsa radice incorporata, e l'istruzione `System.out.println` stampa il nome di ogni **risorsa non‑radice**.

## Come iterare le risorse non‑radice
Il frammento sopra dimostra il modello di base:

1. Recupera l'intera collezione con `prj.getResources()`.  
2. Usa `isRoot()` per filtrare il segnaposto.  
3. Accedi a qualsiasi campo della risorsa (ad es., `Rsc.NAME`, `Rsc.COST`) secondo necessità.

Puoi estendere questo modello per aggregare i costi, esportare in CSV o applicare regole di business personalizzate.

## Problemi comuni e suggerimenti
- **Controlli null** – Alcune risorse possono avere campi opzionali; verifica sempre `null` quando chiami `get()`.  
- **Prestazioni** – Per progetti molto grandi, considera di iterare con un ciclo basato su indice per evitare la creazione di collezioni intermedie.  
- **Licenza** – Eseguire il codice senza una licenza valida aggiungerà una filigrana ai file esportati; assicurati di attivare la licenza all'inizio dell'applicazione.

## Conclusione
Seguendo questi passaggi ora sai **come iterare le risorse non‑radice** usando Aspose.Tasks per Java. Questa tecnica ti aiuta a concentrarti sulle risorse reali del progetto, a pulire le estrazioni di dati e a costruire soluzioni di project‑management più affidabili.

## FAQ's
### Posso usare Aspose.Tasks per Java per creare nuovi file di progetto?
Sì, Aspose.Tasks fornisce funzionalità CRUD (Create, Read, Update, Delete) complete per i formati di progetto MPP, MPT e XML.  

### Il supporto di Aspose.Tasks copre tutte le versioni dei file Microsoft Project?
Assolutamente. Gestisce i file Project 2003‑2019, incluse le specifiche più recenti di MPP.  

### È Aspose.Tasks compatibile con framework Java come Spring?
Sì, puoi iniettare la libreria nei bean Spring o usarla in qualsiasi applicazione Java standard.  

### Posso personalizzare i campi dei dati di progetto usando Aspose.Tasks?
Certamente. L'API ti permette di aggiungere, modificare o eliminare campi personalizzati su attività, risorse e assegnazioni.  

### Fornisce Aspose.Tasks supporto e documentazione per gli sviluppatori?
Il prodotto include documentazione API completa, esempi di codice e un forum di supporto dedicato per assistenza rapida.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose