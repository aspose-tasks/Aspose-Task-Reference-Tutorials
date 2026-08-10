---
date: 2026-06-15
description: Erfahren Sie, wie Sie zeitphasenbezogene Daten aus MS Project‑Ressourcen
  mit Aspose.Tasks für Java extrahieren. Schritt‑für‑Schritt‑Anleitung zum Abrufen
  einer Ressource nach ID.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Zeitphasenbezogene Daten für Ressourcen in Aspose.Tasks lesen
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Zeitphasenbezogene Daten für Ressourcen in Aspose.Tasks lesen – Ressource nach
  ID abrufen
url: /de/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zeitphasenbezogene Daten für Ressourcen in Aspose.Tasks

## Einführung
In diesem Tutorial lernen Sie **how to get resource by id** und lesen dessen zeitphasenbezogene Daten mit Aspose.Tasks für Java. Wir führen Sie durch jeden Schritt – vom Einrichten des Projektordners bis zum Ausgeben von Arbeits‑ und Kosten‑zeitphasenwerten – damit Sie wertvolle Planungsinformationen aus jeder Microsoft‑Project‑Datei programmgesteuert extrahieren können. Aspose.Tasks für Java ist eine umfassende API, die Entwicklern ermöglicht, Microsoft‑Project‑Dateien zu erstellen, zu lesen, zu ändern und zu konvertieren, ohne dass Microsoft Project installiert sein muss, und unterstützt eine breite Palette von Projektmanagement‑Funktionen und Formaten.

## Schnelle Antworten
- **Was macht „get resource by id“?** Sie ruft ein bestimmtes `Resource`‑Objekt aus einem `Project` anhand seiner eindeutigen Kennung ab.  
- **Welche Bibliothek verarbeitet zeitphasenbezogene Daten?** Aspose.Tasks für Java stellt die `Resource.getTimephasedData`‑API bereit.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich große Projekte lesen?** Ja – Aspose.Tasks kann Dateien mit bis zu 10.000 Aufgaben verarbeiten, ohne die gesamte Datei in den Speicher zu laden.  
- **Welche Java‑Version wird benötigt?** Java 8 oder höher; die Bibliothek ist mit allen gängigen JDKs kompatibel.

## Was ist „get resource by id“?
`get resource by id` ist ein Methodenaufruf, der eine `Resource`‑Instanz aus einem geladenen `Project` anhand der numerischen ID der Ressource abruft. Dieser Vorgang ermöglicht präzisen Zugriff auf die detaillierten Eigenschaften einer Ressource, wie deren Zuordnungen, Kalender und benutzerdefinierte Felder, und ist entscheidend, um zeitphasenbezogene Arbeits‑ oder Kostendaten, die mit dieser spezifischen Ressource verknüpft sind, zu extrahieren.

## Warum Aspose.Tasks für zeitphasenbezogene Daten verwenden?
Aspose.Tasks unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** (MPP, XML, CSV usw.) und kann zeitphasenbezogene Arbeits‑ und Kostendaten für Ressourcen über mehrjährige Zeitpläne hinweg extrahieren, wobei der Speicherverbrauch gering bleibt. Die API liefert standardmäßig Daten in 15‑Minuten‑Intervallen, was Ihnen detaillierte Einblicke für Berichte oder benutzerdefinierte Analysen ermöglicht.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass das JDK auf Ihrem System installiert ist. Sie können es von der [Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen und den Installationsanweisungen folgen.  
2. Aspose.Tasks for Java Bibliothek: Laden Sie die Aspose.Tasks for Java‑Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter und befolgen Sie die in der Dokumentation bereitgestellten Installationsanweisungen.

## Pakete importieren
Der erste Schritt besteht darin, die erforderlichen Aspose.Tasks‑Klassen in Ihre Java‑Quelldatei zu importieren.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Schritt 1: Datenverzeichnis einrichten
Zuerst definieren Sie das Verzeichnis, in dem sich Ihre MS‑Project‑Datei befindet. Das Trennen des Datenordners vom Quellcode erleichtert die Wartung des Projekts.

```java
String dataDir = "Your Data Directory";
```

## Schritt 2: MS Project-Vorlagendatei lesen
Geben Sie den Namen Ihrer MS‑Project‑Vorlagendatei an. Die Verwendung einer Vorlage sorgt für konsistente Spalteneinstellungen in verschiedenen Projekten.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Schritt 3: Eingabedatei als Projekt lesen
Die Klasse `Project` ist das Kernobjekt von Aspose.Tasks, das eine Microsoft‑Project‑Datei im Speicher repräsentiert. Das Laden der Datei verschafft Ihnen programmgesteuerten Zugriff auf Aufgaben, Ressourcen und Zeitpläne.

```java
Project project = new Project(dataDir + fileName);
```

## Schritt 4: Ressource nach ID abrufen
Um eine bestimmte Ressource abzurufen, rufen Sie die Methode `getResources().getById(id)` auf. Dies ist die exakt referenzierte Operation des Haupt‑Schlüsselworts.

```java
Resource resource = project.getResources().getByUid(1);
```

## Schritt 5: Zeitphasenbezogene Daten für Ressourcenarbeit ausgeben
Sobald Sie das `Resource`‑Objekt haben, können Sie `resource.getTimephasedData(ResourceTimephasedDataType.Work)` aufrufen, um Arbeitszuweisungen über die Zeit zu erhalten. Die zurückgegebene Sammlung enthält `TimephasedData`‑Objekte, die das Startdatum, Enddatum und die Arbeitsmenge für jedes Intervall umfassen.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Schritt 6: Zeitphasenbezogene Daten für Ressourcenkosten ausgeben
Analog liefert `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` Kosteninformationen, aufgeschlüsselt nach denselben Zeitintervallen. Dies ist nützlich für Budget‑ und Kostenverfolgungsberichte.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Wie man Ressource nach ID in einer Zeile abruft?
Laden Sie das Projekt und rufen Sie dann `project.getResources().getById(5)` auf – ersetzen Sie **5** durch die tatsächliche Ressourcen‑ID, die Sie benötigen. Dieser einzelne Aufruf gibt das `Resource`‑Objekt zurück, woraufhin Sie dessen zeitphasenbezogene Daten, Zuordnungen oder benutzerdefinierte Felder abfragen können. Die Methode läuft in O(1)‑Zeit, da Ressourcen intern indiziert sind.

## Häufige Probleme und Lösungen
- **Resource not found** – Stellen Sie sicher, dass die ID in der Projektdatei existiert; IDs beginnen bei 1 und sind pro Ressource eindeutig.  
- **Empty timephased data** – Prüfen Sie, ob die Ressource Arbeits‑ oder Kosten‑Zuordnungen hat; andernfalls ist die Sammlung leer.  
- **Large file performance** – Verwenden Sie `Project.setLoadOptions(LoadOptions.fromFile(...))`, um Lazy Loading für Projekte größer als 500 MB zu aktivieren.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks andere Projekttypen außer Microsoft Project verarbeiten?**  
A: Ja, Aspose.Tasks unterstützt MPP, XML, CSV und mehrere andere Formate, sodass Sie über verschiedene Standards hinweg lesen und schreiben können.

**Q: Ist Aspose.Tasks mit verschiedenen Java‑Entwicklungsumgebungen kompatibel?**  
A: Absolut. Die Bibliothek funktioniert mit allen gängigen IDEs (IntelliJ IDEA, Eclipse, NetBeans) und Build‑Tools (Maven, Gradle).

**Q: Kann ich Projektdaten mit Aspose.Tasks manipulieren?**  
A: Ja, Sie können Aufgaben, Ressourcen, Zuordnungen und sogar benutzerdefinierte Felder über die API erstellen, ändern und löschen.

**Q: Ist Aspose.Tasks für Unternehmens‑Projekte geeignet?**  
A: Ja. Unternehmen setzen Aspose.Tasks für die Verarbeitung großer Datenmengen, Batch‑Konvertierungen und serverseitige Berichte ein, da keine Installation von Microsoft Project erforderlich ist.

**Q: Wo finde ich Unterstützung, wenn ich beim Einsatz von Aspose.Tasks auf Probleme stoße?**  
A: Sie können das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) besuchen, um Hilfe von der Community und dem Support‑Team zu erhalten.

## Fazit
In diesem Tutorial haben wir gelernt, wie man **get resource by id** verwendet und dessen zeitphasenbezogene Arbeits‑ und Kostendaten mit Aspose.Tasks für Java ausliest. Durch das Befolgen dieser Schritte können Sie effizient wertvolle Planungsinformationen aus Ihren Projektdateien extrahieren und in benutzerdefinierte Berichts‑ oder Analyse‑Pipelines integrieren.

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose

## Verwandte Tutorials

- [Ressource zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/resource-management/create-resources/)
- [MS Project‑Ressourcenkosten mit Aspose.Tasks für Java verwalten](/tasks/java/resource-management/resource-cost/)
- [Arbeitswochen in Java aus dem MS Project‑Kalender mit Aspose.Tasks lesen](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}