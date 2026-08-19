---
date: 2026-02-28
description: Apprenez à utiliser Aspose.Tasks pour Java afin de gérer les données
  temporelles des tâches, téléchargez la bibliothèque, essayez‑la gratuitement et
  simplifiez le suivi de projet.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment utiliser Aspose.Tasks pour gérer les données temporelles des tâches
  (Java)
url: /fr/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser Aspose.Tasks pour les données temporelles des tâches

## Introduction
If you’re looking for **how to use Aspose** to keep a tight grip on your project schedule, you’ve come to the right place. Precise tracking of task timephased data is a cornerstone of successful project management, and Aspose.Tasks for Java gives you the tools you need to automate that process. In this tutorial we’ll walk through a complete, end‑to‑end example that shows you how to use Aspose.Tasks to create a project, assign resources, set baselines, and finally retrieve and display timephased data.

## Réponses rapides
- **Que signifie « données temporelles » ?** Ce sont des données ventilées par intervalles de temps (jours, semaines, mois) qui montrent le travail, le coût ou le travail restant sur la chronologie du projet.  
- **Quelle bibliothèque fournit cette capacité ?** Aspose.Tasks for Java.  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Un essai gratuit suffit pour le développement ; une licence est requise pour la production.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure.  
- **Puis‑je exporter les résultats vers Excel ?** Oui – vous pouvez parcourir la collection `TimephasedData` et écrire les valeurs dans le format dont vous avez besoin.

## Qu’est‑ce que les données temporelles des tâches ?
Task timephased data represents the amount of work (or cost) scheduled for a task during each time slice of the project calendar. It enables you to see how work is distributed, spot overallocation, and compare planned vs. actual progress.

## Pourquoi utiliser Aspose.Tasks pour gérer les données temporelles ?
- **Contrôle total** – programmatically create, modify, and query timephased information without opening Microsoft Project.  
- **Cross‑platform** – works on any OS that supports Java.  
- **Pas de dépendances COM** – ideal for server‑side automation.  
- **API riche** – supports baselines, work contours, and custom fields out of the box.

## Prérequis
Before diving into the code, make sure you have:

- **Environnement de développement Java** – JDK 8+ installed and `JAVA_HOME` configured.  
- **Bibliothèque Aspose.Tasks for Java** – Download and include the Aspose.Tasks library in your project. You can find the library [here](https://releases.aspose.com/tasks/java/).  
- **Répertoire de documents** – A folder on your machine where the sample project file (`project.xml`) will be read from and written to.

## Importer les packages
In your Java project, import the necessary Aspose.Tasks classes:

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

## Étape 1 : définir la date de début du projet
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explication:* Nous créons une instance `Project`, initialisons un `Calendar` à la date de début souhaitée, et l’assignons à la propriété `START_DATE` du projet.

## Étape 2 : définir la tâche et la ressource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explication:* Une nouvelle tâche nommée **Task** est ajoutée sous la tâche racine. Nous créons également une ressource appelée **Rsc** et définissons ses taux standard et heures supplémentaires.

## Étape 3 : définir la durée de la tâche
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explication:* La tâche est planifiée pour une durée de **6 jours**.

## Étape 4 : affecter la ressource à la tâche
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explication:* La ressource définie précédemment est liée à la tâche via un `ResourceAssignment`.

## Étape 5 : configurer l’affectation de ressource
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explication:* Nous définissons les dates d’arrêt et de reprise de l’affectation (en utilisant une valeur de substitution) et appliquons un contour de travail **Back‑Loaded**, qui déplace plus de travail vers la fin de l’affectation.

## Étape 6 : définir la ligne de base
```java
project.setBaseline(BaselineType.Baseline);
```
*Explication:* Capturer une ligne de base vous permet de comparer les valeurs planifiées et réelles ultérieurement.

## Étape 7 : mettre à jour l’avancement de la tâche
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explication:* La tâche est marquée comme **50 % terminée**, ce qui affectera les calculs du travail restant.

## Étape 8 : récupérer les données temporelles
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explication:* Cet appel récupère le **travail restant** pour l’affectation, ventilé selon les intervalles de temps du projet.

## Étape 9 : afficher les données temporelles
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explication:* Nous affichons simplement le nombre d’entrées temporelles et la valeur de la première entrée. Dans un scénario réel, vous parcourriez la liste et exporteriez les données vers un rapport ou une interface.

## Problèmes courants et solutions
- **NullPointerException sur `getTimephasedData`** – Assurez‑vous que les dates `START` et `FINISH` de l’affectation sont définies avant d’appeler la méthode.  
- **Contour de travail incorrect** – Vérifiez que le `WorkContourType` choisi correspond à votre stratégie de planification ; `BackLoaded` n’est qu’une des plusieurs options.  
- **La ligne de base ne reflète pas les changements** – N’oubliez pas d’appeler `project.setBaseline` *après* avoir défini les tâches, ressources et affectations.

## Foire aux questions
### Q: Puis‑je utiliser Aspose.Tasks for Java dans n’importe quel projet Java ?
R: Oui, Aspose.Tasks for Java est compatible avec tout projet basé sur Java.

### Q: Où puis‑je trouver un support supplémentaire pour Aspose.Tasks for Java ?
R: Consultez le [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) pour le support et les discussions.

### Q: Existe‑t‑il un essai gratuit disponible pour Aspose.Tasks for Java ?
R: Oui, vous pouvez explorer un essai gratuit [here](https://releases.aspose.com/).

### Q: Comment puis‑je obtenir une licence temporaire pour Aspose.Tasks for Java ?
R: Vous pouvez acquérir une licence temporaire [here](https://purchase.aspose.com/temporary-license/).

### Q: Où puis‑je acheter Aspose.Tasks for Java ?
R: Vous pouvez acheter Aspose.Tasks for Java [here](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-02-28  
**Testé avec :** Aspose.Tasks for Java 24.12 (le plus récent au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}