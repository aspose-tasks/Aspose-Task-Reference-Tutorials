---
date: 2026-01-13
description: Erfahren Sie, wie Sie nicht‑Wurzel‑Ressourcen in Microsoft‑Project‑Dateien
  mit Aspose.Tasks für Java iterieren.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Iterieren von Nicht‑Root‑Ressourcen mit Aspose.Tasks für Java
url: /de/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nicht‑Stammressourcen mit Aspose.Tasks für Java iterieren

## Einführung
Aspose.Tasks for Java ist eine leistungsstarke Bibliothek, die Entwicklern eine saubere, objektorientierte Möglichkeit bietet, mit Microsoft Project‑Dateien zu arbeiten. In diesem Tutorial lernen Sie **wie man Nicht‑Stammressourcen iteriert**, sodass Sie Ressourcendaten lesen, ändern oder analysieren können, ohne sich mit dem Stamm‑Platzhalter zu befassen. Egal, ob Sie ein Reporting‑Tool, ein Migrations‑Skript oder einen benutzerdefinierten Scheduler erstellen, das Beherrschen dieser Technik macht Ihren Code präziser und effizienter.

## Schnelle Antworten
- **Was bedeutet „non‑root resource“?** Eine Ressource, die nicht der Standard‑„Project“-Platzhalter (der Stammknoten) ist.  
- **Warum die Stammressource herausfiltern?** Der Stamm enthält keine nützlichen Planungsdaten und kann Berichte verunreinigen.  
- **Welche Aspose.Tasks‑Klasse liefert die Ressourcensammlung?** `Project.getResources()`.  
- **Benötige ich eine Lizenz für diesen Code?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich das mit Java 17 verwenden?** Ja – Aspose.Tasks unterstützt Java 8 und höher.

## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – Installieren Sie das neueste JDK von der [Oracle-Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java Bibliothek** – Laden Sie die neueste JAR von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die erforderlichen Aspose.Tasks‑Klassen:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Schritt 1: Datenverzeichnis einrichten
```java
String dataDir = "Your Data Directory";
```
Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad, in dem Ihre `.mpp`‑Dateien liegen.

## Schritt 2: Projektdatei laden
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Dies erstellt eine `Project`‑Instanz, indem **ResourceCosts.mpp** aus dem von Ihnen angegebenen Ordner geladen wird.

## Schritt 3: Nicht‑Stammressourcen iterieren
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Die Schleife durchläuft jedes `Resource`‑Objekt im Projekt. Die Prüfung `isRoot()` überspringt die eingebaute Stammressource, und die Anweisung `System.out.println` gibt den Namen jeder **Nicht‑Stammressource** aus.

## Wie man Nicht‑Stammressourcen iteriert
Das obige Snippet demonstriert das Kernmuster:

1. Rufen Sie die vollständige Sammlung mit `prj.getResources()` ab.  
2. Verwenden Sie `isRoot()`, um den Platzhalter herauszufiltern.  
3. Greifen Sie bei Bedarf auf beliebige Ressourcenfelder zu (z. B. `Rsc.NAME`, `Rsc.COST`).

Sie können dieses Muster erweitern, um Kosten zu aggregieren, nach CSV zu exportieren oder benutzerdefinierte Geschäftsregeln anzuwenden.

## Häufige Fallstricke & Tipps
- **Null‑Prüfungen** – Einige Ressourcen können optionale Felder besitzen; schützen Sie sich immer vor `null`, wenn Sie `get()` aufrufen.  
- **Performance** – Bei sehr großen Projekten sollten Sie eine indexbasierte Schleife in Betracht ziehen, um das Erzeugen Zwischensammlungen zu vermeiden.  
- **Lizenzierung** – Das Ausführen des Codes ohne gültige Lizenz fügt exportierten Dateien ein Wasserzeichen hinzu; stellen Sie sicher, dass Sie Ihre Lizenz frühzeitig in der Anwendung aktivieren.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt **wie man Nicht‑Stammressourcen** mit Aspose.Tasks für Java iteriert. Diese Technik hilft Ihnen, sich auf tatsächliche Projektressourcen zu konzentrieren, Datenextrakte zu bereinigen und zuverlässigere Projekt‑Management‑Lösungen zu erstellen.

## FAQ
### Kann ich Aspose.Tasks für Java verwenden, um neue Projektdateien zu erstellen?
Ja, Aspose.Tasks bietet vollständige CRUD‑Funktionen (Create, Read, Update, Delete) für die Projektformate MPP, MPT und XML.

### Unterstützt Aspose.Tasks alle Versionen von Microsoft‑Project‑Dateien?
Absolut. Es unterstützt Project‑Dateien von 2003 bis 2019, einschließlich der neuesten MPP‑Spezifikationen.

### Ist Aspose.Tasks mit Java‑Frameworks wie Spring kompatibel?
Ja, Sie können die Bibliothek in Spring‑Beans injizieren oder in jeder Standard‑Java‑Anwendung verwenden.

### Kann ich Projektdatenfelder mit Aspose.Tasks anpassen?
Definitiv. Die API ermöglicht das Hinzufügen, Ändern oder Löschen benutzerdefinierter Felder bei Aufgaben, Ressourcen und Zuweisungen.

### Bietet Aspose.Tasks Support und Dokumentation für Entwickler?
Das Produkt enthält umfassende API‑Dokumentation, Code‑Beispiele und ein dediziertes Support‑Forum für schnelle Hilfe.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-01-13  
**Getestet mit:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose