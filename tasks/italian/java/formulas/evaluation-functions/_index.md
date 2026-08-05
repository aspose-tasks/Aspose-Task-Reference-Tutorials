---
date: 2026-02-13
description: Scopri come generare un report di progetto creando un oggetto progetto
  in Java, aggiungendo attributi estesi e utilizzando le funzioni di valutazione con
  Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Genera Rapporto di Progetto – Crea Oggetto Progetto Java
url: /it/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Supporto alle Funzioni di Valutazione nelle Formule di Aspose.Tasks

## Introduzione
Aspose.Tasks for Java ti consente di **generate project report** creando un **project object** in Java e valutando le funzioni di Microsoft Project direttamente nel tuo codice. Incorporando queste formule, puoi eseguire calcoli sofisticati, generare report personalizzati e automatizzare l'analisi del progetto senza uscire dall'ambiente di sviluppo. In questo tutorial vedremo come creare un project object, aggiungere un attributo esteso e utilizzare le funzioni di valutazione per **add custom field task**.

## Risposte Rapide
- **What does “create project object java” mean?** Crea un'istanza `Project` in memoria che puoi manipolare programmaticamente.  
- **Which library is required?** Aspose.Tasks for Java (scarica dal sito ufficiale).  
- **Do I need a license?** È necessaria una licenza temporanea o completa di Aspose.Tasks per l'uso in produzione; è disponibile una versione di prova gratuita.  
- **Can I use custom fields?** Sì – puoi **add extended attribute** ai task e trattarli come campi personalizzati.  
- **Is this compatible with all Project file formats?** Aspose.Tasks supporta i formati MPP, MPT e XML.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Environment** – JDK 8+ e un IDE come IntelliJ IDEA o Eclipse.  
2. **Aspose.Tasks for Java Library** – Scarica e includi la libreria dalla [pagina di download di Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importa Pacchetti
Aggiungi lo spazio dei nomi Aspose.Tasks alla tua classe Java così da poter lavorare con progetti, task e attributi estesi:

```java
import com.aspose.tasks.*;
```

## Genera Report di Progetto – Crea Project Object Java
Istanzia un nuovo oggetto `Project`. Questo servirà da contenitore per tutti i task, le risorse e i dati personalizzati che definirai.

```java
Project project = new Project();
```

La riga sopra **creates project object java** che parte vuota e pronta per la personalizzazione.

## Come Aggiungere un Attributo Esteso
Definisci un attributo esteso che memorizzerà dati numerici personalizzati (ad esempio, un valore di seno) per ogni task.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Qui **add extended attribute** di tipo `Number` chiamato “Sine” e lo associamo ai task.

## Aggiungi l'Attributo Esteso al Progetto
Registra la definizione dell'attributo nel progetto in modo che ogni task possa fare riferimento ad esso.

```java
project.getExtendedAttributes().add(attr);
```

## Crea un Nuovo Task
Aggiungi un task semplice chiamato “Task” sotto il task radice del progetto.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Associa l'Attributo Esteso al Task
Collega l'attributo esteso precedentemente definito al task appena creato.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Ora il task contiene un campo personalizzato “Sine” che puoi utilizzare in formule o calcoli. Questo è anche il modo in cui **add custom field task** dati programmaticamente.

## Perché Usare le Funzioni di Valutazione?
Incorporare le funzioni di MS Project nelle formule di Aspose.Tasks ti permette di:

- Eseguire calcoli on‑the‑fly (ad es., `Sin([Start])`) senza strumenti esterni.  
- Mantenere tutta la logica del progetto all'interno di un unico codice gestibile.  
- Generare report dinamici che riflettono le modifiche dei dati in tempo reale, aiutandoti a **generate project report** automaticamente.

## Problemi Comuni e Soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Formula returns `NaN`** | Verifica che il tipo del campo personalizzato corrisponda al tipo numerico previsto. |
| **Extended attribute not visible** | Assicurati che la definizione dell'attributo sia aggiunta al progetto **prima** di creare i task. |
| **License exception** | Installa una licenza temporanea o completa di **Aspose.Tasks**; la modalità di prova può limitare alcune funzionalità. |
| **Missing temporary license** | Ottieni una **temporary Aspose license** dal sito Aspose. |

## Domande Frequenti

**Q: Can Aspose.Tasks for Java handle complex MS Project formulas?**  
A: Sì, Aspose.Tasks for Java supporta la valutazione di un'ampia gamma di funzioni di MS Project, consentendo calcoli complessi all'interno delle applicazioni Java.

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project files?**  
A: Sì, Aspose.Tasks for Java supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.

**Q: Can I try Aspose.Tasks for Java before purchasing?**  
A: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks for Java dal sito web [qui](https://purchase.aspose.com/buy).

**Q: How can I get support for Aspose.Tasks for Java?**  
A: Puoi ottenere supporto dal forum della community di Aspose.Tasks [qui](https://forum.aspose.com/c/tasks/15).

**Q: Is there a temporary license available for Aspose.Tasks for Java?**  
A: Sì, puoi ottenere una licenza temporanea per scopi di test dal sito Aspose [qui](https://purchase.aspose.com/temporary-license/).

## Conclusione
Seguendo questi passaggi hai imparato a **create project object**, **add extended attribute** e a sfruttare le funzioni di valutazione per **generate project report** automaticamente. Ora puoi estendere questa base per costruire analisi di progetto più avanzate, dashboard personalizzate o strumenti di pianificazione automatizzati—tutto alimentato da Aspose.Tasks for Java.

---

**Ultimo Aggiornamento:** 2026-02-13  
**Testato Con:** Aspose.Tasks for Java 24.10  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}