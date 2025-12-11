---
date: 2025-12-11
description: Erfahren Sie, wie Sie Gruppendefinitionsdaten aus Microsoft Project‑Dateien
  mit Aspose.Tasks für Java lesen. Folgen Sie unserem Schritt‑für‑Schritt‑Tutorial.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Gruppendefinitionsdaten in Aspose.Tasks lesen
url: /de/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gruppendefinitionsdaten in Aspose.Tasks lesen

## Einleitung
Aspose.Tasks für Java ist eine leistungsstarke Bibliothek, die Entwicklern das einfache Manipulieren von Microsoft‑Project‑Dateien ermöglicht. In diesem Tutorial **lernen Sie, wie Sie Gruppendefinitionsdaten** Schritt für Schritt aus einer Projektdatei auslesen, sodass Sie Aufgaben‑Gruppeninformationen in Ihren Java‑Anwendungen extrahieren und verarbeiten können.

## Schnelle Antworten
- **Was bedeutet “read group definition”?** Es bezieht sich auf das Extrahieren der Definition von Aufgabengruppen (Name, Kriterien, Formatierung) aus einer Microsoft‑Project‑Datei.  
- **Welche Bibliothek benötige ich?** Aspose.Tasks für Java.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche IDEs werden unterstützt?** Jede Java‑IDE wie IntelliJ IDEA oder Eclipse.  
- **Wie viel Code ist nötig?** Weniger als 30 Zeilen Java‑Code, um ein Projekt zu laden und Gruppendetails anzuzeigen.

## Was ist das Lesen von Gruppendefinitionen?
Eine *Gruppendefinition* in Microsoft Project beschreibt, wie Aufgaben anhand von Kriterien (z. B. Status, Priorität) zusammengefasst werden. Das Auslesen dieser Definition ermöglicht es, die Gruppierungslogik, Farben, Schriftarten und die Sortierreihenfolge programmgesteuert zu inspizieren.

## Warum Gruppendefinitionsdaten lesen?
- **Automatisierung:** Erstellen Sie benutzerdefinierte Berichte, die die Gruppierung aus Project widerspiegeln.  
- **Migration:** Übertragen Sie Gruppierungsregeln in ein anderes Projekt oder ein anderes Projekt‑Management‑System.  
- **Validierung:** Stellen Sie sicher, dass die erwarteten Gruppen existieren, bevor Sie Massen‑Updates durchführen.  
- **Anpassung:** Wenden Sie zusätzliche Geschäftslogik basierend auf den Schrift‑ oder Farbeinstellungen der Gruppe an.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java Development Kit (JDK)** – jede aktuelle Version (8 oder neuer).  
2. **Aspose.Tasks für Java Bibliothek** – herunterladen von [hier](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  

## Pakete importieren
Zuerst importieren Sie das Kern‑Aspose‑Tasks‑Paket:

```java
import com.aspose.tasks.*;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Richten Sie Ihr Datenverzeichnis ein
Definieren Sie den Ordner, der die `.mpp`‑Datei enthält, die Sie untersuchen möchten.

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten Pfad zu Ihrem Projektdatei‑Standort.

### Schritt 2: Projektdatei laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie auf Ihre `.mpp`‑Datei verweisen.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Schritt 3: Anzahl der Aufgabengruppen abrufen
Geben Sie die Gesamtzahl der im Projekt definierten Aufgabengruppen aus.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Schritt 4: Spezifische Aufgabengruppeninformationen abrufen
Holen Sie sich eine bestimmte Gruppe (Index 1 in diesem Beispiel) und zeigen Sie deren Namen sowie die Anzahl der enthaltenen Kriterien an.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Schritt 5: Gruppenkriteriums‑Informationen abrufen
Jede Gruppe kann ein oder mehrere Kriterien besitzen. Das nachfolgende Snippet extrahiert Details wie das für die Gruppierung verwendete Feld, den Gruppierungsmodus, die Zellenfarbe und das Muster.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Schritt 6: Elterngruppe prüfen
Manchmal gehört ein Kriterium zu einer Elterngruppe. Diese Prüfung bestätigt die Beziehung.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Schritt 7: Schriftinformationen des Kriteriums abrufen
Gruppenkriterien können benutzerdefinierte Schriftstile haben. Der folgende Code gibt die Schriftfamilie, Größe, Stil und Sortierrichtung aus.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **`NullPointerException` bei `criterion.getParentGroup()`** | Das Kriterium hat möglicherweise keine Elterngruppe. | Fügen Sie vor dem Vergleich eine Null‑Prüfung hinzu. |
| **Datei nicht gefunden** | Der `dataDir`‑Pfad ist falsch. | Verwenden Sie `Paths.get(dataDir, "project.mpp").toAbsolutePath()` zur Überprüfung. |
| **Lizenz nicht gesetzt** | Die Aspose‑Bibliothek läuft im Evaluierungsmodus und kann die Ausgabe einschränken. | Registrieren Sie Ihre Lizenz mit `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Tasks für Java verwenden, um Projektdateien zu ändern?**  
A: Ja, die Bibliothek bietet vollständige Lese‑/Schreib‑Funktionen für Microsoft‑Project‑Dateien.

**F: Ist Aspose.Tasks für Java mit allen Versionen von Microsoft‑Project‑Dateien kompatibel?**  
A: Sie unterstützt MPP, XML und andere gängige Project‑Formate über viele Versionen hinweg.

**F: Wie kann ich Fehler beim Arbeiten mit Aspose.Tasks für Java behandeln?**  
A: Umschließen Sie Datei‑Operationen in `try‑catch`‑Blöcken und prüfen Sie `TasksException` für detaillierte Meldungen.

**F: Bietet Aspose.Tasks für Java Unterstützung für den Export von Projektdaten in andere Formate?**  
A: Absolut – Sie können mit den Export‑APIs in PDF, XLSX, CSV und weitere Formate exportieren.

**F: Wo finde ich zusätzliche Ressourcen und Support für Aspose.Tasks für Java?**  
A: Besuchen Sie die [Aspose.Tasks für Java Dokumentation](https://reference.aspose.com/tasks/java/) für vollständige API‑Referenzen und das [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15) für Community‑Hilfe.

## Fazit
In diesem Tutorial haben wir gezeigt, wie man **Gruppendefinitionsdaten** aus einer Microsoft‑Project‑Datei mit Aspose.Tasks für Java ausliest. Durch Befolgen der obigen Schritte können Sie Gruppennamen, Kriterien, Formatierungen und Elterngruppe‑Beziehungen extrahieren, was Ihnen ermöglicht, benutzerdefinierte Berichte zu erstellen, Einstellungen zu migrieren oder Validierungslogik in Ihren Java‑Anwendungen zu automatisieren.

---

**Zuletzt aktualisiert:** 2025-12-11  
**Getestet mit:** Aspose.Tasks für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}