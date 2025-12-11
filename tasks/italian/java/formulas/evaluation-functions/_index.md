---
date: 2025-12-09
description: Scopri come creare un oggetto progetto Java e supportare le funzioni
  di valutazione nelle formule Aspose.Tasks usando Java. Scopri come creare un attributo
  esteso per le attività.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Creare l'oggetto Project in Java – Supportare le funzioni di valutazione in
  Aspose.Tasks
url: /it/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Funzioni di Valutazione del Supporto in Aspose.Tasks Formulas

## Introduzione
Aspose.Tasks per Java ti consente di **creare project object java** istanze e valutare le funzioni di Microsoft Project direttamente nel tuo codice Java. Incorporando queste formule, puoi eseguire calcoli sofisticati, generare report personalizzati e automatizzare l'analisi del progetto senza uscire dall'ambiente di sviluppo. Questo tutorial ti guida attraverso l'intero processo—dalla configurazione dell'oggetto progetto all'aggiunta di un attributo esteso che può contenere dati personalizzati.

## Risposte Rapide
- **Cosa significa “create project object java”?** Crea un'istanza `Project` in memoria che puoi manipolare programmaticamente.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (scaricabile dal sito ufficiale).  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per l'uso in produzione; è disponibile una versione di prova gratuita.  
- **Posso usare campi personalizzati?** Sì – puoi definire e collegare attributi estesi ai task.  
- **È compatibile con tutti i formati di file Project?** Aspose.Tasks supporta i formati MPP, MPT e XML.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Ambiente di Sviluppo Java** – JDK 8+ e un IDE come IntelliJ IDEA o Eclipse.  
2. **Libreria Aspose.Tasks per Java** – Scarica e includi la libreria dalla [pagina di download di Aspose.Tasks per Java](https://releases.aspose.com/tasks/java/).

## Importare i Pacchetti
Aggiungi lo spazio dei nomi Aspose.Tasks alla tua classe Java così potrai lavorare con progetti, task e attributi estesi:

```java
import com.aspose.tasks.*;
```

## Passo 1: Create Project Object Java
Istanzia un nuovo oggetto `Project`. Questo fungerà da contenitore per tutti i task, le risorse e i dati personalizzati che definirai.

```java
Project project = new Project();
```

La riga sopra **creates project object java** che parte vuoto e pronto per la personalizzazione.

## Passo 2: Come Creare un Attributo Esteso
Definisci un attributo esteso che memorizzerà dati numerici personalizzati (ad esempio, un valore di seno) per ogni task.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Qui **create extended attribute** di tipo `Number` denominato “Sine” e lo associamo ai task.

## Passo 3: Aggiungere l'Attributo Esteso al Progetto
Registra la definizione dell'attributo nel progetto in modo che ogni task possa fare riferimento ad esso.

```java
project.getExtendedAttributes().add(attr);
```

## Passo 4: Creare un Nuovo Task
Aggiungi un task semplice chiamato “Task” sotto il task radice del progetto.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Passo 5: Associare l'Attributo Esteso al Task
Collega l'attributo esteso precedentemente definito al task appena creato.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Ora il task contiene un campo personalizzato “Sine” che puoi utilizzare nelle formule o nei calcoli.

## Perché Utilizzare le Funzioni di Valutazione?
Incorporare le funzioni di MS Project nelle formule di Aspose.Tasks ti permette di:

- Eseguire calcoli al volo (ad esempio, `Sin([Start])`) senza strumenti esterni.  
- Tenere tutta la logica del progetto all'interno di un unico codice mantenibile.  
- Generare report dinamici che riflettono le modifiche dei dati in tempo reale.

## Problemi Comuni e Soluzioni
| Problema | Soluzione |
|----------|-----------|
| **La formula restituisce `NaN`** | Verifica che il tipo del campo personalizzato corrisponda al tipo numerico previsto. |
| **Attributo esteso non visibile** | Assicurati che la definizione dell'attributo sia aggiunta al progetto **prima** di creare i task. |
| **Eccezione di licenza** | Installa una licenza temporanea o completa; la modalità di prova potrebbe limitare alcune funzionalità. |

## Domande Frequenti

**D: Aspose.Tasks per Java può gestire formule complesse di MS Project?**  
R: Sì, Aspose.Tasks per Java supporta la valutazione di un'ampia gamma di funzioni di MS Project, consentendo calcoli complessi all'interno delle applicazioni Java.

**D: Aspose.Tasks per Java è compatibile con diverse versioni di file Microsoft Project?**  
R: Sì, Aspose.Tasks per Java supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.

**D: Posso provare Aspose.Tasks per Java prima di acquistarlo?**  
R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per Java dal sito [qui](https://purchase.aspose.com/buy).

**D: Come posso ottenere supporto per Aspose.Tasks per Java?**  
R: Puoi ottenere supporto dal forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**D: È disponibile una licenza temporanea per Aspose.Tasks per Java?**  
R: Sì, puoi ottenere una licenza temporanea per scopi di test dal sito Aspose [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2025-12-09  
**Testato con:** Aspose.Tasks per Java 24.10  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}