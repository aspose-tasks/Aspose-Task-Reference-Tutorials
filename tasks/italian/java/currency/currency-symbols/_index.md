---
date: 2026-09-20
description: Scopri come estrarre il simbolo di valuta mpp e aggiornare le proprietà
  del progetto usando Aspose.Tasks per Java. Modifica e recupera il simbolo in poche
  righe di codice.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Estrai il simbolo di valuta mpp usando Aspose.Tasks per Java
og_description: Scopri come estrarre il simbolo di valuta mpp e aggiornare le proprietà
  del progetto usando Aspose.Tasks per Java. Rapido, affidabile e pronto per la produzione.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Come estrarre il simbolo di valuta mpp con Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Come estrarre il simbolo di valuta mpp con Aspose.Tasks Java
url: /it/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estrai il simbolo della valuta mpp usando Aspose.Tasks per Java

## Introduzione
Nella presente guida imparerai a lavorare con **java project properties** — in particolare come **extract currency symbol mpp** da un file Microsoft Project (MPP) e come **change currency symbol java** o **retrieve currency symbol java** utilizzando la libreria Aspose.Tasks. Che tu stia costruendo uno strumento di reporting finanziario, integrando i dati di Project in un sistema ERP, o semplicemente abbia bisogno di mostrare il simbolo di valuta corretto nella tua interfaccia, padroneggiare questo piccolo ma essenziale compito renderà le tue applicazioni Java più robuste e user‑friendly.

## Risposte rapide
- **Cosa significa “extract currency symbol mpp”?** Significa leggere il simbolo di valuta memorizzato in un file MPP (Microsoft Project).  
- **Quale libreria gestisce questo?** Aspose.Tasks for Java fornisce una semplice API per il compito.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quanto tempo ci vuole?** Con il codice qui sotto, puoi ottenere il simbolo in meno di un minuto.  
- **Posso anche modificare il simbolo?** Sì – puoi impostare un nuovo valore usando la stessa proprietà `Prj.CURRENCY_SYMBOL`.

## Cos'è “extract currency symbol mpp”?
Estrarre il simbolo della valuta da un file MPP significa leggere la stringa a singolo carattere che Microsoft Project memorizza nell'intestazione del file per rappresentare l'unità monetaria del progetto. Questa operazione ti consente di visualizzare il simbolo corretto (come $, €, £) nelle tue applicazioni senza codificare un valore in modo fisso.

## Perché aggiornare il simbolo della valuta nelle proprietà del progetto Java?
Aggiornare il simbolo della valuta ti consente di localizzare report, fatture e dashboard al volo. Le aziende che gestiscono progetti in diverse regioni possono cambiare il simbolo in un unico passaggio, evitando la necessità di duplicare l'intero file di progetto. Aspose.Tasks può modificare la proprietà in memoria e salvare nuovamente il file, supportando progetti con fino a 2.000 attività senza un impatto di prestazioni evidente.

## Prerequisiti
1. **Java Development Kit (JDK)** – versione 8 o superiore.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dalla [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Un file **project.mpp** valido collocato in una cartella a cui puoi fare riferimento dal tuo codice.

## Importa i pacchetti
Per prima cosa, importa le classi di cui avremo bisogno per lavorare con i file Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Passo 1: definisci la directory dei dati
Indica all'applicazione dove si trova il tuo file *.mpp*.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Usa `System.getProperty("user.dir")` per costruire un percorso assoluto che funzioni su qualsiasi macchina.

## Passo 2: carica il file MS Project
`Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta in memoria un singolo file Microsoft Project. Creare questo oggetto carica la struttura del file senza richiedere l'installazione di Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Passo 3: recupera (e opzionalmente modifica) il simbolo della valuta
`Prj.CURRENCY_SYMBOL` è la chiave di proprietà che memorizza il simbolo della valuta. Leggerla restituisce il simbolo corrente; assegnare una nuova stringa aggiorna la definizione della valuta del progetto.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

La chiamata `System.out.println` stampa il simbolo (ad es., `$`) sulla console, confermando che l'estrazione è riuscita.

## Problemi comuni e come risolverli
| Sintomo | Causa probabile | Soluzione |
|---------|----------------|-----------|
| `NullPointerException` su `project.get(...)` | Percorso file errato o file non trovato | Verifica `dataDir` e il nome del file; usa `new File(dataDir).exists()` per il debug |
| Simbolo inaspettato (ad es., `?`) | Progetto creato con una locale non standard | Assicurati che il file MPP di origine definisca effettivamente un simbolo di valuta; puoi impostarne uno programmaticamente come mostrato sopra |
| Errore di licenza | Uso della versione di prova senza un file di licenza valido | Carica la tua licenza con `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` prima di creare l'oggetto `Project` |

## Domande frequenti

**Q: Posso manipolare altri attributi del progetto oltre ai simboli di valuta usando Aspose.Tasks?**  
A: Sì, Aspose.Tasks ti consente di modificare attività, risorse, assegnazioni, calendari e molte altre proprietà del progetto.

**Q: Aspose.Tasks è compatibile con diverse versioni di file MS Project?**  
A: Assolutamente. Supporta i formati MPP, MPT e XML da Project 98 fino alle ultime versioni.

**Q: Aspose.Tasks offre documentazione e supporto per gli sviluppatori?**  
A: Documentazione API completa, esempi di codice e un forum di supporto dedicato sono disponibili sul sito web di Aspose.Tasks.

**Q: Posso provare Aspose.Tasks prima di acquistarlo?**  
A: Sì – una versione di prova completamente funzionale può essere scaricata dal [sito Aspose](https://purchase.aspose.com/buy).

**Q: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
A: Le licenze temporanee sono disponibili sulla [pagina di licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/) per scopi di valutazione.

---

**Ultimo aggiornamento:** 2026-09-20  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose

## Tutorial correlati

- [Project Properties Java – Read Metadata with Aspose.Tasks](/tasks/java/project-properties/)
- [How to Retrieve Currency from MS Project with Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}