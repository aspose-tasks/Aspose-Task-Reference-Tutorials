---
date: 2026-01-28
description: Scopri come leggere gli attributi di attività estesi usando Aspose.Tasks
  per Java e cambiare il tipo di campo personalizzato in modo efficiente.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Leggi gli attributi di attività estesi con Aspose.Tasks per Java
url: /it/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggere gli attributi di attività estesi con Aspose.Tasks per Java

## Introduzione
In questo tutorial completo scoprirai come **read extended task attributes** dai file Microsoft Project utilizzando la libreria Aspose.Tasks per Java. Che tu stia creando uno strumento di reporting, sincronizzando dati, o abbia semplicemente bisogno di una comprensione più approfondita dei campi personalizzati, padroneggiare questa funzionalità ti consentirà di estrarre ogni informazione memorizzata in un progetto. Ti guideremo attraverso la configurazione necessaria, ti mostreremo come cambiare il tipo di campo personalizzato durante l'elaborazione degli attributi e ti forniremo consigli pratici per evitare gli errori più comuni.

## Risposte rapide
- **Cosa significa “read extended task attributes”?** Si riferisce all'estrazione dei valori dei campi personalizzati che vanno oltre le proprietà di attività predefinite in un file Project.  
- **Quale classe fornisce l'accesso a questi attributi?** La classe `ExtendedAttribute` in Aspose.Tasks.  
- **È necessaria una licenza per eseguire il codice?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso cambiare il tipo di attributo a runtime?** Sì – utilizza l'istruzione `switch` per **switch custom field type** basato su `CustomFieldType`.  
- **È compatibile con Java 8 e versioni successive?** Assolutamente, l'API supporta JDK 8+.

## Cos'è read extended task attributes?
Gli attributi di attività estesi sono campi definiti dall'utente (testo, data, numero, flag, ecc.) che integrano le proprietà standard delle attività in Microsoft Project. Aspose.Tasks li espone tramite la collezione `ExtendedAttribute` collegata a ciascun oggetto `Task`, consentendo di leggere o modificare i loro valori programmaticamente.

## Perché leggere gli attributi di attività estesi?
- **Visibilità completa:** Ottieni una visione dei dati personalizzati che gli stakeholder hanno aggiunto al programma.  
- **Automazione:** Popola dashboard, genera report personalizzati o migra dati verso altri sistemi senza esportazione manuale.  
- **Flessibilità:** Lavora con qualsiasi tipo di campo personalizzato — testo, data, durata, costo, flag — gestendo ogni caso in modo appropriato.

## Prerequisiti
- Conoscenza di base della programmazione Java.  
- Java Development Kit (JDK) installato sulla tua macchina.  
- Un IDE come IntelliJ IDEA o Eclipse.  

## Importare i pacchetti
Inizia importando le classi necessarie per il progetto Aspose.Tasks:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Passo 1: Accesso a Task e Attributi Estesi
Carica un file Project e itera attraverso ogni attività per accedere ai suoi attributi estesi:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Passo 2: Recuperare l'ID del campo e il GUID del valore
Stampa gli identificatori interni che ti aiutano a capire a quale campo personalizzato ti stai riferendo:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Passo 3: Come cambiare il tipo di campo personalizzato quando si leggono gli attributi di attività estesi
Utilizza un'istruzione `switch` su `CustomFieldType` per gestire correttamente ogni possibile tipo di dato:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Ripeti questi passaggi per ogni attività nel tuo progetto per esplorare e manipolare ogni attributo di attività esteso.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Valori null restituiti** | Verifica che il campo personalizzato sia effettivamente popolato nel file .mpp di origine. |
| **Tipo errato visualizzato** | Assicurati di utilizzare il `CustomFieldType` corretto nell'istruzione `switch`; tipi non corrispondenti causeranno valori predefiniti. |
| **Rallentamento delle prestazioni su progetti grandi** | Elabora le attività in batch o filtra solo le attività necessarie usando `project.getRootTask().getChildren().stream()` con i predicati appropriati. |

## Domande frequenti
### Posso modificare gli attributi di attività estesi programmaticamente?
Sì, puoi modificare gli attributi di attività estesi usando Aspose.Tasks per Java. Consulta la documentazione per istruzioni dettagliate.

### È disponibile una versione di prova?
Sì, puoi accedere alla prova gratuita [here](https://releases.aspose.com/).

### Dove posso trovare supporto per Aspose.Tasks per Java?
Per supporto, visita il [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Come posso ottenere una licenza temporanea?
Puoi ottenere una licenza temporanea [here](https://purchase.aspose.com/temporary-license/).

### Dove posso acquistare la versione completa di Aspose.Tasks per Java?
Puoi acquistare la versione completa [here](https://purchase.aspose.com/buy).

---

**Ultimo aggiornamento:** 2026-01-28  
**Testato con:** Aspose.Tasks Java API (ultima versione stabile)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}