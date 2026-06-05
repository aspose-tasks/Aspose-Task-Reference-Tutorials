---
date: 2026-06-05
description: Erfahren Sie, wie Sie Resource Assignment mit Aspose.Tasks für Java erstellen,
  Ressourcen zu einem Projekt hinzufügen und Leveling Delay Properties verwalten.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Leveling Delay Properties für Resource Assignments in Aspose.Tasks behandeln
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Resource Assignment mit Aspose.Tasks für Java erstellen
url: /de/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ressourcenzuweisung erstellen mit Aspose.Tasks für Java

In diesem umfassenden Leitfaden lernen Sie **wie man resource assignment aspotasks** mit der Aspose.Tasks-Bibliothek für Java erstellt. Egal, ob Sie eine benutzerdefinierte Planungs-Engine entwickeln, Massen‑Projekt‑Updates automatisieren oder einfach Microsoft‑Project‑Dateien ohne die Desktop‑Anwendung manipulieren müssen, das Beherrschen dieser Schritte ermöglicht es Ihnen, Ihre Projektdaten genau und vollständig kontrollierbar zu halten.

## Schnelle Antworten
- **Was bedeutet „add resource to project“?** Es erstellt einen neuen Ressourceneintrag, der später Aufgaben zugewiesen werden kann.  
- **Kann ich nach der Zuweisung eine Level‑Verzögerung festlegen?** Ja, mittels der Felder `Asn.DELAY` oder `Asn.LEVELING_DELAY`.  
- **Benötige ich eine Lizenz, um diesen Code auszuführen?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kostenpflichtige Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder neuer.  
- **Ist dies mit allen MS‑Project‑Dateiformaten kompatibel?** Aspose.Tasks unterstützt über 12 Formate – darunter .MPP, .XML, .XER, .CSV, .PDF und weitere.

## Was bedeutet „add resource to project“ in Aspose.Tasks?
Das Hinzufügen einer Ressource zu einem Projekt bedeutet, ein `Resource`‑Objekt im `Project`‑Modell zu erstellen. Dieses Objekt kann später über `ResourceAssignment` mit Aufgaben verknüpft werden, wodurch Sie Arbeit, Kosten und Level‑Einstellungen verfolgen können. Durch das Einfügen einer Ressource geben Sie dem Scheduler etwas zum Zuweisen, und Sie können später deren Eigenschaften wie Verfügbarkeit, Sätze und Kalenderzuweisungen abfragen oder ändern.

## Warum Level‑Verzögerungseigenschaften behandeln?
Die Level‑Verzögerung weist den Scheduler an, den Start einer überlasteten Zuweisung zu verschieben und die Arbeit gleichmäßiger über die Zeitleiste zu verteilen. Durch die Konfiguration dieser Verzögerung vermeiden Sie unrealistische Startdaten, reduzieren Warnungen bei Überlastungen und erzeugen einen Zeitplan, der reale Ressourcenkapazitäten widerspiegelt. Das Anpassen der Verzögerung gibt Ihnen zudem eine feinkörnige Kontrolle darüber, wie viel Puffer der Engine einfügen darf, sodass Sie Projekttermine einhalten können, während Sie Ressourcengrenzen respektieren.

## Wie erstellt man resource assignment aspotasks?
Laden Sie Ihr `Project`‑Objekt, fügen Sie eine Aufgabe hinzu, erstellen Sie eine Ressource und verbinden Sie diese anschließend mit einer `ResourceAssignment`. Dieser End‑zu‑End‑Ablauf ermöglicht es Ihnen, programmgesteuert eine vollständige Projektstruktur aufzubauen und sofort die Level‑Verzögerung für die Zuweisung zu steuern. Der Prozess demonstriert den Kern‑Workflow: Projektinitialisierung, Aufgabendefinition, Ressourcenerstellung, Verknüpfung der Zuweisung und schließlich das Anwenden von Planungsparametern wie der Level‑Verzögerung.

## Voraussetzungen
1. Java Development Kit (JDK): Stellen Sie sicher, dass das Java JDK auf Ihrem System installiert ist. Sie können es von der [Website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) herunterladen und installieren.  
2. Aspose.Tasks for Java Bibliothek: Laden Sie die Aspose.Tasks for Java Bibliothek von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.

## Pakete importieren
Die folgenden Importe bringen die Kernklassen von Aspose.Tasks, die für die Projektmanipulation benötigt werden, ein.  
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

## Wie erstellt man resource assignment aspotasks?
Laden Sie Ihr `Project`‑Objekt, fügen Sie eine Aufgabe hinzu, erstellen Sie eine Ressource und verbinden Sie diese anschließend mit einer `ResourceAssignment`. Dieser End‑zu‑End‑Ablauf ermöglicht es Ihnen, programmgesteuert eine vollständige Projektstruktur aufzubauen und sofort die Level‑Verzögerung für die Zuweisung zu steuern. Der Prozess demonstriert den Kern‑Workflow: Projektinitialisierung, Aufgabendefinition, Ressourcenerstellung, Verknüpfung der Zuweisung und schließlich das Anwenden von Planungsparametern wie der Level‑Verzögerung.

## Schritt 1: Projektobjekt erstellen
Die Klasse `Project` ist der oberste Container von Aspose.Tasks, der eine komplette Projektdatei im Speicher repräsentiert. Durch die Instanziierung erhalten Sie eine leere Basis, um Aufgaben, Ressourcen und Zuweisungen hinzuzufügen.
```java
Project prj = new Project();
```

## Schritt 2: Aufgabe erstellen
Die Klasse `Task` repräsentiert ein einzelnes Arbeitselement im Zeitplan. Das Hinzufügen einer Aufgabe demonstriert **wie man task hinzufügt** programmgesteuert und bietet ein Ziel für die bevorstehende Ressourcenzuweisung.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Schritt 3: Startdatum und Dauer der Aufgabe festlegen
Definieren Sie, wann die Aufgabe beginnt und wie lange sie läuft. Korrekte Startdaten sind entscheidend, da Level‑Berechnungen sie als Grundlage für jede später angegebene Verzögerung verwenden.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Schritt 4: Ressource hinzufügen
Jetzt **add resource to project** wir, indem wir einen neuen `Resource`‑Eintrag erstellen. Die Klasse `Resource` stellt eine Person, Ausrüstung oder ein Material dar, das Aufgaben zugewiesen werden kann.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Schritt 5: Ressourcenzuweisung erstellen
`ResourceAssignment` verknüpft eine `Task` mit einer `Resource`. Diese Zuordnung ermöglicht es Ihnen, Arbeit, Kosten und Level‑Details für eine bestimmte Ressource bei einer bestimmten Aufgabe zu erfassen.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Schritt 6: Level‑Verzögerung festlegen
Konfigurieren Sie die Level‑Verzögerung für die Zuweisung. Auf Null zu setzen bedeutet keine zusätzliche Verzögerung, Sie können den Wert jedoch nach Bedarf anpassen. Das Feld `Asn.DELAY` speichert die Verzögerung in Minuten; `Asn.LEVELING_DELAY` ist ein Alias, der auf dieselbe Weise funktioniert.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Schritt 7: Ergebnisse anzeigen
Geben Sie die wichtigen Eigenschaften aus, um zu überprüfen, ob alles korrekt gesetzt wurde. Dieser Schritt hilft Ihnen, zu bestätigen, dass die Ressource, Aufgabe und Verzögerungswerte genau Ihren Erwartungen entsprechen, bevor Sie die Datei speichern.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Häufige Fallstricke & Tipps
- **Fallstrick:** Das Vergessen, das Startdatum der Aufgabe festzulegen, kann dazu führen, dass die Zuweisung standardmäßig auf den Projektstart gesetzt wird.  
- **Tipp:** Verwenden Sie `prj.getDuration(value, TimeUnitType.Day)`, um die Granularität der Verzögerung zu steuern.  
- **Tipp:** Nachdem Sie mehrere Ressourcen hinzugefügt haben, rufen Sie `prj.updateResourceAssignments()` auf, damit der Scheduler das Leveling neu berechnet.  
- **Pro‑Tipp:** Für große Projekte (10.000+ Aufgaben) aktivieren Sie `prj.setAutoCalculate(false)` vor Massenupdates und rufen Sie anschließend einmal `prj.calculate()` am Ende auf, um die Leistung zu verbessern.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.Tasks mit anderen Java‑Bibliotheken verwenden?**  
A: Ja, Aspose.Tasks lässt sich nahtlos in Bibliotheken wie Jackson für JSON‑Verarbeitung oder Apache POI für zusätzliche Tabellenkalkulations‑Operationen integrieren, sodass Sie umfangreichere Projektmanagement‑Lösungen erstellen können.

**Q: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Aspose.Tasks unterstützt über 12 Dateiformate – darunter .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML und .MPP12 – und gewährleistet nahtloses Round‑Trip‑Editing über alle wichtigen Project‑Versionen hinweg.

**Q: Wo finde ich zusätzlichen Support für Aspose.Tasks?**  
A: Unterstützung und Community‑Diskussionen finden Sie im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

**Q: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Ja, ein voll funktionsfähiger kostenloser Test ist auf der [Releases‑Seite](https://releases.aspose.com/) verfügbar.

**Q: Wie kann ich eine temporäre Lizenz für die Evaluation erhalten?**  
A: Fordern Sie eine temporäre Lizenz über die [temporäre Lizenz‑Seite](https://purchase.aspose.com/temporary-license/) an, um die Bibliothek ohne Evaluationsbeschränkungen zu nutzen.

---

**Letzte Aktualisierung:** 2026-06-05  
**Getestet mit:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Verwandte Tutorials

- [Ressourcenzuweisungen in Aspose.Tasks erstellen](/tasks/java/resource-assignments/create-resource-assignments/)
- [Zuweisungsbudget in Java mit Aspose.Tasks verwalten](/tasks/java/resource-assignments/assignment-budget/)
- [Wie man Zuweisungen stoppt und Ressourcenzuweisungen in Aspose.Tasks fortsetzt](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}