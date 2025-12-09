---
date: 2025-12-07
description: Scopri come **creare un progetto di prova** e **aggiungere un campo personalizzato**
  mentre manipoli i file Microsoft Project usando Aspose.Tasks per Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Crea progetto di test e usa le formule con Aspose.Tasks per Java
url: /it/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un progetto di test e utilizza le formule con Aspose.Tasks per Java

## Introduzione
In questo tutorial **creerai file di progetto di test**, aggiungerai un campo personalizzato e lavorerai con le formule di MS Project utilizzando la libreria Aspose.Tasks per Java. Aspose.Tasks rende semplice **manipolare i dati di Microsoft Project** in modo programmatico—che tu debba generare pianificazioni, calcolare date o automatizzare i report. Alla fine della guida avrai un esempio eseguibile che definisce un attributo esteso, imposta una scadenza per un'attività e salva il progetto come file MPP.

## Risposte rapide
- **Di cosa tratta il tutorial?** Creare un progetto di test, aggiungere un campo personalizzato, definire un attributo esteso e impostare una scadenza per un'attività con una formula.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (ultima versione).  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza per la produzione.  
- **Quale IDE posso usare?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, VS Code) che supporti JDK 8+.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per copiare il codice ed eseguirlo.

## Che cos'è un “progetto di test” in Aspose.Tasks?
Un **progetto di test** è un file Microsoft Project leggero creato programmaticamente per dimostrare o convalidare funzionalità. Contiene un insieme minimo di attività, risorse e campi personalizzati che puoi manipolare senza influire sui dati di progetto reali.

## Perché usare Aspose.Tasks per manipolare Microsoft Project?
- **Copertura completa dell'API** – accedi a ogni proprietà di Project, Task e Resource.  
- **Nessuna installazione di Office richiesta** – funziona su server, pipeline CI e container Docker.  
- **Cross‑platform** – funziona su Windows, Linux e macOS con lo stesso codice Java.  
- **Motore di formule robusto** – calcola date, durate e campi personalizzati direttamente nel file di progetto.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- **Java Development Kit (JDK) 8+** – scaricalo dal sito Oracle o utilizza OpenJDK.  
- **Aspose.Tasks per Java** – ottieni l'ultimo JAR dalla [pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/) e aggiungilo al classpath del tuo progetto o alle dipendenze Maven/Gradle.

## Importa i pacchetti
Per prima cosa, importa le classi di cui avremo bisogno:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guida passo‑passo

### Passo 1: Crea un progetto di test con un campo personalizzato
Iniziamo **creando un progetto di test** e aggiungendo un campo personalizzato che in seguito conterrà il risultato della nostra formula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Suggerimento:* `CreateTestProjectWithCustomField()` è un metodo di supporto che costruisce una programmazione minima e registra un attributo esteso pronto per l'assegnazione della formula.

### Passo 2: Definisci un attributo esteso (Aggiungi campo personalizzato)
Successivamente, **definiamo l'attributo esteso** – essenzialmente il campo personalizzato – e gli assegniamo un alias leggibile. Qui è dove inseriamo la logica per **aggiungere il campo personalizzato**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** rende il campo leggibile in Project.  
- **Formula** calcola il numero di giorni tra la data *Finish* di un'attività e la sua *Deadline*.

### Passo 3: Imposta la scadenza per un'attività (Aggiungi attività di scadenza e imposta la scadenza)
Ora **aggiungiamo i dati della scadenza** impostando la proprietà *Deadline* su un'attività specifica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- L'istanza `Calendar` definisce il momento esatto della scadenza.  
- `set(Tsk.DEADLINE, …)` **imposta la scadenza dell'attività** per l'attività selezionata.

### Passo 4: Salva il progetto (Manipola il file Microsoft Project)
Infine, **manipoliamo Microsoft Project** salvando le modifiche in un file MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Puoi aprire `SaveFile.mpp` in Microsoft Project per vedere il campo personalizzato, il risultato della formula e la scadenza riflessi nella pianificazione.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Formula non valutata** | Assicurati che la stringa `Formula` dell'attributo utilizzi i nomi di campo corretti (ad esempio, `[Deadline]`, `[Finish]`). |
| **Attività non trovata** | Verifica che l'ID dell'attività (`1` nell'esempio) esista; usa `project.getRootTask().getChildren().size()` per il debug. |
| **Eccezione di licenza** | Applica una licenza valida di Aspose.Tasks prima di chiamare qualsiasi metodo API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Domande frequenti

**D: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
R: Sì, Aspose.Tasks fornisce API per .NET, Java e altre piattaforme, consentendoti di **manipolare i file Microsoft Project** nel linguaggio che preferisci.

**D: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
R: Assolutamente. Scarica una versione di prova completa dalla [pagina di download di Aspose.Tasks](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione dettagliata per Aspose.Tasks?**  
R: La documentazione ufficiale è disponibile su [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**D: Come posso ottenere supporto per Aspose.Tasks?**  
R: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per porre domande e condividere esperienze con la community.

**D: È necessaria una licenza temporanea per la valutazione?**  
R: È disponibile una licenza temporanea per test a breve termine; puoi richiederla [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2025-12-07  
**Testato con:** Aspose.Tasks per Java 24.12 (ultima versione al momento della scrittura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}