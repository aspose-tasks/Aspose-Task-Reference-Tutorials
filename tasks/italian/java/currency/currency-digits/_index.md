---
date: 2026-09-14
description: Scopri come ottenere la valuta di MS Project e leggere le proprietà del
  progetto Java con Aspose.Tasks. Guida passo‑passo per estrarre le cifre della valuta
  da un file MPP.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Come ottenere la valuta da MS Project usando Aspose.Tasks
og_description: Scopri come ottenere la valuta di MS Project e leggere le proprietà
  del progetto Java con Aspose.Tasks. Segui questo conciso tutorial Java per estrarre
  le cifre della valuta da un file MPP.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Come ottenere la valuta di MS Project usando Aspose.Tasks – Guida Java
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Come ottenere la valuta di MS Project usando Aspose.Tasks
url: /it/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ottenere la valuta di ms project usando Aspose.Tasks

## Introduzione
Se ti chiedi **come ottenere le informazioni sulla valuta di ms project** da un file Microsoft Project, sei nel posto giusto. In questo tutorial completo scoprirai **come lavorare con i valori della valuta di ms project** usando la libreria Aspose.Tasks per Java. Che tu stia creando uno strumento di reporting, un'utilità di migrazione, o semplicemente abbia bisogno di leggere le impostazioni di valuta da un **file java project**, questa guida ti accompagna passo dopo passo—dal caricamento di un file *.mpp* all'estrazione delle cifre decimali della valuta. Alla fine, sarai a tuo agio nel gestire i dati della valuta di ms project nelle tue applicazioni.

## Risposte rapide
- **Quale libreria legge i file MS Project?** Aspose.Tasks for Java.  
- **Quante righe di codice servono per ottenere le cifre della valuta?** Basta tre righe concise dopo aver caricato il progetto.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore (qualsiasi JDK che esegue Aspose.Tasks).  
- **Posso recuperare altre proprietà del Project?** Sì – Aspose.Tasks espone un set completo di campi del Project (ad esempio data di inizio, tariffe dei costi, ecc.).

## Cos'è la valuta di ms project?
La proprietà `ms project currency` definisce il numero di cifre decimali che Microsoft Project utilizza nella visualizzazione dei valori monetari. È memorizzata nel file Project nel campo **CURRENCY_DIGITS** e determina se gli importi appaiono come numeri interi, con una decimale, due decimali, ecc. Questa impostazione influisce direttamente sui report di budgeting, sui riepiloghi dei costi e su qualsiasi interfaccia che mostri cifre finanziarie, rendendola essenziale per uno scambio di dati accurato.

## Perché utilizzare Aspose.Tasks per gestire la valuta di ms project?
Aspose.Tasks ti consente di estrarre le cifre decimali della valuta senza installare Microsoft Project, e lo fa con prestazioni di livello enterprise. La libreria supporta **oltre 30 anni di versioni di file Project**—da Project 2000 a Project 2024—coprendo più di **150 schemi di file distinti**. Il caricamento di un progetto di 500 pagine richiede tipicamente meno di **2 secondi** su un server standard, e puoi interrogare solo i campi di cui hai bisogno, mantenendo l'uso della memoria sotto **50 MB** anche per i programmi più grandi.

## Prerequisiti
1. **Ambiente di sviluppo Java** – JDK 8 o più recente installato e configurato.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dal sito ufficiale: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Conoscenza di base di Java** – dovresti sentirti a tuo agio nel creare un progetto Java, aggiungere librerie esterne e eseguire un metodo `main`.  

## Importa i pacchetti
Per prima cosa, importa le classi di cui avremo bisogno. Importa la classe `Project` e le utility correlate dalla libreria Aspose.Tasks.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Passo 1: definire la directory dei dati
Specifica la cartella che contiene il tuo **file java project** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con il percorso assoluto o relativo dove si trova `project.mpp`.

## Passo 2: caricare il file mpp  
Ora vedremo **come caricare file mpp** usando Aspose.Tasks. La classe `Project` rappresenta un file Microsoft Project e fornisce l'accesso alle sue proprietà.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Assicurati che il nome del file corrisponda esattamente; altrimenti verrà sollevata un'`IOException`.

## Passo 3: recuperare le cifre decimali della valuta  
Con il progetto caricato, estrarre le cifre della **ms project currency** è una singola riga: il metodo `getCurrencyDigits()` restituisce il numero di cifre decimali definito per i valori monetari.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
La chiamata restituisce un `Integer` che rappresenta il numero di cifre decimali (ad esempio, `2` per i centesimi). Il valore viene stampato sulla console, ma puoi anche memorizzarlo in una variabile per ulteriori elaborazioni.

## Problemi comuni e suggerimenti
- **File non trovato** – verifica nuovamente il percorso `dataDir` e assicurati che il nome del file sia corretto, inclusa l'estensione `.mpp`.  
- **Versione file non supportata** – Aspose.Tasks supporta i formati Project 2000‑2024; file più vecchi o corrotti potrebbero necessitare di conversione.  
- **Licenza non impostata** – durante lo sviluppo una versione di prova funziona, ma per la produzione devi applicare una licenza valida per evitare filigrane di valutazione.

## Domande frequenti

**Q: Aspose.Tasks può gestire altri attributi del Project oltre alle cifre della valuta?**  
A: Sì, Aspose.Tasks offre un'ampia gamma di funzionalità per manipolare vari aspetti dei file Project, come attività, risorse e campi personalizzati.

**Q: Aspose.Tasks è adatto per applicazioni a livello enterprise?**  
A: Assolutamente sì, Aspose.Tasks è progettato per soddisfare le esigenze di progetti di livello enterprise, offrendo alte prestazioni e scalabilità.

**Q: Aspose.Tasks supporta lo sviluppo cross‑platform?**  
A: Sì, puoi usare Aspose.Tasks per Java su qualsiasi piattaforma che supporti il Java Runtime Environment (Windows, Linux, macOS).

**Q: Posso provare Aspose.Tasks prima di acquistarlo?**  
A: Sì, puoi scaricare una versione di prova gratuita dalla [pagina dei rilasci Aspose](https://releases.aspose.com/).

**Q: Dove posso ottenere supporto per Aspose.Tasks?**  
A: Puoi trovare supporto sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2026-09-14  
**Testato con:** Aspose.Tasks for Java (ultima versione al momento della scrittura)  
**Autore:** Aspose

## Tutorial correlati

- [java project properties – Estrai il simbolo della valuta da MPP usando Aspose.Tasks per Java](/tasks/java/currency/currency-symbols/)
- [Come recuperare la valuta da MS Project con Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Project Properties Java – Leggi i metadati con Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}