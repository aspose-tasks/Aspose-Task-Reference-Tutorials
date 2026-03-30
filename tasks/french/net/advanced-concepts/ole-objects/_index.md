---
date: 2026-03-16
description: Apprenez à supprimer les objets OLE à l'aide d'Aspose.Tasks pour .NET,
  et découvrez comment gérer les objets OLE et les effacer efficacement dans vos projets.
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Comment supprimer les objets OLE dans Aspose.Tasks pour .NET
url: /fr/net/advanced-concepts/ole-objects/
weight: 22
---

 code block placeholders unchanged. Also keep markdown formatting.

Let's write final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment supprimer les objets OLE dans Aspose.Tasks pour .NET

## Introduction

Aspose.Tasks for .NET vous donne un contrôle complet sur les objets OLE (Object Linking and Embedding) qui se trouvent à l’intérieur des fichiers Microsoft Project. Dans ce tutoriel, vous apprendrez **comment supprimer les objets OLE**, comment **gérer le contenu OLE**, et les étapes exactes pour **effacer les données OLE** lorsqu’elles ne sont plus nécessaires. À la fin, vous serez capable de charger un fichier de projet, d’inspecter ses objets OLE intégrés, de les supprimer en toute sécurité et d’enregistrer le projet nettoyé — le tout avec du code C# clair et lisible.

## Quick Answers
- **Quelle est la méthode principale pour supprimer les objets OLE ?** Utilisez `project.OleObjects.Clear()` puis enregistrez le projet.  
- **Ai‑je besoin d’une licence spéciale ?** Une licence valide d’Aspose.Tasks est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Puis‑je inspecter le contenu OLE avant la suppression ?** Oui, parcourez `project.OleObjects` pour lire les propriétés ou les octets du contenu.  
- **Est‑il sûr de nettoyer les objets OLE dans de gros projets ?** Absolument – l’opération est rapide et n’affecte pas les autres données du projet.

## What is “remove OLE objects” in the context of Aspose.Tasks?

Supprimer les objets OLE signifie effacer les fichiers intégrés (images, feuilles Excel, documents Word, etc.) qui sont stockés à l’intérieur d’un fichier Microsoft Project (.mpp). Cela est utile lorsque vous souhaitez réduire la taille du fichier, éliminer des références obsolètes ou vous conformer à des politiques de conservation des données.

## Why manage OLE objects with Aspose.Tasks?

- **Fine‑grained control** – Access each OLE object’s ID, name, and raw bytes.  
- **Automation** – Programmatically clean up dozens of projects without opening them in Microsoft Project.  
- **Cross‑version support** – Works with Project 2007‑2023 files.  

## Prerequisites

Avant de commencer, assurez‑vous d’avoir :

1. **Aspose.Tasks for .NET** installé. Vous pouvez le télécharger [ici](https://releases.aspose.com/tasks/net/).  
2. Des connaissances de base en **C#** et dans l’écosystème **.NET**.  
3. Un environnement de développement tel que **Visual Studio** (Community ou supérieur).  

## Import Namespaces

Tout d’abord, importez les espaces de noms qui exposent l’API Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## How to manage OLE objects – Step‑by‑step guide

Ci‑dessous, nous parcourons trois scénarios courants :

1. **Inspecting OLE objects** – read their properties and a snippet of the binary content.  
2. **Clearing all OLE objects** – the core “remove OLE objects” operation.  
3. **Reading visual placement information** – useful when you need to adjust how OLE objects appear in Gantt or other views.

### Scenario 1: Inspect OLE objects

#### Step 1: Load project file  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Access OLE objects  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### Step 3: Iterate through OLE objects  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### Step 4: Retrieve a small chunk of the binary content (optional)  
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

### Scenario 2: How to clear OLE – removing all embedded objects

#### Step 1: Load project file  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Clear OLE objects  
```csharp
project.OleObjects.Clear();
```

#### Step 3: Save the cleaned project  
```csharp
project.Save("ClearedProject.mpp");
```

> **Pro tip:** After clearing OLE objects, you can call `project.Save` with a different file name to keep the original untouched.

### Scenario 3: Getting visual object placement properties

#### Step 1: Load project file  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Access the first OLE object and its placement in the Gantt view  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### Step 3: Retrieve placement properties  
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## Common pitfalls and troubleshooting

| Problème | Raison | Solution |
|----------|--------|----------|
| `project.OleObjects` is empty | The source .mpp file contains no OLE objects. | Verify the project file actually embeds OLE data (e.g., an attached Excel sheet). |
| `project.Save` throws an exception | File is locked or you lack write permissions. | Close any open instances of the file and ensure the target folder is writable. |
| Content bytes look corrupted | You are reading the full byte array as text. | Use `Get10Bytes` or write the bytes to a file to inspect them in a proper viewer. |

## Frequently Asked Questions

**Q : Aspose.Tasks peut‑il gérer différents formats d’objets OLE ?**  
R : Oui, il prend en charge les images, les documents Office, les PDF et de nombreux autres formats OLE.

**Q : L’API est‑elle compatible avec les anciennes versions de Microsoft Project ?**  
R : Absolument – Aspose.Tasks fonctionne avec les fichiers Project de 2007 jusqu’aux dernières versions 2023.

**Q : Comment supprimer uniquement certains objets OLE au lieu de tout effacer ?**  
R : Localisez l’`OleObject` souhaité par son `Id` ou son `Name` et appelez `project.OleObjects.Remove(oleObject)` avant d’enregistrer.

**Q : La suppression des objets OLE affecte‑t‑elle les dépendances ou les calendriers des tâches ?**  
R : Non. Les objets OLE sont des éléments visuels indépendants ; les supprimer ne modifie pas les relations entre les tâches.

**Q : Où puis‑je trouver plus d’exemples sur la manipulation des OLE ?**  
R : Consultez la documentation officielle d’Aspose.Tasks et la référence API pour les classes `OleObject` et `VisualObjectsPlacements`.

## Conclusion

Nous avons couvert tout ce dont vous avez besoin pour **supprimer les objets OLE** et gérer le contenu OLE dans Aspose.Tasks pour .NET. En suivant les exemples pas à pas, vous pouvez inspecter, nettoyer et ajuster le placement visuel des objets OLE, gardant ainsi vos fichiers de projet légers et ciblés.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-16  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose