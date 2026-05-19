---
date: 2026-01-15
description: Erfahren Sie, wie Sie mit budgetierten Kostenarbeiten, die in Microsoft‑Project‑Dateien
  geplant sind, mit Aspose.Tasks für Java arbeiten. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Budgetierte Kostenarbeit geplant mit Aspose.Tasks für Java
url: /de/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Budgeted Cost Work Scheduled mit Aspose.Tasks für Java

## Einführung

Das Verwalten von **budgeted cost work scheduled** (BCWS) ist entscheidend, um ein Projekt im Zeitplan zu halten und sicherzustellen, dass die finanzielle Prognose mit der geplanten Arbeit übereinstimmt. In Microsoft Project stellt BCWS den Geldbetrag dar, der bis zu einem bestimmten Datum für die geplante Arbeit ausgegeben worden sein sollte. Aspose.Tasks für Java gibt Ihnen die vollständige programmgesteuerte Kontrolle über diese Werte, sodass Sie Ressourcen‑Kosten auslesen, ändern und berichten können, ohne die .mpp‑Datei manuell zu öffnen. In diesem Tutorial führen wir Sie durch ein vollständiges Beispiel, das zeigt, wie ein Projekt geladen, über seine Ressourcen iteriert und das budgeted cost work scheduled zusammen mit anderen wichtigen Kostenkennzahlen angezeigt wird.

## Schnellantworten
- **Was bedeutet BCWS?** Budgeted Cost Work Scheduled – die geplanten Kosten für bis dato terminierte Arbeit.  
- **Welche API‑Eigenschaft ruft BCWS ab?** `Rsc.BCWS` auf einem `Resource`‑Objekt.  
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose Evaluierungslizenz reicht für Tests; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Kann ich BCWS‑Werte ändern?** Ja, Sie können `Rsc.BCWS` wie jedes andere numerische Feld setzen.  
- **Unterstützte Project‑Versionen?** Alle Microsoft Project‑Versionen von 2000 bis zum neuesten .mpp‑Format.

## Was ist budgeted cost work scheduled?

**Budgeted Cost Work Scheduled (BCWS)** ist eine Leistungskennzahl, die die Kosten widerspiegelt, die bis zu einem bestimmten Zeitpunkt für die geplante Arbeit angefallen sein sollten. Sie ist ein Grundpfeiler des Earned Value Management (EVM) und hilft Projektleitern, geplante mit tatsächlichen Ausgaben zu vergleichen.

## Voraussetzungen

Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie:

1. Die Grundlagen von Java gut beherrschen.  
2. Aspose.Tasks für Java in Ihr Projekt eingebunden haben (Maven/Gradle oder JAR).  
3. Eine Microsoft Project‑Datei (`.mpp`) besitzen, die Ressourcen mit Kostendaten enthält (z. B. *ResourceCosts.mpp*).

## Pakete importieren

Importieren Sie zunächst die für die Projekt‑ und Ressourcenverwaltung benötigten Aspose.Tasks‑Klassen:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Schritt 1: Datenverzeichnis definieren

```java
String dataDir = "Your Data Directory";
```

Ersetzen Sie `"Your Data Directory"` durch den absoluten oder relativen Pfad, in dem *ResourceCosts.mpp* liegt.

## Schritt 2: MS Project‑Datei laden

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

Der `Project`‑Konstruktor liest die .mpp‑Datei ein und erstellt eine In‑Memory‑Repräsentation, die Sie abfragen können.

## Schritt 3: Durch Ressourcen iterieren

```java
for (Resource res : prj.getResources()) {
```

Diese Schleife durchläuft jede im Projekt definierte Ressource und gibt Ihnen Zugriff auf deren Kostenfelder.

## Schritt 4: Ressourcennamen und Kosten prüfen

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Innerhalb des `if`‑Blocks führen wir aus:

* Ausgabe der **Gesamtkosten** (`Rsc.COST`).  
* Ausgabe der **tatsächlichen Kosten der geleisteten Arbeit** (`Rsc.ACWP`).  
* Ausgabe des **budgeted cost work scheduled** (`Rsc.BCWS`) – die zentrale Kennzahl, auf die wir uns konzentrieren.  
* Ausgabe des **budgeted cost work performed** (`Rsc.BCWP`).

Diese vier Werte geben Ihnen einen schnellen Überblick über den finanziellen Stand des Projekts.

## Warum die Überwachung von budgeted cost work scheduled wichtig ist

* **Frühwarnung:** Wenn BCWS deutlich höher ist als die tatsächlichen Kosten, könnten Sie Ressourcen überlasten.  
* **Earned‑Value‑Analyse:** BCWS ist ein wichtiger Eingabewert für die Berechnung von Cost Variance (CV) und Schedule Variance (SV).  
* **Prognosen:** Präzise BCWS‑Daten helfen, zukünftige Cash‑Flow‑Bedarfe vorherzusagen und Stakeholder‑Berichte zu erstellen.

## Häufige Probleme & Fehlersuche

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| `null` wird für BCWS ausgegeben | Ressource hat keine Kostensatz‑Tabelle definiert | Definieren Sie eine Kostensatz‑Tabelle für die Ressource in Microsoft Project oder setzen Sie sie programmgesteuert über `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` beim Durchlaufen der Ressourcen | Projektdatei ist beschädigt oder enthält leere Ressourceneinträge | Validieren Sie die .mpp‑Datei in Microsoft Project und entfernen Sie leere Ressourcen |
| Unerwartete Werte (z. B. negatives BCWS) | Benutzerdefinierte Felder überschreiben Standard‑Kostenfelder | Stellen Sie sicher, dass Sie auf das Standardfeld `Rsc.BCWS` zugreifen und nicht auf ein benutzerdefiniertes Feld mit demselben Namen |

## Häufig gestellte Fragen

**F: Kann ich den BCWS‑Wert programmgesteuert aktualisieren?**  
A: Ja. Verwenden Sie `res.set(Rsc.BCWS, newValue)` und speichern Sie das Projekt anschließend mit `prj.save("Updated.mpp")`.

**F: Unterstützt Aspose.Tasks Projekte mit mehreren Währungen?**  
A: Absolut. Kostenfelder berücksichtigen die in der Projektdatei definierten Währungseinstellungen.

**F: Gibt es eine Möglichkeit, diese Kostenkennzahlen als CSV zu exportieren?**  
A: Sie können über die Ressourcen iterieren und die Werte in einen `StringBuilder` schreiben oder eine CSV‑Bibliothek nutzen, um die Datei zu erzeugen.

**F: Wie unterscheidet sich BCWS von BCWP?**  
A: BCWS ist die geplante Kosten für terminierte Arbeit, während BCWP (Budgeted Cost Work Performed) die geplanten Kosten für bereits abgeschlossene Arbeit widerspiegelt.

**F: Benötige ich eine spezielle Lizenz, um Kostendaten zu lesen?**  
A: Die Evaluierungslizenz bietet vollen Lese‑/Schreibzugriff; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.

## Fazit

Durch die Nutzung von Aspose.Tasks für Java erhalten Sie präzisen, programmgesteuerten Zugriff auf **budgeted cost work scheduled** und weitere wichtige Kostenkennzahlen. Das ermöglicht Ihnen, benutzerdefinierte Dashboards zu erstellen, Earned‑Value‑Berichte zu automatisieren und Ihre Projekte finanziell im Griff zu behalten – ganz ohne manuelle Interaktion mit Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-01-15  
**Getestet mit:** Aspose.Tasks für Java 24.12 (latest)  
**Autor:** Aspose