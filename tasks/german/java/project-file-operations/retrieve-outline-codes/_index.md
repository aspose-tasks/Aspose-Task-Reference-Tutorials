---
title: Rufen Sie MS Project-Gliederungscodes in Aspose.Tasks ab
linktitle: Gliederungscodes in Aspose.Tasks abrufen
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Microsoft Project-Gliederungscodes programmgesteuert mit Aspose.Tasks für Java abrufen. Erweitern Sie Ihre Projektmanagementfähigkeiten.
weight: 15
url: /de/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rufen Sie MS Project-Gliederungscodes in Aspose.Tasks ab

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für Java Microsoft Project-Gliederungscodes abrufen. Gliederungscodes in MS Project bieten eine strukturierte Möglichkeit, Projektaufgaben, Ressourcen und Zuweisungen zu kategorisieren und zu organisieren. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert zu bearbeiten und zu verwalten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Java-Entwicklungsumgebung
Stellen Sie sicher, dass auf Ihrem System das Java Development Kit (JDK) installiert ist. Sie können JDK von der Oracle-Website herunterladen und installieren.
### 2. Aspose.Tasks-Bibliothek
 Laden Sie die Aspose.Tasks-Bibliothek herunter und fügen Sie sie in Ihr Java-Projekt ein. Sie können die Bibliothek unter herunterladen[Aspose.Tasks für Java-Downloadseite](https://releases.aspose.com/tasks/java/).
## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete aus Aspose.Tasks in Ihren Java-Code:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Lassen Sie uns nun den bereitgestellten Beispielcode in mehrere Schritte aufteilen:
## Schritt 1: Laden Sie das Projekt
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 In diesem Schritt laden wir die Microsoft Project-Datei in eine`Project` Objekt unter Verwendung des angegebenen Dateinamens.
## Schritt 2: Gliederungscodes abrufen
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Wir durchlaufen jede Gliederungscodedefinition im Projekt.
## Schritt 3: Greifen Sie auf die Eigenschaften des Gliederungscodes zu
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Wir rufen verschiedene Eigenschaften der Gliederungscodedefinition wie Alias, Feld-ID und Feldname ab und drucken sie aus.
## Schritt 4: Überprüfen Sie den benutzerdefinierten Unternehmenscode
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Wir prüfen, ob es sich bei dem Gliederungscode um einen benutzerdefinierten Unternehmenscode handelt, und drucken das Ergebnis entsprechend aus.
## Schritt 5: Gliederungscodemasken anzeigen
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Wir durchlaufen jede mit dem Gliederungscode verknüpfte Maske und geben deren Ebene und Maskenwert aus.
## Schritt 6: Gliederungscodewerte anzeigen
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Wir durchlaufen jeden Gliederungscodewert und geben seine Beschreibung, Wert-ID, seinen Wert und seinen Typ aus.
## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java MS Project-Gliederungscodes abruft. Durch Befolgen der bereitgestellten Schritte können Sie effektiv auf Gliederungscodes in Ihren Java-Anwendungen zugreifen und diese bearbeiten und so erweiterte Projektmanagementfunktionen ermöglichen.
## FAQs
### F1: Kann ich Aspose.Tasks für Java verwenden, um Gliederungscodes in einer Projektdatei zu ändern?
A: Ja, Aspose.Tasks für Java bietet APIs zum programmgesteuerten Ändern von Gliederungscodes in MS Project-Dateien.
### F2: Gibt es eine Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java herunterladen[Aspose.Tasks-Website](https://releases.aspose.com/).
### F3: Wie erhalte ich technischen Support für Aspose.Tasks für Java?
 A: Sie können technischen Support erhalten, indem Sie die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) und stellen Sie dort Ihre Fragen.
### F4: Kann ich eine temporäre Lizenz für Aspose.Tasks für Java erwerben?
 A: Ja, Sie können eine temporäre Lizenz für Aspose.Tasks für Java erwerben[Kaufseite](https://purchase.aspose.com/temporary-license/).
### F5: Wo finde ich die vollständige Dokumentation für Aspose.Tasks für Java?
 A: Sie können sich auf die beziehen[Dokumentation](https://reference.aspose.com/tasks/java/) Ausführliche Informationen zur Verwendung von Aspose.Tasks für Java finden Sie hier.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
