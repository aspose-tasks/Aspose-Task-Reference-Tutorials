---
date: 2026-09-09
description: Scopri come cambiare il simbolo della valuta nei progetti Aspose.Tasks
  Java, impostare i codici valuta, regolare i simboli e applicare formati personalizzati
  per i file Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Imposta le proprietà della valuta nei progetti Aspose.Tasks
og_description: Come cambiare il simbolo della valuta in Aspose.Tasks usando Java.
  Scopri istruzioni passo‑passo, requisiti e consigli per personalizzare la formattazione
  dei costi del progetto.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Come cambiare il simbolo della valuta in Aspose.Tasks – Guida Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Come cambiare il simbolo della valuta nei progetti Aspose.Tasks – Guida Java
url: /it/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come modificare il simbolo della valuta in Aspose.Tasks – Guida Java

## Introduzione
In questo tutorial imparerai **come modificare il simbolo della valuta** per un file Microsoft Project utilizzando l'Aspose.Tasks Java API. Che tu stia preparando report per un cliente estero, consolidando budget tra più regioni, o semplicemente debba adeguare gli standard contabili della tua azienda, la regolazione del simbolo della valuta garantisce che ogni campo relativo ai costi mostri il segno monetario corretto. La guida illustra ogni passaggio, dalla configurazione dell'ambiente di sviluppo al salvataggio delle modifiche in un file di progetto nuovo o esistente.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Tasks per Java.  
- **Posso modificare il simbolo della valuta?** Sì – impostare `Prj.CURRENCY_SYMBOL` e scegliere `CurrencySymbolPositionType`.  
- **Quali formati di file sono supportati?** XML, MPP e molti altri tramite `SaveFileFormat`.  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è necessaria una licenza per la produzione.  
- **Quanto tempo richiede l'implementazione?** Circa 5‑10 minuti per una configurazione di base.

## Come modificare il simbolo della valuta in Aspose.Tasks usando Java?
Carica il progetto di destinazione (o creane uno nuovo), imposta le proprietà della valuta desiderate e salva il file. L'intera operazione consiste in tre chiamate API: creare o caricare un oggetto `Project`, assegnare il codice, il simbolo e la posizione della valuta, quindi invocare `project.save`. Questo approccio funziona sia per progetti nuovi sia per file esistenti senza richiedere l'installazione di Microsoft Project.

## Perché usare Aspose.Tasks per modificare la valuta?
Aspose.Tasks fornisce **copertura API completa per oltre 30 proprietà correlate alla valuta**, consentendoti di definire codice, simbolo, cifre decimali e posizionamento in un unico luogo. La libreria elabora file Project di centinaia di pagine in meno di un secondo su hardware server tipico e funziona su Windows, Linux e macOS senza dipendenze aggiuntive.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK) 8 o superiore** – l'API richiede almeno JDK 8.  
2. **Aspose.Tasks per Java** – scarica l'ultimo JAR dalla [pagina di download di Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – Eclipse, IntelliJ IDEA o qualsiasi editor che supporti Java.  
4. **Una cartella scrivibile** – dove verrà salvato il file di progetto generato.

## Importare i pacchetti
Le classi seguenti ti danno accesso alle proprietà del progetto, alla gestione dei file e alle impostazioni della valuta.  

`Project` – rappresenta un file Microsoft Project in memoria.  
`Prj` – contiene costanti per tutte le proprietà a livello di progetto, inclusi i campi della valuta.  
`CurrencySymbolPositionType` – enumera le possibili posizioni per il simbolo della valuta (prima o dopo l'importo).  

Queste importazioni sono necessarie prima che qualsiasi codice possa manipolare un progetto.

## Guida passo‑passo

### Passo 1: Definire la directory dei dati
Scegli una cartella che contiene i tuoi file sorgente e dove verrà scritto l'output. Assicurati che la directory esista e che il tuo processo Java abbia i permessi di scrittura.

### Passo 2: Creare una nuova istanza di progetto
La classe `Project` è l'oggetto di livello superiore di Aspose.Tasks che rappresenta un singolo file Project in memoria. Istanziandola si crea un progetto vuoto pronto per la configurazione.

### Passo 3: Impostare le proprietà della valuta
Qui configuri il codice della valuta, il numero di cifre decimali, il simbolo stesso e la posizione del simbolo.  

- **Codice valuta** – un codice ISO 4217 a tre lettere, ad esempio `AUD` o `USD`.  
- **Cifre decimali** – tipicamente 2 per la maggior parte delle valute.  
- **Simbolo della valuta** – il carattere o la stringa visualizzata con gli importi, ad esempio `$` o `€`.  
- **Posizione del simbolo** – `CurrencySymbolPositionType.Before` posiziona il simbolo prima del numero; `After` lo posiziona dopo.  

Queste impostazioni influenzano ogni campo relativo ai costi (tariffe risorse, budget attività, ecc.) nel progetto.

> **Consiglio professionale:** se devi modificare la valuta per un file esistente, caricalo con `new Project("file.mpp")` prima di applicare le impostazioni sopra.

### Passo 4: Salvare il progetto aggiornato
Scrivi il progetto su disco usando il formato desiderato. Il formato XML è leggibile dall'uomo, mentre `SaveFileFormat.MPP` preserva la piena compatibilità con Microsoft Project.

### Passo 5: Confermare il successo
Stampa un breve messaggio o una voce di log così sai che l'operazione è terminata senza errori. Questo è particolarmente utile nelle pipeline automatizzate.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **`NullPointerException` su `project.save`** | `dataDir` non è un percorso valido o non ha i permessi di scrittura. | Assicurati che la directory esista e che il tuo processo Java abbia accesso in scrittura. |
| **Il simbolo della valuta non viene visualizzato** | La posizione del simbolo è impostata in modo errato per la tua locale. | Usa `CurrencySymbolPositionType.Before` se il simbolo deve precedere l'importo. |
| **Il file di progetto non si apre in MS Project** | Salvataggio in un formato più vecchio con impostazioni incompatibili. | Salva usando `SaveFileFormat.MPP` per piena compatibilità con le versioni recenti di MS Project. |

## Domande frequenti

**D: Posso impostare più valute in un singolo progetto usando Aspose.Tasks?**  
R: Sì, puoi assegnare impostazioni di valuta diverse a risorse o attività individuali modificando i rispettivi campi di costo dopo aver definito la valuta a livello di progetto.

**D: Aspose.Tasks è compatibile con diverse versioni di file Microsoft Project?**  
R: Assolutamente. La libreria supporta file MPP da Project 2000 fino alle ultime versioni, oltre a XML e altri formati di interscambio.

**D: Aspose.Tasks offre supporto per formati di valuta personalizzati?**  
R: Sì, puoi definire simboli personalizzati, cifre decimali e posizionamento per soddisfare qualsiasi requisito regionale, e queste impostazioni vengono salvate nel file.

**D: Posso integrare Aspose.Tasks con altri framework Java?**  
R: Certamente. L'API è pure Java, quindi funziona senza problemi con Spring, Hibernate, Maven, Gradle e altri ecosistemi.

**D: Dove posso trovare ulteriore assistenza o esempi?**  
R: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assistenza della community, o consulta la documentazione ufficiale per riferimenti API dettagliati.

## Conclusione
Ora sai **come modificare il simbolo della valuta** nei progetti Aspose.Tasks usando Java, come impostare il codice della valuta, regolare le cifre decimali e applicare un simbolo personalizzato. Queste funzionalità ti consentono di generare report di costo specifici per locale, allineare i budget di progetto agli standard contabili regionali e mantenere i file Microsoft Project coerenti tra team globali.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Tutorial correlati

- [proprietà del progetto Java – Estrarre il simbolo della valuta da MPP usando Aspose.Tasks per Java](/tasks/java/currency/currency-symbols/)
- [Leggere le proprietà della valuta Java con progetti Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Gestire i codici valuta Java con Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}