---
title: Intervalles récurrents MS Project sans effort dans Aspose.Tasks
linktitle: Gestion des intervalles récurrents dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer sans effort les intervalles récurrents dans MS Project à l'aide d'Aspose.Tasks pour .NET.
weight: 12
url: /fr/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Intervalles récurrents MS Project sans effort dans Aspose.Tasks

## Introduction
Cherchez-vous à gérer efficacement les intervalles récurrents dans les fichiers Microsoft Project à l’aide d’Aspose.Tasks pour .NET ? Ce didacticiel complet vous guidera étape par étape tout au long du processus, vous garantissant ainsi de gérer sans effort les intervalles récurrents dans vos projets. Avant de plonger dans le didacticiel, passons en revue quelques prérequis pour nous assurer que vous êtes prêt à commencer.
## Conditions préalables
Avant de poursuivre ce didacticiel, assurez-vous d'avoir les éléments suivants :
1. Connaissance de la programmation C# : Une compréhension de base du langage de programmation C# et de sa syntaxe est requise.
2. Visual Studio installé : assurez-vous que Visual Studio est installé sur votre système pour coder et compiler les applications .NET.
3. Bibliothèque Aspose.Tasks pour .NET : téléchargez et installez la bibliothèque Aspose.Tasks pour .NET. Vous pouvez l'obtenir de[ici](https://releases.aspose.com/tasks/net/).

## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par la bibliothèque Aspose.Tasks for .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Maintenant, décomposons chaque exemple en plusieurs étapes et expliquons-les en détail.
## Étape 1 : initialiser l'objet du projet :
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Ici, nous initialisons une nouvelle instance du`Project` classe en fournissant le chemin d’accès au fichier Microsoft Project.
## Étape 2 : Définir la date d’état :
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Cette étape définit la date d'état du projet à sa date de début.
## Étape 3 : Accédez à la vue Diagramme de Gantt :
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Nous accédons à la vue Diagramme de Gantt du projet.
## Étape 4 : Lire la ligne de progression :
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Cette étape récupère l'intervalle récurrent pour les lignes de progression à partir de la vue Diagramme de Gantt.
## Étape 5 : Afficher les informations sur l'intervalle :
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Ici, nous affichons des informations sur l'intervalle, le numéro de la semaine hebdomadaire et les jours hebdomadaires.
## Étape 6 : Redéfinir l'intervalle récurrent :
```csharp
var newInterval = new RecurringInterval();
```
 Nous créons une nouvelle instance de`RecurringInterval` pour redéfinir l’intervalle récurrent.
## Étape 7 : Définir les lignes de progression mensuelles :
```csharp
// Définissez des lignes de progression mensuelles par jour.
interval.MonthlyDay = true;
// Définissez le nombre de jours des lignes de progression mensuelles.
interval.MonthlyDayDayNumber = 1;
// Définissez le nombre de mois des lignes de progression mensuelles.
interval.MonthlyDayMonthNumber = 1;
// Définissez des lignes de progression par premier ou dernier jour prédéfini.
interval.MonthlyFirstLast = true;
// Définissez le type de premier ou de dernier jour des lignes de progression mensuelles.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Définissez le nombre de mois des lignes de progression.
interval.MonthlyFirstLastMonthNumber = 1;
```
Ces étapes configurent les lignes de progression mensuelles en fonction de paramètres spécifiés.
## Étape 8 : Mettre à jour les lignes de progression :
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Nous mettons à jour les lignes de progression dans la vue Diagramme de Gantt avec l'intervalle récurrent nouvellement défini.
## Étape 9 : Enregistrer le projet au format PDF :
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Enfin, nous enregistrons le projet avec l'intervalle récurrent mis à jour sous forme de fichier PDF.

## Conclusion
En conclusion, la gestion des intervalles récurrents dans les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour .NET est simplifiée grâce aux fonctionnalités complètes fournies par la bibliothèque. En suivant le guide étape par étape décrit dans ce didacticiel, vous pouvez gérer efficacement les intervalles récurrents dans vos projets, améliorant ainsi la productivité et l'organisation.
### FAQ
### Puis-je utiliser Aspose.Tasks pour .NET avec d’autres langages de programmation ?
Oui, Aspose.Tasks pour .NET peut être utilisé avec n'importe quel langage pris en charge par .NET tel que C# et VB.NET.
### Existe-t-il une version d’essai disponible pour Aspose.Tasks pour .NET ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l’assistance pour Aspose.Tasks pour .NET ?
 Vous pouvez obtenir de l'aide sur le forum Aspose.Tasks[ici](https://forum.aspose.com/c/tasks/15).
### Puis-je acheter une licence temporaire pour Aspose.Tasks pour .NET ?
 Oui, vous pouvez acheter une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver la documentation complète d’Aspose.Tasks pour .NET ?
 La documentation complète peut être trouvée[ici](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
