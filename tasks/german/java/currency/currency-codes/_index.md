---
date: 2025-12-09
description: Erfahren Sie, wie Sie MS‑Project‑Dateien lesen und Währungscodes effizient
  mit Aspose.Tasks für Java verwalten. Optimieren Sie Ihre Projektmanagement‑Aufgaben
  mühelos.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Wie man MS Project‑Dateien liest und Währungscodes mit Aspose.Tasks verwaltet
url: /de/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So lesen Sie MS Project-Dateien und verwalten Währungscodes mit Aspose.Tasks

## Einführung
Willkommen! In diesem Tutorial erfahren Sie **wie man MS Project-Dateien** liest und speziell **Währungscodes** mit der Aspose.Tasks Java API verwaltet. Egal, ob Sie Berichte erstellen, Projekte mit mehreren Währungen konsolidieren oder einfach sicherstellen möchten, dass die richtigen Finanzsymbole angezeigt werden – diese Anleitung führt Sie durch jeden Schritt, von der Einrichtung Ihrer Umgebung bis zum programmgesteuerten Abrufen des Währungscodes. Am Ende können Sie MS Project-Dateien problemlos lesen und die benötigten Währungsinformationen extrahieren.

## Schnelle Antworten
- **Was macht die API?** Sie liest MS Project-Dateien und stellt Eigenschaften wie den Währungscode bereit.  
- **Welche Sprache wird verwendet?** Java, über die Aspose.Tasks für Java Bibliothek.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich den Code in einer Zeile abrufen?** Ja – `prj.get(Prj.CURRENCY_CODE)` gibt den Währungscode als Zeichenkette zurück.  
- **Ist es mit allen Project-Versionen kompatibel?** Aspose.Tasks unterstützt sowohl ältere (MPP) als auch neuere (XML, XER) Formate.

## Was bedeutet **read ms project file**?
Das Lesen einer MS Project-Datei bedeutet, programmgesteuert ein *.mpp* (oder ein anderes unterstütztes) Projektdokument zu öffnen und auf seine Datenstrukturen – Aufgaben, Ressourcen, Kalender und finanzielle Einstellungen – zuzugreifen, ohne manuell mit Microsoft Project zu interagieren.

## Warum Aspose.Tasks zum **read msproject** verwenden?
- **Vollständige Formatunterstützung** – funktioniert mit Dateien von Project 98 bis zu den neuesten Office-Versionen.  
- **Keine COM- oder Office-Installation erforderlich** – reines Java, ideal für serverseitige Automatisierung.  
- **Umfangreiche API** – bietet direkten Zugriff auf Eigenschaften wie `Prj.CURRENCY_CODE` und ermöglicht es Ihnen, **how to retrieve currency** Informationen sofort abzurufen.  
- **Performance** – leichtgewichtiges Parsen, ideal für die Stapelverarbeitung vieler Projekte.

## Voraussetzungen
Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

### Java Development Kit (JDK) installiert
Stellen Sie sicher, dass ein aktuelles JDK auf Ihrem Rechner verfügbar ist. Sie können die neueste JDK-Version von [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen und installieren.

### Aspose.Tasks für Java Bibliothek
Laden Sie die Aspose.Tasks für Java Bibliothek herunter und richten Sie sie ein. Detaillierte Dokumentation und die neuesten Binärdateien finden Sie [hier](https://reference.aspose.com/tasks/java/).

## Pakete importieren
Um zu beginnen, importieren wir die notwendigen Pakete in Ihrem Java‑Projekt:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Datenverzeichnis einrichten
Definieren Sie den Ordner, der Ihre *.mpp*‑Datei enthält. Passen Sie den Pfad an Ihre Umgebung an.
```java
String dataDir = "Your Data Directory";
```

### Schritt 2: Projektdatei laden
Erzeugen Sie eine `Project`‑Instanz, indem Sie die MS Project‑Datei laden. Dies ist der Punkt, an dem Sie **read msproject** Daten in den Speicher einlesen.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Schritt 3: Währungscode abrufen
Jetzt, wo das Projekt geladen ist, können Sie **how to retrieve currency** Informationen mit einem einzigen Aufruf erhalten. Dies demonstriert die Verwendung von **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Die Ausgabe ist der dreibuchstabige ISO‑Währungscode (z. B. `USD`, `EUR`, `GBP`), den das Projekt verwendet.

### Schritt 4: (Optional) Währungscode verwenden
Möglicherweise möchten Sie den abgerufenen Code an anderer Stelle einsetzen – etwa zur Formatierung von Kostenwerten in einem benutzerdefinierten Bericht oder zur Übergabe an eine Finanz‑API. Hier ein kurzer Überblick (kein zusätzlicher Code‑Block nötig):
- Speichern Sie den Code in einer Variablen.  
- Verwenden Sie ihn beim Erstellen von Geldbeträgen.  
- Übergeben Sie ihn an nachgelagerte Dienste, die einen Währungsidentifikator benötigen.

## Häufige Probleme und Lösungen
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null-Ausgabe** | Projektdatei definiert keine Währung (Standard ist leer). | Setzen Sie die Währung in Microsoft Project oder weisen Sie sie vor dem Lesen über `prj.set(Prj.CURRENCY_CODE, "USD");` zu. |
| **Datei nicht gefunden** | Falscher `dataDir`‑Pfad. | Überprüfen Sie den Pfad und stellen Sie sicher, dass der Dateiname exakt übereinstimmt, einschließlich Groß‑/Kleinschreibung. |
| **Nicht unterstützte Dateiversion** | Sehr alte oder beschädigte *.mpp*‑Datei. | Verwenden Sie die neueste Aspose.Tasks‑Version oder konvertieren Sie die Datei zuerst in Microsoft Project in ein neueres Format. |

## Häufig gestellte Fragen

**Q: Kann Aspose.Tasks komplexe Projektstrukturen verarbeiten?**  
A: Ja, die API kann mehrstufige Aufgabenhierarchien, Ressourcenpools und benutzerdefinierte Felder problemlos lesen und manipulieren.

**Q: Ist Aspose.Tasks mit verschiedenen Versionen von MS Project‑Dateien kompatibel?**  
A: Absolut. Es unterstützt MPP, XML, XER und andere Formate über viele Microsoft Project‑Versionen hinweg.

**Q: Bietet Aspose.Tasks Dokumentation und Support?**  
A: Umfassende Dokumentation, Code‑Beispiele und dedizierter Support sind auf der Aspose‑Website verfügbar.

**Q: Kann ich Aspose.Tasks vor dem Kauf testen?**  
A: Es wird eine kostenlose Testversion angeboten, mit der Sie alle Funktionen, einschließlich des Lesens von Währungscodes, evaluieren können.

**Q: Wo kann ich temporäre Lizenzen für Aspose.Tasks erhalten?**  
A: Temporäre Lizenzen können von der [Website](https://purchase.aspose.com/temporary-license/) für kurzfristige Evaluierung bezogen werden.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Tasks for Java (latest version)  
**Author:** Aspose