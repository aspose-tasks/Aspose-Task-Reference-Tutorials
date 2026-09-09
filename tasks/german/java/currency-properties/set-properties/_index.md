---
date: 2026-09-09
description: Erfahren Sie, wie Sie das Währungssymbol in Aspose.Tasks Java‑Projekten
  ändern, Währungscodes festlegen, Symbole anpassen und benutzerdefinierte Formate
  für Microsoft Project‑Dateien anwenden.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Währungseigenschaften in Aspose.Tasks-Projekten festlegen
og_description: Wie man das Währungssymbol in Aspose.Tasks mit Java ändert. Entdecken
  Sie schrittweise Anleitungen, Voraussetzungen und Tipps zur Anpassung der Kostenformatierung
  von Projekten.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Wie man das Währungssymbol in Aspose.Tasks ändert – Java‑Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Wie man das Währungssymbol in Aspose.Tasks-Projekten ändert – Java‑Leitfaden
url: /de/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man das Währungssymbol in Aspose.Tasks – Java‑Leitfaden

## Einführung
In diesem Tutorial lernen Sie **wie man das Währungssymbol ändert** für eine Microsoft Project‑Datei mithilfe der Aspose.Tasks Java‑API. Egal, ob Sie Berichte für einen ausländischen Kunden erstellen, Budgets über mehrere Regionen konsolidieren oder einfach die Buchhaltungsstandards Ihres Unternehmens einhalten müssen, die Anpassung des Währungssymbols stellt sicher, dass jedes kostenbezogene Feld das korrekte Geldzeichen anzeigt. Der Leitfaden führt Sie durch jeden Schritt, von der Einrichtung der Entwicklungsumgebung bis zum Persistieren der Änderungen in einer neuen oder bestehenden Projektdatei.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Tasks for Java.  
- **Kann ich das Währungssymbol ändern?** Ja – setzen Sie `Prj.CURRENCY_SYMBOL` und wählen Sie `CurrencySymbolPositionType`.  
- **Welche Dateiformate werden unterstützt?** XML, MPP und viele andere über `SaveFileFormat`.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; für die Produktion ist eine Lizenz erforderlich.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein Basis‑Setup.

## Wie man das Währungssymbol in Aspose.Tasks mit Java ändert?
Laden Sie das Zielprojekt (oder erstellen Sie ein neues), setzen Sie die gewünschten Währungseigenschaften und speichern Sie die Datei. Der gesamte Vorgang besteht aus drei API‑Aufrufen: Erstellen oder Laden eines `Project`‑Objekts, Zuweisen des Währungscodes, Symbols und der Position und anschließend Aufruf von `project.save`. Dieser Ansatz funktioniert sowohl für neue Projekte als auch für bestehende Dateien, ohne dass Microsoft Project installiert sein muss.

## Warum Aspose.Tasks zum Ändern von Währungen verwenden?
Aspose.Tasks bietet **vollständige API‑Abdeckung für über 30 währungsbezogene Eigenschaften**, sodass Sie Code, Symbol, Dezimalstellen und Position an einer Stelle definieren können. Die Bibliothek verarbeitet mehrseitige Project‑Dateien in weniger als einer Sekunde auf typischer Server‑Hardware und funktioniert unter Windows, Linux und macOS ohne zusätzliche Abhängigkeiten.

## Voraussetzungen
1. **Java Development Kit (JDK) 8 oder höher** – die API erfordert mindestens JDK 8.  
2. **Aspose.Tasks for Java** – laden Sie das neueste JAR von der [Aspose.Tasks Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.  
3. **Eine IDE** – Eclipse, IntelliJ IDEA oder ein beliebiger Editor, der Java unterstützt.  
4. **Ein beschreibbarer Ordner** – in dem die erzeugte Projektdatei gespeichert wird.

## Pakete importieren
Die folgenden Klassen geben Ihnen Zugriff auf Projekteigenschaften, Dateiverarbeitung und Währungseinstellungen.  

`Project` – repräsentiert eine Microsoft Project‑Datei im Speicher.  
`Prj` – enthält Konstanten für alle Projekte‑Ebene‑Eigenschaften, einschließlich Währungsfelder.  
`CurrencySymbolPositionType` – enumeriert mögliche Positionen für das Währungssymbol (vor oder nach dem Betrag).  

Diese Importe sind erforderlich, bevor irgendein Code ein Projekt manipulieren kann.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis definieren
Wählen Sie einen Ordner, der Ihre Quelldateien enthält und in dem die Ausgabe geschrieben wird. Stellen Sie sicher, dass das Verzeichnis existiert und Ihr Java‑Prozess Schreibrechte hat.

### Schritt 2: Neue Projektinstanz erstellen
Die `Project`‑Klasse ist das oberste Objekt von Aspose.Tasks, das eine einzelne Project‑Datei im Speicher repräsentiert. Durch die Instanziierung wird ein leeres Projekt erstellt, das bereit zur Konfiguration ist.

### Schritt 3: Währungseigenschaften festlegen
Hier konfigurieren Sie den Währungscode, die Anzahl der Dezimalstellen, das Symbol selbst und die Position des Symbols.  

- **Währungscode** – ein dreibuchstabiger ISO‑4217‑Code wie `AUD` oder `USD`.  
- **Dezimalstellen** – typischerweise 2 für die meisten Währungen.  
- **Währungssymbol** – das Zeichen oder die Zeichenkette, die bei Beträgen angezeigt wird, z. B. `$` oder `€`.  
- **Symbolposition** – `CurrencySymbolPositionType.Before` platziert das Symbol vor der Zahl; `After` platziert es dahinter.  

Diese Einstellungen wirken sich auf jedes kostenbezogene Feld (Ressourcensätze, Aufgabenbudgets usw.) im Projekt aus.

> **Pro‑Tipp:** Wenn Sie die Währung für eine bestehende Datei ändern müssen, laden Sie sie mit `new Project("file.mpp")` bevor Sie die obigen Einstellungen anwenden.

### Schritt 4: Aktualisiertes Projekt speichern
Schreiben Sie das Projekt mit dem gewünschten Format zurück auf die Festplatte. Das XML‑Format ist menschenlesbar, während `SaveFileFormat.MPP` die volle Kompatibilität mit Microsoft Project bewahrt.

### Schritt 5: Erfolg bestätigen
Geben Sie eine kurze Meldung oder einen Log‑Eintrag aus, damit Sie wissen, dass der Vorgang ohne Fehler abgeschlossen wurde. Das ist besonders in automatisierten Pipelines nützlich.

## Häufige Probleme & Lösungen
| Problem | Grund | Lösung |
|---------|-------|--------|
| **`NullPointerException` on `project.save`** | `dataDir` ist kein gültiger Pfad oder hat keine Schreibrechte. | Stellen Sie sicher, dass das Verzeichnis existiert und Ihr Java‑Prozess Schreibzugriff hat. |
| **Currency symbol not showing** | Die Symbolposition ist für Ihr Gebietsschema falsch eingestellt. | Verwenden Sie `CurrencySymbolPositionType.Before`, wenn das Symbol der Zahl vorausgehen soll. |
| **Project file does not open in MS Project** | Speicherung in einem älteren Format mit inkompatiblen Einstellungen. | Speichern Sie mit `SaveFileFormat.MPP` für volle Kompatibilität mit aktuellen MS‑Project‑Versionen. |

## Häufig gestellte Fragen

**F: Kann ich mehrere Währungen in einem einzigen Projekt mit Aspose.Tasks festlegen?**  
A: Ja, Sie können unterschiedliche Währungseinstellungen einzelnen Ressourcen oder Aufgaben zuweisen, indem Sie deren jeweilige Kostenfelder ändern, nachdem die projektweite Währung festgelegt wurde.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project‑Dateien kompatibel?**  
A: Absolut. Die Bibliothek unterstützt MPP‑Dateien von Project 2000 bis zu den neuesten Versionen sowie XML und andere Austauschformate.

**F: Bietet Aspose.Tasks Unterstützung für benutzerdefinierte Währungsformate?**  
A: Ja, Sie können benutzerdefinierte Symbole, Dezimalstellen und Positionen definieren, um jede regionale Anforderung zu erfüllen, und diese Einstellungen werden in der gespeicherten Datei beibehalten.

**F: Kann ich Aspose.Tasks in andere Java‑Frameworks integrieren?**  
A: Sicherlich. Die API ist reines Java, sodass sie nahtlos mit Spring, Hibernate, Maven, Gradle und anderen Ökosystemen funktioniert.

**F: Wo finde ich weitere Hilfe oder Beispiele?**  
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Unterstützung oder konsultieren Sie die offizielle Dokumentation für detaillierte API‑Referenzen.

## Fazit
Sie wissen jetzt **wie man das Währungssymbol ändert** in Aspose.Tasks‑Projekten mit Java, wie man den Währungscode setzt, Dezimalstellen anpasst und ein benutzerdefiniertes Symbol anwendet. Diese Möglichkeiten ermöglichen Ihnen, länderspezifische Kostenberichte zu erstellen, Projektbudgets an regionale Buchhaltungsstandards anzupassen und Ihre Microsoft Project‑Dateien konsistent über globale Teams hinweg zu halten.

---

**Zuletzt aktualisiert:** 2026-09-09  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Verwandte Tutorials

- [java-Projekteigenschaften – Währungssymbol aus MPP mit Aspose.Tasks für Java extrahieren](/tasks/java/currency/currency-symbols/)
- [Währungseigenschaften in Java mit Aspose.Tasks‑Projekten lesen](/tasks/java/currency-properties/read-properties/)
- [Währungscodes in Java mit Aspose.Tasks verwalten](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}