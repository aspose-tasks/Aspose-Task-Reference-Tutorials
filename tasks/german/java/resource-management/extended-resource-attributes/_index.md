---
date: 2026-06-10
description: Erfahren Sie, wie Sie ein erweitertes Attribut in Java erstellen, eine
  Microsoft Project-Datei laden, numerische Werte festlegen und das Projekt mit Aspose.Tasks
  für Java als XML speichern.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Verwalten erweiterter Ressourcenattribute in Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Wie man erweiterte Attribute in Java mit Aspose.Tasks erstellt
url: /de/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein erweitertes Attribut in Java mit Aspose.Tasks erstellt

## Einführung
In diesem praxisorientierten Leitfaden **erstellen Sie ein erweitertes Attribut in Java** für eine Microsoft‑Project‑Datei mit Aspose.Tasks. Wir führen Sie durch das Laden eines bestehenden Projekts, das Definieren eines neuen numerischen Attributs, das Zuweisen eines Werts zu einer Ressource und schließlich das Persistieren der Änderungen als XML‑Datei. Am Ende haben Sie ein wiederverwendbares Code‑Muster, das in jede Java‑basierte Projekt‑Management‑Lösung integriert werden kann.

## Schnelle Antworten
- **Was ist ein erweitertes Attribut?**  
  Ein benutzerdefiniertes Feld (z. B. Alter, Fähigkeitsstufe), das zusätzliche Daten für Ressourcen oder Vorgänge speichert.  
- **Welche API erstellt es?**  
  Aspose.Tasks für Java stellt die Klasse `ExtendedAttributeDefinition` zur Verfügung, um benutzerdefinierte Attribute zu definieren und zu verwalten.  
- **Brauche ich eine Lizenz?**  
  Eine temporäre Evaluierungslizenz funktioniert für die Entwicklung; für Produktionsbereitstellungen ist eine Voll‑Lizenz erforderlich.  
- **Kann ich Zahlen speichern?**  
  Ja – verwenden Sie `setNumericValue(BigDecimal)`, um präzise Dezimalwerte zuzuweisen.  
- **Wie speichere ich die Änderungen?**  
  Rufen Sie `project.save("output.xml", SaveFileFormat.Xml)` auf, um das aktualisierte Projekt im XML‑Format zu schreiben.

## Was ist ein benutzerdefiniertes Attribut?
Ein **benutzerdefiniertes Attribut** (auch als erweitertes Attribut bezeichnet) ist eine zusätzliche Spalte, die Sie zu Ressourcen oder Vorgängen in Microsoft Project hinzufügen können. Es ermöglicht Ihnen, Daten zu erfassen, die von den integrierten Feldern nicht abgedeckt werden, wie z. B. das Alter von Mitarbeitern, Zertifizierungsstufen oder jede geschäftsspezifische Kennzahl.

## Warum ein erweitertes Attribut in Java erstellen?
Das Erstellen eines erweiterten Attributs in Java ermöglicht es Ihnen, Projektdaten programmgesteuert zu erweitern, Konsistenz über Dateien hinweg sicherzustellen und automatisierte Berichte zu ermöglichen. Durch einmaliges Definieren des Attributs können Sie es auf beliebig viele Ressourcen oder Vorgänge anwenden, ohne manuelle Eingaben, was Zeit spart und Fehler reduziert.

- **Daten an Ihre Organisation anpassen** – speichern Sie jede für Sie relevante Kennzahl ohne manuelle Excel‑Umwege.  
- **Erweiterte Berichte ermöglichen** – fragen Sie das benutzerdefinierte Feld später für Dashboards oder Analysen ab.  
- **Konsistenz wahren** – wenden Sie die gleiche Definition programmgesteuert auf Dutzende von Projekten an und eliminieren Sie menschliche Fehler.  
- **Leistungstests** – Aspose.Tasks verarbeitet Projekte mit bis zu 10.000 Vorgängen und 5.000 Ressourcen, ohne die gesamte Datei in den Speicher zu laden, laut den Produktbenchmarks.

## Voraussetzungen
1. **Java Development Kit** – JDK 8 oder neuer installiert.  
2. **Aspose.Tasks für Java** – laden Sie die neueste Version von [hier](https://releases.aspose.com/tasks/java/) herunter.  
3. **IDE** – Eclipse, IntelliJ IDEA oder jede Java‑kompatible Entwicklungsumgebung.  

## Wie man ein erweitertes Attribut in Java erstellt?
Laden Sie Ihr Projekt, definieren Sie das Attribut, hängen Sie es an eine Ressource an und speichern Sie die Datei – alles in wenigen einfachen Schritten. Die folgenden Abschnitte teilen jeden Schritt in eine knappe Erklärung und den Platzhalter, an dem Ihr tatsächlicher Code steht.

### Schritt‑für‑Schritt‑Anleitung

#### Pakete importieren
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` und verwandte Klassen befinden sich im Namensraum `com.aspose.tasks`. Importieren Sie sie am Anfang Ihrer Java‑Datei.

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

#### Schritt 1: Datenverzeichnis definieren
`Paths` ist eine Hilfsklasse, die Methoden bereitstellt, um einen Dateisystempfad plattformunabhängig zu erhalten.

```java
String dataDir = "Your Data Directory";
```

#### Schritt 2: Microsoft Project‑Datei laden
`Project` repräsentiert eine Microsoft‑Project‑Datei im Speicher und ermöglicht Lese‑ und Schreibzugriff auf deren Inhalt.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Schritt 3: Das benutzerdefinierte Attribut definieren
`ExtendedAttributeDefinition` definiert das Schema eines neuen benutzerdefinierten Feldes, das an Ressourcen oder Vorgänge angehängt werden kann.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Schritt 4: Numerischen Wert in Java setzen
`ExtendedAttributeResource` enthält den Wert eines benutzerdefinierten Attributs für eine bestimmte Ressourceninstanz.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Schritt 5: Ressource hinzufügen und das benutzerdefinierte Attribut anhängen
`Resource` modelliert eine Projektressource wie eine Person, Ausrüstung oder Material.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Schritt 6: Projekt als XML speichern
`SaveFileFormat` enumeriert die unterstützten Ausgabeformate zum Speichern eines Projekts, einschließlich XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Schritt 7: Ergebnis anzeigen
`System.out.println` gibt eine Textzeile auf die Standard‑Konsolenausgabe aus.

```java
System.out.println("Process completed Successfully");
```

## Häufige Fallstricke & Tipps
- **Konflikte bei Attribut‑IDs:** Rufen Sie stets `project.getExtendedAttributes().getById(id)` auf, bevor Sie eine neue Definition erstellen, um doppelte Kennungen zu vermeiden.  
- **Umgang mit Präzision:** Bevorzugen Sie `BigDecimal` gegenüber `float`/`double` für exakte numerische Werte; dies verhindert Rundungsfehler in Berichten.  
- **Zuverlässigkeit von Dateipfaden:** Verwenden Sie `Paths.get(...).toAbsolutePath()` oder konfigurieren Sie das Arbeitsverzeichnis Ihrer IDE, um `FileNotFoundException` zu vermeiden.  

## Häufig gestellte Fragen

**F: Kann ich benutzerdefinierte Attribute sowohl für Vorgänge als auch für Ressourcen erstellen?**  
A: Ja – verwenden Sie `ExtendedAttributeTask` anstelle von `ExtendedAttributeResource`, wenn Sie das Attributschema definieren.

**F: Ist es möglich, mehrere benutzerdefinierte Attribute gleichzeitig hinzuzufügen?**  
A: Absolut. Erstellen Sie separate `ExtendedAttributeDefinition`‑Objekte für jedes Attribut und hängen Sie sie an die gewünschten Ressourcen oder Vorgänge an.

**F: In welchen Formaten kann ich das Projekt speichern?**  
A: Aspose.Tasks unterstützt XML, MPP, PDF, HTML und mehr als 30 weitere Formate. In diesem Beispiel haben wir `SaveFileFormat.Xml` verwendet.

**F: Benötige ich eine Lizenz für Entwicklungs‑Builds?**  
A: Eine temporäre Evaluierungslizenz reicht für Tests aus. Für jede Produktionsbereitstellung ist eine vollständige kommerzielle Lizenz erforderlich.

**F: Wie lese ich später die Werte des benutzerdefinierten Attributs aus?**  
A: Rufen Sie `resource.getExtendedAttributes()` auf und iterieren Sie über die Sammlung; holen Sie den gespeicherten Wert mit `getNumericValue()` oder `getTextValue()`.

---

**Zuletzt aktualisiert:** 2026-06-10  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Ressourcen erstellt – Ressourcenmanagement mit Aspose.Tasks für Java](/tasks/java/resource-management/)
- [Benutzerdefiniertes Feld erstellen – Aspose - Erweiterte Attribute verarbeiten](/tasks/java/project-management/extended-attributes/)
- [Wie man ein Projekt erstellt – Neue Vorgangsattribute mit Aspose.Tasks festlegen](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}