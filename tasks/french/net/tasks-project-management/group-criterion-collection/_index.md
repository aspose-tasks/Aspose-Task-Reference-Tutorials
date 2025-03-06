---
title: Gérer les critères du groupe MS Project avec Aspose.Tasks
linktitle: Gestion de la collecte de critères de groupe dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer la collection Group Criterion MS Project à l’aide d’Aspose.Tasks pour .NET. Guide étape par étape pour les développeurs.
type: docs
weight: 28
url: /fr/net/tasks-project-management/group-criterion-collection/
---
## Introduction
Aspose.Tasks for .NET est une API puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programme. Dans ce didacticiel, nous allons explorer comment gérer la collection Group Criterion dans MS Project à l'aide d'Aspose.Tasks.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Tasks pour .NET : assurez-vous que la bibliothèque Aspose.Tasks est installée dans votre projet .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).

2. Fichier Microsoft Project : disposez d'un fichier Microsoft Project (MPP) prêt à utiliser.

## Importer des espaces de noms

Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre code C#. Cette étape est cruciale pour accéder aux fonctionnalités fournies par Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Étape 1 : Charger le fichier de projet

 Initialiser un`Project` objet en chargeant le fichier MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Étape 2 : accéder aux critères du groupe

Récupérez le groupe du projet et accédez à ses critères.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Étape 3 : Itérer sur les critères de groupe

Parcourez chaque critère du groupe et affichez ses propriétés.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Étape 4 : Effacer les critères de groupe

Effacez les critères de groupe existants s’ils ne sont pas en lecture seule.

```csharp
group.GroupCriteria.Clear();
```

## Étape 5 : Ajouter un nouveau critère

Créez un nouveau critère de groupe et ajoutez-le au groupe.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Étape 6 : Copier les critères vers un autre groupe

Copiez les critères d'un groupe à un autre.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Conclusion

Dans ce didacticiel, nous avons appris à gérer la collection Group Criterion MS Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez manipuler efficacement les critères de groupe dans vos fichiers Microsoft Project par programme.

## FAQ

### Q1 : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?

R : Oui, Aspose.Tasks prend en charge les fichiers Microsoft Project de différentes versions, notamment 2003, 2007, 2010, 2013 et 2016.

### Q2 : Puis-je appliquer plusieurs critères à un seul groupe ?

R : Absolument, vous pouvez ajouter plusieurs critères à un groupe en parcourant chacun d'eux et en les ajoutant en conséquence.

### Q3 : Existe-t-il une version d’essai disponible pour Aspose.Tasks ?

 R : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks auprès de[ici](https://releases.aspose.com/).

### Q4 : Où puis-je trouver de la documentation pour Aspose.Tasks ?

 R : Vous pouvez vous référer à la documentation[ici](https://reference.aspose.com/tasks/net/).

### Q5 : Comment puis-je obtenir de l'aide si je rencontre des problèmes ?

 R : Si vous avez des questions ou rencontrez des problèmes, vous pouvez demander de l'aide sur le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).