---
title: Attributi attività estesi in Aspose.Tasks
linktitle: Attributi attività estesi in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Esplora gli attributi delle attività estese in Aspose.Tasks per Java. Guida passo passo, domande frequenti e supporto. Ottimizza la gestione del tuo progetto oggi!
weight: 16
url: /it/java/task-properties/extended-task-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Attributi attività estesi in Aspose.Tasks

## introduzione
Benvenuti nella nostra guida completa sull'utilizzo degli attributi di attività estesi in Aspose.Tasks per Java. Aspose.Tasks è una potente libreria Java che ti consente di lavorare senza problemi con i documenti di Microsoft Project. In questo tutorial, approfondiremo gli attributi estesi delle attività e dimostreremo come utilizzarli per migliorare le capacità di gestione dei progetti.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
- Conoscenza base della programmazione Java.
- Java Development Kit (JDK) installato sul tuo computer.
- Un ambiente di sviluppo integrato (IDE) come IntelliJ o Eclipse.
## Importa pacchetti
Inizia importando i pacchetti necessari per dare il via al tuo progetto Aspose.Tasks:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Ora suddividiamo l'esempio in più passaggi per guidarti attraverso il processo:
## Passaggio 1: accesso all'attività e agli attributi estesi
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## Passaggio 2: recupero dell'ID campo e del GUID valore
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## Passaggio 3: gestione di diversi tipi di attributi
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
Ripeti questi passaggi per ogni attività del tuo progetto per esplorare e manipolare gli attributi estesi dell'attività.
## Conclusione
In conclusione, comprendere e utilizzare gli attributi estesi delle attività in Aspose.Tasks per Java può migliorare significativamente le capacità di gestione dei progetti. Questa guida fornisce una solida base per iniziare questo viaggio.
## Domande frequenti
### Posso modificare gli attributi dell'attività estesa a livello di codice?
Sì, puoi modificare gli attributi dell'attività estesa utilizzando Aspose.Tasks per Java. Fare riferimento alla documentazione per istruzioni dettagliate.
### È disponibile una versione di prova?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.Tasks per Java?
 Per supporto, visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Come posso ottenere una licenza temporanea?
 È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso acquistare la versione completa di Aspose.Tasks per Java?
 Puoi acquistare la versione completa[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
