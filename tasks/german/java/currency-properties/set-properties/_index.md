---
date: 2025-12-04
description: Lernen Sie, wie Sie die Währung in Aspose.Tasks‑Java‑Projekten festlegen,
  einschließlich dem Ändern der Währung und des Währungssymbols in Java. Bearbeiten
  Sie Microsoft‑Project‑Dateien mühelos.
language: de
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Wie man die Währung in Aspose.Tasks-Projekten festlegt – Java-Leitfaden
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So setzen Sie die Währung in Aspose.Tasks-Projekten – Java‑Leitfaden

## Einführung
In diesem Tutorial lernen Sie **wie man die Währung** für eine Microsoft‑Project‑Datei mit der Aspose.Tasks‑Java‑API festlegt. Egal, ob Sie die *Währung* für internationale Teams *ändern* müssen oder das *Währungssymbol* in Java anpassen wollen, die nachfolgenden Schritte führen Sie durch den Prozess mit klaren Erklärungen und sofort ausführbarem Code.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Tasks for Java.  
- **Kann ich das Währungssymbol ändern?** Ja – verwenden Sie `CurrencySymbolPositionType` und `Prj.CURRENCY_SYMBOL`.  
- **Welche Dateiformate werden unterstützt?** XML, MPP und über `SaveFileFormat`.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine Lizenz erforderlich.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein Basis‑Setup.

## Was ist „Währung“ in einer Projektdatei?
Die Währung eines Projekts definiert, wie Kostenwerte angezeigt werden – Code (z. B. `AUD`), Anzahl der Dezimalstellen, Symbol (`$`) und die Position des Symbols. Das Festlegen dieser Eigenschaften stellt sicher, dass jedes kostenbezogene Feld (Ressourcensätze, Aufgabenbudgets usw.) das korrekte monetäre Format für Ihr Publikum widerspiegelt.

## Warum Aspose.Tasks zum Ändern der Währung verwenden?
- **Keine Microsoft‑Project‑Installation erforderlich** – Dateien auf jedem Server manipulieren.  
- **Vollständige API‑Abdeckung** – alle währungsbezogenen Felder sind über `Prj`‑Konstanten verfügbar.  
- **Plattformübergreifend** – funktioniert auf Windows, Linux und macOS mit jeder Java‑kompatiblen IDE.  
- **Hohe Leistung** – große Projektdateien schnell und zuverlässig verarbeiten.

## Voraussetzungen
1. **Java Development Kit (JDK)** – Version 8 oder höher.  
2. **Aspose.Tasks for Java** – laden Sie das neueste JAR von der [Aspose.Tasks‑Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.  
3. **Eine IDE** – Eclipse, IntelliJ IDEA oder ein beliebiger Editor Ihrer Wahl.  
4. **Ein beschreibbarer Ordner** – in dem die erzeugte Projektdatei gespeichert wird.

## Pakete importieren
Importieren Sie zunächst die Klassen, die Zugriff auf Projekteigenschaften und die Dateiverarbeitung bieten.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis definieren
Geben Sie den Ordner an, der Ihre Quelldateien enthält und in den die Ausgabe geschrieben wird.

```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Neue Projektinstanz erstellen
Instanziieren Sie ein neues `Project`‑Objekt. Dieses Objekt stellt eine Microsoft‑Project‑Datei im Arbeitsspeicher dar.

```java
Project project = new Project();
```

### Schritt 3: Währungseigenschaften festlegen
Hier legen wir die Details zum **Setzen der Währung** fest, wie Code, Dezimalstellen, Symbol und Symbolposition.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro‑Tipp:** Wenn Sie die **Währung** für ein bestehendes Projekt **ändern** müssen, laden Sie die Datei einfach mit `new Project("file.mpp")`, bevor Sie die obigen Einstellungen anwenden.

### Schritt 4: Aktualisiertes Projekt speichern
Schreiben Sie das Projekt im gewünschten Format zurück auf die Festplatte. In diesem Beispiel verwenden wir das XML‑Format, Sie können aber auch `SaveFileFormat.MPP` wählen.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Schritt 5: Erfolg bestätigen
Geben Sie eine freundliche Meldung aus, damit Sie wissen, dass der Vorgang ohne Fehler abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

## Häufige Probleme & Lösungen

| Problem | Ursache | Lösung |
|---------|---------|--------|
| **`NullPointerException` on `project.save`** | `dataDir` ist kein gültiger Pfad oder hat keine Schreibberechtigung. | Stellen Sie sicher, dass das Verzeichnis existiert und Ihr Java‑Prozess Schreibzugriff hat. |
| **Währungssymbol wird nicht angezeigt** | Die Symbolposition ist für Ihr Gebietsschema falsch eingestellt. | Verwenden Sie `CurrencySymbolPositionType.Before`, wenn das Symbol dem Betrag vorausgehen soll. |
| **Projektdatei lässt sich nicht in MS Project öffnen** | Speichern im älteren Format mit inkompatiblen Einstellungen. | Speichern Sie mit `SaveFileFormat.MPP` für volle Kompatibilität mit neueren MS‑Project‑Versionen. |

## Häufig gestellte Fragen

**F: Kann ich in einem einzigen Projekt mehrere Währungen mit Aspose.Tasks festlegen?**  
A: Ja, Aspose.Tasks ermöglicht es, mehrere Währungen innerhalb einer einzigen Projektdatei zu verwalten, indem Sie die Währungseigenschaften pro Ressource oder pro Aufgabe festlegen.

**F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Auf jeden Fall. Die Bibliothek unterstützt MPP‑Dateien von Project 2000 bis zu den neuesten Versionen sowie XML und andere Formate.

**F: Bietet Aspose.Tasks Unterstützung für benutzerdefinierte Währungsformate  
A: Ja, Sie können benutzerdefinierte Symbole, Dezimalstellen und Positionen definieren, um jede regionale Anforderung zu erfüllen.

**F: Kann ich Aspose.Tasks mit anderen Java‑Bibliotheken oder -Frameworks integrieren?**  
A: Sicherlich. Die API ist reines Java, sodass sie nahtlos mit Spring, Hibernate, Maven, Gradle und anderen Ökosystemen funktioniert.

**F: Wo finde ich zusätzliche Unterstützung oder Hilfe für Aspose.Tasks?**  
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Hilfe oder konsultieren Sie die offizielle Dokumentation für detaillierte API‑Referenzen.

## Fazit
Sie wissen jetzt, **wie man die Währung festlegt**, wie man **Währungswerte** ändert und wie man **Währungssymbole im Java‑Stil** mit Aspose.Tasks für Java ändert. Diese Möglichkeiten ermöglichen es Ihnen, Kostendaten für globale Teams anzupassen, länderspezifische Berichte zu erstellen und Ihre Projektdateien über Grenzen hinweg konsistent zu halten.

**Zuletzt aktualisiert:** 2025-12-04  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}