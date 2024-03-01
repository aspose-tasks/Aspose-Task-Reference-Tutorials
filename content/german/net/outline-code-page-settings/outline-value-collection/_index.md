---
title: Verwalten Sie MS Project-Gliederungswerte mit Aspose.Tasks
linktitle: Sammlung von Gliederungswerten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Gliederungswerte in Microsoft Project-Dateien mit Aspose.Tasks für .NET verwalten. Schritt-für-Schritt-Anleitung mit Codebeispielen.
type: docs
weight: 17
url: /de/net/outline-code-page-settings/outline-value-collection/
---
## Einführung
Aspose.Tasks für .NET bietet umfassende Funktionen für die Interaktion mit Microsoft Project-Dateien. Eine dieser Funktionen ist die Möglichkeit, Gliederungswerte innerhalb eines Projekts zu verwalten. In diesem Tutorial erfahren Sie, wie Sie Gliederungswerte mit Aspose.Tasks für .NET sammeln und bearbeiten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Aspose.Tasks für .NET: Sie können die Bibliothek herunterladen von[Hier](https://releases.aspose.com/tasks/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine geeignete IDE installiert haben, z. B. Visual Studio.
3. Grundkenntnisse in C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.
## Namespaces importieren
Importieren Sie in Ihre C#-Codedatei die erforderlichen Namespaces, um auf Aspose.Tasks-Klassen und -Methoden zuzugreifen:
```csharp
using Aspose.Tasks;
using System;

```
Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte unterteilen:
## Schritt 1: Laden Sie eine Projektdatei
 Initialisieren Sie zunächst a`Project` Objekt durch Laden einer vorhandenen Microsoft Project-Datei:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Schritt 2: Vorhandene Gliederungswerte löschen
Löschen Sie als Nächstes alle vorhandenen Gliederungswerte aus dem Projekt:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Schritt 3: Definieren Sie einen neuen Gliederungscode
Definieren Sie nun einen neuen Gliederungscode mit einer Beschreibung und einem Wert:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Schritt 4: Gliederungswert aktualisieren
Aktualisieren Sie den Wert des Gliederungscodes:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Schritt 5: Iterieren Sie über die Gliederungswerte
Durchlaufen Sie die Gliederungswerte und drucken Sie deren Details aus:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Schritt 6: Umrisswerte bearbeiten
Führen Sie nach Bedarf Vorgänge wie das Entfernen, Einfügen und Kopieren von Umrisswerten aus:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für .NET mit Gliederungswerten in Microsoft Project-Dateien arbeitet. Indem Sie die bereitgestellten Schritte befolgen, können Sie Gliederungswerte innerhalb Ihrer Projekte effizient verwalten und so eine größere Kontrolle und Flexibilität ermöglichen.
## FAQs
### F: Kann ich mehrere Gliederungscodes gleichzeitig bearbeiten?
A: Ja, Sie können mit Aspose.Tasks mehrere Gliederungscodes innerhalb eines Projekts definieren und bearbeiten.
### F: Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project-Dateien kompatibel?
A: Ja, Aspose.Tasks unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich MPP- und XML-Formate.
### F: Wie kann ich mit Fehlern umgehen, wenn ich mit Umrisswerten arbeite?
A: Sie können Fehlerbehandlungsmechanismen wie Try-Catch-Blöcke implementieren, um Ausnahmen elegant zu verwalten.
### F: Kann ich das Erscheinungsbild der Umrisswerte in meinem Projekt anpassen?
A: Ja, Aspose.Tasks bietet umfangreiche APIs, um das Erscheinungsbild und Verhalten von Gliederungswerten entsprechend Ihren Anforderungen anzupassen.
### F: Wo finde ich zusätzliche Ressourcen und Unterstützung für Aspose.Tasks?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung und erkunden Sie die[Dokumentation](https://reference.aspose.com/tasks/net/) Ausführliche Informationen zu APIs und Funktionen finden Sie hier.