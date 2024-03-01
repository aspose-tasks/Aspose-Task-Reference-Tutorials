---
title: Erweiterte Aufgabenattribute in Aspose.Tasks
linktitle: Erweiterte Aufgabenattribute in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Entdecken Sie erweiterte Aufgabenattribute in Aspose.Tasks für Java. Schritt-für-Schritt-Anleitung, FAQs und Support. Optimieren Sie noch heute Ihr Projektmanagement!
type: docs
weight: 16
url: /de/java/task-properties/extended-task-attributes/
---
## Einführung
Willkommen zu unserem umfassenden Leitfaden zur Nutzung erweiterter Aufgabenattribute in Aspose.Tasks für Java. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die Ihnen die nahtlose Arbeit mit Microsoft Project-Dokumenten ermöglicht. In diesem Tutorial befassen wir uns mit den erweiterten Aufgabenattributen und zeigen, wie Sie diese nutzen können, um Ihre Projektmanagementfähigkeiten zu verbessern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Java-Programmierung.
- Installiertes Java Development Kit (JDK) auf Ihrem Computer.
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ oder Eclipse.
## Pakete importieren
Beginnen Sie mit dem Importieren der erforderlichen Pakete, um Ihr Aspose.Tasks-Projekt zu starten:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen, um Sie durch den Prozess zu führen:
## Schritt 1: Zugreifen auf Aufgaben- und erweiterte Attribute
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## Schritt 2: Feld-ID und Wert-GUID abrufen
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## Schritt 3: Umgang mit verschiedenen Attributtypen
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
Wiederholen Sie diese Schritte für jede Aufgabe in Ihrem Projekt, um erweiterte Aufgabenattribute zu erkunden und zu bearbeiten.
## Abschluss
Zusammenfassend lässt sich sagen, dass das Verständnis und die Verwendung erweiterter Aufgabenattribute in Aspose.Tasks für Java Ihre Projektmanagementfähigkeiten erheblich verbessern können. Dieser Leitfaden bietet eine solide Grundlage für den Einstieg in diese Reise.
## Häufig gestellte Fragen
### Kann ich erweiterte Aufgabenattribute programmgesteuert ändern?
Ja, Sie können erweiterte Aufgabenattribute mit Aspose.Tasks für Java ändern. Detaillierte Anweisungen finden Sie in der Dokumentation.
### Gibt es eine Testversion?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Tasks für Java?
 Für Unterstützung besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
### Wie kann ich eine temporäre Lizenz erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Wo kann ich die Vollversion von Aspose.Tasks für Java kaufen?
 Sie können die Vollversion erwerben[Hier](https://purchase.aspose.com/buy).