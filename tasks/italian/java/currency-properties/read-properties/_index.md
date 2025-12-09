---
date: 2025-12-04
description: Scopri come leggere le proprietà della valuta in Java dai file MS Project
  usando Aspose.Tasks per Java. Segui questa guida passo passo per estrarre il codice
  della valuta, il simbolo, le cifre e la posizione in modo programmatico.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Leggi le proprietà della valuta Java con i progetti Aspose.Tasks
url: /it/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggere le proprietà della valuta Java con i progetti Aspose.Tasks

## Introduzione
In questo tutorial **leggerai le proprietà della valuta Java** dai file Microsoft Project utilizzando l'API Aspose.Tasks per Java. Aspose.Tasks ti consente di lavorare con file .mpp senza avere Microsoft Project installato, rendendolo ideale per reportistica automatizzata, migrazione dati o integrazione in applicazioni aziendali basate su Java. Alla fine di questa guida, sarai in grado di estrarre il codice della valuta, il simbolo, il numero di cifre decimali e la posizione del simbolo direttamente da un file di progetto.

## Risposte rapide
- **Cosa significa “leggere le proprietà della valuta java”?** Si riferisce al recupero dei metadati relativi alla valuta (codice, simbolo, cifre, posizione) da un file MS Project usando codice Java.  
- **È necessaria una licenza per provare?** È disponibile una versione di prova gratuita di Aspose.Tasks; è richiesta una licenza commerciale per l'uso in produzione.  
- **Quale versione di JDK è richiesta?** Java 8 o superiore.  
- **Posso modificare le impostazioni della valuta dopo averle lette?** Sì, Aspose.Tasks consente sia operazioni di lettura che di scrittura sulle proprietà della valuta.  
- **È compatibile con tutte le versioni .mpp?** L'API supporta i file creati con Microsoft Project 2003‑2021.

## Che cosa significa leggere le proprietà della valuta java?
Leggere le proprietà della valuta in Java significa accedere alle impostazioni a livello di progetto che definiscono come vengono visualizzati i valori monetari in un file Microsoft Project. Queste impostazioni includono il codice ISO della valuta (ad es., **USD**), il simbolo (**$**), il numero di cifre decimali e se il simbolo appare prima o dopo l'importo.

## Perché leggere le proprietà della valuta java con Aspose.Tasks?
- **Nessuna installazione di Microsoft Project necessaria** – l'API funziona su qualsiasi piattaforma che supporta Java.  
- **Estrazione rapida in‑processo** – ideale per l'elaborazione batch di un gran numero di file di progetto.  
- **Controllo totale** – puoi combinare i valori recuperati con report personalizzati o integrarli in sistemi ERP.  
- **Supporto cross‑versione** – funziona con file .mpp da Project 2003 fino all'ultima versione 2021.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – Java 8 o più recente installato e configurato nel tuo `PATH`.  
2. **Aspose.Tasks for Java JAR** – scarica l'ultima libreria da [qui](https://releases.aspose.com/tasks/java/) e aggiungila al classpath del tuo progetto.  

## Importa i pacchetti
Inizia importando lo spazio dei nomi Aspose.Tasks necessario per la manipolazione del progetto:

```java
import com.aspose.tasks.*;
```

## Passo 1: Configura la directory del progetto
Definisci la cartella che contiene il file `.mpp` da analizzare. Tenere il percorso in una variabile rende il codice riutilizzabile:

```java
String dataDir = "Your Data Directory";
```

*Sostituisci `"Your Data Directory"` con il percorso assoluto o relativo della cartella in cui risiede `project.mpp`.*

## Passo 2: Crea un'istanza del lettore di progetto
Carica il file Microsoft Project in un oggetto `Project`. Questo oggetto ti dà accesso a tutte le proprietà del progetto, incluse le impostazioni della valuta:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Se il tuo file ha un nome diverso, modifica `"project.mpp"` di conseguenza.*

## Passo 3: Visualizza le proprietà della valuta
Ora recupera ciascun attributo della valuta usando l'enumerazione `Prj` e stampa i risultati sulla console. L'API restituisce oggetti che puoi convertire in stringhe per la visualizzazione:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Ciò che vedrai:**  
- **Currency Code** – codice ISO‑4217 come `USD`, `EUR`, `JPY`.  
- **Currency Digits** – solitamente `2` per la maggior parte delle valute, `0` per lo Yen giapponese.  
- **Currency Symbol** – il carattere mostrato nei report (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` per **prima** dell'importo, `1` per **dopo**.

## Passo 4: Completamento del processo
Segnala che l'estrazione è terminata con successo. Questo semplice messaggio è utile quando il codice viene eseguito come parte di un batch più ampio:

```java
System.out.println("Process completed Successfully");
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Correzione |
|----------|----------------|------------|
| **FileNotFoundException** | Il percorso `dataDir` è errato o il nome del file è scritto male. | Verifica la stringa della directory e assicurati che il file `.mpp` esista nella posizione specificata. |
| **NullPointerException on `project.get(...)`** | Il file di progetto non contiene informazioni sulla valuta (improbabile) o la chiave della proprietà è sbagliata. | Usa `project.contains(Prj.CURRENCY_CODE)` per controllare l'esistenza prima della lettura. |
| **LicenseException** | Esecuzione senza una licenza valida di Aspose.Tasks in ambiente di produzione. | Applica un file di licenza usando `License license = new License(); license.setLicense("Aspose.Tasks.lic");` prima di creare l'oggetto `Project`. |

## Domande frequenti

**D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?**  
R: Aspose.Tasks supporta i file .mpp generati da Microsoft Project 2003‑2021, coprendo sia i formati più vecchi sia quelli più recenti.

**D: Posso modificare le proprietà della valuta usando Aspose.Tasks?**  
R: Sì, è possibile sia leggere sia scrivere le impostazioni della valuta. Usa `project.set(Prj.CURRENCY_CODE, "EUR");` e poi salva il progetto.

**D: Aspose.Tasks è adatto per uso commerciale?**  
R: Assolutamente sì. È una libreria commerciale; puoi acquistare una licenza [qui](https://purchase.aspose.com/buy).

**D: Aspose.Tasks offre una versione di prova gratuita?**  
R: Sì, è disponibile una versione di prova completa [qui](https://releases.aspose.com/).

**D: Dove posso trovare aiuto o supporto per Aspose.Tasks?**  
R: Il forum ufficiale di Aspose.Tasks è il posto migliore per assistenza – visitalo [qui](https://forum.aspose.com/c/tasks/15).

## Conclusione
Ora sai **come leggere le proprietà della valuta Java** da un file MS Project usando Aspose.Tasks per Java. Questa funzionalità ti permette di incorporare i metadati della valuta in report personalizzati, analisi finanziarie o pipeline di integrazione senza dipendere da Microsoft Project. Sentiti libero di sperimentare modificando le proprietà o combinando questi dati con altri attributi del progetto per creare soluzioni più ricche.

---

**Ultimo aggiornamento:** 2025-12-04  
**Testato con:** Aspose.Tasks for Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}