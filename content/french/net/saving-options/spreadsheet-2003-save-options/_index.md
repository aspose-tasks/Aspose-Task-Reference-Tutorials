---
title: MS Project avec options de feuille de calcul 2003 pour Aspose.Tasks
linktitle: Options d'enregistrement de la feuille de calcul 2003 pour Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Master Spreadsheet 2003 Enregistrez les options de MS Project avec Aspose.Tasks pour .NET. Personnalisez et enregistrez en toute transparence les fichiers MS Project par programme.
type: docs
weight: 19
url: /fr/net/saving-options/spreadsheet-2003-save-options/
---
## Introduction
Dans ce didacticiel, nous allons explorer l'exploitation d'Aspose.Tasks pour .NET afin d'utiliser les options de sauvegarde de MS Project de Spreadsheet 2003. Cet outil puissant permet une manipulation et une personnalisation transparentes des fichiers MS Project dans l'environnement .NET. Décomposons le processus étape par étape.
## Conditions préalables
Avant de vous lancer dans ce didacticiel, assurez-vous de disposer des prérequis suivants :
1.  Installation d'Aspose.Tasks for .NET : Téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/).
2. Familiarité avec la programmation C# : une compréhension de base du langage de programmation C# est nécessaire pour comprendre les concepts abordés dans ce didacticiel.

## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet C# :
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Ces espaces de noms donnent accès aux fonctionnalités nécessaires à l'enregistrement des fichiers MS Project au format Spreadsheet 2003 et à la personnalisation des options d'affichage.
## Étape 1 : Charger le projet
Tout d'abord, chargez le fichier MS Project à l'aide d'Aspose.Tasks :
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
 remplacer`"Your Document Directory"`avec le chemin du répertoire réel où se trouve votre fichier MS Project.
## Étape 2 : définir les options d'enregistrement
 Définissez les options d'enregistrement de Spreadsheet 2003 en créant une instance de`Spreadsheet2003SaveOptions`,
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Étape 3 : Personnaliser les colonnes d'affichage
Personnalisez les colonnes d'affichage pour le diagramme de Gantt, la vue Ressources et la vue Affectation :
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
Ces étapes ajoutent des colonnes personnalisées aux vues respectives, améliorant ainsi les capacités de visualisation et d'analyse du fichier MS Project.
## Étape 4 : Enregistrez le projet
Enfin, enregistrez le projet avec les options spécifiées :
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
Cette commande enregistre le projet modifié au format Spreadsheet 2003 et les colonnes de la vue personnalisée.

## Conclusion
L'utilisation d'Aspose.Tasks pour .NET, en particulier les options d'enregistrement MS Project de Spreadsheet 2003, permet aux développeurs de gérer et de personnaliser efficacement les fichiers MS Project par programme. En suivant le guide étape par étape décrit dans ce didacticiel, vous pouvez intégrer de manière transparente ces fonctionnalités dans vos applications .NET, améliorant ainsi la productivité et la flexibilité.

## FAQ
### Q : Aspose.Tasks pour .NET peut-il être utilisé à la fois dans des applications Web et de bureau ?
: Oui, Aspose.Tasks pour .NET peut être intégré de manière transparente aux applications Web et de bureau, offrant ainsi des fonctionnalités cohérentes sur toutes les plates-formes.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez accéder à un essai gratuit d'Aspose.Tasks pour .NET à partir du[site web](https://releases.aspose.com/), vous permettant d'explorer ses fonctionnalités avant de faire un achat.
### Q : Existe-t-il des limites à la personnalisation des colonnes d’affichage à l’aide d’Aspose.Tasks pour .NET ?
R : Aspose.Tasks pour .NET offre des options de personnalisation étendues pour les colonnes d'affichage, avec des limitations minimes. Cependant, des personnalisations complexes peuvent nécessiter une connaissance avancée de la bibliothèque.
### Q : Puis-je demander de l'aide si je rencontre des problèmes lors de l'utilisation d'Aspose.Tasks pour .NET ?
 R : Absolument ! Vous pouvez trouver une assistance et des ressources complètes sur le forum Aspose.Tasks à l'adresse[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15), où des experts et des membres de la communauté sont disponibles pour vous aider à résoudre toutes les questions ou défis auxquels vous pourriez être confronté.
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Tasks pour .NET ?
 R : Vous pouvez acquérir une licence temporaire pour Aspose.Tasks for .NET auprès du[page d'achat](https://purchase.aspose.com/temporary-license/), vous permettant d'évaluer toutes les capacités de la bibliothèque.