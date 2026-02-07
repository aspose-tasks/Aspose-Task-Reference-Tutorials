---
date: 2026-02-07
description: Scopri come impostare il codice valuta Java nei progetti Aspose.Tasks,
  cambiare il simbolo della valuta e applicare un formato valuta personalizzato per
  i file Microsoft Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: codice valuta java – Come impostare nei progetti Aspose.Tasks
url: /it/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare il codice valuta in Aspose.Tasks – Guida Java

## Introduzione
In questo tutorial imparerai **come impostare il codice valuta java** per un file Microsoft Project utilizzando l'API Java di Aspose.Tasks. Che tu abbia bisogno di *modificare la valuta* per team internazionali, regolare il *simbolo della valuta*, o applicare un **formato valuta personalizzato**, i passaggi seguenti ti guideranno attraverso il processo con spiegazioni chiare e codice pronto all'uso.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Tasks for Java.  
- **Posso cambiare il simbolo della valuta?** Sì – usa `CurrencySymbolPositionType` e `Prj.CURRENCY_SYMBOL`.  
- **Quali formati di file sono supportati?** XML, MPP e molti altri tramite `SaveFileFormat`.  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita funziona per i test; è necessaria una licenza per la produzione.  
- **Quanto tempo richiede l'implementazione?** Circa 5‑10 minuti per una configurazione di base.

## Come impostare il codice valuta Java in Aspose.Tasks
La valuta di un progetto definisce come vengono visualizzati i valori di costo — codice (ad es., `AUD`), numero di cifre decimali, simbolo (`$`) e posizione del simbolo. Impostare queste proprietà garantisce che ogni campo relativo ai costi (tariffe delle risorse, budget delle attività, ecc.) rifletta il formato monetario corretto per il tuo pubblico.

## Perché usare Aspose.Tasks per cambiare la valuta?
- **Nessuna installazione di Microsoft Project necessaria** – manipola i file su qualsiasi server.  
- **Copertura completa dell'API** – tutti i campi relativi alla valuta sono esposti tramite le costanti `Prj`.  
- **Cross‑platform** – funziona su Windows, Linux e macOS con qualsiasi IDE compatibile con Java.  
- **Alte prestazioni** – elabora rapidamente e in modo affidabile file di progetto di grandi dimensioni.  
- **Supporta formati valuta personalizzati** – puoi definire simboli, cifre decimali e posizionamento per corrispondere agli standard regionali.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – versione 8 o superiore.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dalla [pagina di download di Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – Eclipse, IntelliJ IDEA o qualsiasi editor tu preferisca.  
4. **Una cartella scrivibile** – dove verrà salvato il file di progetto generato.

## Importa i pacchetti
Per prima cosa, importa le classi che forniscono l'accesso alle proprietà del progetto e alla gestione dei file.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Guida passo‑passo

### Passo 1: Definisci la directory dei dati
Specifica la cartella che contiene i tuoi file sorgente e dove verrà scritto l'output.

```java
String dataDir = "Your Data Directory";
```

### Passo 2: Crea una nuova istanza di Project
Istanzia un nuovo oggetto `Project`. Questo oggetto rappresenta un file Microsoft Project in memoria.

```java
Project project = new Project();
```

### Passo 3: Imposta le proprietà della valuta
Qui è dove **impostiamo il codice valuta** dettagli come codice, cifre decimali, simbolo e posizione del simbolo.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Suggerimento professionale:** Se devi **cambiare la valuta del progetto** per un file esistente, caricalo semplicemente con `new Project("file.mpp")` prima di applicare le impostazioni sopra.

### Passo 4: Salva il progetto aggiornato
Scrivi il progetto nuovamente su disco nel formato desiderato. In questo esempio usiamo il formato XML, ma puoi anche scegliere `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Passo 5: Conferma il successo
Stampa un messaggio amichevole così sai che l'operazione è stata completata senza errori.

```java
System.out.println("Process completed Successfully");
```

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **`NullPointerException` on `project.save`** | `dataDir` non è un percorso valido o non ha i permessi di scrittura. | Assicurati che la directory esista e che il tuo processo Java abbia i permessi di scrittura. |
| **Currency symbol not showing** | La posizione del simbolo è impostata in modo errato per la tua locale. | Usa `CurrencySymbolPositionType.Before` se il simbolo deve precedere l'importo. |
| **Project file does not open in MS Project** | Salvataggio in un formato più vecchio con impostazioni incompatibili. | Salva usando `SaveFileFormat.MPP` per piena compatibilità con le versioni recenti di MS Project. |

## Domande frequenti

**D: Posso impostare più valute in un singolo progetto usando Aspose.Tasks?**  
R: Sì, Aspose.Tasks consente di gestire più valute all'interno di un unico file di progetto impostando le proprietà della valuta per risorsa o per attività.

**D: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?**  
R: Assolutamente. La libreria supporta file MPP da Project 2000 fino alle ultime versioni, così come XML e altri formati.

**D: Aspose.Tasks fornisce supporto per formati valuta personalizzati?**  
R: Sì, puoi definire simboli personalizzati, cifre decimali e posizionamento per soddisfare qualsiasi requisito regionale.

**D: Posso integrare Aspose.Tasks con altre librerie o framework Java?**  
R: Certamente. L'API è pura Java, quindi funziona senza problemi con Spring, Hibernate, Maven, Gradle e altri ecosistemi.

**D: Dove posso trovare supporto o assistenza aggiuntiva per Aspose.Tasks?**  
R: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per l'aiuto della community, o consulta la documentazione ufficiale per riferimenti API dettagliati.

## Conclusione
Ora sai **come impostare il codice valuta java**, come **cambiare i valori della valuta** e come **cambiare il simbolo della valuta** usando Aspose.Tasks per Java. Queste funzionalità ti permettono di personalizzare i dati di costo per team globali, generare report specifici per locale e mantenere i tuoi file di progetto coerenti attraverso i confini.

---

**Ultimo aggiornamento:** 2026-02-07  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}