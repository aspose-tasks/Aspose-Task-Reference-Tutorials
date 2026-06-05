---
date: 2026-01-23
description: Scopri come identificare le attività cross‑project usando Aspose.Tasks
  per Java. Esplora l'integrazione senza soluzione di continuità e una gestione efficiente.
linktitle: Identify Cross Project Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Identifica le attività cross‑project in Aspose.Tasks
url: /it/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identificare le attività cross‑project in Aspose.Tasks

## Introduzione
Benvenuti al nostro tutorial completo su **come identificare le attività cross‑project** in modo efficiente con Aspose.Tasks per Java. Che siate sviluppatori esperti o alle prime armi, questa guida vi accompagnerà passo dopo passo nell’integrare questa funzionalità nelle vostre applicazioni Java.

## Risposte rapide
- **Cosa significa “identificare le attività cross‑project”?** Significa individuare le attività che fanno riferimento o dipendono da attività in un altro file di progetto.  
- **Quale metodo stampa l’ID dell’attività?** Utilizzate `externalTask.get(Tsk.ID)` per stampare l’ID dell’attività.  
- **Come imposto la directory del documento?** Assegnate il percorso della cartella a una variabile `String` (ad es., `dataDir`).  
- **Quale proprietà recupera un’attività per UID?** Chiamate `getChildren().getByUid(yourUid)`.  
- **È necessaria una licenza per l’uso in produzione?** Sì, è richiesta una licenza valida di Aspose.Tasks per le distribuzioni commerciali.

## Cos’è “identificare le attività cross‑project”?
Identificare le attività cross‑project consente di tracciare le relazioni tra attività distribuite su più file Microsoft Project. Questo è fondamentale per portafogli di progetti su larga scala in cui le attività sono condivise o dipendenti da programmazioni esterne.

## Perché usare Aspose.Tasks per Java?
- **Nessun Microsoft Project necessario** – lavorate direttamente con i file .mpp in Java.  
- **Accesso completo all’API** – recuperate ID, ID esterni, UID e molto altro.  
- **Cross‑platform** – eseguite il codice su qualsiasi ambiente compatibile con JVM.

## Prerequisiti
Prima di iniziare, assicuratevi di avere:

- Conoscenze di base della programmazione Java.  
- Aspose.Tasks per Java installato. Potete scaricarlo **[qui](https://releases.aspose.com/tasks/java/)**.

## Importare i pacchetti
Per prima cosa, importate le classi essenziali di Aspose.Tasks che consentono la manipolazione dei progetti.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Passo 1: Impostare la directory del documento
Definite la cartella in cui risiedono i vostri file .mpp. Questo passo è allineato con la keyword secondaria **set document directory**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Passo 2: Caricare il progetto esterno
Caricate il file di progetto esterno (ad es., *External.mpp*) così da poter es.

```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Passo 3: Recuperare l’attività esterna per UID
Utilizzate l’**UID** (Unique Identifier) dell’attività per recuperare lo specifico task di interesse. Questo soddisfa la keyword secondaria **get task uid**.

```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Passo 4: Stampare l’ID dell’attività (Caso d’uso principale)
Ora che avete l’oggetto task, stampate il suo ID interno. Questo dimostra la keyword secondaria **print task id**.

```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Passo 5: Stampare l’ID originale (esterno) dell’attività
Potete anche recuperare l’ID che l’attività aveva nel suo progetto originale.

```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Ripetete i passaggi sopra per qualsiasi altra attività che dovete tracciare tra progetti.

## Problemi comuni e consigli
- **Errori di percorso** – Assicuratevi che `dataDir` termini con il separatore di file appropriato (`/` o `\\`).  
- **UID non trovato** – Verificate che l’UID esista nel progetto esterno; usate `externalProject.getRootTask().getChildren().size()` per elencare gli UID disponibili.  
- **Eccezioni di licenza** – Una licenza mancante o non valida genererà un’eccezione di licenza a runtime.

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
R: Sì, Aspose.Tasks supporta più linguaggi, tra cui Java, .NET e altri.

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks per Java?**  
R: Consultate la documentazione **[qui](https://reference.aspose.com/tasks/java/)**.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks per Java?**  
R: Sì, potete ottenere una prova gratuita **[qui](https://releases.aspose.com/)**.

**D: Come posso ottenere una licenza temporanea per Aspose.Tasks?**  
R: Ottenete una licenza temporanea **[qui](https://purchase.aspose.com/temporary-license/)**.

**D: Avete bisogno di assistenza o avete domande specifiche?**  
R: Visitate il forum di supporto di Aspose.Tasks **[qui](https://forum.aspose.com/c/tasks/15)**.

---

**Ultimo aggiornamento:** 2026-01-23  
**Testato con:** Aspose.Tasks per Java 24.11 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}