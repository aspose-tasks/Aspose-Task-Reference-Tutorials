---
date: 2026-02-10
description: Scopri come estrarre e aggiornare le proprietà di un progetto Java, come
  il simbolo della valuta, utilizzando Aspose.Tasks per Java. Cambia la valuta del
  progetto e recupera facilmente il simbolo della valuta.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Proprietà del progetto Java – Estrarre il simbolo della valuta da MPP usando
  Aspose.Tasks per Java
url: /it/java/currency/currency-symbols/
weight: 12
---

**Author:** Aspose -> "Autore:".

Then closing shortcodes.

Make sure to keep markdown formatting.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estrai il simbolo della valuta mpp usando Aspose.Tasks per Java

## Introduzione
In questo tutorial imparerai a lavorare con **java project properties** — in particolare come estrarre il simbolo della valuta da un file Microsoft Project (MPP) e come **change currency symbol java** o **retrieve currency symbol java** usando la libreria Aspose.Tasks. Che tu stia costruendo uno strumento di reporting, integrando i dati di Project in un sistema finanziario, o semplicemente abbia bisogno di visualizzare il simbolo della valuta corretto nella tua interfaccia, padroneggiare questo piccolo ma fondamentale compito renderà le tue applicazioni Java più robuste e user‑friendly.

## Risposte rapide
- **Che cosa significa “extract currency symbol mpp”?** Significa leggere il simbolo della valuta memorizzato in un file MPP (Microsoft Project).  
- **Quale libreria gestisce questo?** Aspose.Tasks for Java fornisce un'API semplice per il compito.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quanto tempo ci vuole?** Con il codice qui sotto, puoi ottenere il simbolo in meno di un minuto.  
- **Posso anche modificare il simbolo?** Sì – puoi impostare un nuovo valore usando la stessa proprietà `Prj.CURRENCY_SYMBOL`.

## Che cos'è “extract currency symbol mpp”?
Microsoft Project memorizza il simbolo della valuta (ad es., $, €, £) nell'intestazione del file di progetto. L'operazione **extract currency symbol mpp** legge quel valore così puoi visualizzarlo o manipolarlo programmaticamente.

## Perché aggiornare il simbolo della valuta nelle proprietà del progetto java?
I progetti spesso coprono più regioni. Essere in grado di **change project currency** o **update currency symbol** a runtime ti consente di adattare report, fatture o dashboard al mercato locale senza ricreare l'intero file di progetto. Questa flessibilità è una parte fondamentale della gestione efficace delle **java project properties**.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – versione 8 o superiore.  
2. **Aspose.Tasks for Java** – scarica l'ultimo JAR dalla [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Un file **project.mpp** valido collocato in una cartella a cui puoi fare riferimento dal tuo codice.

## Importa i pacchetti
Prima, importa le classi necessarie per lavorare con i file Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Passo 1: Definisci la directory dei dati
Indica all'applicazione dove si trova il tuo file *.mpp*.

```java
String dataDir = "Your Data Directory";
```

> **Suggerimento:** Usa `System.getProperty("user.dir")` per costruire un percorso assoluto che funzioni su qualsiasi macchina.

## Passo 2: Carica il file MS Project
Crea un oggetto `Project` che rappresenta il file MPP in memoria.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Passo 3: Recupera (e opzionalmente modifica) il simbolo della valuta
Ora **retrieve currency symbol java** leggendo la proprietà `Prj.CURRENCY_SYMBOL`. Puoi anche **change currency symbol java** (o **change project currency**) assegnando una nuova stringa alla stessa proprietà.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

La chiamata `System.out.println` stampa il simbolo (ad es., `$`) sulla console, confermando che l'estrazione è avvenuta con successo.

## Problemi comuni e come risolverli
| Sintomo | Causa probabile | Soluzione |
|---------|-----------------|-----------|
| `NullPointerException` su `project.get(...)` | Percorso file errato o file non trovato | Verifica `dataDir` e il nome del file; usa `new File(dataDir).exists()` per il debug |
| Simbolo inatteso (ad es., `?`) | Progetto creato con una locale non standard | Assicurati che il file MPP di origine definisca effettivamente un simbolo di valuta; puoi impostarne uno programmaticamente come mostrato sopra |
| Errore di licenza | Uso della versione di prova senza un file di licenza valido | Carica la tua licenza con `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` prima di creare l'oggetto `Project` |

## Domande frequenti

**D: Posso manipolare altri attributi del progetto oltre ai simboli di valuta usando Aspose.Tasks?**  
R: Sì, Aspose.Tasks ti consente di modificare attività, risorse, assegnazioni, calendari e molte altre proprietà del progetto.

**D: Aspose.Tasks è compatibile con diverse versioni dei file MS Project?**  
R: Assolutamente. Supporta i formati MPP, MPT e XML da Project 98 fino alle ultime versioni.

**D: Aspose.Tasks offre documentazione e supporto per gli sviluppatori?**  
R: Documentazione API completa, esempi di codice e un forum di supporto dedicato sono disponibili sul sito di Aspose.Tasks.

**D: Posso provare Aspose.Tasks prima di acquistarlo?**  
R: Sì – una versione di prova completamente funzionale può essere scaricata dal [Aspose website](https://purchase.aspose.com/buy).

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
R: Le licenze temporanee sono fornite sulla [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) per scopi di valutazione.

**Ultimo aggiornamento:** 2026-02-10  
**Testato con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}