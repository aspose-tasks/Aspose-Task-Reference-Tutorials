---
date: 2026-03-27
description: Erfahren Sie, wie Sie MS Project‑Gliederungscodes programmgesteuert mit
  Aspose.Tasks für Java abrufen können. Verbessern Sie Ihre Projektmanagementfähigkeiten.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project‑Gliederungscodes in Aspose.Tasks abrufen
url: /de/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Outline Codes mit Aspose.Tasks abrufen

## Einführung
In diesem Tutorial erfahren Sie **wie Sie MS Project Outline Codes abrufen** mit Aspose.Tasks für Java. Outline‑Codes in MS Project bieten Ihnen eine leistungsstarke Möglichkeit, Aufgaben, Ressourcen und Zuordnungen zu kategorisieren, und der programmgesteuerte Zugriff ermöglicht es Ihnen, benutzerdefinierte Berichte, Automatisierungen oder Integrationslösungen zu erstellen. Wir führen Sie durch ein vollständiges, Schritt‑für‑Schritt‑Beispiel, das Sie in Ihr eigenes Projekt übernehmen können.

## Schnelle Antworten
- **Was macht der Code?** Er lädt eine Projektdatei und gibt jede Outline‑Code‑Definition, deren Masken und Werte aus.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (jede aktuelle Version).  
- **Brauche ich eine Lizenz?** Eine Testversion funktioniert für die Entwicklung; für die Produktion ist eine Voll‑lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.  
- **Kann ich die Codes nach dem Abrufen ändern?** Ja – dieselbe API ermöglicht das Hinzufügen, Bearbeiten oder Löschen von Outline‑Codes.

## Was sind MS Project Outline Codes?
Outline‑Codes sind benutzerdefinierte Felder, die Projektmanagern ermöglichen, Aufgaben über die Standardhierarchie hinaus zu gruppieren und zu filtern. Sie können einfache numerische Werte, Zeichenketten oder sogar organisationsweite benutzerdefinierte Codes sein, die auf Unternehmensebene definiert sind. Durch das Auslesen dieser Codes können Sie Dashboards steuern, Daten exportieren oder Namenskonventionen automatisch durchsetzen.

## Warum MS Project Outline Codes mit Aspose.Tasks abrufen?
- **Automatisierung:** Berichte erstellen oder Workflows auslösen, ohne manuelle Exporte.  
- **Integration:** Outline‑Codes mit ERP-, PPM- oder BI‑Tools synchronisieren.  
- **Anpassung:** Geschäftsregeln basierend auf Code‑Werten anwenden (z. B. Kostenzuordnung).  
- **Plattformübergreifend:** Funktioniert unter Windows, Linux und macOS, unabhängig von der Microsoft Project UI.

## Wie liest man MPP‑Dateien für Outline‑Codes?
Das Lesen einer MPP‑Datei (Microsoft Project) ist der erste Schritt zum Extrahieren von Outline‑Codes. Aspose.Tasks abstrahiert das Dateiformat, sodass Sie die binäre Struktur nicht selbst parsen müssen. Die Klasse `Project` übernimmt die schwere Arbeit, sodass Sie sich auf die tatsächlich benötigten Daten konzentrieren können.

## Benutzerdefinierte Felder in MS Project
Outline‑Codes sind eine Art von **benutzerdefinierten Feldern** in MS Project. Während Standardfelder Daten, Dauer und Ressourcen abdecken, ermöglichen benutzerdefinierte Felder das Speichern organisationsspezifischer Informationen. Der Zugriff über Aspose.Tasks bietet Ihnen dieselbe Flexibilität programmatisch.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen eingerichtet sind:

### 1. Java-Entwicklungsumgebung
Stellen Sie sicher, dass das Java Development Kit (JDK) auf Ihrem System installiert ist. Sie können das JDK von der Oracle‑Website herunterladen und installieren.

### 2. Aspose.Tasks‑Bibliothek
Laden Sie die Aspose.Tasks‑Bibliothek herunter und binden Sie sie in Ihr Java‑Projekt ein. Sie können die Bibliothek von der [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) herunterladen.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete von Aspose.Tasks in Ihrem Java‑Code:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Nun zerlegen wir den bereitgestellten Beispielcode in mehrere Schritte:

## Schritt 1: Projekt laden
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
In diesem Schritt laden wir die Microsoft‑Project‑Datei in ein `Project`‑Objekt, indem wir den angegebenen Dateinamen verwenden.

## Schritt 2: Outline‑Codes abrufen
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Wir iterieren über jede Outline‑Code‑Definition im Projekt.

## Schritt 3: Eigenschaften von Outline‑Codes zugreifen
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Wir rufen verschiedene Eigenschaften der Outline‑Code‑Definition ab und geben sie aus, z. B. Alias, Feld‑ID und Feldname.

## Schritt 4: Enterprise‑Custom‑Code prüfen
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Wir prüfen, ob der Outline‑Code ein Enterprise‑Custom‑Code ist, und geben das Ergebnis entsprechend aus.

## Schritt 5: Outline‑Code‑Masken anzeigen
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Wir iterieren über jede mit dem Outline‑Code verbundene Maske und geben deren Ebene und Maskenwert aus.

## Schritt 6: Outline‑Code‑Werte anzeigen
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Wir iterieren über jeden Outline‑Code‑Wert und geben dessen Beschreibung, Wert‑ID, Wert und Typ aus.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| **Keine Ausgabe** | Projektdateipfad ist falsch | Stellen Sie sicher, dass `projectName` auf eine gültige `.mpp`‑Datei verweist. |
| **Null‑Werte** | Outline‑Code ist in der Datei nicht definiert | Stellen Sie sicher, dass die Projektdatei tatsächlich Outline‑Codes enthält (im MS Project UI prüfen). |
| **LicenseException** | Verwendung der Testversion ohne korrekte Aktivierung | Wenden Sie eine temporäre oder vollständige Lizenz an via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks für Java verwenden, um Outline‑Codes in einer Projektdatei zu ändern?**  
A: Ja, Aspose.Tasks für Java bietet APIs, um Outline‑Codes programmgesteuert zu ändern. Sie können Definitionen mit demselben `Project`‑Objekt hinzufügen, bearbeiten oder löschen.

**F: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java von der [Aspose.Tasks‑Website](https://releases.aspose.com/) herunterladen.

**F: Wie kann ich technischen Support für Aspose.Tasks für Java erhalten?**  
A: Sie können technischen Support erhalten, indem Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) besuchen und dort Ihre Fragen stellen.

**F: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?**  
A: Ja, Sie können eine temporäre Lizenz für Aspose.Tasks für Java über die [Kaufseite](https://purchase.aspose.com/temporary-license/) erwerben.

**F: Wo finde ich die vollständige Dokumentation für Aspose.Tasks für Java?**  
A: Sie können die [Dokumentation](https://reference.aspose.com/tasks/java/) für detaillierte Informationen zur Verwendung von Aspose.Tasks für Java einsehen.

## Fazit
In diesem Tutorial haben wir gelernt, **MS Project Outline Codes** mit Aspose.Tasks für Java abzurufen. Durch Befolgen der bereitgestellten Schritte können Sie Outline‑Codes in Ihren Java‑Anwendungen effektiv zugreifen und manipulieren, wodurch erweiterte Projektmanagement‑Funktionen wie benutzerdefinierte Berichte, Automatisierung und Integration mit anderen Unternehmenssystemen ermöglicht werden.

---

**Zuletzt aktualisiert:** 2026-03-27  
**Getestet mit:** Aspose.Tasks for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}