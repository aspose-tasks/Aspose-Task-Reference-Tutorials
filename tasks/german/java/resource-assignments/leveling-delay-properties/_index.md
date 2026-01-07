---
date: 2026-01-07
description: Erfahren Sie, wie Sie einer Projektdatei eine Ressource hinzufügen und
  die Eigenschaften für die Ausgleichsverzögerung bei Ressourcen‑Zuweisungen mit Aspose.Tasks
  für Java handhaben.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man einer Ressource ein Projekt hinzufügt und Leveling‑Delay‑Eigenschaften
  in Aspose.Tasks verarbeitet
url: /de/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine Ressource zum Projekt hinzufügt und Level‑Delay‑Eigenschaften in Aspose.Tasks verwaltet

## Einführung
In diesem Tutorial lernen Sie **wie man eine Ressource zum Projekt hinzufügt**, während Sie gleichzeitig Level‑Delay‑Eigenschaften für Ressourcenzuweisungen mit Aspose.Tasks für Java verwalten. Egal, ob Sie eine Planungs‑Engine bauen oder Projekt‑Updates automatisieren, das Beherrschen dieser Schritte ermöglicht es Ihnen, Ihre Projektdaten genau zu halten, ohne Microsoft Project installiert zu haben.

## Schnellantworten
- **Was bedeutet „Ressource zum Projekt hinzufügen“?** Es erstellt einen neuen Ressourceneintrag, der Aufgaben zugewiesen werden kann.  
- **Kann ich nach der Zuweisung ein Level‑Delay setzen?** Ja, über die Felder `Asn.DELAY` oder `Asn.LEVELING_DELAY`.  
- **Benötige ich eine Lizenz, um diesen Code auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kostenpflichtige Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.  
- **Ist dies mit allen MS‑Project‑Dateiformaten kompatibel?** Aspose.Tasks unterstützt .MPP, .XML, .XER und weitere.

## Was bedeutet „Ressource zum Projekt hinzufügen“ in Aspose.Tasks?
Eine Ressource zu einem Projekt hinzuzufügen bedeutet, ein `Resource`‑Objekt innerhalb des `Project`‑Modells zu erstellen. Dieses Objekt kann später über `ResourceAssignment` mit Aufgaben verknüpft werden, sodass Sie Arbeit, Kosten und Level‑Einstellungen nachverfolgen können.

## Warum Level‑Delay‑Eigenschaften behandeln?
Level‑Delay hilft dem Scheduler, Arbeit zu verteilen, wenn Ressourcen überlastet sind. Durch das Setzen eines Delays teilen Sie der Engine mit, den Beginn einer Zuweisung zu verschieben, Konflikte zu vermeiden und das Projekt realistisch zu halten.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass das Java JDK auf Ihrem System installiert ist. Sie können es von der [Website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) herunterladen und installieren.  
2. Aspose.Tasks für Java Bibliothek: Laden Sie die Aspose.Tasks für Java Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.

## Pakete importieren
Importieren Sie zunächst die notwendigen Pakete in Ihr Java‑Projekt, um die Funktionalitäten von Aspose.Tasks zu nutzen:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Schritt 1: Ein Project‑Objekt erstellen
Instanziieren Sie ein `Project`‑Objekt, das als Container für alle Aufgaben, Ressourcen und Zuweisungen dient:
```java
Project prj = new Project();
```

## Schritt 2: Eine Aufgabe erstellen
Fügen Sie dem Projekt eine Aufgabe hinzu. Dies demonstriert **wie man programmatisch eine Aufgabe hinzufügt**:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Schritt 3: Startdatum und Dauer der Aufgabe festlegen
Definieren Sie, wann die Aufgabe beginnt und wie lange sie läuft:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Schritt 4: Eine Ressource hinzufügen
Jetzt **fügen wir eine Ressource zum Projekt hinzu**, indem wir einen neuen `Resource`‑Eintrag erstellen:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Schritt 5: Eine Ressourcenzuweisung erstellen
Verknüpfen Sie die Aufgabe mit der neu hinzugefügten Ressource:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Schritt 6: Level‑Delay setzen
Konfigurieren Sie das Level‑Delay für die Zuweisung. Ein Wert von Null bedeutet kein zusätzliches Delay, Sie können den Wert bei Bedarf anpassen:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Schritt 7: Ergebnisse anzeigen
Geben Sie die wichtigen Eigenschaften aus, um zu überprüfen, ob alles korrekt gesetzt wurde:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Häufige Stolperfallen & Tipps
- **Stolperfalle:** Das Vergessen, das Startdatum der Aufgabe zu setzen, kann dazu führen, dass die Zuweisung standardmäßig auf den Projektstart gesetzt wird.  
- **Tipp:** Verwenden Sie `prj.getDuration(value, TimeUnitType.Day)`, um die Granularität des Delays zu steuern.  
- **Tipp:** Nachdem Sie mehrere Ressourcen hinzugefügt haben, rufen Sie `prj.updateResourceAssignments()` auf, damit der Scheduler das Leveling neu berechnet.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt **wie man eine Ressource zum Projekt hinzufügt**, sie einer Aufgabe zuweist und Level‑Delay‑Eigenschaften mit Aspose.Tasks für Java verwaltet. Dieses Wissen ermöglicht Ihnen, robuste Projekt‑Automatisierungslösungen zu bauen, die mit realen Ressourcengrenzen im Einklang stehen.

## FAQ
### Q: Kann ich Aspose.Tasks mit anderen Java‑Bibliotheken verwenden?

A: Ja, Aspose.Tasks kann mit anderen Java‑Bibliotheken integriert werden, um die Projektmanagement‑Funktionen zu erweitern.

### Q: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft‑Project‑Dateien kompatibel?

A: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft‑Project‑Dateien und stellt damit die Kompatibilität in unterschiedlichen Umgebungen sicher.

### Q: Wo finde ich zusätzlichen Support für Aspose.Tasks?

A: Sie finden Support und Ressourcen im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

### Q: Kann ich Aspose.Tasks vor dem Kauf testen?

A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks von der [Releases‑Seite](https://releases.aspose.com/) erhalten.

### Q: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?

A: Sie können eine temporäre Lizenz über die [Temporäre‑Lizenz‑Seite](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke anfordern.

## Weitere häufig gestellte Fragen

**F: Was passiert, wenn ich ein nicht‑null Level‑Delay setze?**  
A: Der Scheduler verschiebt den Beginn der Zuweisung um die angegebene Dauer, was hilft, Überlastungen zu lösen.

**F: Kann ich das Level‑Delay nach dem Speichern des Projekts auslesen?**  
A: Ja, Sie können die Projektdatei erneut öffnen und die Eigenschaft `Asn.DELAY` der Zuweisung lesen.

**F: Gibt es eine Möglichkeit, das Level‑Delay für alle Zuweisungen gleichzeitig anzuwenden?**  
A: Sie können über `prj.getResourceAssignments()` iterieren und das Delay für jede Zuweisung in einer Schleife setzen.

---

**Zuletzt aktualisiert:** 2026-01-07  
**Getestet mit:** Aspose.Tasks für Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}