---
date: 2026-02-10
description: Scopri come recuperare i codici di valuta dai file MS Project usando
  Aspose.Tasks per Java – il modo rapido per ottenere il codice di valuta di cui hanno
  bisogno gli sviluppatori Java.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come recuperare la valuta da MS Project con Aspose.Tasks
url: /it/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come recuperare la valuta da MS Project con Aspose.Tasks

## Introduzione
Benvenuti! In questo tutorial scoprirete **come recuperare i codici di valuta** da un file MS Project utilizzando l'API Aspose.Tasks per Java. Che stiate generando report finanziari multivaluta, consolidando progetti da diverse regioni, o semplicemente abbiate bisogno dei simboli monetari corretti per l'elaborazione successiva, questa guida vi accompagna passo passo—dalla configurazione dell'ambiente all'estrazione programmatica del codice di valuta. Alla fine, sarete a vostro agio nella lettura dei file MS Project e nell'uso della chiamata **get currency code java** per ottenere l'identificatore ISO della valuta.

## Risposte rapide
- **Cosa fa l'API?** Legge i file MS Project ed espone proprietà come il codice di valuta.  
- **Quale linguaggio viene usato?** Java, tramite la libreria Aspose.Tasks per Java.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; per la produzione è richiesta una licenza commerciale.  
- **Posso recuperare il codice in una sola riga?** Sì—`prj.get(Prj.CURRENCY_CODE)` restituisce la stringa del codice di valuta.  
- **È compatibile con tutte le versioni di Project?** Aspose.Tasks supporta sia i formati più vecchi (MPP) sia quelli più recenti (XML, XER).

## Che cosa è **read ms project file**?
Leggere un file MS Project significa aprire programmaticamente un documento *.mpp* (o altro formato supportato) e accedere alle sue strutture dati—attività, risorse, calendari e impostazioni finanziarie—senza interagire manualmente con Microsoft Project.

## Perché usare Aspose.Tasks per **read msproject** file?
- **Supporto completo dei formati** – funziona con file da Project 98 fino alle ultime versioni di Office.  
- **Nessun COM o installazione di Office necessaria** – puro Java, perfetto per l'automazione lato server.  
- **API ricca** – fornisce accesso diretto a proprietà come `Prj.CURRENCY_CODE`, permettendovi di **how to retrieve currency** istantaneamente.  
- **Prestazioni** – parsing leggero, ideale per l'elaborazione batch di molti progetti.

## Prerequisiti
Prima di immergerci nel codice, assicuratevi di avere quanto segue:

### Java Development Kit (JDK) installato
Verificate che un JDK recente sia disponibile sulla vostra macchina. Potete scaricare e installare l'ultima versione del JDK da [qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Libreria Aspose.Tasks per Java
Scaricate e configurate la libreria Aspose.Tasks per Java. Documentazione dettagliata e gli ultimi binari sono disponibili [qui](https://reference.aspose.com/tasks/java/).

## Importare i pacchetti
Per iniziare, importiamo i pacchetti necessari nel vostro progetto Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Guida passo‑passo

### Passo 1: Configurare la directory dei dati
Definite la cartella che contiene il vostro file *.mpp*. Regolate il percorso in base al vostro ambiente.
```java
String dataDir = "Your Data Directory";
```

### Passo 2: Caricare il file di progetto
Create un'istanza `Project` caricando il file MS Project. Questo è il punto in cui **read msproject** viene caricato in memoria.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Passo 3: Recuperare il codice di valuta
Ora che il progetto è caricato, potete **how to retrieve currency** con una singola chiamata. Questo dimostra l'uso di **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
L'output sarà il codice ISO a tre lettere (ad esempio `USD`, `EUR`, `GBP`) configurato per il progetto.

### Passo 4: Come recuperare il codice di valuta in Java (contesto aggiuntivo)
Se dovete memorizzare il valore per un uso futuro, assegnatelo semplicemente a una variabile:

*Non è necessario alcun blocco di codice aggiuntivo* – basta conservare la stringa restituita da `prj.get(Prj.CURRENCY_CODE)` e passarla a qualsiasi servizio finanziario, motore di report o componente UI.

### Passo 5: (Opzionale) Utilizzare il codice di valuta
Potrebbe essere utile applicare il codice recuperato altrove—ad esempio per formattare i valori di costo in un report personalizzato o per inviarlo a un'API finanziaria. Scenari tipici includono:

- **Generazione di report** – anteporre il codice alle colonne di costo (`USD 1.200`).  
- **Integrazione API** – inviare il codice ISO a gateway di pagamento che richiedono un identificatore di valuta.  
- **Consolidamento dati** – raggruppare più progetti per valuta per analisi di portafoglio.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Output nullo** | Il file di progetto non definisce una valuta (il valore predefinito è vuoto). | Impostate la valuta in Microsoft Project o assegnatela tramite `prj.set(Prj.CURRENCY_CODE, "USD");` prima della lettura. |
| **File non trovato** | Percorso `dataDir` errato. | Verificate il percorso e assicuratevi che il nome del file corrisponda esattamente, includendo la distinzione tra maiuscole e minuscole. |
| **Versione file non supportata** | File *.mpp* molto vecchio o corrotto. | Utilizzate l'ultima versione di Aspose.Tasks o convertite il file in un formato più recente con Microsoft Project prima. |

## Domande frequenti

**D: Aspose.Tasks può gestire strutture di progetto complesse?**  
R: Sì, l'API può leggere e manipolare gerarchie di attività a più livelli, pool di risorse e campi personalizzati senza problemi.

**D: Aspose.Tasks è compatibile con diverse versioni di file MS Project?**  
R: Assolutamente. Supporta MPP, XML, XER e altri formati su molte versioni di Microsoft Project.

**D: Aspose.Tasks fornisce documentazione e supporto?**  
R: Documentazione completa, esempi di codice e supporto dedicato sono disponibili sul sito Aspose.

**D: Posso provare Aspose.Tasks prima di acquistare?**  
R: È offerta una versione di prova gratuita per valutare tutte le funzionalità, incluso il recupero dei codici di valuta.

**D: Dove posso ottenere licenze temporanee per Aspose.Tasks?**  
R: Le licenze temporanee sono disponibili sul [sito web](https://purchase.aspose.com/temporary-license/) per valutazioni a breve termine.

---

**Ultimo aggiornamento:** 2026-02-10  
**Testato con:** Aspose.Tasks per Java (ultima versione)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}