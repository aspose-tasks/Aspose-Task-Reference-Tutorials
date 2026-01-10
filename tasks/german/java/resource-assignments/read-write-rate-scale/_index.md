---
date: 2026-01-10
description: Erfahren Sie, wie Sie die Kostenskala lesen und Ressourcen‑Zuweisungen
  in Aspose.Tasks für Java verwalten. Definieren Sie Materialressourcen, wie Sie die
  Skala festlegen, und weisen Sie Ressourcen Aufgaben zu.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man die Rate‑Skala liest und die Rate‑Skala für Ressourcen‑Zuweisungen
  in Aspose.Tasks schreibt
url: /de/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Rate Scale liest und schreibt für Ressourcen‑Zuweisungen in Aspose.Tasks

In diesem Tutorial erfahren Sie **wie man die Rate**‑Skaleneinstellungen liest und sie für Ressourcen‑Zuweisungen mit Aspose.Tasks für Java anpasst. Egal, ob Sie einen Scheduler, ein Reporting‑Tool erstellen oder einfach Projekt‑Updates automatisieren müssen, die Beherrschung der Manipulation von Rate Scale gibt Ihnen eine feinkörnige Kontrolle über Material‑ und Arbeitsressourcen.

## Schnelle Antworten
- **Was ist die primäre Klasse für die Rate‑Verarbeitung?** `ResourceAssignment` mit der Eigenschaft `Asn.RATE_SCALE`.  
- **Welches Enum definiert die Skalierungsoptionen?** `RateScaleType` (Day, Week, Month, etc.).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Evaluationslizenz funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich die Skalierung nach dem Speichern ändern?** Ja – laden Sie das Projekt neu und ändern Sie `Asn.RATE_SCALE` wie gezeigt.  
- **Unterstützte IDEs?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) kann den Code kompilieren.

## Was ist Rate Scale?
Die Rate Scale bestimmt die Zeiteinheit (Tag, Woche, Monat usw.), auf die der Kostensatz einer Ressource angewendet wird. Durch Anpassen der Skalierung können Sie den Materialverbrauch oder den Arbeitsaufwand genau modellieren.

## Warum Rate Scale lesen und schreiben?
Das Lesen der aktuellen Skalierung hilft Ihnen, vorhandene Zeitpläne zu prüfen, während das Schreiben einer neuen Skalierung es Ihnen ermöglicht, Ressourcen an die Abrechnungs‑ oder Verbrauchsrichtlinien des Projekts anzupassen. Dies ist besonders nützlich, wenn **Materialressourcen**‑Kosten definiert werden oder wenn Sie **die Skalierung** für nicht‑standardmäßige Arbeitskalender festlegen müssen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen haben:
1. **Java Development Environment** – JDK 8 oder höher installiert.  
2. **Aspose.Tasks for Java Library** – Laden Sie die Bibliothek von [hier](https://releases.aspose.com/tasks/java/) herunter und installieren Sie sie.

## Pakete importieren
Zuerst importieren Sie die erforderlichen Aspose.Tasks‑Klassen.

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

## Schritt 1: Richten Sie Ihr Java‑Projekt ein
Erstellen Sie ein Maven‑ oder Gradle‑Projekt und fügen Sie das Aspose.Tasks‑JAR zu Ihrem Klassenpfad hinzu. Dieser Schritt stellt sicher, dass der Compiler die importierten Klassen finden kann.

## Schritt 2: Laden Sie die Projektdatei
Laden Sie die vorhandene Microsoft‑Project‑Datei, mit der Sie arbeiten möchten.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Schritt 3: Aufgabe hinzufügen
Erstellen Sie eine neue Aufgabe, die später Ressourcen‑Zuweisungen erhalten wird.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Schritt 4: Ressourcen definieren
Hier **definieren wir eine Materialressource** und eine reguläre Arbeitsressource. Beachten Sie die Verwendung von `ResourceType.Material` für die material‑Typ‑Ressource.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Schritt 5: Ressourcen der Aufgabe zuweisen
Jetzt **weisen wir Ressourcen der Aufgabe zu** und geben an, **wie die Skalierung gesetzt wird**, indem wir `RateScaleType.Week` verwenden. Dies veranschaulicht sowohl das Lesen als auch das Schreiben der Rate Scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Schritt 6: Projekt speichern
Speichern Sie die Änderungen in einer neuen Datei, damit wir später die gespeicherte Rate Scale überprüfen können.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Schritt 7: Ressourcen‑Zuweisungen abrufen
Laden Sie das gespeicherte Projekt erneut und **lesen Sie die Rate**‑Skala, um zu bestätigen, dass sie korrekt geschrieben wurde.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Häufige Fallstricke & Tipps
- **UID‑Mismatch** – Beim Abrufen von Zuweisungen nach UID stellen Sie sicher, dass die UID‑Werte denen entsprechen, die während der Erstellung zugewiesen wurden.  
- **Falscher Ressourcentyp** – Die Verwendung von `ResourceType.Material` für eine Arbeitsressource führt dazu, dass die Rate‑Berechnungen unerwartet reagieren.  
- **Speicherformat** – Speichern Sie immer mit `SaveFileFormat.Mpp` (oder einem anderen unterstützten Format), um benutzerdefinierte Felder wie die Rate Scale zu erhalten.

## Fazit
Die Verwaltung und Prüfung der Rate Scale für Ressourcen‑Zuweisungen in Aspose.Tasks für Java ist unkompliziert, sobald Sie die relevanten Klassen und Eigenschaften kennen. Wenn Sie dieser Anleitung folgen, können Sie **Rate‑Informationen lesen**, **Materialressourcen**‑Objekte **definieren**, **die Skalierung setzen** und **Ressourcen der Aufgabe zuweisen** mit Zuversicht.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks für Java mit jeder Java‑IDE verwenden?**  
A: Ja, Aspose.Tasks für Java ist mit allen gängigen Java‑IDEs kompatibel, einschließlich IntelliJ IDEA, Eclipse und NetBeans.

**Q: Unterstützt Aspose.Tasks andere Dateiformate neben MPP?**  
A: Ja, Aspose.Tasks unterstützt verschiedene Dateiformate, darunter MPP, XML und HTML.

**Q: Ist Aspose.Tasks für Projektmanagement auf Unternehmens‑Ebene geeignet?**  
A: Absolut, Aspose.Tasks bietet umfassende Funktionen zur Verwaltung von Projekten jeder Größe und ist somit für Projektmanagement auf Unternehmens‑Ebene geeignet.

**Q: Kann ich Ressourcen‑Zuweisungen über die Rate Scale hinaus weiter anpassen?**  
A: Ja, Aspose.Tasks bietet umfangreiche Möglichkeiten zur Anpassung von Ressourcen‑Zuweisungen, einschließlich Kosten-, Arbeits- und Dauereinstellungen.

**Q: Gibt es ein Community‑Forum für Aspose.Tasks‑Support?**  
A: Ja, Sie finden Unterstützung und können mit anderen Benutzern im Aspose.Tasks‑Forum [hier](https://forum.aspose.com/c/tasks/15) interagieren.

---

**Zuletzt aktualisiert:** 2026-01-10  
**Getestet mit:** Aspose.Tasks for Java 24.12 (zum Zeitpunkt der Erstellung aktuell)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}