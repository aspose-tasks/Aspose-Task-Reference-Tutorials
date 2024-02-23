---
title: Configurer les temps de travail dans Aspose.Tasks
linktitle: Configurer les temps de travail dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Améliorez la planification des projets dans .NET avec Aspose.Tasks. Configurez les temps de travail sans effort pour une gestion précise des ressources. Téléchargez la bibliothèque maintenant !
type: docs
weight: 13
url: /fr/net/time-recurrence-configuration/working-times/
---
## Introduction
Dans la gestion de projet, un contrôle précis des temps de travail est crucial pour une planification et une allocation précises des ressources. Aspose.Tasks for .NET fournit une solution puissante pour gérer les informations sur le temps de travail au sein de vos projets. Ce tutoriel vous guidera tout au long du processus de configuration des temps de travail à l'aide d'Aspose.Tasks dans un environnement .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
- Compréhension de base du langage de programmation C#.
- Aspose.Tasks pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
- Configurez Visual Studio ou tout autre environnement de développement C# préféré.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Tasks :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## Étape 1 : Créer un calendrier
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Ici, nous lançons un nouveau projet et créons un calendrier nommé "MyCalendar" basé sur le calendrier standard. Ce calendrier servira à définir des horaires de travail précis.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Étape 2 : Afficher les informations sur la semaine de travail
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
Cette étape imprime le nombre total de jours ouvrables dans le calendrier spécifié.
## Étape 3 : Détails des temps de travail
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
Dans cette partie, nous parcourons chaque jour de la semaine, en imprimant le type de jour et les temps de travail associés. Vous pouvez personnaliser les horaires de travail pour chaque jour de la semaine en fonction des exigences de votre projet.
## Conclusion
La configuration efficace des temps de travail dans Aspose.Tasks pour .NET garantit une planification de projet et une gestion des ressources précises. En suivant ce guide étape par étape, vous pouvez intégrer de manière transparente les ajustements du temps de travail dans les flux de travail de votre projet.
## Questions fréquemment posées
### Aspose.Tasks est-il adapté à la gestion de projets à grande échelle ?
Oui, Aspose.Tasks est conçu pour gérer des projets de différentes tailles, offrant des fonctionnalités robustes pour une gestion de projet efficace.
### Puis-je définir des horaires de travail différents pour différents membres de l'équipe ?
Absolument. Vous pouvez personnaliser les horaires de travail en fonction de chaque ressource, permettant ainsi des horaires individualisés.
### Aspose.Tasks prend-il en charge l'intégration avec d'autres outils de gestion de projet ?
Oui, Aspose.Tasks facilite l'intégration avec divers outils de gestion de projet, améliorant ainsi l'interopérabilité.
### Est-il possible d'importer/exporter les données du projet dans différents formats ?
Aspose.Tasks prend en charge plusieurs formats de fichiers, permettant des opérations d'importation/exportation transparentes pour les données du projet.
### À quelle fréquence les mises à jour d’Aspose.Tasks sont-elles publiées ?
Des mises à jour sont régulièrement publiées pour garantir la compatibilité avec les dernières technologies et répondre aux commentaires des utilisateurs.