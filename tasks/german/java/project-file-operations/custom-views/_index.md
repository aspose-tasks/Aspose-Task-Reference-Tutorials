---
date: 2025-12-18
description: Erfahren Sie, wie Sie in Aspose.Tasks für Java eine Ansicht erstellen,
  einschließlich des Speicherns von Projektansichten und des Festlegens von Ansichtseigenschaften.
  Steigern Sie die Effizienz im Projektmanagement mit maßgeschneiderten benutzerdefinierten
  MS Project‑Ansichten.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Wie man eine Ansicht erstellt: Benutzerdefinierte MS Project‑Ansichten in
  Aspose.Tasks'
url: /de/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Ansichten erstellt: Benutzerdefinierte MS Project‑Ansichten in Aspose.Tasks

## Einführung
Wenn Sie nach **how to create view** suchen, die den einzigartigen Berichtserfordernissen Ihres Projekts entspricht, sind Sie hier genau richtig. Im Projektmanagement kann das Anpassen von Ansichten die Übersichtlichkeit und Effizienz beim Umgang mit Aufgaben und Ressourcen erheblich verbessern. **Aspose.Tasks for Java** stellt Ihnen eine umfangreiche API zur Verfügung, um **add custom view java**‑artige Lösungen zu implementieren, sodass Sie MS Project‑Ansichten exakt nach Ihren Bedürfnissen gestalten können. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess, vom Einrichten eines Projekts bis zum Speichern der Projektansicht.

## Schnelle Antworten
- **Was ist der Hauptzweck?** Eine benutzerdefinierte MS Project‑Ansicht mit Aspose.Tasks for Java zu erstellen und zu speichern.  
- **Welche Klasse erstellt eine Ansicht?** `GanttChartView` (oder andere Ansichtstypen).  
- **Wie bringe ich die Ansicht ins Menü?** `view.setShowInMenu(true)` setzen.  
- **Wie speichere ich die Ansicht zusammen mit dem Projekt?** `MPPSaveOptions` mit `setWriteViewData(true)` verwenden.  
- **Benötige ich eine Lizenz?** Ja, für den Produktionseinsatz ist eine gültige Aspose.Tasks‑Lizenz erforderlich.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

### Java‑Entwicklungsumgebung
Stellen Sie sicher, dass Java auf Ihrem System installiert ist.

### Aspose.Tasks for Java
Laden Sie Aspose.Tasks for Java von [hier](https://releases.aspose.com/tasks/java/) herunter und installieren Sie es.

## Pakete importieren
Importieren Sie zunächst die notwendigen Pakete in Ihr Java‑Projekt:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Schritt 1: Projekt einrichten
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Schritt 2: Ansicht erstellen
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Schritt 3: Ansichtseigenschaften anpassen *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### Wie man die Ansicht im Menü anzeigt
Der Aufruf `view.setShowInMenu(true)` sorgt dafür, dass die neu erstellte Ansicht im MS Project **view menu** erscheint und End‑Benutzern schnellen Zugriff ermöglicht.

## Schritt 4: Ansichtseinstellungen optimieren
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Schritt 5: Ansicht zum Projekt hinzufügen *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Schritt 6: Projekt speichern *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Warum das Speichern der Projektansicht wichtig ist
Durch `options.setWriteViewData(true)` wird Aspose.Tasks angewiesen, **save project view**‑Informationen in die MPP‑Datei zu schreiben, sodass die benutzerdefinierte Ansicht über Sitzungen hinweg erhalten bleibt.

## Schritt 7: Ansichtseigenschaften prüfen
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Häufige Anwendungsfälle
- **Stakeholder‑Reporting:** Eine Ansicht erstellen, die nur hochrangige Meilensteine und kritische Aufgaben zeigt.  
- **Ressourcenzuweisung:** Eine Ansicht bauen, die Ressourcen zusammen mit ihren zugewiesenen Aufgaben für schnelle Kapazitätsprüfungen auflistet.  
- **Druckfertige Dokumente:** Seiteneinstellungen (wie in Schritt 4) anpassen, um druckbare Projektschnappschüsse zu erzeugen.

## Tipps zur Fehlersuche
- **Ansicht erscheint nicht im Menü:** Prüfen Sie, ob `view.setShowInMenu(true)` vor dem Speichern aufgerufen wurde.  
- **Spalten fehlen im Ausdruck:** Sicherstellen, dass `setFirstColumnsCount` die benötigten Spalten abdeckt und `setPrintFirstColumnsCountOnAllPages(true)` aktiviert ist.  
- **Lizenz‑Ausnahmen:** Bei Lizenzfehlern prüfen Sie, ob eine gültige Aspose.Tasks‑Lizenzdatei geladen wurde, bevor das `Project`‑Objekt erstellt wird.

## Häufig gestellte Fragen
### Q1: Kann ich Ansichten über Gantt‑Diagramme hinaus anpassen?
A: Ja, Aspose.Tasks for Java bietet Flexibilität, verschiedene Ansichtstypen jenseits von Gantt‑Diagrammen zu customisieren, einschließlich Tabellen und Diagrammen.

### Q2: Ist Aspose.Tasks for Java für groß angelegte Projekte geeignet?
A: Absolut. Die Bibliothek ist darauf ausgelegt, Projekte jeder Größe zu bewältigen und bietet robuste Leistung sowie Speicherverwaltung.

### Q3: Unterstützt Aspose.Tasks for Java das Exportieren von Ansichten in verschiedene Formate?
A: Ja, Sie können Ansichten in PDF, XLSX, HTML und andere Formate exportieren, um einen nahtlosen Austausch über Plattformen hinweg zu gewährleisten.

### Q4: Kann ich die Erstellung benutzerdefinierter Ansichten mit Aspose.Tasks for Java automatisieren?
A: Sicherlich. Die API ermöglicht vollständige Automatisierung, sodass Sie benutzerdefinierte Ansichten programmgesteuert erzeugen und verwalten können.

### Q5: Gibt es ein Community‑Forum für den Support von Aspose.Tasks for Java?
A: Ja, Sie finden Hilfe und können sich mit anderen Nutzern im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) zu Java‑bezogenen Fragen und Diskussionen austauschen.

---

**Zuletzt aktualisiert:** 2025-12-18  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}