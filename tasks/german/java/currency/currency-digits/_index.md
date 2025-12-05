---
date: 2025-12-05
description: Lernen Sie, wie Sie die Währungsstellen in MS Project effizient mit Aspose.Tasks
  für Java handhaben. Schritt‑für‑Schritt‑Anleitung zur Java‑Projektdateiverarbeitung
  und zum Laden von MPP‑Dateien.
language: de
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Währungsstellen von MS Project mit Aspose.Tasks verarbeiten
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Umgang mit ms project currency Ziffern mit Aspose.Tasks

## Einführung
In diesem umfassenden Tutorial erfahren Sie **wie man mit ms project currency**-Werten mit der Aspose.Tasks-Bibliothek für Java arbeitet. Egal, ob Sie ein Reporting‑Tool, ein Migrations‑Utility erstellen oder einfach die Währungseinstellungen aus einer **java project file** lesen müssen, führt Sie dieser Leitfaden durch jeden Schritt – vom Laden einer *.mpp*-Datei bis zum Extrahieren der Währungsziffern. Am Ende können Sie ms project currency‑Daten in Ihren eigenen Anwendungen problemlos handhaben.

## Schnelle Antworten
- **Welche Bibliothek liest MS Project‑Dateien?** Aspose.Tasks for Java.  
- **Wie viele Code‑Zeilen werden benötigt, um die Währungsziffern zu erhalten?** Nur drei kompakte Zeilen, nachdem das Projekt geladen wurde.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 oder höher (jedes JDK, das Aspose.Tasks ausführen kann).  
- **Kann ich andere Projekteigenschaften abrufen?** Ja – Aspose.Tasks stellt ein vollständiges Set von Projektfeldern bereit (z. B. Startdatum, Kostensätze usw.).

## Was ist ms project currency?
`ms project currency` bezieht sich auf die numerische Präzision (Anzahl der Dezimalstellen), die Microsoft Project bei der Anzeige von Geldbeträgen verwendet. Sie wird in der Projektdatei als **CURRENCY_DIGITS**‑Eigenschaft gespeichert und bestimmt, ob Beträge als ganze Zahlen, mit einer Dezimalstelle, zwei Dezimalstellen usw. angezeigt werden.

## Warum Aspose.Tasks für die Handhabung von ms project currency verwenden?
- **Keine Microsoft Project‑Installation erforderlich** – Arbeiten Sie direkt mit *.mpp*-Dateien auf jeder Plattform, die Java unterstützt.  
- **Starke Typensicherheit** – Die API liefert stark typisierte Werte, wodurch Parsing‑Fehler reduziert werden.  
- **Leistungsoptimiert** – Laden Sie große Projekte schnell und extrahieren Sie nur die benötigten Felder.  
- **Plattformübergreifend** – Ausführen unter Windows, Linux oder macOS ohne Änderungen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Java-Entwicklungsumgebung** – JDK 8 oder neuer installiert und konfiguriert.  
2. **Aspose.Tasks for Java** – Laden Sie das neueste JAR von der offiziellen Seite herunter: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Grundlegende Java‑Kenntnisse** – Sie sollten in der Lage sein, ein Java‑Projekt zu erstellen, externe Bibliotheken hinzuzufügen und eine `main`‑Methode auszuführen.  

## Pakete importieren
Zuerst importieren wir die benötigten Klassen.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Schritt 1: Datenverzeichnis definieren
Geben Sie den Ordner an, der Ihre **java project file** (`*.mpp`) enthält.  
```java
String dataDir = "Your Data Directory";
```
Ersetzen Sie `"Your Data Directory"` durch den absoluten oder relativen Pfad, in dem sich `project.mpp` befindet.

## Schritt 2: MPP‑Datei laden
Jetzt sehen wir, **wie man mpp**‑Dateien mit Aspose.Tasks lädt.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Stellen Sie sicher, dass der Dateiname exakt übereinstimmt; andernfalls wird eine `IOException` ausgelöst.

## Schritt 3: Währungsziffern abrufen
Nachdem das Projekt geladen ist, lässt sich die **ms project currency**‑Ziffern mit einer einzigen Zeile extrahieren:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Der Aufruf gibt ein `Integer` zurück, das die Anzahl der Dezimalstellen darstellt (z. B. `2` für Cent). Der Wert wird in der Konsole ausgegeben, kann aber auch in einer Variablen für weitere Verarbeitung gespeichert werden.

## Häufige Probleme & Tipps
- **Datei nicht gefunden** – Überprüfen Sie den `dataDir`‑Pfad und stellen Sie sicher, dass der Dateiname korrekt ist, einschließlich der `.mpp`‑Erweiterung.  
- **Nicht unterstützte Dateiversion** – Aspose.Tasks unterstützt Project‑Formate von 2000‑2024; ältere oder beschädigte Dateien müssen ggf. konvertiert werden.  
- **Lizenz nicht gesetzt** – Während der Entwicklung funktioniert eine Testversion, für die Produktion muss jedoch eine gültige Lizenz angewendet werden, um Evaluations‑Wasserzeichen zu vermeiden.

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks andere Projektattribute neben den Währungsziffern verarbeiten?**  
A: Ja, Aspose.Tasks bietet ein breites Spektrum an Funktionen, um verschiedene Aspekte von Projektdateien zu manipulieren, wie Aufgaben, Ressourcen und benutzerdefinierte Felder.

**Q: Ist Aspose.Tasks für Unternehmens‑Anwendungen geeignet?**  
A: Absolut, Aspose.Tasks ist darauf ausgelegt, den Anforderungen von Unternehmens‑Projekten gerecht zu werden, und bietet hohe Leistung und Skalierbarkeit.

**Q: Unterstützt Aspose.Tasks plattformübergreifende Entwicklung?**  
A: Ja, Sie können Aspose.Tasks für Java auf jeder Plattform verwenden, die die Java Runtime Environment unterstützt (Windows, Linux, macOS).

**Q: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen.

**Q: Wo bekomme ich Support für Aspose.Tasks?**  
A: Unterstützung finden Sie im [Aspose.Tasks‑Forum](https://forum.aspose.com/c/tasks/15).

---

**Zuletzt aktualisiert:** 2025-12-05  
**Getestet mit:** Aspose.Tasks for Java 24.11 (zum Zeitpunkt des Schreibens die neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}