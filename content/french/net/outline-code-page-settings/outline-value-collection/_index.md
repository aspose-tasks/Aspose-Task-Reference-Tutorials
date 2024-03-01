---
title: Gérer les valeurs de plan MS Project avec Aspose.Tasks
linktitle: Collection de valeurs de plan dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les valeurs hiérarchiques dans les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Tutoriel étape par étape avec des exemples de code.
type: docs
weight: 17
url: /fr/net/outline-code-page-settings/outline-value-collection/
---
## Introduction
Aspose.Tasks for .NET fournit un ensemble complet de fonctionnalités pour interagir avec les fichiers Microsoft Project. L'une de ces fonctionnalités est la possibilité de gérer les valeurs de plan au sein d'un projet. Dans ce didacticiel, nous explorerons comment collecter et manipuler des valeurs de plan à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Aspose.Tasks pour .NET : vous pouvez télécharger la bibliothèque à partir de[ici](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : assurez-vous d'avoir installé un IDE approprié, tel que Visual Studio.
3. Connaissance de base de C# : Une connaissance du langage de programmation C# sera bénéfique.
## Importer des espaces de noms
Dans votre fichier de code C#, importez les espaces de noms nécessaires pour accéder aux classes et méthodes Aspose.Tasks :
```csharp
using Aspose.Tasks;
using System;

```
Décomposons l'exemple fourni en plusieurs étapes :
## Étape 1 : Charger un fichier de projet
 Tout d'abord, initialisez un`Project` objet en chargeant un fichier Microsoft Project existant :
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Étape 2 : Effacer les valeurs de plan existantes
Ensuite, effacez toutes les valeurs de plan existantes du projet :
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
## Étape 3 : Définir un nouveau code hiérarchique
Maintenant, définissez un nouveau code hiérarchique avec une description et une valeur :
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
## Étape 4 : Mettre à jour la valeur du plan
Mettez à jour la valeur du code hiérarchique :
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Étape 5 : Itérer sur les valeurs de plan
Parcourez les valeurs du plan et imprimez leurs détails :
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Étape 6 : Manipuler les valeurs de plan
Effectuez des opérations telles que la suppression, l'insertion et la copie de valeurs de plan selon vos besoins :
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
## Conclusion
Dans ce didacticiel, nous avons appris à utiliser les valeurs de plan dans les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En suivant les étapes fournies, vous pouvez gérer efficacement les valeurs de plan au sein de vos projets, permettant ainsi un plus grand contrôle et une plus grande flexibilité.
## FAQ
### Q : Puis-je manipuler plusieurs codes hiérarchiques simultanément ?
R : Oui, vous pouvez définir et manipuler plusieurs codes hiérarchiques au sein d'un projet à l'aide d'Aspose.Tasks.
### Q : Aspose.Tasks est-il compatible avec différentes versions des fichiers Microsoft Project ?
R : Oui, Aspose.Tasks prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP et XML.
### Q : Comment puis-je gérer les erreurs lorsque je travaille avec des valeurs hiérarchiques ?
R : Vous pouvez implémenter des mécanismes de gestion des erreurs tels que des blocs try-catch pour gérer les exceptions avec élégance.
### Q : Puis-je personnaliser l’apparence des valeurs de plan dans mon projet ?
R : Oui, Aspose.Tasks fournit des API complètes pour personnaliser l'apparence et le comportement des valeurs de plan en fonction de vos besoins.
### Q : Où puis-je trouver des ressources supplémentaires et une assistance pour Aspose.Tasks ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir le soutien de la communauté et explorer les[Documentation](https://reference.aspose.com/tasks/net/) pour des informations détaillées sur les API et les fonctionnalités.