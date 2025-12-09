---
date: 2025-12-09
description: Impara come impostare la directory dei dati e configurare la visualizzazione
  del diagramma di Gantt in Aspose.Tasks usando Java. Questa guida mostra anche come
  personalizzare i campi della tabella e configurare i progetti Java del diagramma
  di Gantt passo dopo passo.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Imposta la directory dei dati per la visualizzazione del diagramma di Gantt
  in Aspose.Tasks
url: /it/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Impostare la Directory dei Dati per la Visualizzazione del Diagramma di Gantt in Aspose.Tasks

## Introduzione
In questo tutorial, imparerai **come impostare la directory dei dati** e configurare la visualizzazione del diagramma di Gantt di MS Project in progetti Aspose.Tasks usando Java. Aspose.Tasks è una robusta API Java che consente di manipolare i file Microsoft Project programmaticamente. Alla fine di questa guida sarai in grado di **personalizzare i campi della tabella**, regolare la directory dei dati e visualizzare il tuo progetto esattamente come desideri.

## Risposte Rapide
- **Qual è il primo passo?** Imposta il percorso della directory dei dati dove risiedono i file del tuo progetto.  
- **Quale libreria è necessaria?** Aspose.Tasks per Java (scaricabile dal sito ufficiale).  
- **Posso aggiungere attributi personalizzati?** Sì – puoi definire attributi estesi e mostrarli nel diagramma di Gantt.  
- **Ho bisogno di una licenza per i test?** È disponibile una licenza temporanea per scopi di valutazione.  
- **Quale IDE funziona meglio?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, NetBeans) funzionerà.

## Cos'è “impostare la directory dei dati” e perché è importante?
Impostare la directory dei dati indica ad Aspose.Tasks dove leggere e scrivere i file di progetto. Senza un percorso corretto l'API non può trovare i tuoi file `.mpp`, causando errori FileNotFound. Definire questa directory all'inizio del tuo codice rende il resto del flusso di lavoro pulito e ripetibile.

## Perché personalizzare i campi della tabella in un diagramma di Gantt?
I campi della tabella personalizzati ti consentono di mostrare informazioni aggiuntive — come attributi personalizzati, dati delle risorse o note specifiche del progetto — direttamente nella visualizzazione Gantt. Questo rende il diagramma più informativo per gli stakeholder e riduce la necessità di passare tra più report.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – qualsiasi versione recente (8+).  
2. **Libreria Aspose.Tasks** – scaricala da [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, o qualsiasi editor compatibile con Java che preferisci.

## Importare i Pacchetti
Per prima cosa, importa lo spazio dei nomi Aspose.Tasks così da poter lavorare con le sue classi:

```java
import com.aspose.tasks.*;
```

## Guida Passo‑Passo

### Passo 1: Configurare la Directory dei Dati
Definisci la cartella che contiene i tuoi file di progetto. Questo è il passo **impostare la directory dei dati** su cui si concentra il tutorial.

```java
String dataDir = "Your Data Directory";
```

Sostituisci `"Your Data Directory"` con il percorso assoluto della cartella dove è memorizzato `project.mpp`.

### Passo 2: Caricare il File di Progetto
Crea un'istanza `Project` caricando un file Microsoft Project esistente.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Passo 3: Aggiungere una Nuova Attività
Inserisci una nuova attività (task) nella radice del progetto.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Passo 4: Definire un Attributo Personalizzato
Crea una definizione di attributo personalizzato che potrai successivamente associare ai task.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Passo 5: Aggiungere l'Attributo Personalizzato al Task
Assegna il nuovo attributo definito al task che hai creato.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Passo 6: Personalizzare la Tabella – **customize table fields**
Aggiungi l'attributo personalizzato come colonna nella tabella del diagramma di Gantt, specificando larghezza, titolo e allineamento.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Passo 7: Salvare il Progetto
Salva le modifiche in un nuovo file che può essere aperto in Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problemi Comuni e Soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **FileNotFoundException** durante il caricamento del progetto | Il percorso **impostare la directory dei dati** è errato o manca una barra finale. | Verifica che `dataDir` punti alla cartella esatta e includi il separatore di file corretto (`/` o `\\`). |
| Attributo personalizzato non visibile nella visualizzazione Gantt | Il campo della tabella è stato aggiunto all'indice sbagliato o la larghezza della colonna è troppo piccola. | Assicurati che `table.getTableFields().add(3, attrField);` utilizzi un indice valido e regola `setWidth` secondo necessità. |
| LicenseException durante il salvataggio | Nessuna licenza valida è stata applicata per l'uso in produzione. | Applica una licenza temporanea o permanente prima di chiamare `project.save()`. |

## Domande Frequenti

**Q: Posso usare Aspose.Tasks con altri linguaggi di programmazione?**  
A: Sì, Aspose.Tasks è disponibile per più linguaggi di programmazione tra cui .NET, Java e C++.

**Q: È disponibile una versione di prova gratuita per Aspose.Tasks?**  
A: Sì, puoi scaricare una versione di prova gratuita da [here](https://releases.aspose.com/).

**Q: Dove posso trovare supporto per Aspose.Tasks?**  
A: Puoi trovare supporto e fare domande sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Come posso acquistare una licenza per Aspose.Tasks?**  
A: Puoi acquistare una licenza da [here](https://purchase.aspose.com/buy).

**Q: Ho bisogno di una licenza temporanea per scopi di test?**  
A: Sì, puoi ottenere una licenza temporanea da [here](https://purchase.aspose.com/temporary-license/).

## Conclusione
Ora hai imparato come **impostare la directory dei dati**, aggiungere una nuova attività, definire e associare un attributo personalizzato, e **personalizzare i campi della tabella** in una visualizzazione del diagramma di Gantt usando Aspose.Tasks per Java. Questi passaggi ti danno il pieno controllo su come i dati del progetto vengono visualizzati, rendendo i tuoi diagrammi di Gantt più informativi e su misura per le esigenze dei tuoi stakeholder.

---

**Ultimo Aggiornamento:** 2025-12-09  
**Testato Con:** Aspose.Tasks Java 24.12 (latest)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}