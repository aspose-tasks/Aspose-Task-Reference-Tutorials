---
date: 2026-06-10
description: Erfahren Sie, wie Sie Rate und Rate Scale für Ressourcenzuweisungen mit
  Aspose.Tasks für Java lesen und schreiben. Unterstützt Materialressourcen, mehrere
  Formate und große Projekte.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Rate Scale lesen und schreiben für Ressourcenzuweisungen in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Wie man Rate Scale liest und schreibt für Ressourcenzuweisungen in Aspose.Tasks
url: /de/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Rate‑Skala liest und schreibt für Ressourcen‑Zuweisungen in Aspose.Tasks

In diesem Tutorial erfahren Sie **wie man die Rate‑Skala** liest und sie für Ressourcen‑Zuweisungen mit Aspose.Tasks für Java anpasst. Egal, ob Sie einen Scheduler, ein Reporting‑Tool erstellen oder einfach Projekt‑Updates automatisieren müssen, das Beherrschen der Manipulation von Rate‑Skalen gibt Ihnen eine feinkörnige Kontrolle über Material‑ und Arbeitsressourcen.

## Schnelle Antworten
`ResourceAssignment` verknüpft eine Aufgabe mit einer Ressource und enthält zuweisungs‑spezifische Daten.  
`Asn` enthält Konstanten für Zuweisungsfelder, einschließlich `RATE_SCALE`.  
`RateScaleType`‑Enum listet mögliche Zeiteinheiten für die Rate‑Skalierung auf.  

- **Was ist die primäre Klasse für die Rate‑Verarbeitung?** `ResourceAssignment` mit der Eigenschaft `Asn.RATE_SCALE`.  
- **Welcher Enum definiert die Skalierungsoptionen?** `RateScaleType` (Day, Week, Month, etc.).  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Evaluationslizenz funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich die Skalierung nach dem Speichern ändern?** Ja – laden Sie das Projekt neu und ändern Sie `Asn.RATE_SCALE` wie gezeigt.  
- **Unterstützte IDEs?** Jede Java‑IDE (IntelliJ IDEA, Eclipse, NetBeans) kann den Code kompilieren.

## Wie man die Rate‑Skala für Ressourcen‑Zuweisungen liest

Laden Sie das Projekt, finden Sie die gewünschte `ResourceAssignment` und rufen Sie `getRateScale()` auf – dies gibt einen `RateScaleType`‑Wert zurück, der Ihnen sagt, ob die Rate pro Tag, Woche, Monat oder einer anderen Einheit angewendet wird. Die Antwort ist sofort verfügbar und erfordert nur zwei API‑Aufrufe, was es ideal für Auditskripte oder UI‑Anzeige macht.

## Wie man die Rate‑Skala für Ressourcen‑Zuweisungen schreibt

Erstellen oder holen Sie ein `ResourceAssignment`‑Objekt, setzen Sie dessen `Asn.RATE_SCALE`‑Eigenschaft auf den gewünschten `RateScaleType` (z. B. `RateScaleType.Week`) und speichern Sie anschließend das Projekt. Diese einzelne Eigenschaftsänderung aktualisiert automatisch die Kostenberechnungen und bleibt in allen unterstützten Dateiformaten erhalten. Nach dem Setzen der Skalierung müssen Sie möglicherweise auch die Standard‑ oder Überstundensatz der Ressource an die neue Zeiteinheit anpassen, um genaue Kostenberechnungen sicherzustellen.

## Was ist Rate‑Skala?

Die Rate‑Skala bestimmt die Zeiteinheit (Tag, Woche, Monat usw.), auf die der Kostensatz einer Ressource angewendet wird. Durch Anpassen der Skalierung können Sie den Materialverbrauch oder den Arbeitsaufwand genau modellieren. Beispielsweise bedeutet das Setzen der Skalierung auf Woche, dass der Kostensatz als Kosten pro Woche interpretiert wird und die Gesamtkosten einer Aufgabe basierend auf der Anzahl der Wochen berechnet werden, in denen die Ressource zugewiesen ist.

## Warum Rate‑Skala lesen und schreiben?

Das Lesen der aktuellen Skalierung hilft Ihnen, bestehende Zeitpläne zu prüfen, während das Schreiben einer neuen Skalierung es Ihnen ermöglicht, Ressourcen an die Abrechnungs‑ oder Verbrauchsrichtlinien des Projekts anzupassen. Dies ist besonders nützlich, wenn **Materialressourcen‑Kosten** definiert werden oder wenn Sie die **Skalierung** für nicht‑standardmäßige Arbeitskalender festlegen müssen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. **Java-Entwicklungsumgebung** – JDK 8 oder höher installiert.  
2. **Aspose.Tasks für Java Bibliothek** – Laden Sie die Bibliothek von [hier](https://releases.aspose.com/tasks/java/) herunter und installieren Sie sie.

## Pakete importieren
Die Klasse `ResourceAssignment` stellt eine Verknüpfung zwischen einer Aufgabe und einer Ressource dar, während `RateScaleType` die möglichen Zeiteinheiten für eine Rate aufzählt. Importieren Sie die notwendigen Aspose.Tasks‑Klassen, bevor Sie mit dem Codieren beginnen.  

`Project` ist das Hauptobjekt, das Microsoft‑Project‑Dateien lädt und speichert.  
`Resource` definiert eine Projektressource wie Arbeit oder Material.  
`ResourceType`‑Enum gibt an, ob eine Ressource Arbeit oder Material ist.  
`Task` stellt ein Arbeitselement im Projektzeitplan dar.  
`SaveFileFormat`‑Enum definiert das Ausgabeformat zum Speichern eines Projekts.

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

## Schritt 1: Richten Sie Ihr Java‑Projekt ein
Erstellen Sie ein Maven‑ oder Gradle‑Projekt und fügen Sie das Aspose.Tasks‑JAR zu Ihrem Klassenpfad hinzu. Dieser Schritt stellt sicher, dass der Compiler die importierten Klassen finden kann.

## Schritt 2: Laden Sie die Projektdatei
Laden Sie die vorhandene Microsoft‑Project‑Datei, mit der Sie arbeiten möchten.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Schritt 3: Aufgabe hinzufügen
Erstellen Sie eine neue Aufgabe, die später Ressourcen‑Zuweisungen erhalten wird.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Schritt 4: Ressourcen definieren
Hier **definieren wir eine Materialressource** und eine reguläre Arbeitsressource. Beachten Sie die Verwendung von `ResourceType.Material` für die material‑typische Ressource.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Schritt 5: Ressourcen der Aufgabe zuweisen
Jetzt **weisen wir Ressourcen der Aufgabe zu** und geben an, **wie die Skalierung gesetzt wird**, indem wir `RateScaleType.Week` verwenden. Dies veranschaulicht sowohl das Lesen als auch das Schreiben der Rate‑Skala.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Schritt 6: Projekt speichern
Speichern Sie die Änderungen in einer neuen Datei, damit wir später die gespeicherte Rate‑Skala überprüfen können.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Schritt 7: Ressourcen‑Zuweisungen abrufen
Laden Sie das gespeicherte Projekt erneut und **lesen Sie die Rate‑Skala**, um zu bestätigen, dass sie korrekt geschrieben wurde.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Häufige Fallstricke & Tipps
- **UID‑Mismatch** – Beim Abrufen von Zuweisungen nach UID stellen Sie sicher, dass die UID‑Werte denen entsprechen, die während der Erstellung zugewiesen wurden.  
- **Falscher Ressourcentyp** – Die Verwendung von `ResourceType.Material` für eine Arbeitsressource führt dazu, dass die Rate‑Berechnungen unerwartet funktionieren.  
- **Speicherformat** – Speichern Sie immer mit `SaveFileFormat.Mpp` (oder einem anderen unterstützten Format), um benutzerdefinierte Felder wie die Rate‑Skala zu erhalten.  
- **Große Projekte** – Aspose.Tasks kann Dateien mit **500+ Seiten** verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, dank seiner Streaming‑Architektur.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks für Java mit jeder Java‑IDE verwenden?**  
A: Ja, Aspose.Tasks für Java ist mit allen gängigen Java‑IDEs kompatibel, einschließlich IntelliJ IDEA, Eclipse und NetBeans.

**Q: Unterstützt Aspose.Tasks andere Dateiformate neben MPP?**  
A: Ja, Aspose.Tasks unterstützt verschiedene Dateiformate, darunter MPP, XML und HTML.

**Q: Ist Aspose.Tasks für das Projektmanagement auf Unternehmens‑Ebene geeignet?**  
A: Absolut, Aspose.Tasks bietet umfassende Funktionen zur Verwaltung von Projekten jeder Größe und ist somit für das Projektmanagement auf Unternehmens‑Ebene geeignet.

**Q: Kann ich Ressourcen‑Zuweisungen über die Rate‑Skala hinaus weiter anpassen?**  
A: Ja, Aspose.Tasks bietet umfangreiche Möglichkeiten zur Anpassung von Ressourcen‑Zuweisungen, einschließlich Kosten-, Arbeits- und Dauereinstellungen.

**Q: Gibt es ein Community‑Forum für den Support von Aspose.Tasks?**  
A: Ja, Sie finden Unterstützung und können mit anderen Benutzern im Aspose.Tasks‑Forum [hier](https://forum.aspose.com/c/tasks/15) interagieren.

---

**Zuletzt aktualisiert:** 2026-06-10  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt des Schreibens neueste Version)  
**Autor:** Aspose

## Verwandte Tutorials

- [Ressourcen‑Zuweisungen in Aspose.Tasks erstellen](/tasks/java/resource-assignments/create-resource-assignments/)
- [Wie man Zuweisungen ändert – Gemeinsame Ressourcen mit Aspose lesen](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Wie man Notizen zu Ressourcen‑Zuweisungen in Aspose.Tasks hinzufügt](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}