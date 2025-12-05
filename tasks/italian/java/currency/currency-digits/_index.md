---
date: 2025-12-05
description: Scopri come gestire in modo efficiente le cifre della valuta in MS Project
  utilizzando Aspose.Tasks per Java. Guida passo passo che copre la gestione dei file
  di progetto Java e come caricare i file MPP.
language: it
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gestire le cifre della valuta di MS Project con Aspose.Tasks
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestire le cifre della valuta di ms project con Aspose.Tasks

## Introduzione
In questo tutorial completo scoprirai **come lavorare con i valori della valuta di ms project** utilizzando la libreria Aspose.Tasks per Java. Che tu stia costruendo uno strumento di reporting, un'utilità di migrazione, o semplicemente abbia bisogno di leggere le impostazioni di valuta da un **java project file**, questa guida ti accompagna passo passo—dal caricamento di un file *.mpp* all'estrazione delle cifre della valuta. Alla fine, sarai a tuo agio nel gestire i dati della valuta di ms project nelle tue applicazioni.

## Risposte rapide
- **Quale libreria legge i file MS Project?** Aspose.Tasks for Java.  
- **Quante righe di codice servono per ottenere le cifre della valuta?** Solo tre righe concise dopo il caricamento del progetto.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore (qualsiasi JDK che esegue Aspose.Tasks).  
- **Posso recuperare altre proprietà del Project?** Sì – Aspose.Tasks espone un set completo di campi del Project (ad esempio, data di inizio, tariffe dei costi, ecc.).

## Cos'è la valuta di ms project?
`ms project currency` si riferisce alla precisione numerica (numero di cifre decimali) che Microsoft Project utilizza quando visualizza valori monetari. È memorizzata nel file Project come proprietà **CURRENCY_DIGITS** e determina se gli importi appaiono come numeri interi, con una decimale, due decimali, ecc.

## Perché usare Aspose.Tasks per gestire la valuta di ms project?
- **Nessuna installazione di Microsoft Project richiesta** – lavora direttamente con file *.mpp* su qualsiasi piattaforma che supporta Java.  
- **Forte sicurezza dei tipi** – l'API restituisce valori tipizzati, riducendo gli errori di parsing.  
- **Ottimizzato per le prestazioni** – carica rapidamente progetti di grandi dimensioni ed estrae solo i campi necessari.  
- **Cross‑platform** – esegui su Windows, Linux o macOS senza modifiche.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

1. **Ambiente di sviluppo Java** – JDK 8 o più recente installato e configurato.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dal sito ufficiale: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Conoscenza di base di Java** – dovresti sentirti a tuo agio nel creare un progetto Java, aggiungere librerie esterne ed eseguire un metodo `main`.  

## Importare i pacchetti
Per prima cosa, importa le classi di cui avremo bisogno.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Passo 1: Definire la directory dei dati
Specifica la cartella che contiene il tuo **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con il percorso assoluto o relativo dove risiede `project.mpp`.

## Passo 2: Caricare il file MPP  
Ora vedremo **come caricare file mpp** usando Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Assicurati che il nome del file corrisponda esattamente; altrimenti verrà generata un'`IOException`.

## Passo 3: Recuperare le cifre della valuta  
Con il progetto caricato, estrarre le **cifre della valuta di ms project** è una singola riga:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
La chiamata restituisce un `Integer` che rappresenta il numero di cifre decimali (ad esempio, `2` per i centesimi). Il valore è stampato sulla console, ma puoi anche memorizzarlo in una variabile per ulteriori elaborazioni.

## Problemi comuni e suggerimenti
- **File non trovato** – verifica il percorso `dataDir` e assicurati che il nome del file sia corretto, inclusa l'estensione `.mpp`.  
- **Versione del file non supportata** – Aspose.Tasks supporta i formati Project 2000‑2024; file più vecchi o corrotti potrebbero necessitare di conversione.  
- **Licenza non impostata** – durante lo sviluppo una versione di prova funziona, ma per la produzione devi applicare una licenza valida per evitare filigrane di valutazione.

## Domande frequenti

**Q: Aspose.Tasks può gestire altri attributi del Project oltre alle cifre della valuta?**  
A: Sì, Aspose.Tasks offre un'ampia gamma di funzionalità per manipolare vari aspetti dei file Project, come attività, risorse e campi personalizzati.

**Q: Aspose.Tasks è adatto per applicazioni a livello enterprise?**  
A: Assolutamente, Aspose.Tasks è progettato per soddisfare le esigenze di progetti di livello enterprise, offrendo alte prestazioni e scalabilità.

**Q: Aspose.Tasks supporta lo sviluppo cross‑platform?**  
A: Sì, puoi utilizzare Aspose.Tasks for Java su qualsiasi piattaforma che supporta il Java Runtime Environment (Windows, Linux, macOS).

**Q: Posso provare Aspose.Tasks prima di acquistarlo?**  
A: Sì, puoi scaricare una versione di prova gratuita da [qui](https://releases.aspose.com/).

**Q: Dove posso ottenere supporto per Aspose.Tasks?**  
A: Puoi trovare supporto sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Ultimo aggiornamento:** 2025-12-05  
**Testato con:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}