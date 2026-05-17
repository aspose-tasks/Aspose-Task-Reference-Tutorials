---
date: 2026-02-10
description: Scopri come ottenere i valori di valuta, leggere i file MS Project e
  convertire i file di progetto Java usando Aspose.Tasks. Guida passo passo per estrarre
  le cifre della valuta.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Come ottenere la valuta da MS Project usando Aspose.Tasks
url: /it/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ottenere la valuta da MS Project usando Aspose.Tasks

## Introduzione
Se ti stai chiedendo **come ottenere la valuta** da un file Microsoft Project, sei nel posto giusto. In questo tutorial completo scoprirai **come lavorare con i valori della valuta di ms project** usando la libreria Aspose.Tasks per Java. Che tu stia costruendo uno strumento di reporting, un'utilità di migrazione, o semplicemente abbia bisogno di leggere le impostazioni della valuta da un **file di progetto java**, questa guida ti accompagna passo passo—dall'apertura di un file *.mpp* all'estrazione delle cifre decimali della valuta. Alla fine, sarai a tuo agio nel gestire i dati della valuta di ms project nelle tue applicazioni.

## Risposte rapide
- **Quale libreria legge i file MS Project?** Aspose.Tasks for Java.  
- **Quante righe di codice servono per ottenere le cifre della valuta?** Solo tre righe concise dopo aver caricato il progetto.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.  
- **Quale versione di Java è supportata?** Java 8 o superiore (qualsiasi JDK che esegue Aspose.Tasks).  
- **Posso recuperare altre proprietà del Project?** Sì – Aspose.Tasks espone un set completo di campi del Project (ad es., data di inizio, tariffe dei costi, ecc.).

## Cos'è la valuta di ms project?
`ms project currency` si riferisce alla precisione numerica (numero di cifre decimali) che Microsoft Project utilizza per visualizzare i valori monetari. È memorizzata nel file Project come proprietà **CURRENCY_DIGITS** e determina se gli importi appaiono come numeri interi, con una cifra decimale, due cifre decimali, ecc.

## Perché usare Aspose.Tasks per gestire la valuta di ms project?
- **Nessuna installazione di Microsoft Project richiesta** – lavora direttamente con file *.mpp* su qualsiasi piattaforma che supporta Java.  
- **Forte sicurezza tipizzata** – l'API restituisce valori tipizzati, riducendo gli errori di parsing.  
- **Ottimizzata per le prestazioni** – carica rapidamente progetti di grandi dimensioni ed estrai solo i campi di cui hai bisogno.  
- **Cross‑platform** – esegui su Windows, Linux o macOS senza modifiche.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

1. **Ambiente di sviluppo Java** – JDK 8 o più recente installato e configurato.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dal sito ufficiale: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Conoscenza di base di Java** – dovresti sentirti a tuo agio nel creare un progetto Java, aggiungere librerie esterne e eseguire un metodo `main`.  

## Importa i pacchetti
Per prima cosa, importa le classi di cui avremo bisogno.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Passo 1: Definisci la directory dei dati
Specifica la cartella che contiene il tuo **file di progetto java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Sostituisci `"Your Data Directory"` con il percorso assoluto o relativo dove si trova `project.mpp`.

## Passo 2: Carica il file MPP  
Ora vedremo **come caricare file mpp** usando Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Assicurati che il nome del file corrisponda esattamente; altrimenti verrà generata un'`IOException`.

## Passo 3: Recupera le cifre decimali della valuta  
Con il progetto caricato, estrarre le cifre della **ms project currency** è una singola riga:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
La chiamata restituisce un `Integer` che rappresenta il numero di cifre decimali (ad esempio, `2` per i centesimi). Il valore è stampato sulla console, ma puoi anche memorizzarlo in una variabile per ulteriori elaborazioni.

## Problemi comuni e suggerimenti
- **File non trovato** – verifica nuovamente il percorso `dataDir` e assicurati che il nome del file sia corretto, includendo l'estensione `.mpp`.  
- **Versione del file non supportata** – Aspose.Tasks supporta i formati Project 2000‑2024; file più vecchi o corrotti potrebbero necessitare di conversione.  
- **Licenza non impostata** – durante lo sviluppo una versione di prova funziona, ma in produzione devi applicare una licenza valida per evitare filigrane di valutazione.

## Domande frequenti

**Q: Aspose.Tasks può gestire altri attributi del Project oltre alle cifre della valuta?**  
A: Sì, Aspose.Tasks offre un'ampia gamma di funzionalità per manipolare vari aspetti dei file Project, come attività, risorse e campi personalizzati.

**Q: Aspose.Tasks è adatto per applicazioni a livello enterprise?**  
A: Assolutamente sì, Aspose.Tasks è progettato per soddisfare le esigenze di progetti di livello enterprise, offrendo alte prestazioni e scalabilità.

**Q: Aspose.Tasks supporta lo sviluppo cross‑platform?**  
A: Sì, puoi utilizzare Aspose.Tasks per Java su qualsiasi piattaforma che supporta il Java Runtime Environment (Windows, Linux, macOS).

**Q: Posso provare Aspose.Tasks prima di acquistarlo?**  
A: Sì, puoi scaricare una versione di prova gratuita da [qui](https://releases.aspose.com/).

**Q: Dove posso ottenere supporto per Aspose.Tasks?**  
A: Puoi trovare supporto sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Conclusione
Ora sai **come ottenere le cifre della valuta** da un file MS Project usando Aspose.Tasks per Java. Il processo è semplice: carica il progetto, chiama `project.get(Prj.CURRENCY_DIGITS)` e utilizza il risultato nella tua applicazione. Sentiti libero di esplorare altre proprietà del progetto con lo stesso schema e integrare questa logica in soluzioni più ampie di reporting o migrazione.

---

**Last Updated:** 2026-02-10  
**Testato con:** Aspose.Tasks for Java (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}