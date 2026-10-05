---
date: 2026-10-05
description: Erfahren Sie, wie Sie ein Testprojekt erstellen und Tage zwischen Daten
  mit Aspose.Tasks für Java berechnen, ein benutzerdefiniertes Feld hinzufügen und
  MPP-Dateien effizient bearbeiten.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Arbeiten mit Formeln in Aspose.Tasks
og_description: Erstellen Sie ein Testprojekt und berechnen Sie Tage zwischen Daten
  mit Aspose.Tasks für Java. Dieser Leitfaden zeigt, wie man ein benutzerdefiniertes
  Feld hinzufügt, Aufgabenfristen festlegt und das Projekt als MPP-Datei speichert.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Testprojekt erstellen und Tage zwischen Daten berechnen
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Testprojekt erstellen und Tage zwischen Daten berechnen
url: /de/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Testprojekt erstellen und Tage zwischen Daten berechnen

In diesem Tutorial **Testprojekt erstellen** und **Tage zwischen Daten berechnen** indem Sie ein benutzerdefiniertes Feld hinzufügen, ein erweitertes Attribut definieren und eine Microsoft Project‑Formel über die Aspose.Tasks‑Bibliothek für Java anwenden. Egal, ob Sie Zeitpläne erstellen, Fristen berechnen oder Berichte automatisieren müssen, Aspose.Tasks ermöglicht es Ihnen, Projektdaten programmgesteuert zu manipulieren, ohne eine Desktop‑Installation, unterstützt mehr als 50 Eingabe‑ und Ausgabeformate und verarbeitet mehrseitige Dateien im speichereffizienten Modus.

## Schnelle Antworten
- **Worum geht es in diesem Tutorial?** Es zeigt, wie man ein Testprojekt erstellt, ein erweitertes Attribut definiert, eine Aufgabenfrist festlegt und eine Formel verwendet, um Tage zwischen Daten zu berechnen.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks for Java (neueste Version).  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche IDE kann ich verwenden?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, VS Code), die JDK 8+ unterstützt.  
- **Wie lange dauert die Implementierung?** Ungefähr 10‑15 Minuten, um den Code zu kopieren und auszuführen.

## Was bedeutet „Tage zwischen Daten berechnen“ in Aspose.Tasks?
In Aspose.Tasks ist eine Formel ein String, der Aufgabenfelder referenzieren und Berechnungen durchführen kann. `[Deadline] - [Finish]` ist die von Aspose.Tasks verwendete Formelsyntax, um die numerische Differenz in Tagen zwischen zwei Datumsfeldern zurückzugeben. Das Ergebnis wird als numerischer Wert gespeichert, der ganze Tage darstellt und den Sie in einem benutzerdefinierten Feld anzeigen oder für weitere Berechnungen verwenden können.

## Warum Aspose.Tasks zum Berechnen von Tagen zwischen Daten verwenden?
Aspose.Tasks bietet **vollständige API‑Abdeckung** für jede Projekt-, Aufgaben‑ und Ressourcen‑Eigenschaft, läuft unter Windows, Linux und macOS und **erfordert nicht Microsoft Project oder Office**. Die Engine kann Projekte mit **mehr als 500 Aufgaben** in weniger als einer Sekunde auf typischer Server‑Hardware verarbeiten, was sie ideal für CI‑Pipelines, Docker‑Container und hochvolumige Batch‑Verarbeitung macht.

## Wie setze ich eine Frist für eine Aufgabe
java.util.Calendar ist eine Java‑Klasse, die einen bestimmten Zeitpunkt darstellt. Sie setzen eine Frist, indem Sie einen `java.util.Calendar`‑Wert dem Feld `Tsk.DEADLINE` einer Aufgabe zuweisen. Nachdem Sie die Calendar‑Instanz erstellt haben, setzen Sie Jahr, Monat und Tag auf die gewünschte Frist und rufen dann `task.set(Tsk.DEADLINE, calendar);` auf. Die Frist wird in der Projektdatei gespeichert und kann in Formeln wie `[Deadline] - [Finish]` verwendet werden.

## Wie definiere ich ein erweitertes Attribut
Ein erweitertes Attribut ist ein benutzerdefiniertes Feld, das das Ergebnis Ihrer Formel speichert. Sie erstellen es einmal, geben ihm einen freundlichen Alias und hängen den Ausdruck `[Deadline] - [Finish]` an, sodass jede Aufgabe das Intervall automatisch berechnen kann. Erstellen Sie es, indem Sie `ExtendedAttribute` instanziieren, dessen Alias setzen, die Formel zuweisen und es zur Sammlung des Projekts hinzufügen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK) 8+** – herunterladen von der Oracle‑Website oder OpenJDK verwenden.  
- **Aspose.Tasks for Java** – das neueste JAR von der [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) beziehen und zu Ihrem Klassenpfad oder den Maven/Gradle‑Abhängigkeiten hinzufügen.

## Pakete importieren
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Testprojekt mit benutzerdefiniertem Feld erstellen
Wir beginnen mit dem **Erstellen eines Testprojekts** und dem Hinzufügen eines benutzerdefinierten Feldes, das später das Ergebnis unserer Formel enthält.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro Tipp:* `CreateTestProjectWithCustomField()` ist eine Hilfsmethode, die einen minimalen Zeitplan erstellt und ein erweitertes Attribut registriert, das bereit für die Zuweisung einer Formel ist.

### Schritt 2: Erweitertes Attribut definieren (benutzerdefiniertes Feld hinzufügen)
Als Nächstes **definieren wir ein erweitertes Attribut** – im Wesentlichen das benutzerdefinierte Feld – und geben ihm einen freundlichen Alias. Hier fügen wir die Logik zum **Hinzufügen des benutzerdefinierten Feldes** ein.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** macht das Feld in Project lesbar.  
- **Formula** berechnet die Anzahl der Tage zwischen dem *Finish*-Datum einer Aufgabe und ihrer *Deadline* – das Kernstück von *Tage zwischen Daten berechnen*.

### Schritt 3: Frist für eine Aufgabe festlegen (Deadline‑Aufgabe hinzufügen & Aufgabenfrist setzen)
Jetzt fügen wir **Deadline‑Aufgabendaten** hinzu, indem wir die *Deadline*-Eigenschaft einer bestimmten Aufgabe setzen.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Die `Calendar`‑Instanz definiert den genauen Fristzeitpunkt.  
- `set(Tsk.DEADLINE, …)` **setzt die Aufgabenfrist** für die ausgewählte Aufgabe.

### Schritt 4: Projekt speichern (Microsoft‑Project‑Datei manipulieren)
Abschließend **manipulieren wir Microsoft Project**, indem wir die Änderungen in einer MPP‑Datei speichern.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Sie können `SaveFile.mpp` in Microsoft Project öffnen, um das benutzerdefinierte Feld, das Formelergebnis und die Frist im Zeitplan zu sehen.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| **Formel wird nicht ausgewertet** | Stellen Sie sicher, dass der `Formula`‑String des Attributs korrekte Feldnamen verwendet (z. B. `[Deadline]`, `[Finish]`). |
| **Aufgabe nicht gefunden** | Überprüfen Sie, ob die Aufgaben‑ID (`1` im Beispiel) existiert; verwenden Sie `project.getRootTask().getChildren().size()` zum Debuggen. |
| **Lizenzausnahme** | Wenden Sie eine gültige Aspose.Tasks‑Lizenz an, bevor Sie API‑Methoden aufrufen (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?**  
A: Ja, Aspose.Tasks bietet APIs für .NET, Java und andere Plattformen, sodass Sie Microsoft‑Project‑Dateien in der von Ihnen gewählten Sprache manipulieren können.

**Q: Gibt es eine kostenlose Testversion für Aspose.Tasks?**  
A: Auf jeden Fall. Laden Sie eine voll funktionsfähige Testversion von der [Aspose.Tasks download page](https://releases.aspose.com/) herunter.

**Q: Wo finde ich ausführliche Dokumentation zu Aspose.Tasks?**  
A: Die offiziellen Dokumente finden Sie unter [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Wie kann ich Support für Aspose.Tasks erhalten?**  
A: Besuchen Sie das [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), um Fragen zu stellen und Erfahrungen mit der Community zu teilen.

**Q: Benötige ich eine temporäre Lizenz für die Evaluierung?**  
A: Eine temporäre Lizenz ist für kurzfristige Tests verfügbar; Sie können eine über die [temporary license request page](https://purchase.aspose.com/temporary-license/) anfordern.

---

**Zuletzt aktualisiert:** 2026-10-05  
**Getestet mit:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man MPP-Datei erstellt – Leeres Projekt im MPP-Format mit Aspose.Tasks erstellen & speichern](/tasks/java/project-configuration/create-save-mpp/)
- [Projektstartdatum in MS Project mit Aspose.Tasks für Java festlegen](/tasks/java/project-properties/write-project-info/)
- [Wie man ein erweitertes Attribut in Java mit Aspose.Tasks erstellt](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}