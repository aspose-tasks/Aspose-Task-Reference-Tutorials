---
date: 2026-09-25
description: Scopri come recuperare i codici valuta dai file MS Project utilizzando
  Aspose.Tasks per Java – il modo rapido per ottenere il codice valuta di cui hanno
  bisogno gli sviluppatori Java.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Gestisci i codici valuta in Aspose.Tasks
og_description: Recupera il codice valuta Java dai file MS Project utilizzando Aspose.Tasks.
  Questa guida ti mostra come leggere il progetto, estrarre l'identificatore di valuta
  ISO e applicarlo nelle applicazioni Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Recupera il codice valuta Java da MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Recupera il codice valuta Java da MS Project con Aspose.Tasks
url: /it/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperare il codice valuta Java da MS Project con Aspose.Tasks

## Introduzione
In questo tutorial imparerai **come recuperare il codice valuta Java** da un file MS Project utilizzando l'Aspose.Tasks Java API. Che tu debba generare report finanziari multi‑valuta, consolidare progetti in diverse regioni, o semplicemente visualizzare il simbolo monetario corretto in un sistema a valle, i passaggi seguenti ti guideranno dalla configurazione dell'ambiente alla chiamata a riga singola che restituisce l'identificatore ISO della valuta. Alla fine della guida sarai in grado di caricare qualsiasi formato di file Project supportato ed estrarre il codice valuta a tre lettere come `USD`, `EUR` o `GBP`.

## Risposte rapide
- **Che cosa fa l'API?** Legge i file MS Project e espone proprietà come il codice valuta.  
- **Quale linguaggio è usato?** Java, tramite la libreria Aspose.Tasks per Java.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso recuperare il codice in una sola riga?** Sì—`prj.get(Prj.CURRENCY_CODE)` restituisce immediatamente la stringa del codice valuta.  
- **È compatibile con tutte le versioni di Project?** Aspose.Tasks supporta più di 20 formati di input, inclusi MPP legacy, XML e file XER.

## Che cosa significa leggere un file MS Project?
Leggere un file MS Project significa aprire programmaticamente un *.mpp* (o qualsiasi altro formato supportato come XML o XER) e accedere alle sue strutture dati interne. Queste strutture includono attività, risorse, calendari, tabelle dei costi e impostazioni finanziarie. Analizzando il file è possibile estrarre informazioni senza avviare Microsoft Project, abilitando flussi di lavoro automatizzati di reporting, migrazione e integrazione.

## Perché utilizzare Aspose.Tasks per leggere file MS Project?
Aspose.Tasks offre una soluzione pure‑Java che elimina la necessità di interop COM o di un'installazione locale di Microsoft Project. Supporta più di 20 formati di file, può gestire progetti con migliaia di attività consumando meno di 100 MB di memoria, e fornisce un ricco modello a oggetti. L'accesso diretto a costanti come `Prj.CURRENCY_CODE` consente di recuperare le informazioni sulla valuta in modo immediato e affidabile.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere quanto segue:

### Java Development Kit (JDK) installato
È richiesto un JDK recente (11 o successivo). Scaricalo dal sito ufficiale di Oracle: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Libreria Aspose.Tasks per Java
Ottieni gli ultimi binari di Aspose.Tasks per Java e aggiungili al classpath del tuo progetto. La documentazione completa e i link per il download sono disponibili [here](https://reference.aspose.com/tasks/java/).

## Importare i pacchetti
La classe `Project` e le costanti `Prj` si trovano nello spazio dei nomi `com.aspose.tasks`. Importale all'inizio del tuo file sorgente Java:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Guida passo‑passo

### Passo 1: impostare la directory dei dati
Definisci la cartella che contiene il tuo file *.mpp*. Regola il percorso per corrispondere al tuo ambiente in modo che il runtime possa individuare il file di progetto.

```java
String dataDir = "Your Data Directory";
```

### Passo 2: caricare il file di progetto
La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file MS Project in memoria. Creare un'istanza legge il file e costruisce un modello in‑memory che puoi interrogare.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Passo 3: recuperare il codice valuta
La costante `Prj.CURRENCY_CODE` identifica la proprietà che memorizza l'identificatore ISO della valuta. Chiamando `prj.get(Prj.CURRENCY_CODE)` ottieni il codice a tre lettere in un'unica operazione.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
L'output sarà il codice ISO a tre lettere (ad esempio, `USD`, `EUR`, `GBP`) configurato per il progetto.

### Passo 4: come recuperare il codice valuta in Java (contesto aggiuntivo)
Carica il tuo progetto, chiama `prj.get(Prj.CURRENCY_CODE)` e memorizza il risultato in una `String`. Puoi quindi passare questo valore a qualsiasi servizio finanziario, motore di reporting o componente UI che richieda un identificatore di valuta.

### Passo 5: (opzionale) utilizzare il codice valuta
Tipici scenari a valle includono:

- **Generazione di report** – anteporre il codice alle colonne di costo (`USD 1,200`).  
- **Integrazione API** – inviare il codice ISO ai gateway di pagamento che richiedono un parametro valuta.  
- **Consolidamento dati** – raggruppare più progetti per valuta per analisi a livello di portafoglio.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Output nullo** | Il file di progetto non definisce una valuta (il valore predefinito è vuoto). | Imposta la valuta in Microsoft Project o assegnala tramite `prj.set(Prj.CURRENCY_CODE, "USD");` prima della lettura. |
| **File non trovato** | Percorso `dataDir` errato. | Verifica il percorso e assicurati che il nome del file corrisponda esattamente, inclusa la sensibilità al maiuscolo/minuscolo. |
| **Versione file non supportata** | File *.mpp* molto vecchio o corrotto. | Aggiorna alla versione più recente di Aspose.Tasks o converti il file in un formato più recente in Microsoft Project prima. |

## Domande frequenti

**D: Aspose.Tasks può gestire strutture di progetto complesse?**  
R: Sì, l'API legge gerarchie di attività multi‑livello, pool di risorse, campi personalizzati e calendari senza limitazioni.

**D: Aspose.Tasks è compatibile con diverse versioni dei file MS Project?**  
R: Assolutamente. Supporta MPP, XML, XER e altri formati da Project 98 fino alle ultime versioni di Office.

**D: Aspose.Tasks fornisce documentazione e supporto?**  
R: Riferimento API completo, esempi di codice e supporto tecnico dedicato sono disponibili sul sito web di Aspose.

**D: Posso provare Aspose.Tasks prima di acquistarlo?**  
R: È offerta una versione di prova gratuita così da poter valutare tutte le funzionalità, incluso l'estrazione del codice valuta.

**D: Dove posso ottenere una licenza temporanea per la valutazione?**  
R: Licenze temporanee sono disponibili dal [website](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-09-25  
**Testato con:** Aspose.Tasks per Java (ultima versione)  
**Autore:** Aspose

## Tutorial correlati

- [Proprietà del progetto Java – Leggere i metadati con Aspose.Tasks](/tasks/java/project-properties/)
- [Come leggere le informazioni del progetto da Microsoft Project con Aspose.Tasks per Java](/tasks/java/project-properties/read-project-info/)
- [Recuperare i codici di outline di MS Project in Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}