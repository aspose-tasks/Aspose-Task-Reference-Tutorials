---
title: Leggi i dati della tabella dal file in Aspose.Tasks
linktitle: Leggi i dati della tabella dal file in Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Sblocca la potenza di Aspose.Tasks per Java. Impara a estrarre i dati delle tabelle dai file in questo tutorial completo.
weight: 17
url: /it/java/project-data-reading/read-table-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi i dati della tabella dal file in Aspose.Tasks

## introduzione
In questo tutorial esploreremo come leggere i dati della tabella da un file utilizzando Aspose.Tasks per Java. Aspose.Tasks è una potente libreria Java che consente agli sviluppatori di lavorare con i documenti di Microsoft Project a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. È possibile scaricarlo e installarlo dal sito Web Oracle.
2.  Aspose.Tasks per Java JAR File: scarica la libreria Aspose.Tasks per Java dal file[Link per scaricare](https://releases.aspose.com/tasks/java/) e includilo nel tuo progetto Java.

## Importa pacchetti
Importa i pacchetti necessari per lavorare con Aspose.Tasks nel tuo progetto Java:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## Passaggio 1: impostare la directory dei dati
Definisci il percorso della directory in cui si trova il file di progetto:
```java
String dataDir = "Your Data Directory";
```
 Sostituire`"Your Data Directory"` con il percorso effettivo della directory dei dati.
## Passaggio 2: caricare il file di progetto
Caricare il file di progetto utilizzando Aspose.Tasks:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 Assicurati di sostituire`"Project2003.mpp"` con il nome del file di progetto.
## Passaggio 3: recuperare le informazioni sulla tabella
Ottieni la tabella dal progetto e scorri i suoi campi:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
Questo frammento di codice recupera informazioni sui campi della tabella come larghezza, titolo e allineamento.

## Conclusione
In questo tutorial, abbiamo imparato come leggere i dati della tabella da un file utilizzando Aspose.Tasks per Java. Seguendo questi passaggi è possibile estrarre e manipolare in modo efficiente i dati dai documenti Microsoft Project nelle applicazioni Java.
## Domande frequenti
### D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?
R: Aspose.Tasks supporta varie versioni di Microsoft Project, inclusi Project 2003, 2007, 2010, 2013 e 2016.
### D: Posso modificare i dati della tabella e salvarli nuovamente nel file di progetto?
R: Sì, puoi utilizzare Aspose.Tasks per modificare i dati della tabella a livello di codice e salvare le modifiche nel file di progetto originale.
### D: Aspose.Tasks richiede una licenza separata per uso commerciale?
 R: Sì, è necessario acquistare una licenza per Aspose.Tasks se intendi utilizzarlo in un ambiente commerciale. È possibile ottenere una licenza da[pagina di acquisto](https://purchase.aspose.com/buy).
### D: È disponibile una prova gratuita per Aspose.Tasks?
 R: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks da[pagina delle uscite](https://releases.aspose.com/).
### D: Dove posso trovare aiuto e supporto per Aspose.Tasks?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)per l'assistenza e il supporto da parte della comunità e del team Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
