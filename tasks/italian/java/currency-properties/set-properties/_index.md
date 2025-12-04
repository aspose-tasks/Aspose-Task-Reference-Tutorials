---
date: 2025-12-04
description: Impara come impostare la valuta nei progetti Aspose.Tasks Java, incluso
  come cambiare la valuta e modificare il simbolo della valuta in Java. Manipola i
  file Microsoft Project senza sforzo.
language: it
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Come impostare la valuta nei progetti Aspose.Tasks – Guida Java
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la valuta nei progetti Aspose.Tasks – Guida Java

## Introduzione
In questo tutorial imparerai **come impostare la valuta** per un file Microsoft Project utilizzando l'Aspose.Tasks Java API. Che tu abbia bisogno di *modificare la valuta* per team internazionali o di regolare il *simbolo della valuta* in Java, i passaggi seguenti ti guideranno attraverso il processo con spiegazioni chiare e codice pronto all'uso.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Tasks for Java.  
- **Posso modificare il simbolo della valuta?** Sì – usa `CurrencySymbolPositionType` e `Prj.CURRENCY_SYMBOL`.  
- **Quali formati di file sono supportati?** XML, MPP e molti altri tramite `SaveFileFormat`.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza per la produzione.  
- **Quanto tempo richiede l'implementazione?** Circa 5‑10 minuti per una configurazione di base.

## Che cos’è la “valuta” in un file Project?
La valuta di un progetto definisce come vengono visualizzati i valori di costo—codice (ad es. `AUD`), numero di cifre decimali, simbolo (`$`) e posizione del simbolo. Impostare queste proprietà garantisce che ogni campo relativo ai costi (tariffe risorse, budget attività, ecc.) rifletta il formato monetario corretto per il tuo pubblico.

## Perché usare Aspose.Tasks per modificare la valuta?
- **Nessuna installazione di Microsoft Project necessaria** – manipola i file su qualsiasi server.  
- **Copertura completa dell'API** – tutti i campi relativi alla valuta sono esposti tramite le costanti `Prj`.  
- **Cross‑platform** – funziona su Windows, Linux e macOS con qualsiasi IDE compatibile con Java.  
- **Alte prestazioni** – elabora rapidamente file di progetto di grandi dimensioni in modo affidabile.

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
Qui è dove **impostare la valuta** includendo dettagli come codice, cifre decimali, simbolo e posizione del simbolo.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Suggerimento:** Se devi **modificare la valuta** per un progetto esistente, carica semplicemente il file con `new Project("file.mpp")` prima di applicare le impostazioni sopra.

### Passo 4: Salva il progetto aggiornato
Scrivi il progetto su disco nel formato desiderato. In questo esempio utilizziamo il formato XML, ma puoi anche scegliere `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 5: Conferma il successo
Stampa un messaggio amichevole così saprai che l'operazione è terminata senza errori.

```java
System.out.println("Process completed Successfully");
```

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **`NullPointerException` su `project.save`** | `dataDir` non è un percorso valido o non ha permessi di scrittura. | Verifica che la directory esista e che il processo Java abbia accesso in scrittura. |
| **Il simbolo della valuta non viene visualizzato** | La posizione del simbolo è impostata in modo errato per la tua locale. | Usa `CurrencySymbolPositionType.Before` se il simbolo deve precedere l'importo. |
| **Il file di progetto non si apre in MS Project** | Salvataggio in un formato più vecchio con impostazioni incompatibili. | Salva usando `SaveFileFormat.MPP` per piena compatibilità con le versioni recenti di MS Project. |

## Domande frequenti

**D: Posso impostare più valute in un unico progetto usando Aspose.Tasks?**  
R: Sì, Aspose.Tasks consente di gestire più valute all'interno di un singolo file di progetto impostando le proprietà della valuta a livello di risorsa o di attività.

**D: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?**  
R: Assolutamente. La libreria supporta file MPP da Project 2000 fino alle versioni più recenti, oltre a XML e altri formati.

**D: Aspose.Tasks offre supporto per formati di valuta personalizzati?**  
R: Sì, è possibile definire simboli personalizzati, cifre decimali e posizionamento per soddisfare qualsiasi requisito regionale.

**D: Posso integrare Aspose.Tasks con altre librerie o framework Java?**  
R: Certamente. L'API è puramente Java, quindi funziona senza problemi con Spring, Hibernate, Maven, Gradle e altri ecosistemi.

**D: Dove posso trovare supporto aggiuntivo o assistenza per Aspose.Tasks?**  
R: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per aiuto dalla community, o consulta la documentazione ufficiale per riferimenti API dettagliati.

## Conclusione
Ora sai **come impostare la valuta**, come **modificare i valori della valuta** e come **cambiare il simbolo della valuta in stile Java** usando Aspose.Tasks for Java. Queste funzionalità ti permettono di adattare i dati di costo per team globali, generare report specifici per locale e mantenere i tuoi file di progetto coerenti oltre i confini.

---

**Ultimo aggiornamento:** 2025-12-04  
**Testato con:** Aspose.Tasks for Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}