---
title: Durée de la tâche dans différentes unités avec Aspose.Tasks
linktitle: Durée de la tâche dans différentes unités avec Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explorez la gestion de la durée des tâches dans les projets Java avec Aspose.Tasks. Calculez et convertissez avec précision les durées en minutes, jours, heures, semaines et mois.
type: docs
weight: 32
url: /fr/java/task-properties/task-duration-different-units/
---
## Introduction
Dans le domaine de la gestion de projet, comprendre et gérer la durée des tâches est un aspect essentiel. Aspose.Tasks for Java fournit un ensemble d'outils puissants pour gérer cela efficacement. Dans ce didacticiel, nous vous guiderons dans la récupération des durées des tâches dans différentes unités à l'aide d'Aspose.Tasks.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
- Kit de développement Java (JDK) installé
-  Aspose.Tasks pour la bibliothèque Java. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/java/)
- Une compréhension de base de la programmation Java
## Importer des packages
Dans votre projet Java, incluez la bibliothèque Aspose.Tasks. Ajoutez l'instruction d'importation suivante au début de votre code :
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Étape 1 : Configurez votre projet
Commencez par créer un nouveau projet Java dans votre environnement de développement intégré (IDE) préféré. Assurez-vous d'inclure la bibliothèque Aspose.Tasks dans les dépendances de votre projet.
## Étape 2 : Lire le modèle de projet
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Lire le fichier modèle MS Project
String fileName = dataDir + "project.xml";
// Lire le fichier d'entrée en tant que projet
Project project = new Project(fileName);
```
 Assurez-vous de remplacer`"Your Document Directory"` avec le chemin réel vers vos fichiers de projet.
## Étape 3 : Récupérer une tâche
```java
// Obtenez une tâche pour calculer sa durée dans différents formats
Task task = project.getRootTask().getChildren().getById(1);
```
 Ici, nous obtenons une tâche du projet. Ajuster`getById(1)` en fonction de l'ID de tâche de votre projet.
## Étape 4 : Durée en minutes
```java
// Obtenez la durée en minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
Cette étape calcule la durée de la tâche en minutes.
## Étape 5 : Durée en jours
```java
// Obtenez la durée en jours
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
Cette étape calcule la durée de la tâche en jours.
## Étape 6 : Durée en heures
```java
// Obtenez la durée en heures
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
Cette étape calcule la durée de la tâche en heures.
## Étape 7 : Durée en semaines
```java
// Obtenez la durée en semaines
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
Cette étape calcule la durée de la tâche en semaines.
## Étape 8 : Durée en mois
```java
// Obtenez la durée en mois
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
Cette étape calcule la durée de la tâche en mois.
## Conclusion
La gestion de la durée des tâches est simplifiée avec Aspose.Tasks pour Java. Ce didacticiel vous a guidé pas à pas tout au long du processus, en vous apportant des éclaircissements sur les différentes unités de temps.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.Tasks pour Java avec n’importe quel IDE Java ?
Oui, Aspose.Tasks for Java est compatible avec n’importe quel environnement de développement intégré (IDE) Java.
### Q : Comment puis-je obtenir l'ID d'une tâche dans un fichier Microsoft Project ?
Vous pouvez inspecter le fichier projet ou utiliser l'API Aspose.Tasks pour récupérer les ID de tâches par programme.
### Q : Aspose.Tasks est-il adapté à la gestion de projets à grande échelle ?
Absolument. Aspose.Tasks est conçu pour gérer efficacement des projets de différentes tailles.
### Q : Où puis-je trouver de la documentation supplémentaire ?
 Visiter le[Documentation](https://reference.aspose.com/tasks/java/)pour des ressources complètes.
### Q : Puis-je essayer Aspose.Tasks pour Java avant d'acheter ?
 Oui, vous pouvez explorer un[essai gratuit](https://releases.aspose.com/) pour évaluer ses capacités.