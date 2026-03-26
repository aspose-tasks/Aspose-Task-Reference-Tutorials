---
date: 2025-12-20
description: Erfahren Sie, wie Sie MS‑Project‑Gliederungscodes programmgesteuert mit
  Aspose.Tasks für Java abrufen können. Verbessern Sie Ihre Projektmanagementfähigkeiten.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS‑Project‑Gliederungscodes in Aspose.Tasks abrufen
url: /de/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Abrufen von MS Project Gliederungscodes in Aspose.Tasks

## Einleitung
In diesem Tutorial erfahren Sie **wie Sie MS Project Gliederungscodes** mit Aspose.Tasks für Java abrufen können. Gliederungscodes in MS Project bieten Ihnen eine leistungsstarke Möglichkeit, Aufgaben, Ressourcen und Zuordnungen zu kategorisieren. Der programmgesteuerte Zugriff ermöglicht benutzerdefinierte Berichte, Automatisierungen oder Integrationslösungen. Wir führen Sie Schritt für Schritt durch ein vollständiges Beispiel, das Sie in Ihr eigenes Projekt übernehmen können.

## Kurze Antworten
- **Was macht der Code?** Er lädt eine Projektdatei und gibt jede Gliederungscode‑Definition, deren Masken und Werte aus.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java (jede aktuelle Version).  
- **Benötige ich eine Lizenz?** Eine Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine Volllizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher.  
- **Kann ich die Codes nach dem Abrufen ändern?** Ja – dieselbe API ermöglicht das Hinzufügen, Bearbeiten oder Löschen von Gliederungscodes.

## Was sind MS Project Gliederungscodes?
Gliederungscodes sind benutzerdefinierte Felder, die Projektleitern ermöglichen, Aufgaben über die Standard‑Hierarchie hinaus zu gruppieren und zu filtern. Sie können einfache numerische Werte, Zeichenketten oder sogar unternehmensweite benutzerdefinierte Codes sein, die auf Organisationsebene definiert wurden. Durch das Auslesen dieser Codes können Sie Dashboards steuern, Daten exportieren oder Namenskonventionen automatisch durchsetzen.

## Warum MS Project Gliederungscodes mit Aspose.Tasks abrufen?
- **Automatisierung:** Berichte erstellen oder Workflows auslösen, ohne manuelle Exporte.  
- **Integration:** Gliederungscodes mit ERP-, PPM‑ oder BI‑Tools synchronisieren.  
- **Anpassung:** Geschäftsregeln basierend auf Code‑Werten anwenden (z. B. Kostenzuordnung).  
- **Plattformübergreifend:** Funktioniert unter Windows, Linux und macOS, unabhängig von der Microsoft Project‑Benutzeroberfläche.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Java‑Entwicklungsumgebung
Stellen Sie sicher, dass das Java Development Kit (JDK) auf Ihrem System installiert ist. Sie können das JDK von der Oracle‑Website herunterladen und installieren.

### 2. Aspose.Tasks‑Bibliothek
Laden Sie die Aspose.Tasks‑Bibliothek herunter und binden Sie sie in Ihr Java‑Projekt ein. Sie können die Bibliothek von der [Aspose.Tasks für Java Download‑Seite](https://releases.aspose.com/tasks/java/) herunterladen.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete von Aspose.Tasks in Ihrem Java‑Code:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Nun zerlegen wir den bereitgestellten Beispielcode in mehrere Schritte:

## Schritt 1: Projekt laden
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
In diesem Schritt laden wir die Microsoft‑Project‑Datei in ein `Project`‑Objekt, indem wir den angegebenen Dateinamen verwenden.

## Schritt 2: Gliederungscodes abrufen
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Wir iterieren über jede Gliederungscode‑Definition im Projekt.

## Schritt 3: Eigenschaften des Gliederungscodes zugreifen
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Wir rufen verschiedene Eigenschaften der Gliederungscode‑Definition ab und geben sie aus, z. B. Alias, Feld‑ID und Feldname.

## Schritt 4: Unternehmens‑Custom‑Code prüfen
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Wir prüfen, ob der Gliederungscode ein unternehmensweiter benutzerdefinierter Code ist, und geben das Ergebnis entsprechend aus.

## Schritt 5: Gliederungscode‑Masken anzeigen
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Wir iterieren über jede mit dem Gliederungscode verbundene Maske und geben deren Ebene und Maskenwert aus.

## Schritt 6: Gliederungscode‑Werte anzeigen
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Wir iterieren über jeden Gliederungscode‑Wert und geben Beschreibung, Wert‑ID, Wert und Typ aus.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|--------|-----|
| **Keine Ausgabe** | Projektdateipfad ist falsch | Stellen Sie sicher, dass `projectName` auf eine gültige `.mpp`‑Datei verweist. |
| **Null‑Werte** | Gliederungscode nicht in der Datei definiert | Vergewissern Sie sich, dass die Projektdatei tatsächlich Gliederungscodes enthält (im MS Project UI prüfen). |
| **LicenseException** | Testversion ohne korrekte Aktivierung verwendet | Aktivieren Sie eine temporäre oder Voll‑Lizenz via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks für Java verwenden, um Gliederungscodes in einer Projektdatei zu ändern?**  
A: Ja, Aspose.Tasks für Java bietet APIs zum programmgesteuerten Ändern von Gliederungscodes. Sie können Definitionen hinzufügen, bearbeiten oder löschen, indem Sie dasselbe `Project`‑Objekt verwenden.

**F: Gibt es eine Testversion von Aspose.Tasks für Java?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java von der [Aspose.Tasks‑Website](https://releases.aspose.com/) herunterladen.

**F: Wie erhalte ich technischen Support für Aspose.Tasks für Java?**  
A: Sie erhalten technischen Support, indem Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) besuchen und dort Ihre Fragen stellen.

**F: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?**  
A: Ja, Sie können eine temporäre Lizenz für Aspose.Tasks für Java über die [Kauf‑Seite](https://purchase.aspose.com/temporary-license/) erwerben.

**F: Wo finde ich die vollständige Dokumentation für Aspose.Tasks für Java?**  
A: Die [Dokumentation](https://reference.aspose.com/tasks/java/) bietet detaillierte Informationen zur Verwendung von Aspose.Tasks für Java.

## Fazit
In diesem Tutorial haben wir gelernt, **MS Project Gliederungscodes** mit Aspose.Tasks für Java abzurufen. Durch Befolgen der bereitgestellten Schritte können Sie Gliederungscodes in Ihren Java‑Anwendungen effektiv zugreifen und manipulieren, wodurch erweiterte Projektmanagement‑Funktionen wie benutzerdefinierte Berichte, Automatisierung und Integration mit anderen Unternehmenssystemen ermöglicht werden.

---

**Zuletzt aktualisiert:** 2025-12-20  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}