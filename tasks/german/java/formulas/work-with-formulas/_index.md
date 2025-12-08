---
date: 2025-12-07
description: Erfahren Sie, wie Sie ein **Testprojekt erstellen** und ein **benutzerdefiniertes
  Feld hinzufügen**, während Sie Microsoft Project‑Dateien mit Aspose.Tasks für Java
  manipulieren.
language: de
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Testprojekt erstellen und Formeln mit Aspose.Tasks für Java verwenden
url: /java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Testprojekt erstellen und Formeln mit Aspose.Tasks für Java verwenden

## Einleitung
In diesem Tutorial **erstellen Sie Testprojekt**-Dateien, fügen ein benutzerdefiniertes Feld hinzu und arbeiten mit MS Project-Formeln mithilfe der Aspose.Tasks-Bibliothek für Java. Aspose.Tasks macht es einfach, **Microsoft Project**-Daten programmgesteuert zu **manipulieren** – egal, ob Sie Zeitpläne erstellen, Daten berechnen oder Berichte automatisieren müssen. Am Ende der Anleitung haben Sie ein ausführbares Beispiel, das ein erweitertes Attribut definiert, eine Frist für eine Aufgabe festlegt und das Projekt als MPP-Datei speichert.

## Schnelle Antworten
- **Worum geht es im Tutorial?** Erstellen eines Testprojekts, Hinzufügen eines benutzerdefinierten Feldes, Definieren eines erweiterten Attributs und Festlegen einer Aufgabenfrist mit einer Formel.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (neueste Version).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Lizenz erforderlich.  
- **Welche IDE kann ich verwenden?** Jede Java-IDE (IntelliJ IDEA, Eclipse, VS Code), die JDK 8+ unterstützt.  
- **Wie lange dauert die Umsetzung?** Etwa 10‑15 Minuten, um den Code zu kopieren und auszuführen.

## Was ist ein „Testprojekt“ in Aspose.Tasks?
Ein **Testprojekt** ist eine leichtgewichtige Microsoft Project-Datei, die programmgesteuert erstellt wird, um Funktionen zu demonstrieren oder zu validieren. Sie enthält einen minimalen Satz von Aufgaben, Ressourcen und benutzerdefinierten Feldern, die Sie manipulieren können, ohne reale Projektdaten zu beeinflussen.

## Warum Aspose.Tasks zum Manipulieren von Microsoft Project verwenden?
- **Vollständige API-Abdeckung** – Zugriff auf jede Project-, Task- und Resource-Eigenschaft.  
- **Keine Office-Installation erforderlich** – funktioniert auf Servern, CI-Pipelines und Docker-Containern.  
- **Plattformübergreifend** – läuft auf Windows, Linux und macOS mit demselben Java-Code.  
- **Robuste Formelumgebung** – berechnet Daten, Dauern und benutzerdefinierte Felder direkt in der Projektdatei.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK) 8+** – Download von der Oracle-Website oder OpenJDK verwenden.  
- **Aspose.Tasks für Java** – das neueste JAR von der [Aspose.Tasks für Java Download-Seite](https://releases.aspose.com/tasks/java/) beziehen und zum Klassenpfad oder zu den Maven/Gradle-Abhängigkeiten Ihres Projekts hinzufügen.

## Pakete importieren
Zuerst importieren wir die benötigten Klassen:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Testprojekt mit benutzerdefiniertem Feld erstellen
Wir beginnen mit dem **Erstellen eines Testprojekts** und dem Hinzufügen eines benutzerdefinierten Feldes, das später unser Formelergebnis enthält.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Profi‑Tipp:* `CreateTestProjectWithCustomField()` ist eine Hilfsmethode, die einen minimalen Zeitplan erstellt und ein erweitertes Attribut registriert, das bereit für die Zuweisung einer Formel ist.

### Schritt 2: Erweitertes Attribut definieren (benutzerdefiniertes Feld hinzufügen)
Als Nächstes **definieren wir ein erweitertes Attribut** – im Wesentlichen das benutzerdefinierte Feld – und geben ihm einen lesbaren Alias. Hier fügen wir die **Logik für das benutzerdefinierte Feld** hinzu.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** macht das Feld im Project lesbar.  
- **Formula** berechnet die Anzahl der Tage zwischen dem *Finish*-Datum einer Aufgabe und ihrer *Deadline*.

### Schritt 3: Frist für eine Aufgabe festlegen (Deadline‑Aufgabe hinzufügen & Aufgabenfrist setzen)
Jetzt **fügen wir Deadline‑Aufgabendaten** hinzu, indem wir die *Deadline*-Eigenschaft einer bestimmten Aufgabe setzen.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Die `Calendar`-Instanz definiert den genauen Fristzeitpunkt.  
- `set(Tsk.DEADLINE, …)` **setzt die Aufgabenfrist** für die ausgewählte Aufgabe.

### Schritt 4: Projekt speichern (Microsoft Project-Datei manipulieren)
Abschließend **manipulieren wir Microsoft Project**, indem wir die Änderungen in einer MPP-Datei speichern.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Sie können `SaveFile.mpp` in Microsoft Project öffnen, um das benutzerdefinierte Feld, das Formelergebnis und die Frist im Zeitplan zu sehen.

## Häufige Probleme und Lösungen

| Problem | Lösung |
|-------|----------|
| **Formula not evaluating** | Stellen Sie sicher, dass die `Formula`-Zeichenkette des Attributs korrekte Feldnamen verwendet (z. B. `[Deadline]`, `[Finish]`). |
| **Task not found** | Überprüfen Sie, ob die Aufgaben-ID (`1` im Beispiel) existiert; verwenden Sie `project.getRootTask().getChildren().size()` zum Debuggen. |
| **License exception** | Wenden Sie eine gültige Aspose.Tasks-Lizenz an, bevor Sie API-Methoden aufrufen (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?**  
**A:** Ja, Aspose.Tasks bietet APIs für .NET, Java und andere Plattformen, sodass Sie **Microsoft Project**-Dateien in der Sprache Ihrer Wahl **manipulieren** können.

**F: Gibt es eine kostenlose Testversion für Aspose.Tasks?**  
**A:** Auf jeden Fall. Laden Sie eine voll funktionsfähige Testversion von der [Aspose.Tasks-Download-Seite](https://releases.aspose.com/) herunter.

**F: Wo finde ich ausführliche Dokumentation zu Aspose.Tasks?**  
**A:** Die offiziellen Dokumente finden Sie unter [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**F: Wie kann ich Support für Aspose.Tasks erhalten?**  
**A:** Besuchen Sie das [Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15), um Fragen zu stellen und Erfahrungen mit der Community zu teilen.

**F: Benötige ich eine temporäre Lizenz für die Evaluierung?**  
**A:** Eine temporäre Lizenz ist für kurzfristige Tests verfügbar; Sie können eine [hier](https://purchase.aspose.com/temporary-license/) anfordern.

---

**Zuletzt aktualisiert:** 2025-12-07  
**Getestet mit:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}