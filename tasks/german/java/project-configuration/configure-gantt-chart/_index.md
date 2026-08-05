---
date: 2026-02-13
description: Erfahren Sie, wie Sie eine neue Aktivität erstellen, das Datenverzeichnis
  festlegen und das Projekt als MPP in Aspose.Tasks Java speichern. Diese Schritt‑für‑Schritt‑Anleitung
  behandelt außerdem die Anpassung von Tabellenspalten.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man eine neue Aktivität erstellt & das Datenverzeichnis für Aspose.Tasks
  festlegt
url: /de/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man neue Aktivität erstellt und das Datenverzeichnis festlegt – Aspose.Tasks

## Einleitung
In diesem Tutorial lernen Sie **wie Sie das Datenverzeichnis festlegen**, wie Sie **eine neue Aktivität erstellen** und wie Sie **ein Projekt als MPP speichern**, während Sie die Gantt‑MS‑Project‑Diagrammansicht in Aspose.Tasks‑Projekten mit Java konfigurieren. Aspose.Tasks ist eine robuste Java‑API, mit der Sie Microsoft‑Project‑Dateien programmgesteuert manipulieren können. Am Ende dieses Leitfadens können Sie **Tabellenfelder anpassen**, das Datenverzeichnis ändern und Ihr Projekt genau so visualisieren, wie Sie es benötigen.

## Schnelle Antworten
- **Was ist der erste Schritt?** Legen Sie den Pfad des Datenverzeichnisses fest, in dem Ihre Projektdateien liegen.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (von der offiziellen Website herunterladbar).  
- **Kann ich benutzerdefinierte Attribute hinzufügen?** Ja – Sie können erweiterte Attribute definieren und im Gantt‑Diagramm anzeigen.  
- **Brauche ich eine Lizenz für Tests?** Eine temporäre Lizenz ist für Evaluierungszwecke verfügbar.  
- **Welche IDE funktioniert am besten?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) funktioniert.

## Was bedeutet „Datenverzeichnis festlegen“ und warum ist das wichtig?
Das Festlegen des Datenverzeichnisses teilt Aspose.Tasks mit, wo Projektdateien gelesen und geschrieben werden sollen. Ohne einen korrekten Pfad kann die API Ihre `.mpp`‑Dateien nicht finden, was zu FileNotFound‑Fehlern führt. Die Definition dieses Verzeichnisses zu Beginn Ihres Codes sorgt dafür, dass der restliche Workflow sauber und wiederholbar ist.

## Warum Tabellenspalten in einem Gantt‑Diagramm anpassen?
Benutzerdefinierte Tabellenspalten ermöglichen es, zusätzliche Informationen – wie benutzerdefinierte Attribute, Ressourcendaten oder projektspezifische Notizen – direkt in der Gantt‑Ansicht anzuzeigen. Das macht das Diagramm für Stakeholder informativer und reduziert die Notwendigkeit, zwischen mehreren Berichten zu wechseln.

## Wie erstellt man eine neue Aktivität?
Eine neue Aktivität (Aufgabe) zu erstellen ist einer der Kernvorgänge beim Aufbau oder der Aktualisierung eines Projektplans. Durch das programmatische Hinzufügen von Aufgaben können Sie die Erstellung komplexer Projektpläne automatisieren, Daten aus anderen Systemen integrieren oder Massenänderungen ohne manuelle Bearbeitung vornehmen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – jede aktuelle Version (8 +).  
2. **Aspose.Tasks‑Bibliothek** – laden Sie sie von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor Ihrer Wahl.

## Pakete importieren
Importieren Sie zunächst den Aspose.Tasks‑Namespace, damit Sie mit dessen Klassen arbeiten können:

```java
import com.aspose.tasks.*;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre Projektdateien enthält. Dies ist der **set data directory**‑Schritt, auf den sich das Tutorial konzentriert.

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad zu dem Ordner, in dem `project.mpp` gespeichert ist.

### Schritt 2: Projektdatei laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie eine vorhandene Microsoft‑Project‑Datei laden.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Schritt 3: Neue Aktivität hinzufügen
Fügen Sie eine neue Aufgabe (Aktivität) in die Wurzel des Projekts ein. Dies demonstriert **how to create new activity** programmgesteuert.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Schritt 4: Benutzerdefiniertes Attribut definieren
Erstellen Sie eine Definition für ein benutzerdefiniertes Attribut, das Sie später Aufgaben zuweisen können.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Schritt 5: Benutzerdefiniertes Attribut zur Aufgabe hinzufügen
Weisen Sie das neu definierte Attribut der zuvor erstellten Aufgabe zu.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Schritt 6: Tabelle anpassen – **customize table fields**
Fügen Sie das benutzerdefinierte Attribut als Spalte in die Gantt‑Diagrammtabelle ein und geben Sie Breite, Titel und Ausrichtung an.

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

### Schritt 7: Projekt speichern
Speichern Sie die Änderungen in einer neuen Datei, die in Microsoft Project geöffnet werden kann. Dieser Schritt **saves the project as MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **FileNotFoundException** beim Laden des Projekts | Der **set data directory**‑Pfad ist falsch oder es fehlt ein abschließender Schrägstrich. | Stellen Sie sicher, dass `dataDir` exakt auf den Ordner zeigt und den richtigen Dateiseparator (`/` oder `\\`) enthält. |
| Benutzerdefiniertes Attribut im Gantt‑Diagramm nicht sichtbar | Das Tabellenspaltenfeld wurde am falschen Index eingefügt oder die Spaltenbreite ist zu klein. | Vergewissern Sie sich, dass `table.getTableFields().add(3, attrField);` einen gültigen Index verwendet und passen Sie `setWidth` nach Bedarf an. |
| LicenseException beim Speichern | Es wurde keine gültige Lizenz für die Produktion angewendet. | Laden Sie vor `project.save()` eine temporäre oder permanente Lizenz. |

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks mit anderen Programmiersprachen verwenden?**  
A: Ja, Aspose.Tasks ist für mehrere Programmiersprachen verfügbar, darunter .NET, Java und C++.

**Q: Gibt es eine kostenlose Testversion für Aspose.Tasks?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen.

**Q: Wo finde ich Support für Aspose.Tasks?**  
A: Support und Fragen finden Sie im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

**Q: Wie kann ich eine Lizenz für Aspose.Tasks erwerben?**  
A: Sie können eine Lizenz von [hier](https://purchase.aspose.com/buy) kaufen.

**Q: Benötige ich eine temporäre Lizenz für Testzwecke?**  
A: Ja, Sie können eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

## Fazit
Sie haben nun gelernt, wie Sie **das Datenverzeichnis festlegen**, **eine neue Aktivität erstellen**, ein benutzerdefiniertes Attribut definieren und zuweisen sowie **das Projekt als MPP speichern**, während Sie **Tabellenfelder anpassen** in einer Gantt‑Diagrammansicht mit Aspose.Tasks für Java. Diese Schritte geben Ihnen die volle Kontrolle darüber, wie Projektdaten angezeigt werden, und machen Ihre Gantt‑Diagramme informativer und besser auf die Bedürfnisse Ihrer Stakeholder zugeschnitten.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}