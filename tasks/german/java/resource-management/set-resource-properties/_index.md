---
date: 2026-08-24
description: Erfahren Sie, wie Sie eine Ressource zu MS Project hinzufügen, den Standardtarif
  und weitere Ressourceneigenschaften in MS Project mit Aspose.Tasks für Java festlegen
  und Ressourcen effizient verwalten.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Ressourceneigenschaften in Aspose.Tasks festlegen
og_description: Ressource zu MS Project hinzufügen und den Standardtarif mit Aspose.Tasks
  für Java festlegen. Erfahren Sie die Voraussetzungen, den Schritt‑für‑Schritt‑Code
  und die Fehlersuche in diesem kompakten Leitfaden.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Ressource zu MS Project hinzufügen und Tarif mit Aspose.Tasks festlegen
  (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Wie man eine Ressource zu MS Project mit Aspose.Tasks hinzufügt
url: /de/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ressource zu MS Project hinzufügen und Tarif in Aspose.Tasks festlegen

## Einführung
Wenn Sie Java‑Anwendungen entwickeln, die Microsoft‑Project‑Dateien lesen oder schreiben müssen, ist **das Hinzufügen einer Ressource zu MS Project** und das Konfigurieren ihres Standardtarifs eine routinemäßige, aber wesentliche Aufgabe. In diesem Leitfaden sehen Sie, wie Sie ein `Project`‑Objekt erstellen, eine Ressource hinzufügen und sowohl Standard‑ als auch Überstundentarife mit Aspose.Tasks für Java festlegen. Am Ende können Sie Kostenberechnungen automatisieren und Ihre Projektpläne aktuell halten, ohne dass Microsoft Project installiert sein muss.

## Schnelle Antworten
- **Welche Klasse repräsentiert eine Projektdatei?** `Project`
- **Welcher Aufruf fügt eine neue Ressource hinzu?** `project.getResources().add()`
- **Wie setzen Sie den Standardtarif?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Ist für den Produktionseinsatz eine Lizenz erforderlich?** Ja, Sie müssen eine gültige Aspose.Tasks‑Lizenz laden.
- **Welche Java‑Versionen werden unterstützt?** Java 8 und neuer (Java 17+ empfohlen).

## Was ist „Standardtarif festlegen“?
Der Vorgang *Standardtarif festlegen* weist einer Ressource einen standardmäßigen Stundensatz zu. Dieser Tarif wird von Projektmanagern verwendet, um Arbeitskosten zu berechnen, Kostenberichte zu erstellen und Budgets zu prognostizieren, sodass die Kostenberechnungen den erwarteten Preis für die von jeder Ressource im Verlauf des Projektlebenszyklus geleistete Arbeit widerspiegeln.

## Warum Tarife mit Aspose.Tasks festlegen?
Aspose.Tasks kann **über 50 Eingabe‑ und Ausgabeformate** verarbeiten, darunter MPP-, MPX-, XML- und Primavera‑Dateien, und bewältigt Projekte mit mehreren hundert Seiten, ohne die gesamte Datei in den Speicher zu laden. Das ermöglicht eine Hochdurchsatz‑Stapelverarbeitung auf Windows-, Linux‑ oder macOS‑Servern und reduziert den manuellen Aufwand in typischen Automatisierungsszenarien um bis zu 90 %.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Punkte bereit sind:

### Einrichtung der Java-Entwicklungsumgebung
1. Installieren Sie JDK 8 oder neuer. Sie können es von der [Oracle-Website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) herunterladen.  
2. Wählen Sie eine IDE wie IntelliJ IDEA, Eclipse oder NetBeans und konfigurieren Sie sie für die Java‑Entwicklung.

### Installation von Aspose.Tasks für Java
1. Laden Sie das neueste Aspose.Tasks‑Paket für Java von der [Download‑Seite](https://releases.aspose.com/tasks/java/) herunter.  
2. Fügen Sie die JAR‑Dateien dem Klassenpfad Ihres Projekts hinzu oder deklarieren Sie die Maven/Gradle‑Abhängigkeit wie in der Produktdokumentation beschrieben.

## Pakete importieren
Importieren Sie die Kernklassen von Aspose.Tasks, die Sie benötigen. Dieser Schritt gibt Ihnen Zugriff auf die Typen `Project`, `Resource` und `Rsc`, die später verwendet werden.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Schritt 1: Projektobjekt erstellen
Die Klasse `Project` ist das oberste Objekt, das eine gesamte MS‑Project‑Datei im Speicher repräsentiert. Durch die Instanziierung wird ein leeres Projekt erstellt, das Sie mit Aufgaben, Ressourcen und anderen Daten füllen können.

```java
Project project = new Project();
```

## Schritt 2: Ressource hinzufügen (Ressource zu MS Project hinzufügen)
Die Klasse `Resource` modelliert eine einzelne Projektressource wie eine Person, Ausrüstung oder Material. Das Hinzufügen einer Ressource über `project.getResources().add()` liefert eine nicht‑null `Resource`‑Instanz, die bereit für die Konfiguration von Eigenschaften ist.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Schritt 3: Ressourceneigenschaften festlegen (wie man Tarife festlegt)
Das `Rsc`‑Enum enthält Konstanten für Ressourcennfelder wie `STANDARD_RATE` und `OVERTIME_RATE`.  
Sie setzen die Standard‑ und Überstundentarife, indem Sie `set` am `Resource`‑Objekt mit den entsprechenden `Rsc`‑Enum‑Werten aufrufen. Die Tarife werden als `BigDecimal` gespeichert, um monetäre Präzision zu bewahren.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| `NullPointerException` beim Aufruf von `set` | Die Ressource wurde nicht korrekt hinzugefügt. | Stellen Sie sicher, dass `project.getResources().add()` eine nicht‑null `Resource` zurückgibt. |
| Tarife erscheinen im gespeicherten File als 0 | Verwendung von `int` anstelle von `BigDecimal`. | Verwenden Sie immer `BigDecimal.valueOf()` für Geldbeträge. |
| Lizenz nicht gefunden | Lizenzdatei wurde nicht geladen, bevor `Project` erstellt wurde. | Laden Sie die Lizenz (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) beim Programmstart. |

## Fazit
Sie wissen jetzt, wie Sie **eine Ressource zu MS Project hinzufügen**, ein `Project`‑Objekt erstellen und **Standard‑ und Überstundentarife** mit Aspose.Tasks für Java festlegen. Diese Fähigkeit ermöglicht es Ihnen, Kostenberechnungen zu automatisieren, benutzerdefinierte Berichte zu erstellen und MS‑Project‑Ressourcen vollständig aus jeder Java‑Anwendung zu verwalten.

## Häufig gestellte Fragen
**F: Kann Aspose.Tasks für Java komplexe MS‑Project‑Dateien verarbeiten?**  
A: Ja, es unterstützt alle gängigen Project‑Formate, einschließlich großer Dateien mit Tausenden von Aufgaben und Ressourcen, und bewahrt jedes Feld ohne Datenverlust.

**F: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks für Java über die [Aspose.Tasks‑Testseite](https://releases.aspose.com/) erhalten.

**F: Wo kann ich Unterstützung für Aspose.Tasks für Java erhalten?**  
A: Sie können Hilfe im [Support‑Forum](https://forum.aspose.com/c/tasks/15) erhalten.

**F: Wie erhalte ich eine temporäre Lizenz für die Evaluierung?**  
A: Eine temporäre Lizenz ist auf der [Seite für temporäre Lizenzen](https://purchase.aspose.com/temporary-license/) verfügbar.

**F: Wo kann ich eine lizensierte Version erwerben?**  
A: Kaufen Sie eine Vollversion über die [Kaufseite](https://purchase.aspose.com/buy).

**Zuletzt aktualisiert:** 2026-08-24  
**Getestet mit:** Aspose.Tasks für Java 24.12 (zum Zeitpunkt der Erstellung die neueste Version)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Ressourcen erstellt – Ressourcenverwaltung mit Aspose.Tasks für Java](/tasks/java/resource-management/)
- [Ressource zum Projekt hinzufügen mit Aspose.Tasks für Java](/tasks/java/resource-management/create-resources/)
- [Wie man eine Ressource zum Projekt hinzufügt und Leveling‑Verzögerungseigenschaften in Aspose.Tasks behandelt](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}