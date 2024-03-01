---
title: Données chronologiques de tâche dans Aspose.Tasks
linktitle: Données chronologiques de tâche dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explorez Aspose.Tasks pour Java et la gestion chronologique des données des tâches principales. Téléchargez la bibliothèque, profitez d'un essai gratuit et rationalisez le suivi de votre projet.
type: docs
weight: 34
url: /fr/java/task-properties/task-timephased-data/
---
## Introduction
Dans le domaine de la gestion de projet, un suivi précis des données chronologiques des tâches est crucial pour une exécution efficace du projet. Aspose.Tasks for Java apparaît comme un outil puissant pour rationaliser ce processus, offrant des fonctionnalités robustes et une flexibilité. Ce didacticiel vous guidera dans l'utilisation d'Aspose.Tasks pour Java pour gérer efficacement les données chronologiques des tâches.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Environnement de développement Java : assurez-vous que Java est installé sur votre système.
-  Aspose.Tasks pour la bibliothèque Java : téléchargez et incluez la bibliothèque Aspose.Tasks dans votre projet. Vous pouvez trouver la bibliothèque[ici](https://releases.aspose.com/tasks/java/).
- Répertoire de documents : créez un répertoire pour les documents de votre projet.
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour Aspose.Tasks :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Étape 1 : Définir la date de début du projet
```java
Project project = new Project(dataDir + "project.xml");
// Code supplémentaire pour les importations de packages
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Explication : Initialisez un objet de calendrier, définissez la date de début et appliquez-le au projet.
## Étape 2 : Définir la tâche et la ressource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Explication : Créez une tâche et une ressource, en définissant les taux pour les heures standard et supplémentaires.
## Étape 3 : Définir la durée de la tâche
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Explication : Définissez la durée de la tâche (par exemple, 6 jours).
## Étape 4 : attribuer une ressource à une tâche
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Explication : Affectez la ressource à la tâche.
## Étape 5 : Configurer l'affectation des ressources
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Explication : Définissez des paramètres tels que l'arrêt, la reprise et le contour du travail pour l'affectation de ressource.
## Étape 6 : Définir la ligne de base
```java
project.setBaseline(BaselineType.Baseline);
```
Explication : Établir une base de référence pour le projet.
## Étape 7 : achèvement de la tâche de mise à jour
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Explication : Indiquez le pourcentage d'achèvement de la tâche.
## Étape 8 : Récupérer les données chronologiques
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Explication : Récupérez les données chronologiques pour le travail restant d'affectation.
## Étape 9 : Afficher les données chronologiques
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Code supplémentaire pour afficher d'autres valeurs
```
Explication : Sortir et afficher les données chronologiques.
## Conclusion
Une gestion efficace des données chronologiques des tâches est indispensable à la réussite du projet. Aspose.Tasks for Java simplifie ce processus en fournissant un ensemble complet de fonctionnalités. En suivant ce didacticiel, vous pouvez intégrer de manière transparente Aspose.Tasks dans votre projet Java, garantissant un contrôle précis sur les délais du projet et l'allocation des ressources.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.Tasks pour Java dans n'importe quel projet Java ?
R : Oui, Aspose.Tasks for Java est compatible avec tout projet basé sur Java.
### Q : Où puis-je trouver une assistance supplémentaire pour Aspose.Tasks pour Java ?
 R : Visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour du soutien et des discussions.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez explorer un essai gratuit[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Tasks pour Java ?
 R : Vous pouvez acquérir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je acheter Aspose.Tasks pour Java ?
 R : Vous pouvez acheter Aspose.Tasks pour Java[ici](https://purchase.aspose.com/buy).