---
date: 2026-09-25
description: Erfahren Sie, wie Sie Währungscodes aus MS Project-Dateien mit Aspose.Tasks
  für Java abrufen - der schnelle Weg, den Java-Entwicklern benötigten Währungscode
  zu erhalten.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Verwalten von Währungscodes in Aspose.Tasks
og_description: Abrufen des Währungscodes Java aus MS Project-Dateien mit Aspose.Tasks.
  Dieser Leitfaden zeigt, wie Sie das Projekt lesen, den ISO-Währungsidentifikator
  extrahieren und ihn in Java-Anwendungen einsetzen.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Abrufen des Währungscodes Java aus MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Abrufen des Währungscodes Java aus MS Project mit Aspose.Tasks
url: /de/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Währungscode java aus MS Project mit Aspose.Tasks abrufen

## Einleitung
In diesem Tutorial lernen Sie **wie man den Währungscode java** aus einer MS‑Project‑Datei mithilfe der Aspose.Tasks‑Java‑API abruft. Egal, ob Sie mehr‑währungs‑Finanzberichte erstellen, Projekte über verschiedene Regionen konsolidieren oder einfach das korrekte Währungssymbol in einem nachgelagerten System anzeigen müssen – die nachfolgenden Schritte führen Sie von der Umgebungseinrichtung bis zum einzeiligen Aufruf, der den ISO‑Währungsidentifikator zurückgibt. Am Ende des Leitfadens können Sie jedes unterstützte Projektdateiformat laden und den dreibuchstabigen Währungscode wie `USD`, `EUR` oder `GBP` extrahieren.

## Schnelle Antworten
- **Was macht die API?** Sie liest MS‑Project‑Dateien und stellt Eigenschaften wie den Währungscode bereit.  
- **Welche Sprache wird verwendet?** Java, über die Aspose.Tasks‑Bibliothek für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich den Code in einer Zeile abrufen?** Ja—`prj.get(Prj.CURRENCY_CODE)` gibt den Währungscode‑String sofort zurück.  
- **Ist es mit allen Project‑Versionen kompatibel?** Aspose.Tasks unterstützt mehr als 20 Eingabeformate, einschließlich älterer MPP‑, XML‑ und XER‑Dateien.

## Was bedeutet das Lesen einer MS Project‑Datei?
Das Lesen einer MS‑Project‑Datei bedeutet, programmgesteuert eine *.mpp*‑Datei (oder ein anderes unterstütztes Format wie XML oder XER) zu öffnen und auf deren interne Datenstrukturen zuzugreifen. Diese Strukturen umfassen Aufgaben, Ressourcen, Kalender, Kostentabellen und finanzielle Einstellungen. Durch das Parsen der Datei können Sie Informationen extrahieren, ohne Microsoft Project zu starten, und so automatisierte Berichte, Migrationen und Integrations‑Workflows ermöglichen.

## Warum Aspose.Tasks zum Lesen von MS Project‑Dateien verwenden?
Aspose.Tasks bietet eine reine Java‑Lösung, die die Notwendigkeit von COM‑Interop oder einer lokalen Microsoft‑Project‑Installation eliminiert. Es unterstützt mehr als 20 Dateiformate, kann Projekte mit tausenden von Aufgaben verarbeiten und verbraucht dabei weniger als 100 MB Speicher. Das reichhaltige Objektmodell ermöglicht direkten Zugriff auf Konstanten wie `Prj.CURRENCY_CODE`, sodass Sie Währungsinformationen sofort und zuverlässig abrufen können.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

### Java Development Kit (JDK) installiert
Ein aktuelles JDK (11 oder höher) ist erforderlich. Laden Sie es von der offiziellen Oracle‑Website herunter: [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java library
Holen Sie sich die neuesten Aspose.Tasks‑für‑Java‑Binärdateien und fügen Sie sie dem Klassenpfad Ihres Projekts hinzu. Die vollständige Dokumentation und Download‑Links finden Sie [hier](https://reference.aspose.com/tasks/java/).

## Pakete importieren
Die `Project`‑Klasse und die `Prj`‑Konstanten befinden sich im Namespace `com.aspose.tasks`. Importieren Sie sie am Anfang Ihrer Java‑Quelldatei:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre *.mpp*‑Datei enthält. Passen Sie den Pfad an Ihre Umgebung an, damit die Laufzeit die Projektdatei finden kann.

```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Projektdatei laden
Die `Project`‑Klasse ist das Top‑Level‑Objekt von Aspose.Tasks, das eine einzelne MS‑Project‑Datei im Speicher repräsentiert. Das Erstellen einer Instanz liest die Datei und baut ein In‑Memory‑Modell, das Sie abfragen können.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Schritt 3: Währungscode abrufen
Die Konstante `Prj.CURRENCY_CODE` identifiziert die Eigenschaft, die den ISO‑Währungsidentifikator speichert. Der Aufruf `prj.get(Prj.CURRENCY_CODE)` gibt den dreibuchstabigen Code in einem einzigen Vorgang zurück.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Die Ausgabe ist der dreibuchstabige ISO‑Währungscode (z. B. `USD`, `EUR`, `GBP`), den das Projekt verwendet.

### Schritt 4: Wie man den Währungscode in Java abruft (zusätzlicher Kontext)
Laden Sie Ihr Projekt, rufen Sie `prj.get(Prj.CURRENCY_CODE)` auf und speichern Sie das Ergebnis in einem `String`. Sie können diesen Wert dann an jeden Finanzservice, Reporting‑Engine oder UI‑Komponente weitergeben, die einen Währungsidentifikator benötigt.

### Schritt 5: (optional) Währungscode verwenden
Typische nachgelagerte Szenarien umfassen:

- **Berichtserstellung** – den Code den Kostenspalten voranstellen (`USD 1.200`).  
- **API‑Integration** – den ISO‑Code an Zahlungsgateways senden, die einen Währungsparameter verlangen.  
- **Datenkonsolidierung** – mehrere Projekte nach Währung gruppieren für Portfolio‑Analysen.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|---------|-------|--------|
| **Null‑Ausgabe** | Die Projektdatei definiert keine Währung (Standard ist leer). | Setzen Sie die Währung in Microsoft Project oder weisen Sie sie vor dem Lesen mit `prj.set(Prj.CURRENCY_CODE, "USD");` zu. |
| **Datei nicht gefunden** | Falscher `dataDir`‑Pfad. | Überprüfen Sie den Pfad und stellen Sie sicher, dass der Dateiname exakt übereinstimmt, einschließlich Groß‑/Kleinschreibung. |
| **Nicht unterstützte Dateiversion** | Sehr alte oder beschädigte *.mpp*-Datei. | Aktualisieren Sie auf die neueste Aspose.Tasks‑Version oder konvertieren Sie die Datei zuerst in ein neueres Format in Microsoft Project. |

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks komplexe Projektstrukturen verarbeiten?**  
A: Ja, die API liest mehrstufige Aufgabenhierarchien, Ressourcengruppen, benutzerdefinierte Felder und Kalender ohne Einschränkung.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von MS‑Project‑Dateien kompatibel?**  
A: Absolut. Es unterstützt MPP, XML, XER und andere Formate von Project 98 bis zu den neuesten Office‑Versionen.

**F: Bietet Aspose.Tasks Dokumentation und Support?**  
A: Umfassende API‑Referenz, Code‑Beispiele und dedizierter technischer Support sind auf der Aspose‑Website verfügbar.

**F: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Eine kostenlose Testversion wird angeboten, sodass Sie alle Funktionen, einschließlich der Währungscode‑Extraktion, evaluieren können.

**F: Wo kann ich eine temporäre Lizenz für die Evaluierung erhalten?**  
A: Temporäre Lizenzen sind über die [Website](https://purchase.aspose.com/temporary-license/) erhältlich.

**Zuletzt aktualisiert:** 2026-09-25  
**Getestet mit:** Aspose.Tasks for Java (neueste Version)  
**Autor:** Aspose

## Verwandte Tutorials

- [Projekt Eigenschaften Java – Metadaten mit Aspose.Tasks lesen](/tasks/java/project-properties/)
- [Wie man Projektinformationen aus Microsoft Project mit Aspose.Tasks für Java liest](/tasks/java/project-properties/read-project-info/)
- [MS Project Gliederungscodes in Aspose.Tasks abrufen](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}