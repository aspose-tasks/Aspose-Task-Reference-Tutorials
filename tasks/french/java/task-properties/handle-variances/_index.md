---
date: 2026-02-20
description: Apprenez à définir la date de début du projet et à gérer les écarts du
  projet en utilisant Aspose.Tasks pour Java. Ce guide montre également comment définir
  efficacement la durée des tâches.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Définir la date de début du projet et gérer les écarts de tâches Aspose.Tasks
url: /fr/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la date de début du projet & gérer les écarts de tâches Aspose.Tasks

## Introduction
Dans le monde de la gestion de projet, **set project start date** est l’une des premières actions que vous prenez pour donner à votre planning une base solide. Aspose.Tasks for Java rend cette étape—et la gestion ultérieure des écarts de tâches—simple et fiable. Dans ce tutoriel vous apprendrez comment définir la date de début du projet, définir la durée d’une tâche et gérer les écarts du projet efficacement.

## Quick Answers
- **Quelle est la méthode principale pour définir la date de début du projet ?** Use `project.set(Prj.START_DATE, …)` with a `java.util.Calendar` instance.  
- **Quelle classe représente une ligne de base pour le suivi des écarts ?** `BaselineType.Baseline`.  
- **Puis-je ajuster les dates de début et de fin d’une tâche après que la ligne de base soit définie ?** Yes, simply update `Tsk.START` and `Tsk.STOP`.  
- **Ai‑je besoin d’une licence pour l’utilisation en développement ?** A temporary license is available for evaluation.  
- **Quelle version d’Aspose.Tasks fonctionne avec ce code ?** The latest Aspose.Tasks for Java release.

## What is **set project start date**?
Définir la date de début du projet définit le jour calendaire à partir duquel toutes les dates des tâches sont calculées. Cela influence les calculs du planning, l’analyse du chemin critique et la création de la ligne de base, le rendant essentiel pour une gestion précise des écarts.

## Pourquoi définir la date de début du projet et gérer les écarts ?
- **Prévisibilité :** Établit une ligne de base connue pour comparer l’avancement réel.  
- **Flexibilité :** Vous permet d’ajuster les dates des tâches individuelles sans perdre le plan original.  
- **Reporting :** Permet des rapports d’écarts clairs qui mettent en évidence les retards ou les terminaisons anticipées du planning.  

## Prerequisites
Avant de commencer, assurez-vous d’avoir les éléments suivants :

- Environnement de développement Java – un JDK installé et un IDE ou un outil de construction prêt.  
- Bibliothèque Aspose.Tasks – téléchargez la bibliothèque **[ici](https://releases.aspose.com/tasks/java/)**.  

## Import Packages
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Setting Up the Project
Créez une nouvelle instance `Project` qui contiendra toutes les tâches et les informations de planning.

```java
Project project = new Project();
```

## Step 2: Adding a Task
Ajoutez une tâche sous la tâche racine. Ce sera l’élément de travail que nous ajusterons plus tard.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Step 3: Setting Start Date and Duration
Définissez la date de début du projet et attribuez une durée à la tâche. Cela illustre **set task duration** en pratique.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Step 4: Setting Baseline
Créez une ligne de base afin de pouvoir comparer plus tard les dates prévues aux dates réelles—essentiel pour **manage project variances**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Step 5: Adjusting Task Start and Stop Dates
Modifiez les dates de début et de fin de la tâche pour simuler un scénario d’écart.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*N’hésitez pas à ajuster les dates et les durées pour correspondre aux besoins spécifiques de votre projet.*

## Common Issues & Tips
- **La ligne de base doit être définie avant de modifier les dates.** If you change dates first, the baseline will capture the altered schedule instead of the original plan.  
- **Les mois du calendrier sont indexés à zéro.** Remember that `Calendar.FEBRUARY` equals month 1, not 2.  
- **Units de durée :** `project.getDuration(2)` creates a duration of two days by default; adjust the unit if you need hours or weeks.  

## Conclusion
En maîtrisant comment **set project start date**, **set task duration** et **manage project variances**, vous obtenez un contrôle complet sur le planning de votre projet avec Aspose.Tasks pour Java. Les étapes ci‑dessus offrent une base solide que vous pouvez étendre à des scénarios plus complexes tels que les projets multi‑phases, l’allocation des ressources et le reporting automatisé.

## Frequently Asked Questions
### Aspose.Tasks est‑il adapté à tous les besoins de gestion de projet ?
Aspose.Tasks est un outil polyvalent adapté à un large éventail de besoins en gestion de projet, offrant flexibilité et fonctionnalités robustes.

### Puis‑je intégrer Aspose.Tasks dans mon projet Java existant ?
Oui, vous pouvez facilement intégrer Aspose.Tasks dans votre projet Java en suivant la documentation fournie **[ici](https://reference.aspose.com/tasks/java/)**.

### Une licence temporaire est‑elle disponible pour Aspose.Tasks ?
Oui, vous pouvez obtenir une licence temporaire pour Aspose.Tasks **[ici](https://purchase.aspose.com/temporary-license/)**.

### Où puis‑je obtenir du support pour Aspose.Tasks ?
Pour le support et les discussions, visitez le forum Aspose.Tasks **[ici](https://forum.aspose.com/c/tasks/15)**.

### Puis‑je télécharger Aspose.Tasks pour Java ?
Oui, téléchargez la dernière version d’Aspose.Tasks pour Java **[ici](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks latest Java release  
**Author:** Aspose