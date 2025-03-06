---
title: Lese- und Schreibratenskala für Ressourcenzuweisungen in Aspose.Tasks
linktitle: Lese- und Schreibratenskala für Ressourcenzuweisungen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie in diesem umfassenden Tutorial, wie Sie die Ratenskalierung für Ressourcenzuweisungen in Aspose.Tasks für Java effektiv verwalten.
weight: 20
url: /de/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lese- und Schreibratenskala für Ressourcenzuweisungen in Aspose.Tasks

## Einführung
In diesem Tutorial befassen wir uns mit der Verwaltung der Ratenskala für Ressourcenzuweisungen mithilfe von Aspose.Tasks für Java, einer robusten Bibliothek für die programmgesteuerte Arbeit mit Microsoft Project-Dateien. Wenn Sie diese Schritte befolgen, können Sie die Ratenskalierungseinstellungen für Ressourcenzuweisungen in Ihren Java-Anwendungen effektiv bearbeiten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem System das Java Development Kit (JDK) installiert ist.
2.  Aspose.Tasks for Java-Bibliothek: Laden Sie die Aspose.Tasks for Java-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete importieren, um mit den Aspose.Tasks-Funktionen arbeiten zu können. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Beginnen Sie mit der Einrichtung Ihres Java-Projekts und beziehen Sie die Aspose.Tasks-Bibliothek in Ihre Abhängigkeiten ein.
## Schritt 2: Laden Sie die Projektdatei
Laden Sie die Projektdatei, mit der Sie arbeiten möchten, in Ihre Java-Anwendung.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Schritt 3: Fügen Sie eine Aufgabe hinzu
Fügen Sie Ihrem Projekt eine neue Aufgabe hinzu.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Schritt 4: Ressourcen definieren
Definieren Sie materielle und immaterielle Ressourcen und geben Sie deren Typen an.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Schritt 5: Ressourcen der Aufgabe zuweisen
Ordnen Sie der Aufgabe die zuvor definierten Ressourcen mit ihren Tariftypen zu.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Schritt 6: Speichern Sie das Projekt
Speichern Sie das Projekt mit den geänderten Ressourcenzuweisungen.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Schritt 7: Ressourcenzuweisungen abrufen
Laden Sie das gespeicherte Projekt erneut und rufen Sie Ressourcenzuweisungen ab, um die Tarifeinstellungen zu überprüfen.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Abschluss
Die Verwaltung der Ratenskala für Ressourcenzuweisungen in Aspose.Tasks für Java ist für ein effektives Projektmanagement von entscheidender Bedeutung. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die Ratenskalierungseinstellungen für Ressourcenzuweisungen in Ihren Java-Anwendungen nahtlos bearbeiten.
## FAQs
### F1: Kann ich Aspose.Tasks für Java mit jeder Java-IDE verwenden?
A: Ja, Aspose.Tasks für Java ist mit allen wichtigen Java-IDEs kompatibel, einschließlich IntelliJ IDEA, Eclipse und NetBeans.
### F2: Unterstützt Aspose.Tasks neben MPP auch andere Dateiformate?
A: Ja, Aspose.Tasks unterstützt verschiedene Dateiformate, einschließlich MPP, XML und HTML.
### F3: Ist Aspose.Tasks für das Projektmanagement auf Unternehmensebene geeignet?
A: Absolut, Aspose.Tasks bietet umfassende Funktionen für die Verwaltung von Projekten jeder Größenordnung und eignet sich daher für das Projektmanagement auf Unternehmensebene.
### F4: Kann ich Ressourcenzuweisungen über die Tarifstaffel hinaus weiter anpassen?
A: Ja, Aspose.Tasks bietet umfangreiche Funktionen zum Anpassen von Ressourcenzuweisungen, einschließlich Kosten-, Arbeits- und Daueranpassungen.
### F5: Gibt es ein Community-Forum für die Aspose.Tasks-Unterstützung?
 A: Ja, Sie können im Aspose.Tasks-Forum Unterstützung finden und mit anderen Benutzern interagieren[Hier](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
