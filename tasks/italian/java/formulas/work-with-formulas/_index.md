---
date: 2026-02-13
description: Scopri come calcolare i giorni tra le date, creare un progetto di prova
  e aggiungere un campo personalizzato mentre manipoli i file di Microsoft Project
  usando Aspose.Tasks per Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Calcolare i giorni tra le date con Aspose.Tasks per Java
url: /it/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calcolare i giorni tra date con Aspose.Tasks per Java

## Introduzione
In questo tutorial **calcolerai i giorni tra date** creando un progetto di test, aggiungendo un campo personalizzato e utilizzando le formule di Microsoft Project tramite la libreria Aspose.Tasks per Java. Che tu debba generare pianificazioni, calcolare scadenze o automatizzare report, Aspose.Tasks ti consente di manipolare i dati di Project programmaticamente senza installare l’applicazione desktop. Alla fine della guida avrai un esempio eseguibile che definisce un attributo esteso, imposta una scadenza per un’attività e salva il progetto come file MPP.

## Risposte rapide
- **Di cosa tratta il tutorial?** Creare un progetto di test, aggiungere un campo personalizzato, definire un attributo esteso e impostare una scadenza per un’attività con una formula per calcolare i giorni tra date.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (ultima versione).  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; per la produzione è richiesta una licenza.  
- **Quale IDE posso usare?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, VS Code) che supporti JDK 8+.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per copiare il codice ed eseguirlo.

## Che cosa significa “calcolare i giorni tra date” in Aspose.Tasks?
Calcolare i giorni tra date significa utilizzare una formula di Project che sottrae un campo data (ad es., **Finish**) da un altro (ad es., **Deadline**) e restituisce la differenza numerica in giorni. È utile per monitorare ritardi di pianificazione, misurare il tempo di buffer o generare report personalizzati.

## Perché usare Aspose.Tasks per calcolare i giorni tra date?
- **Copertura completa dell'API** – accesso a tutte le proprietà di Project, Task e Resource.  
- **Nessuna installazione di Office richiesta** – funziona su server, pipeline CI e container Docker.  
- **Cross‑platform** – gira su Windows, Linux e macOS con lo stesso codice Java.  
- **Motore di formule robusto** – consente di definire calcoli come `[Deadline] - [Finish]` direttamente nel file di progetto.

## Come impostare la scadenza per un’attività
Impostare una scadenza è il primo passo prima di poter calcolare l’intervallo. La scadenza è memorizzata nel campo `Tsk.DEADLINE` di un’attività e può essere assegnata usando un’istanza di `java.util.Calendar`.

## Come definire un attributo esteso
Un attributo esteso è il campo personalizzato che conterrà il risultato della tua formula. Lo definisci una sola volta, gli assegni un alias per leggibilità e poi lo colleghi a una formula che esegue la sottrazione delle date.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- **Java Development Kit (JDK) 8+** – scaricalo dal sito Oracle o adotta OpenJDK.  
- **Aspose.Tasks per Java** – ottieni l’ultimo JAR dalla [pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/) e aggiungilo al classpath del tuo progetto o alle dipendenze Maven/Gradle.

## Importare i pacchetti
Per prima cosa, importa le classi necessarie:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guida passo‑passo

### Passo 1: Creare un progetto di test con un campo personalizzato
Iniziamo **creando un progetto di test** e aggiungendo un campo personalizzato che in seguito conterrà il risultato della formula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Suggerimento:* `CreateTestProjectWithCustomField()` è un metodo di supporto che costruisce una programmazione minima e registra un attributo esteso pronto per l’assegnazione della formula.

### Passo 2: Definire un attributo esteso (Aggiungere campo personalizzato)
Successivamente, **definiamo un attributo esteso** – in pratica il campo personalizzato – e gli assegniamo un alias descrittivo. Qui aggiungiamo la logica del **campo personalizzato**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** rende il campo leggibile in Project.  
- **Formula** calcola il numero di giorni tra la data *Finish* di un’attività e la sua *Deadline* – il fulcro del *calcolare i giorni tra date*.

### Passo 3: Impostare la scadenza per un’attività (Aggiungere attività di scadenza e impostare la scadenza)
Ora **aggiungiamo i dati della scadenza** impostando la proprietà *Deadline* su un’attività specifica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- L’istanza `Calendar` definisce il momento esatto della scadenza.  
- `set(Tsk.DEADLINE, …)` **imposta la scadenza dell’attività** per l’attività scelta.

### Passo 4: Salvare il progetto (Manipolare il file Microsoft Project)
Infine, **manipoliamo Microsoft Project** salvando le modifiche in un file MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Puoi aprire `SaveFile.mpp` in Microsoft Project per vedere il campo personalizzato, il risultato della formula e la scadenza riflessi nella programmazione.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Formula non valutata** | Verifica che la stringa `Formula` dell’attributo utilizzi i nomi di campo corretti (ad es., `[Deadline]`, `[Finish]`). |
| **Attività non trovata** | Controlla che l’ID attività (`1` nell’esempio) esista; usa `project.getRootTask().getChildren().size()` per il debug. |
| **Eccezione di licenza** | Applica una licenza valida di Aspose.Tasks prima di chiamare qualsiasi metodo API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
R: Sì, Aspose.Tasks fornisce API per .NET, Java e altre piattaforme, consentendoti di **manipolare file Microsoft Project** nel linguaggio che preferisci.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
R: Assolutamente. Scarica una versione di prova completa dalla [pagina di download di Aspose.Tasks](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks?**  
R: La documentazione ufficiale è ospitata su [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**D: Come posso ottenere supporto per Aspose.Tasks?**  
R: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per porre domande e condividere esperienze con la community.

**D: È necessaria una licenza temporanea per la valutazione?**  
R: È disponibile una licenza temporanea per test a breve termine; puoi richiederla [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-02-13  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}