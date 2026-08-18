---
date: 2026-02-18
description: Erfahren Sie, wie Sie Gruppendefinitionsdaten aus Microsoft‑Project‑Dateien
  mit Aspose.Tasks für Java lesen. Dieses Tutorial zeigt, wie Sie Gruppendetails auslesen
  und Informationen zur Aufgaben­gruppierung extrahieren.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man Gruppendefinitionsdaten in Aspose.Tasks liest
url: /de/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gruppen-Definitionsdaten in Aspose.Tasks auslesen

## Einführung
Aspose.Tasks für Java ist eine leistungsstarke Bibliothek, die Entwicklern das einfache Manipulieren von Microsoft‑Project‑Dateien ermöglicht. In diesem Tutorial **lernen Sie, wie Sie Gruppen‑Definitionsdaten** Schritt für Schritt aus einer Projektdatei auslesen, sodass Sie Aufgaben‑Gruppeninformationen in Ihren Java‑Anwendungen extrahieren und verarbeiten können. Das Verständnis **wie man Gruppen** ausliest, befähigt Sie, Berichte zu automatisieren, Einstellungen zu migrieren und Projektstrukturen programmgesteuert zu validieren.

## Schnellantworten
- **Was bedeutet „Gruppen‑Definition auslesen“?** Es bezeichnet das Extrahieren der Definition von Aufgaben‑Gruppen (Name, Kriterien, Formatierung) aus einer Microsoft‑Project‑Datei.  
- **Welche Bibliothek benötige ich?** Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche IDEs werden unterstützt?** Jede Java‑IDE wie IntelliJ IDEA oder Eclipse.  
- **Wie viel Code ist nötig?** Weniger als 30 Zeilen Java‑Code, um ein Projekt zu laden und Gruppendetails anzuzeigen.

## So lesen Sie Gruppen‑Definitionsdaten aus
Im Folgenden finden Sie eine kompakte, schrittweise Anleitung, die **zeigt, wie Gruppen‑Informationen** aus einer `.mpp`‑Datei ausgelesen werden. Jeder Schritt enthält eine kurze Erklärung sowie den exakt benötigten Code.

## Was ist eine Gruppen‑Definition?
Eine *Gruppen‑Definition* in Microsoft Project beschreibt, wie Aufgaben anhand von Kriterien (z. B. Status, Priorität) zusammengefasst werden. Das Auslesen dieser Definition ermöglicht es Ihnen, die Gruppierungslogik, Farben, Schriftarten und Sortierreihenfolge, die im Projektfile verwendet werden, programmgesteuert zu prüfen.

## Warum Gruppen‑Definitionsdaten auslesen?
- **Automatisierung:** Erstellen Sie benutzerdefinierte Berichte, die die Gruppierung aus Project widerspiegeln.  
- **Migration:** Übertragen Sie Gruppierungsregeln in ein anderes Projekt oder ein alternatives Projekt‑Management‑System.  
- **Validierung:** Stellen Sie sicher, dass die erwarteten Gruppen existieren, bevor Sie Massen‑Updates durchführen.  
- **Anpassung:** Wenden Sie zusätzliche Geschäftslogik basierend auf Schrift‑ oder Farbeinstellungen der Gruppe an.  
- **Einblick:** Das Wissen **wie man Gruppen** ausliest, hilft Ihnen, unerwartete Aufgaben‑Layouts zu diagnostizieren.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – jede aktuelle Version (8 oder neuer).  
2. **Aspose.Tasks für Java Bibliothek** – herunterladen von [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  

## Pakete importieren
Importieren Sie zunächst das Kern‑Package von Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis festlegen
Definieren Sie den Ordner, der die zu untersuchende `.mpp`‑Datei enthält.

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad zu Ihrem Projektdatei‑Standort.

### Schritt 2: Projektdatei laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie auf Ihre `.mpp`‑Datei verweisen.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Schritt 3: Anzahl der Aufgaben‑Gruppen ermitteln
Geben Sie die Gesamtzahl der im Projekt definierten Aufgaben‑Gruppen aus.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Schritt 4: Informationen zu einer bestimmten Aufgaben‑Gruppe abrufen
Holen Sie sich eine bestimmte Gruppe (Index 1 in diesem Beispiel) und zeigen Sie deren Namen sowie die Anzahl der enthaltenen Kriterien an.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Schritt 5: Kriterien‑Informationen der Gruppe auslesen
Jede Gruppe kann ein oder mehrere Kriterien besitzen. Der nachfolgende Ausschnitt extrahiert Details wie das für die Gruppierung verwendete Feld, den Gruppierungsmodus, die Zellfarbe und das Muster.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Schritt 6: Übergeordnete Gruppe prüfen
Manchmal gehört ein Kriterium zu einer übergeordneten Gruppe. Diese Prüfung bestätigt die Beziehung.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Schritt 7: Schriftinformationen des Kriteriums auslesen
Gruppenkriterien können eigene Schriftstile haben. Der folgende Code gibt Schriftfamilie, Größe, Stil und Sortierrichtung aus.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Häufige Probleme und Lösungen
| Problem | Warum es auftritt | Lösung |
|-------|----------------|-----|
| **`NullPointerException` bei `criterion.getParentGroup()`** | Das Kriterium hat möglicherweise keine übergeordnete Gruppe. | Fügen Sie vor dem Vergleich einen Null‑Check hinzu. |
| **Datei nicht gefunden** | Der Pfad `dataDir` ist falsch. | Verwenden Sie `Paths.get(dataDir, "project.mpp").toAbsolutePath()` zur Überprüfung. |
| **Lizenz nicht gesetzt** | Die Aspose‑Bibliothek läuft im Evaluierungsmodus und kann die Ausgabe einschränken. | Registrieren Sie Ihre Lizenz mit `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## Häufig gestellte Fragen

**F: Kann ich mit Aspose.Tasks für Java Projektdateien ändern?**  
A: Ja, die Bibliothek bietet vollständige Lese‑/Schreib‑Funktionen für Microsoft‑Project‑Dateien.

**F: Ist Aspose.Tasks für Java mit allen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Sie unterstützt MPP, XML und weitere gängige Project‑Formate über zahlreiche Versionen hinweg.

**F: Wie gehe ich mit Fehlern bei der Arbeit mit Aspose.Tasks für Java um?**  
A: Umschließen Sie Datei‑Operationen in `try‑catch`‑Blöcken und prüfen Sie `TasksException` für detaillierte Meldungen.

**F: Bietet Aspose.Tasks für Java Export‑Funktionen für andere Formate?**  
A: Absolut – Sie können mit den Export‑APIs nach PDF, XLSX, CSV und mehr exportieren.

**F: Wo finde ich zusätzliche Ressourcen und Support für Aspose.Tasks für Java?**  
A: Besuchen Sie die [Aspose.Tasks für Java Dokumentation](https://reference.aspose.com/tasks/java/) für vollständige API‑Referenzen und das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Hilfe.

## Fazit
In diesem Tutorial haben wir **gezeigt, wie man Gruppen‑Definitionsdaten** aus einer Microsoft‑Project‑Datei mit Aspose.Tasks für Java ausliest. Durch Befolgen der obigen Schritte können Sie Gruppennamen, Kriterien, Formatierungen und übergeordnete Gruppenbeziehungen extrahieren, wodurch Sie benutzerdefinierte Berichte erstellen, Einstellungen migrieren oder Validierungslogik in Ihren Java‑Anwendungen automatisieren können.

---

**Zuletzt aktualisiert:** 2026-02-18  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}