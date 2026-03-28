---
date: 2026-01-25
description: Erfahren Sie, wie Sie Aufgaben mit Aspose.Tasks für Java Attribute hinzufügen
  und Microsoft‑Project‑Dateien mit erweiterten Attributen anpassen, um eine bessere
  Projektsteuerung zu ermöglichen.
linktitle: Add Extended Attributes to Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man ein Attribut hinzufügt – Erweiterte Attribute zu Aufgaben in Aspose.Tasks
url: /de/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Attribut hinzufügt – Erweiterte Attribute zu Aufgaben in Aspose.Tasks hinzufügen

## Einleitung
Die Verbesserung Ihrer Projektmanagement‑Fähigkeiten ist entscheidend für effizientes Aufgaben‑Tracking und Ressourcenmanagement. In diesem Tutorial **lernen Sie, wie Sie ein Attribut** zu Aufgaben mit Aspose.Tasks für Java hinzufügen, wodurch Sie die Flexibilität erhalten, Microsoft‑Project‑Dateien an die spezifischen Bedürfnisse Ihrer Organisation anzupassen. Wir führen Sie Schritt für Schritt durch den gesamten Prozess, von der Einrichtung der Umgebung bis zum Speichern der aktualisierten Projektdatei.

## Schnelle Antworten
- **Was ist der Hauptzweck?** Benutzerdefinierte (erweiterte) Attribute zu Aufgaben in einer Microsoft‑Project‑Datei hinzuzufügen.  
- **Welche Bibliothek wird benötigt?** Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Lookup‑Werte hinzufügen?** Ja – Sie können Text‑ oder Dauer‑Attribute mit vordefinierten Lookup‑Listen erstellen.  
- **Welche Dateiformate werden beim Speichern unterstützt?** MPP, XML und andere von Aspose.Tasks unterstützte Formate.

## Voraussetzungen
Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse in der Java‑Programmierung.  
- Aspose.Tasks für Java Bibliothek installiert. Sie können sie von der [Website](https://releases.aspose.com/tasks/java/) herunterladen.  
- Eine integrierte Entwicklungsumgebung (IDE) für Java ist auf Ihrem System installiert.

## Pakete importieren
Importieren Sie in Ihrem Java-Projekt die erforderlichen Pakete, um auf die Funktionen von Aspose.Tasks zuzugreifen:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```

Nun zerlegen wir jedes Beispiel in mehrere Schritte:

## Wie man ein Attribut zu einer Aufgabe hinzufügt (Beispiel für Klartext)

### 1. Festlegen des Dokumentverzeichnisses
Zuerst definieren Sie den Ordner, der Ihre Quell‑Projektdatei enthält:
```java
String dataDir = "Your Document Directory";
```

### 2. Laden des Projekts
Erstellen Sie eine `Project`‑Instanz, die auf eine vorhandene `.mpp`‑Datei verweist:
```java
Project project = new Project(dataDir + "project.mpp");
```

### 3. Definieren eines Klartext‑erweiterten Attributs
Erstellen Sie eine Attributdefinition vom Typ **Text1** – diese hält den Stadtnamen für jede Aufgabe:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 4. Hinzufügen der Definition zum Projekt
Registrieren Sie die neue Definition in der Sammlung erweiterter Attribute des Projekts:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 5. Erstellen einer neuen Aufgabe
Fügen Sie eine Unteraufgabe unter der Stammaufgabe hinzu:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 6. Instanziieren des erweiterten Attributs
Erzeugen Sie eine tatsächliche Attributinstanz aus der zuvor erstellten Definition:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 7. Zuweisen eines Wertes
Setzen Sie den konkreten Wert (z. B. die Stadt „London“) für das erweiterte Attribut dieser Aufgabe:
```java
taskExtendedAttributeText1.setTextValue("London");
```

### 8. Anfügen des Attributs an die Aufgabe
Fügen Sie das ausgefüllte Attribut zur Sammlung der Aufgabe hinzu:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

### 9. Speichern des aktualisierten Projekts
Speichern Sie schließlich die Änderungen in einer neuen Datei, damit Sie das Ergebnis in Microsoft Project überprüfen können:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Hinzufügen eines Text‑Attributs mit Lookup‑Option
Um ein Text‑Attribut zu erstellen, das eine vordefinierte Liste von Werten (Lookup) anbietet, wiederholen Sie die obigen Schritte, ersetzen jedoch `ExtendedAttributeTask.Text1` durch `ExtendedAttributeTask.Text2` und füllen die Lookup‑Tabelle mit `taskExtendedAttributeText2Definition.getLookupValues().add(...)`. Dadurch können Benutzer beim Bearbeiten der Aufgabe aus einem festen Satz von Optionen wählen.

## Hinzufügen eines Dauer‑Attributs mit Lookup‑Option
Analog dazu verwenden Sie für ein auf Dauer basierendes Attribut `CustomFieldType.Duration` und `ExtendedAttributeTask.Duration2`. Befüllen Sie die Lookup‑Werte mit konkreten Zeitspannen (z. B. „1 Tag“, „2 Wochen“), um Dauereinträge in Ihrem Projekt zu standardisieren.

## Warum erweiterte Attribute verwenden?
- **Flexibilität:** Beliebige benutzerdefinierte Daten speichern, die nicht von den Standard‑Project‑Feldern abgedeckt werden.  
- **Standardisierung:** Lookup‑Tabellen erzwingen konsistente Dateneingaben.  
- **Reporting:** Benutzerdefinierte Felder können in Berichten und Filtern einbezogen werden und bieten tiefere Einblicke.

## Häufige Probleme & Fehlerbehebung
- **Ungültiger Pfad:** Stellen Sie sicher, dass `dataDir` mit einem Dateiseparator (`/` oder `\\`) endet, der für Ihr Betriebssystem geeignet ist.  
- **Lizenzausnahmen:** Ohne gültige Lizenz läuft die Bibliothek im Evaluierungsmodus und kann Wasserzeichen hinzufügen.  
- **Lookup erscheint nicht:** Nachdem Sie Lookup‑Werte definiert haben, fügen Sie die Definition immer dem Projekt hinzu, bevor Sie Aufgabenattribute erstellen.

## Häufig gestellte Fragen
### Q: Kann ich Aspose.Tasks für Java mit anderen Java‑Bibliotheken verwenden?
A: Ja, Aspose.Tasks für Java kann nahtlos in Ihre Java‑Projekte integriert werden und funktioniert gut mit anderen Java‑Bibliotheken.

### Q: Ist Aspose.Tasks für Java für groß angelegte Projektmanagement‑Anwendungen geeignet?
A: Absolut, Aspose.Tasks für Java ist darauf ausgelegt, Projekte unterschiedlicher Größe, einschließlich groß angelegter Anwendungen, zu bewältigen.

### Q: Gibt es Lizenzüberlegungen bei der Verwendung von Aspose.Tasks für Java in einem kommerziellen Projekt?
A: Ja, stellen Sie sicher, dass Sie die Lizenzinformationen auf der [Aspose.Tasks‑Website](https://purchase.aspose.com/buy) prüfen.

### Q: Wie kann ich Support oder Hilfe zu Aspose.Tasks für Java erhalten?
A: Besuchen Sie das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Support und Diskussionen.

### Q: Kann ich Aspose.Tasks für Java vor dem Kauf testen?
A: Ja, Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) erhalten.

**Additional Q&A**

**Q: Kann ich mehreren erweiterten Attributen zu einer einzelnen Aufgabe hinzufügen?**  
A: Ja, erstellen Sie einfach zusätzliche `ExtendedAttribute`‑Instanzen und fügen jede zur `ExtendedAttributes`‑Sammlung der Aufgabe hinzu.

**Q: Unterstützen Lookup‑Werte Lokalisierung?**  
A: Lookup‑Werte werden als einfache Zeichenketten gespeichert, sodass Sie bei Bedarf lokalisierte Texte für jeden Eintrag bereitstellen können.

## Fazit
Durch Befolgen dieser Schritt‑für‑Schritt‑Anleitung **haben Sie gelernt, wie man ein Attribut** zu Aufgaben in Microsoft‑Project‑Dateien mit Aspose.Tasks für Java hinzufügt. Diese leistungsstarke Anpassung ermöglicht es Ihnen, projektspezifische Daten zu erfassen, das Reporting zu verbessern und Konsistenz in den Zeitplänen Ihrer Organisation zu gewährleisten.

---

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}