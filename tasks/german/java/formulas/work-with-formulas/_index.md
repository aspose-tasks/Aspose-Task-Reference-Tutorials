---
date: 2026-02-13
description: Erfahren Sie, wie Sie die Tage zwischen Daten berechnen, ein Testprojekt
  erstellen und ein benutzerdefiniertes Feld hinzufügen, während Sie Microsoft‑Project‑Dateien
  mit Aspose.Tasks für Java manipulieren.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tage zwischen Daten mit Aspose.Tasks für Java berechnen
url: /de/java/formulas/work-with-formulas/
weight: 11
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Berechnen von Tagen zwischen Daten mit Aspose.Tasks für Java

## Einführung
In diesem Tutorial **berechnen Sie Tage zwischen Daten**, indem Sie ein Testprojekt erstellen, ein benutzerdefiniertes Feld hinzufügen und Microsoft‑Project‑Formeln über die Aspose.Tasks‑Bibliothek für Java verwenden. Egal, ob Sie Zeitpläne erzeugen, Fristen berechnen oder Berichte automatisieren müssen – Aspose.Tasks ermöglicht Ihnen die programmgesteuerte Manipulation von Project‑Daten ohne eine Desktop‑Installation. Am Ende der Anleitung haben Sie ein ausführbares Beispiel, das ein erweitertes Attribut definiert, eine Frist für eine Aufgabe setzt und das Projekt als MPP‑Datei speichert.

## Schnelle Antworten
- **Was behandelt das Tutorial?** Erstellen eines Testprojekts, Hinzufügen eines benutzerdefinierten Feldes, Definieren eines erweiterten Attributs und Setzen einer Aufgabenfrist mit einer Formel zur Berechnung von Tagen zwischen Daten.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (neueste Version).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Welche IDE kann ich verwenden?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, VS Code), die JDK 8+ unterstützt.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten zum Kopieren des Codes und Ausführen.

## Was bedeutet „calculate days between dates“ in Aspose.Tasks?
Das Berechnen von Tagen zwischen Daten bedeutet, eine Project‑Formel zu verwenden, die ein Datumsfeld (z. B. **Finish**) von einem anderen (z. B. **Deadline**) subtrahiert und die numerische Differenz in Tagen zurückgibt. Das ist nützlich, um Terminverschiebungen zu verfolgen, Pufferzeiten zu messen oder benutzerdefinierte Berichte zu erstellen.

## Warum Aspose.Tasks zum Berechnen von Tagen zwischen Daten verwenden?
- **Vollständige API‑Abdeckung** – Zugriff auf jede Project-, Task‑ und Resource‑Eigenschaft.  
- **Keine Office‑Installation erforderlich** – funktioniert auf Servern, CI‑Pipelines und Docker‑Containern.  
- **Plattformübergreifend** – läuft unter Windows, Linux und macOS mit demselben Java‑Code.  
- **Robuste Formelumgebung** – ermöglicht die Definition von Berechnungen wie `[Deadline] - [Finish]` direkt in der Projektdatei.

## Wie man eine Frist für eine Aufgabe festlegt
Eine Frist zu setzen ist der erste Schritt, bevor Sie das Intervall berechnen können. Die Frist wird im Feld `Tsk.DEADLINE` einer Aufgabe gespeichert und kann mit einer `java.util.Calendar`‑Instanz zugewiesen werden.

## Wie man ein erweitertes Attribut definiert
Ein erweitertes Attribut ist das benutzerdefinierte Feld, das das Ergebnis Ihrer Formel enthält. Sie definieren es einmal, geben ihm einen Alias zur besseren Lesbarkeit und hängen dann eine Formel an, die die Datumsdifferenz berechnet.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK) 8+** – Download von der Oracle‑Website oder OpenJDK übernehmen.  
- **Aspose.Tasks für Java** – das neueste JAR von der [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) beziehen und dem Klassenpfad Ihres Projekts oder den Maven/Gradle‑Abhängigkeiten hinzufügen.

## Pakete importieren
Zuerst importieren wir die Klassen, die wir benötigen:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Erstelle ein Testprojekt mit einem benutzerdefinierten Feld
Wir beginnen damit, **ein Testprojekt zu erstellen** und ein benutzerdefiniertes Feld hinzuzufügen, das später das Ergebnis unserer Formel enthält.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` ist eine Hilfsmethode, die einen minimalen Zeitplan erstellt und ein erweitertes Attribut registriert, das bereit für die Zuweisung einer Formel ist.

### Schritt 2: Definiere ein erweitertes Attribut (Benutzerdefiniertes Feld hinzufügen)
Als Nächstes **definieren wir ein erweitertes Attribut** – im Wesentlichen das benutzerdefinierte Feld – und geben ihm einen freundlichen Alias. Hier fügen wir die Logik für das **benutzerdefinierte Feld** hinzu.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** macht das Feld in Project lesbar.  
- **Formel** berechnet die Anzahl der Tage zwischen dem *Finish*-Datum einer Aufgabe und ihrer *Deadline* – das Kernstück von *calculate days between dates*.

### Schritt 3: Frist für eine Aufgabe festlegen (Deadline‑Aufgabe hinzufügen & Aufgabenfrist setzen)
Jetzt **fügen wir Deadline‑Aufgabendaten** hinzu, indem wir die *Deadline*-Eigenschaft einer bestimmten Aufgabe setzen.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Die `Calendar`‑Instanz definiert den genauen Fristzeitpunkt.  
- `set(Tsk.DEADLINE, …)` **setzt die Aufgabenfrist** für die ausgewählte Aufgabe.

### Schritt 4: Projekt speichern (Microsoft Project‑Datei manipulieren)
Abschließend **manipulieren wir Microsoft Project**, indem wir die Änderungen in einer MPP‑Datei persistieren.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Sie können `SaveFile.mpp` in Microsoft Project öffnen, um das benutzerdefinierte Feld, das Formel‑Ergebnis und die Frist im Zeitplan zu sehen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| **Formel wird nicht ausgewertet** | Stellen Sie sicher, dass der `Formula`‑String des Attributs korrekte Feldnamen verwendet (z. B. `[Deadline]`, `[Finish]`). |
| **Aufgabe nicht gefunden** | Prüfen Sie, ob die Aufgaben‑ID (`1` im Beispiel) existiert; verwenden Sie `project.getRootTask().getChildren().size()` zum Debuggen. |
| **Lizenz‑Ausnahme** | Laden Sie eine gültige Aspose.Tasks‑Lizenz, bevor Sie API‑Methoden aufrufen (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?**  
A: Ja, Aspose.Tasks bietet APIs für .NET, Java und weitere Plattformen, sodass Sie **Microsoft Project**‑Dateien in der Sprache Ihrer Wahl **manipulieren** können.

**Q: Gibt es eine kostenlose Testversion von Aspose.Tasks?**  
A: Auf jeden Fall. Laden Sie eine voll funktionsfähige Testversion von der [Aspose.Tasks download page](https://releases.aspose.com/) herunter.

**Q: Wo finde ich ausführliche Dokumentation zu Aspose.Tasks?**  
A: Die offiziellen Dokumente stehen unter [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Wie kann ich Support für Aspose.Tasks erhalten?**  
A: Besuchen Sie das [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), um Fragen zu stellen und Erfahrungen mit der Community zu teilen.

**Q: Benötige ich eine temporäre Lizenz für die Evaluierung?**  
A: Eine temporäre Lizenz ist für kurzfristige Tests verfügbar; Sie können eine Lizenz [hier](https://purchase.aspose.com/temporary-license/) anfordern.

---

**Zuletzt aktualisiert:** 2026-02-13  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}