---
date: 2026-01-13
description: Erfahren Sie, wie Sie ein benutzerdefiniertes Attribut erstellen, eine
  Microsoft‑Project‑Datei laden, einen numerischen Wert in Java festlegen und das
  Projekt mit Aspose.Tasks für Java als XML speichern.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man ein benutzerdefiniertes Attribut in MS Project mit Aspose.Tasks erstellt
url: /de/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein benutzerdefiniertes Attribut in MS Project mit Aspose.Tasks erstellt

## Einführung
In diesem Tutorial **erfahren Sie, wie Sie ein benutzerdefiniertes Attribut** für Ressourcen in einer Microsoft‑Project‑Datei mit Aspose.Tasks für Java erstellen. Wir führen Sie durch das Laden einer Microsoft‑Project‑Datei, das Definieren eines neuen numerischen Attributs, das Zuweisen eines Werts und schließlich das Speichern des Projekts als XML. Am Ende haben Sie ein klares, praxisnahes Beispiel, das Sie an Ihre eigenen Projekt‑Management‑Lösungen anpassen können.

## Schnellantworten
- **Was bedeutet „benutzerdefiniertes Attribut“?**  
  Ein vom Benutzer definiertes Feld, das zusätzliche Informationen (z. B. Alter, Qualifikationsstufe) für eine Ressource oder Aufgabe speichert.  
- **Welche Bibliothek übernimmt das?**  
  Aspose.Tasks für Java bietet eine fluente API zum Erstellen und Verwalten benutzerdefinierter Attribute.  
- **Benötige ich eine Lizenz?**  
  Eine kostenlose temporäre Lizenz reicht für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Kann ich numerische Werte setzen?**  
  Ja – verwenden Sie `setNumericValue` mit einem `BigDecimal` (z. B. `30.5345`).  
- **Wie wird das Projekt gespeichert?**  
  Die geänderte Datei kann mit `SaveFileFormat.Xml` als XML gespeichert werden.

## Was ist ein benutzerdefiniertes Attribut?
Ein **benutzerdefiniertes Attribut** (auch erweitertes Attribut genannt) ist eine zusätzliche Spalte, die Sie zu Ressourcen oder Aufgaben in Microsoft Project hinzufügen können. Es ermöglicht Ihnen, Daten zu erfassen, die von den integrierten Feldern nicht abgedeckt werden, wie z. B. das Alter eines Mitarbeiters, das Zertifizierungsniveau oder jede geschäftsspezifische Kennzahl.

## Warum ein benutzerdefiniertes Attribut in MS Project erstellen?
- **Projekt‑Daten an Ihre Organisation anpassen.**  
- **Erweiterte Berichte ermöglichen**, indem Werte gespeichert werden, die später abgefragt werden können.  
- **Konsistenz wahren** über mehrere Projekte hinweg, indem dieselbe Attributdefinition programmgesteuert angewendet wird.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – JDK 8 oder höher installiert.  
2. **Aspose.Tasks für Java** – Laden Sie die neueste Version von [here](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – Eclipse, IntelliJ IDEA oder jede Java‑kompatible IDE.  

## Schritt‑für‑Schritt‑Anleitung

### Pakete importieren
Importieren Sie zunächst die Aspose.Tasks‑Klassen, die Sie benötigen. Diese bieten die Kernfunktionalität zum Verarbeiten von Projekten, Ressourcen und erweiterten Attributen.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Schritt 1: Datenverzeichnis festlegen
Legen Sie den Ordner fest, in dem sich Ihre Quell‑Projektdatei befindet und in den die Ausgabe geschrieben wird.

```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Microsoft‑Project‑Datei laden
Erstellen Sie eine `Project`‑Instanz, indem Sie die vorhandene Datei laden. Dies ist der **load Microsoft project file**‑Schritt, der Ihnen vollen Zugriff auf den Inhalt gibt.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Schritt 3: Das benutzerdefinierte Attribut definieren
Wir definieren ein neues numerisches Attribut namens **Age**. Die API prüft, ob die Definition bereits existiert; falls nicht, wird sie erstellt.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Schritt 4: Numerischen Wert in Java setzen
Erzeugen Sie eine Instanz des Attributs für eine bestimmte Ressource und weisen Sie ihr einen numerischen Wert mit `setNumericValue` zu. Dies demonstriert **set numeric value java** in Aktion.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Schritt 5: Ressource hinzufügen und das benutzerdefinierte Attribut anhängen
Fügen Sie eine neue Ressource mit dem Namen **R1** hinzu und hängen Sie das zuvor erstellte benutzerdefinierte Attribut an.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Schritt 6: Projekt als XML speichern
Speichern Sie abschließend die Änderungen, indem Sie das Projekt speichern. Dies ist der **save project as xml**‑Schritt, der eine saubere XML‑Darstellung der aktualisierten Datei erzeugt.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Schritt 7: Ergebnis anzeigen
Geben Sie eine freundliche Bestätigung aus, damit Sie wissen, dass der Vorgang ohne Fehler abgeschlossen wurde.

```java
System.out.println("Process completed Successfully");
```

Durch das Befolgen dieser Schritte haben Sie erfolgreich **ein benutzerdefiniertes Attribut erstellt**, eine Microsoft‑Project‑Datei geladen, einen numerischen Wert mit Java gesetzt und das Projekt als XML gespeichert.

## Häufige Stolperfallen & Tipps
- **Konflikte bei Attribut‑IDs:** Prüfen Sie stets `getById`, bevor Sie eine neue Definition erstellen, um doppelte IDs zu vermeiden.  
- **Umgang mit Präzision:** `BigDecimal` bewahrt die Dezimalpräzision; vermeiden Sie `float` oder `double` für exakte Werte.  
- **Dateipfade:** Verwenden Sie absolute Pfade oder konfigurieren Sie das Arbeitsverzeichnis Ihrer IDE, um `FileNotFoundException` zu verhindern.  

## Häufig gestellte Fragen

**F: Kann ich benutzerdefinierte Attribute sowohl für Aufgaben als auch für Ressourcen erstellen?**  
A: Ja – verwenden Sie `ExtendedAttributeTask` anstelle von `ExtendedAttributeResource`, wenn Sie das Attribut definieren.

**F: Ist es möglich, mehrere benutzerdefinierte Attribute auf einmal hinzuzufügen?**  
A: Absolut. Erstellen Sie separate `ExtendedAttributeDefinition`‑Objekte für jedes Attribut und hängen Sie sie an die gewünschten Ressourcen oder Aufgaben an.

**F: In welchen Formaten kann ich das Projekt speichern?**  
A: Aspose.Tasks unterstützt XML, MPP und mehrere andere Formate wie PDF und HTML. In diesem Beispiel haben wir `SaveFileFormat.Xml` verwendet.

**F: Benötige ich eine Lizenz für Aspose.Tasks bei Entwicklungs‑Builds?**  
A: Eine temporäre Lizenz reicht für die Evaluierung. Für Produktions‑Deployments ist eine Voll‑Lizenz erforderlich.

**F: Wie lese ich später die Werte der benutzerdefinierten Attribute aus?**  
A: Verwenden Sie `resource.getExtendedAttributes()`, um über die angehängten Attribute zu iterieren und deren Werte mit `getNumericValue()` oder `getTextValue()` abzurufen.

## Fazit
Ein **benutzerdefiniertes Attribut** in Microsoft Project mit Aspose.Tasks für Java zu erstellen, ist unkompliziert, sobald Sie den Workflow verstehen: Projekt laden, Attribut definieren, Wert setzen, an eine Ressource anhängen und Datei speichern. Dieser Ansatz ermöglicht es Ihnen, Projektdatenmodelle programmgesteuert zu erweitern, was zu umfangreicheren Berichten und einer engeren Integration in Ihre Geschäftsprozesse führt.

---

**Zuletzt aktualisiert:** 2026-01-13  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}