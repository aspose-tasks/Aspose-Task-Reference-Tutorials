---
date: 2025-12-07
description: Erfahren Sie, wie Sie Projektdateien speichern, MS Project‑Formeln schreiben
  und lesen sowie benutzerdefinierte Feldformeln mit Aspose.Tasks für Java hinzufügen.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Projektdatei speichern und MS‑Project‑Formeln mit Aspose.Tasks schreiben
url: /de/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projektdatei speichern und MS‑Project‑Formeln mit Aspose.Tasks schreiben

## Einführung
Im Bereich des Projektmanagements ist der effektive Umgang mit Daten von größter Bedeutung. Aspose.Tasks für Java ist eine robuste Lösung, die die Manipulation und das Extrahieren von Daten aus Microsoft‑Project‑Dateien ermöglicht. Eine leistungsstarke Funktion ist das Schreiben und Lesen von MS‑Project‑Formeln. **Sie lernen außerdem, wie Sie die *Projektdatei speichern* können, nachdem Sie diese Formeln angewendet haben**, sodass Ihre Änderungen für zukünftige Analysen erhalten bleiben. Dieses Tutorial führt Sie Schritt für Schritt durch die Nutzung dieser Funktionalität, um Ihre Projektmanagement‑Aufgaben zu verbessern.

## Schnellantworten
- **Was bewirkt „Projektdatei speichern“?** Es schreibt alle im Speicher vorgenommenen Änderungen zurück in eine .mpp‑Datei auf der Festplatte.  
- **Kann ich benutzerdefinierte Feldformeln hinzufügen?** Ja – Sie können ein benutzerdefiniertes Feld erstellen und eine Formel wie „doppelte Aufgaben‑Kosten“ zuweisen.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welches IDE funktioniert am besten?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, VS Code) kann das Beispiel kompilieren.  
- **Ist die API mit der neuesten MS‑Project‑Version kompatibel?** Aspose.Tasks unterstützt alle aktuellen .mpp‑Formate.

## Was bedeutet „Projektdatei speichern“ in Aspose.Tasks?
Eine Projektdatei zu speichern bedeutet, den aktuellen Zustand des `Project`‑Objekts – einschließlich Aufgaben, Ressourcen und aller benutzerdefinierten Formeln – in einer physischen Microsoft‑Project‑Datei (`.mpp`) zu persistieren. Dieser Vorgang ist nach Änderungen wie dem Hinzufügen eines benutzerdefinierten Feldes oder dem Ändern von Aufgaben‑Kosten unerlässlich.

## Warum ein benutzerdefiniertes Feld hinzufügen und eine benutzerdefinierte Feldformel erstellen?
Ein benutzerdefiniertes Feld bietet einen flexiblen Container für zusätzliche Informationen, die von den Standardfeldern nicht abgedeckt werden. Durch das Anfügen einer Formel – etwa einer, die **Aufgaben‑Kosten verdoppelt** – automatisieren Sie Berechnungen, reduzieren manuelle Fehler und halten Ihre Planungsdaten konsistent.

## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. **Java Development Kit (JDK)** – Java 8 oder höher auf Ihrem Rechner installiert.  
2. **Aspose.Tasks für Java** – Download und Installation von [hier](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Wählen Sie Ihre bevorzugte IDE für die Java‑Entwicklung (IntelliJ IDEA, Eclipse, VS Code usw.).  

## Pakete importieren
Um zu beginnen, importieren Sie die notwendigen Pakete in Ihr Java‑Projekt:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Schritt 1: Datenverzeichnis einrichten
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Definieren Sie den Ordner, in dem Ihre MS‑Project‑Dateien liegen. Dort laden Sie die Quelldatei und später **Projektdatei speichern**.

## Schritt 2: Projektdatei laden
```java
Project project = new Project(dataDir + "project.mpp");
```
Laden Sie die vorhandene Microsoft‑Project‑Datei in ein `Project`‑Objekt, um deren Inhalte zu lesen oder zu ändern.

## Schritt 3: Benutzerdefiniertes Feld hinzufügen und benutzerdefinierte Feldformel erstellen
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
In diesem Schritt **fügen wir das benutzerdefinierte Feld** „Double Costs“ hinzu und **erstellen die benutzerdefinierte Feldformel**, die die Aufgabe‑`[Cost]` mit 2 multipliziert, wodurch **Aufgaben‑Kosten verdoppelt** werden. Die Methode `setFormula` bettet die Berechnung direkt in die Projektdatei ein.

## Schritt 4: Aufgabe hinzufügen und Kosten festlegen
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Erstellen Sie eine neue Aufgabe und weisen Sie ihr Grundkosten von `100` zu. Beim Speichern des Projekts zeigt das benutzerdefinierte Feld automatisch `200` an, weil die zuvor definierte Formel angewendet wird.

## Schritt 5: Projektdatei speichern
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Abschließend **Projektdatei speichern** mit allen Änderungen. Die Methode `save` schreibt das aktualisierte Projekt, einschließlich des neuen benutzerdefinierten Feldes und seiner berechneten Werte, nach `saved.mpp`.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|--------|-----|
| **Formel wird nicht angewendet** | Benutzerdefiniertes Feld nicht zur `ExtendedAttributes`‑Sammlung des Projekts hinzugefügt. | Sicherstellen, dass `project.getAttributes().add(attr);` vor dem Speichern ausgeführt wird. |
| **Datei nicht gefunden** | Falscher `dataDir`‑Pfad. | Prüfen, ob der Verzeichnis‑String mit einem Pfad‑Trennzeichen (`/` oder `\\`) endet. |
| **Kosten erscheinen als 0** | Aufgaben‑Kosten wurden vor dem Speichern nicht gesetzt. | `task.set(Tsk.COST, ...)` vor `project.save` aufrufen. |

## Häufig gestellte Fragen
**F: Ist Aspose.Tasks mit allen Versionen von MS Project kompatibel?**  
A: Ja, Aspose.Tasks unterstützt ein breites Spektrum an MS Project‑Versionen, von älteren .mpp‑Formaten bis zu den neuesten Releases.

**F: Kann ich Aspose.Tasks in mein bestehendes Java‑Projekt integrieren?**  
A: Absolut. Die API ist für eine nahtlose Integration konzipiert; fügen Sie einfach die Aspose.Tasks‑JAR zu Ihrem Klassenpfad hinzu.

**F: Gibt es Einschränkungen bei den Arten von Formeln, die ich erstellen kann?**  
A: Die Bibliothek unterstützt die meisten nativen MS Project‑Formelsyntaxen, einschließlich arithmetischer, logischer und integrierter Funktionen. Sehr komplexe benutzerdefinierte Funktionen können Work‑arounds erfordern.

**F: Unterstützt Aspose.Tasks den plattformübergreifenden Einsatz?**  
A: Ja, die Bibliothek läuft auf jeder Plattform, die Java unterstützt, einschließlich Windows, Linux und macOS.

**F: Wie erhalte ich technischen Support für Aspose.Tasks?**  
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Hilfe oder öffnen Sie ein Support‑Ticket, wenn Sie eine kommerzielle Lizenz besitzen.

## Fazit
In diesem Tutorial haben wir gezeigt, wie man **Projektdatei speichert**, **ein benutzerdefiniertes Feld hinzufügt** und **eine benutzerdefinierte Feldformel erstellt**, die **Aufgaben‑Kosten verdoppelt** – alles mit Aspose.Tasks für Java. Durch Befolgen dieser Schritte können Sie Berechnungen automatisieren, Ihre Projektdaten anreichern und sicherstellen, dass alle Änderungen für zukünftige Berichte und Analysen erhalten bleiben.

---

**Zuletzt aktualisiert:** 2025-12-07  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}