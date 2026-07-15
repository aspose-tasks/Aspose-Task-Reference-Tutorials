---
date: 2026-02-10
description: Erfahren Sie, wie Sie Währungswerte erhalten, MS Project‑Dateien lesen
  und Projektdateien in Java mit Aspose.Tasks konvertieren. Schritt‑für‑Schritt‑Anleitung
  zum Extrahieren von Währungsziffern.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man die Währung aus MS Project mit Aspose.Tasks abruft
url: /de/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Währung aus MS Project mit Aspose.Tasks abruft

## Einführung
Falls Sie sich fragen, **wie man Währungsinformationen** aus einer Microsoft‑Project‑Datei erhält, sind Sie hier genau richtig. In diesem umfassenden Tutorial erfahren Sie, **wie man ms project currency**‑Werte mit der Aspose.Tasks‑Bibliothek für Java verarbeitet. Egal, ob Sie ein Reporting‑Tool, ein Migrations‑Utility bauen oder einfach die Währungseinstellungen aus einer **java project file** auslesen müssen – diese Anleitung führt Sie durch jeden Schritt, vom Laden einer *.mpp*‑Datei bis zum Extrahieren der Währungsstellen. Am Ende können Sie ms project currency‑Daten sicher in Ihren eigenen Anwendungen handhaben.

## Schnellantworten
- **Welche Bibliothek liest MS‑Project‑Dateien?** Aspose.Tasks für Java.  
- **Wie viele Code‑Zeilen benötigt man, um die Währungsstellen zu erhalten?** Nur drei kompakte Zeilen, nachdem das Projekt geladen wurde.  
- **Brauche ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher (jede JDK, die Aspose.Tasks ausführen kann).  
- **Kann ich weitere Projekteigenschaften abrufen?** Ja – Aspose.Tasks stellt ein vollständiges Set von Projektfeldern bereit (z. B. Startdatum, Kostensätze usw.).

## Was ist ms project currency?
`ms project currency` bezeichnet die numerische Präzision (Anzahl der Dezimalstellen), die Microsoft Project bei der Anzeige von Geldbeträgen verwendet. Sie wird im Projekt‑File als **CURRENCY_DIGITS**‑Eigenschaft gespeichert und bestimmt, ob Beträge als ganze Zahlen, mit einer Dezimalstelle, zwei Dezimalstellen usw. angezeigt werden.

## Warum Aspose.Tasks für die Verarbeitung von ms project currency verwenden?
- **Keine Installation von Microsoft Project erforderlich** – arbeiten Sie direkt mit *.mpp*‑Dateien auf jeder Plattform, die Java unterstützt.  
- **Starke Typensicherheit** – die API liefert stark typisierte Werte, wodurch Parsing‑Fehler reduziert werden.  
- **Performance‑optimiert** – große Projekte schnell laden und nur die benötigten Felder extrahieren.  
- **Plattformübergreifend** – läuft unter Windows, Linux oder macOS ohne Änderungen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java‑Entwicklungsumgebung** – JDK 8 oder neuer installiert und konfiguriert.  
2. **Aspose.Tasks für Java** – laden Sie das neueste JAR von der offiziellen Seite herunter: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Grundkenntnisse in Java** – Sie sollten in der Lage sein, ein Java‑Projekt zu erstellen, externe Bibliotheken hinzuzufügen und eine `main`‑Methode auszuführen.  

## Pakete importieren
Zuerst importieren wir die Klassen, die wir benötigen.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Schritt 1: Datenverzeichnis festlegen
Geben Sie den Ordner an, der Ihre **java project file** (`*.mpp`) enthält.  
```java
String dataDir = "Your Data Directory";
```
Ersetzen Sie `"Your Data Directory"` durch den absoluten oder relativen Pfad, in dem sich `project.mpp` befindet.

## Schritt 2: MPP‑Datei laden  
Nun zeigen wir, **wie man mpp**‑Dateien mit Aspose.Tasks lädt.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Stellen Sie sicher, dass der Dateiname exakt übereinstimmt; andernfalls wird eine `IOException` ausgelöst.

## Schritt 3: Währungsstellen abrufen  
Nachdem das Projekt geladen ist, lässt sich die **ms project currency**‑Stellenzahl in einer Zeile ermitteln:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Der Aufruf liefert ein `Integer`, das die Anzahl der Dezimalstellen repräsentiert (z. B. `2` für Cent). Der Wert wird in der Konsole ausgegeben, kann aber auch in einer Variablen für weitere Verarbeitung gespeichert werden.

## Häufige Probleme & Tipps
- **Datei nicht gefunden** – prüfen Sie den `dataDir`‑Pfad und stellen Sie sicher, dass der Dateiname korrekt ist, inklusive der `.mpp`‑Erweiterung.  
- **Nicht unterstützte Dateiversion** – Aspose.Tasks unterstützt Formate von Project 2000‑2024; ältere oder beschädigte Dateien müssen ggf. konvertiert werden.  
- **Lizenz nicht gesetzt** – während der Entwicklung funktioniert eine Testversion, für die Produktion muss jedoch eine gültige Lizenz angewendet werden, um Evaluations‑Wasserzeichen zu vermeiden.

## Häufig gestellte Fragen

**F: Kann Aspose.Tasks andere Projektattribute außer Währungsstellen verarbeiten?**  
A: Ja, Aspose.Tasks bietet ein breites Spektrum an Funktionen zur Manipulation verschiedener Aspekte von Projektdateien, wie Aufgaben, Ressourcen und benutzerdefinierte Felder.

**F: Ist Aspose.Tasks für Enterprise‑Anwendungen geeignet?**  
A: Absolut, Aspose.Tasks ist darauf ausgelegt, den Anforderungen von Unternehmens‑Projekten gerecht zu werden, und bietet hohe Leistung sowie Skalierbarkeit.

**F: Unterstützt Aspose.Tasks plattformübergreifende Entwicklung?**  
A: Ja, Sie können Aspose.Tasks für Java auf jeder Plattform nutzen, die die Java Runtime Environment unterstützt (Windows, Linux, macOS).

**F: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen.

**F: Wo finde ich Support für Aspose.Tasks?**  
A: Unterstützung erhalten Sie im [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Fazit
Sie wissen jetzt, **wie man die Währung**‑Stellen aus einer MS‑Project‑Datei mit Aspose.Tasks für Java abruft. Der Vorgang ist einfach: Projekt laden, `project.get(Prj.CURRENCY_DIGITS)` aufrufen und das Ergebnis in Ihrer Anwendung verwenden. Erkunden Sie gern weitere Projekteigenschaften nach demselben Muster und integrieren Sie diese Logik in umfangreichere Reporting‑ oder Migrationslösungen.

---

**Zuletzt aktualisiert:** 2026-02-10  
**Getestet mit:** Aspose.Tasks für Java (zum Zeitpunkt der Erstellung neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}