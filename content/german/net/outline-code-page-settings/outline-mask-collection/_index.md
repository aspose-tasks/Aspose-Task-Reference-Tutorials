---
title: Beherrschen Sie MS Project-Gliederungsmasken mit Aspose.Tasks
linktitle: Sammlung von Umrissmasken in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Gliederungsmasken für MS Project-Sammlungen mit Aspose.Tasks für .NET bearbeiten. Steigern Sie Ihre Produktivität mit diesem umfassenden Tutorial.
type: docs
weight: 15
url: /de/net/outline-code-page-settings/outline-mask-collection/
---
## Einführung
Möchten Sie die Leistungsfähigkeit der Gliederungsmasken von Microsoft Project mit Aspose.Tasks für .NET nutzen? Hier sind Sie richtig! In diesem umfassenden Tutorial führen wir Sie Schritt für Schritt durch den Prozess und stellen sicher, dass Sie ein solides Verständnis dafür erlangen, wie Sie Umrissmasken in Ihren Projekten effektiv manipulieren. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, dieser Leitfaden vermittelt Ihnen das Wissen und die Fähigkeiten, die Sie zur Optimierung Ihres Arbeitsablaufs benötigen.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installation von Aspose.Tasks für .NET
Stellen Sie sicher, dass Aspose.Tasks für .NET in Ihrer Entwicklungsumgebung installiert ist. Sie können die Bibliothek von der Aspose-Website herunterladen[Hier](https://releases.aspose.com/tasks/net/).
### 2. Grundkenntnisse in C# und .NET Framework
Machen Sie sich mit der Programmiersprache C# und dem .NET Framework vertraut, da in diesem Tutorial beide verwendet werden.
### 3. Microsoft Project-Datei
Halten Sie zu Testzwecken eine Microsoft Project-Datei (MPP) bereit. Sie können eine vorhandene Datei verwenden oder zum Experimentieren eine neue erstellen.
## Namespaces importieren
Beginnen wir mit dem Importieren der erforderlichen Namespaces in Ihr C#-Projekt. Dieser Schritt stellt sicher, dass Sie Zugriff auf die erforderlichen Klassen und Funktionen haben, die von Aspose.Tasks für .NET bereitgestellt werden.

Fügen Sie am Anfang Ihrer Codedatei die folgenden Namespaces hinzu:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen und jeden Schritt im Detail erklären:
## Schritt 1: Initialisieren Sie das Projektobjekt
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Hier erstellen wir eine neue Instanz von`Project` Klasse und laden Sie eine vorhandene Microsoft Project-Datei mit dem Namen „OutlineValues2010.mpp“.
## Schritt 2: Greifen Sie auf die Gliederungscodes zu
```csharp
var outline = project.OutlineCodes[0];
```
Wir greifen auf die Gliederungscodes aus dem Projekt zu. Gliederungscodes sind benutzerdefinierte Felder in Microsoft Project, mit denen Sie Aufgaben kategorisieren und organisieren können.
## Schritt 3: Umrissmasken löschen
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Dieser Schritt stellt sicher, dass alle vorhandenen Umrissmasken gelöscht werden, bevor Sie fortfahren.
## Schritt 4: Erstellen Sie Umrissmasken
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Wir erstellen neue Umrissmasken und legen deren Typen fest. In diesem Beispiel erstellen wir eine gültige und eine falsche Umrissmaske.
## Schritt 5: Masken einfügen und bearbeiten
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Hier fügen wir eine falsche Maske in die Sammlung ein und bearbeiten die Länge einer Maske anhand ihres Index.
## Schritt 6: Masken entfernen
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Wir entfernen die falsche Maske basierend auf ihrem Index aus der Sammlung.
## Schritt 7: Über Masken iterieren
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Diese Schleife durchläuft jede Umrissmaske in der Sammlung und gibt deren Eigenschaften wie Länge, Ebene, Trennzeichen und Typ aus.
## Schritt 8: Masken in ein anderes Projekt kopieren
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Schließlich kopieren wir die Gliederungsmasken von einem Projekt zum anderen und stellen so die Konsistenz über verschiedene Projekte hinweg sicher.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie MS Project-Sammlungsgliederungsmasken mit Aspose.Tasks für .NET bearbeiten. Wenn Sie diesem Tutorial folgen, verfügen Sie nun über die Fähigkeiten, Umrissmasken in Ihren Projekten effizient zu verwalten und so letztendlich Ihre Produktivität und Ihren Arbeitsablauf zu verbessern.
## FAQs
### F1: Kann ich Aspose.Tasks für .NET mit verschiedenen Versionen von Microsoft Project-Dateien verwenden?
A: Ja, Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich MPP-, MPT- und XML-Formate.
### F2: Ist Aspose.Tasks für .NET mit .NET Core kompatibel?
A: Ja, Aspose.Tasks für .NET ist mit .NET Core kompatibel, sodass Sie es in plattformübergreifenden Anwendungen verwenden können.
### F3: Kann ich die Eigenschaften von Umrissmasken entsprechend meinen Projektanforderungen anpassen?
A: Auf jeden Fall! Sie können Umrissmasken anpassen, indem Sie ihre Länge, Ebene, Trennlinie und Art an Ihre spezifischen Projektanforderungen anpassen.
### F4: Bietet Aspose.Tasks für .NET Dokumentation und Support?
A: Ja, Aspose.Tasks für .NET bietet umfassende Dokumentation und engagierten Support über seine Website und[Foren](https://forum.aspose.com/c/tasks/15).
### F5: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können dort auf eine kostenlose Testversion von Aspose.Tasks für .NET zugreifen[Webseite](https://releases.aspose.com/tasks/net/). um die Merkmale und Funktionalitäten zu erkunden, bevor Sie einen Kauf tätigen.