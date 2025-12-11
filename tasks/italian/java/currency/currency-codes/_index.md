---
date: 2025-12-09
description: Scopri come leggere i file MS Project e gestire i codici di valuta in
  modo efficiente utilizzando Aspose.Tasks per Java. Semplifica le tue attività di
  gestione dei progetti senza sforzo.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come leggere un file MS Project e gestire i codici di valuta con Aspose.Tasks
url: /it/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere un file MS Project e gestire i codici di valuta con Aspose.Tasks

## Introduzione
Benvenuti! In questo tutorial scoprirete **come leggere i dati di un file MS Project** e, in particolare, **gestire i codici di valuta** utilizzando l'API Aspose.Tasks per Java. Che stiate generando report, consolidando progetti multivaluta o semplicemente vogliate assicurarvi che i simboli finanziari corretti vengano visualizzati, questa guida vi accompagnerà passo dopo passo—dalla configurazione dell'ambiente al recupero programmatico del codice di valuta. Alla fine, sarete a vostro agio nel leggere i file MS Project e nell'estrarre le informazioni di valuta di cui avete bisogno.

## Risposte rapide
- **Cosa fa l'API?** Legge i file MS Project ed espone proprietà come il codice di valuta.  
- **Quale linguaggio viene usato?** Java, tramite la libreria Aspose.Tasks per Java.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; per la produzione è richiesta una licenza commerciale.  
- **Posso recuperare il codice in una sola riga?** Sì—`prj.get(Prj.CURRENCY_CODE)` restituisce la stringa del codice di valuta.  
- **È compatibile con tutte le versioni di Project?** Aspose.Tasks supporta sia i formati più vecchi (MPP) sia quelli più recenti (XML, XER).

## Che cosa significa **leggere un file ms project**?
Leggere un file MS Project significa aprire programmaticamente un documento di progetto *.mpp* (o altro formato supportato) e accedere alle sue strutture dati—attività, risorse, calendari e impostazioni finanziarie—senza interagire manualmente con Microsoft Project.

## Perché usare Aspose.Tasks per **leggere file msproject**?
- **Supporto completo dei formati** – funziona con file da Project 98 fino alle ultime versioni di Office.  
- **Nessun COM o installazione di Office necessaria** – puro Java, perfetto per l'automazione lato server.  
- **API ricca** – consente l'accesso diretto a proprietà come `Prj.CURRENCY_CODE`, permettendovi di **recuperare le informazioni sulla valuta** istantaneamente.  
- **Prestazioni** – parsing leggero, ideale per l'elaborazione batch di molti progetti.

## Prerequisiti
Prima di immergerci nel codice, assicuratevi di avere quanto segue:

### Java Development Kit (JDK) installato
Assicuratevi che un JDK recente sia disponibile sulla vostra macchina. Potete scaricare e installare l'ultima versione del JDK da [qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Libreria Aspose.Tasks per Java
Scaricate e configurate la libreria Aspose.Tasks per Java. Documentazione dettagliata e gli ultimi binari sono disponibili [qui](https://reference.aspose.com/tasks/java/).

## Import i pacchetti
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
Create un'istanza `Project` caricando il file MS Project. Questo è il punto in cui **leggete i dati msproject** in memoria.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Passo 3: Recuperare il codice di valuta
Ora che il progetto è caricato, potete **recuperare le informazioni sulla valuta** con una singola chiamata. Questo dimostra l'uso di **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
L'output sarà il codice ISO a tre lettere della valuta (ad es., `USD`, `EUR`, `GBP`) configurato per il progetto.

### Passo 4: (Opzionale) Utilizzare il codice di valuta
Potrebbe essere utile applicare il codice recuperato altrove—ad esempio per formattare i valori di costo in un report personalizzato o per passarli a un'API finanziaria. Ecco una rapida illustrazione (non è necessario alcun blocco di codice aggiuntivo):
- Memorizzare il codice in una variabile.  
- Utilizzarlo nella costruzione di stringhe monetarie.  
- Passarlo a servizi downstream che richiedono un identificatore di valuta.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Output nullo** | Il file di progetto non definisce una valuta (il valore predefinito è vuoto). | Impostare la valuta in Microsoft Project o assegnarla tramite `prj.set(Prj.CURRENCY_CODE, "USD");` prima della lettura. |
| **File non trovato** | Percorso `dataDir` errato. | Verificare il percorso e assicurarsi che il nome del file corrisponda esattamente, inclusa la distinzione tra maiuscole e minuscole. |
| **Versione file non supportata** | File *.mpp* molto vecchio o corrotto. | Utilizzare l'ultima versione di Aspose.Tasks o convertire il file in un formato più recente con Microsoft Project prima. |

## Domande frequenti

**D: Aspose.Tasks può gestire strutture di progetto complesse?**  
R: Sì, l'API può leggere e manipolare gerarchie di attività a più livelli, pool di risorse e campi personalizzati senza problemi.

**D: Aspose.Tasks è compatibile con diverse versioni dei file MS Project?**  
R: Assolutamente. Supporta MPP, XML, XER e altri formati across molte versioni di Microsoft Project.

**D: Aspose.Tasks fornisce documentazione e supporto?**  
R: Documentazione completa, esempi di codice e supporto dedicato sono disponibili sul sito Aspose.

**D: Posso provare Aspose.Tasks prima di acquistarlo?**  
R: È offerta una versione di prova gratuita per valutare tutte le funzionalità, incluso il recupero dei codici di valuta.

**D: Dove posso ottenere licenze temporanee per Aspose.Tasks?**  
R: Le licenze temporanee possono essere ottenute dal [sito web](https://purchase.aspose.com/temporary-license/) per valutazioni a breve termine.

---

**Ultimo aggiornamento:** 2025-12-09  
**Testato con:** Aspose.Tasks per Java (ultima versione)  
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
