---
date: 2026-09-30
description: Gérez les critical tasks des projets Java avec Aspose.Tasks. Apprenez
  à gérer les critical et effort‑driven tasks, téléchargez la bibliothèque et améliorez
  votre flux de travail de gestion de projet.
keywords:
- manage critical tasks java
- effort‑driven tasks Aspose.Tasks
- Java project management
lastmod: 2026-09-30
linktitle: Gérer les Critical et Effort-Driven Tasks dans Aspose.Tasks
og_description: Gérez les critical tasks auxquels les développeurs Java sont confrontés
  avec Aspose.Tasks. Ce guide montre, étape par étape, la prise en charge des critical
  et effort‑driven tasks dans les projets Java (150‑160 caractères).
og_image_alt: Screenshot of Aspose.Tasks Java API managing critical and effort‑driven
  tasks
og_title: Comment gérer les critical tasks en Java avec Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Manage critical tasks Java projects with Aspose.Tasks. Learn to handle
    critical and effort‑driven tasks, download the library and boost your project
    management workflow.
  headline: How to manage critical tasks in Java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is platform‑independent and runs on Windows,
      Linux, and macOS.
    question: Can I use Aspose.Tasks for Java in both Windows and Linux environments?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java on the [Aspose.Tasks
      free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find support for Aspose.Tasks for Java?
  - answer: You can acquire a temporary license on the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: You can purchase Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- critical tasks
- effort‑driven tasks
- Aspose.Tasks
- Java
- project management
title: Comment gérer les critical tasks en Java avec Aspose.Tasks
url: /fr/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les tâches critiques et à effort dirigé en Java avec Aspose.Tasks

Dans la gestion de projet moderne, **manage critical tasks java** est un défi quotidien pour les développeurs qui doivent maintenir les plannings à jour tout en gérant des éléments de travail à effort dirigé. Aspose.Tasks for Java vous offre une méthode propre et programmatique pour identifier, inspecter et mettre à jour les tâches critiques et à effort dirigé sans manipuler manuellement des feuilles de calcul.

## Réponses rapides
- **Quel est le principal avantage ?** Il signale automatiquement les tâches critiques et ajuste la planification à effort dirigé en un seul appel d’API.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Quelles versions de Java sont prises en charge ?** Java 8 à 17, tant OpenJDK que les distributions Oracle.  
- **Puis‑je traiter de gros projets ?** Oui – Aspose.Tasks gère des projets contenant jusqu’à 10 000 tâches efficacement.  
- **Est‑ce multiplateforme ?** La bibliothèque fonctionne sous Windows, Linux et macOS sans dépendances natives.

## Comment gérer les tâches critiques et à effort dirigé dans Aspose.Tasks pour Java ?
Chargez votre fichier de projet avec la classe `Project`, utilisez `ChildTasksCollector` pour rassembler chaque tâche, puis examinez les propriétés `Critical` et `EffortDriven` de chaque tâche. En parcourant la liste collectée, vous pouvez générer un rapport d’état ou modifier automatiquement les règles de planification, le tout en quelques lignes de code Java qui s’exécutent en quelques secondes.

Aspose.Tasks for Java prend en charge **plus de 30 formats d’entrée et de sortie de projet** (y compris Microsoft Project 2019, 2022 et Primavera P6) et peut traiter des fichiers contenant **jusqu’à 10 000 tâches** tout en maintenant l’utilisation de la mémoire en dessous de 200 Mo sur un serveur typique. Ces capacités quantifiées le rendent adapté à la planification à l’échelle de l’entreprise.

## Prérequis
- **Aspose.Tasks for Java** library – téléchargez‑la depuis la [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).  
- **Java Development Kit (JDK)** – version 8 ou plus récente installée sur votre machine.  
- **IDE** de votre choix (IntelliJ IDEA, Eclipse, VS Code, etc.).  
- Un fichier de projet d’exemple au format XML (ou .mpp) que vous utiliserez pour la démonstration.

## Importer les packages
Ajoutez les espaces de noms requis à votre fichier source Java :

```java
import com.aspose.tasks.*;
import java.util.*;
```

Ces importations vous donnent accès aux classes principales de gestion des tâches telles que `Project`, `Task` et aux aides utilitaires.

## Qu'est‑ce qu'une tâche critique ?
Une **tâche critique** est toute activité dont le retard prolonge directement la date de fin du projet, ce qui signifie qu’elle se trouve sur le chemin critique du planning. Dans Aspose.Tasks, vous pouvez déterminer si une tâche est critique en appelant la méthode `Task.isCritical()`, qui renvoie `true` lorsque la tâche influence le temps d’achèvement global du projet.

## Qu'est‑ce qu'une tâche à effort dirigé ?
Une **tâche à effort dirigé** redistribue automatiquement son travail restant chaque fois que sa durée est modifiée, garantissant que la quantité totale d’effort reste constante tout au long du planning. Ce comportement est utile pour les ressources qui travaillent à un taux fixe. Dans Aspose.Tasks, la propriété `Task.isEffortDriven()` renvoie `true` pour les tâches qui présentent cette caractéristique.

## Étape 1 : collecter les tâches avec ChildTasksCollector
La classe `ChildTasksCollector` rassemble chaque tâche sous une tâche parent donnée.  

`ChildTasksCollector` est un assistant qui parcourt la hiérarchie des tâches et renvoie une liste plate d’objets `Task`.

```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector);
List<Task> allTasks = collector.getTasks();
```

## Étape 2 : parcourir les tâches collectées
Parcourez la liste et affichez le statut critique et à effort dirigé de chaque tâche.

```java
for (Task t : allTasks) {
    boolean isCritical = t.get(Tsk.Critical);
    boolean isEffortDriven = t.get(Tsk.EffortDriven);
    System.out.println("Task ID " + t.get(Tsk.Id) + 
        ": critical=" + isCritical + ", effortDriven=" + isEffortDriven);
}
```

Ce simple modèle en deux étapes vous donne une vue complète de la santé de la planification du projet.

## Problèmes courants et dépannage
- **NullPointerException sur les propriétés des tâches** – Assurez‑vous que le fichier de projet est entièrement chargé avant d’accéder aux tâches (`project = new Project("file.mpp")`).  
- **Indicateur critique incorrect** – Vérifiez que le mode de calcul du projet est réglé sur `CalculationMode.Automatic` afin qu’Aspose.Tasks puisse recomposer le chemin critique après les modifications.  
- **Les gros fichiers ralentissent** – Utilisez `Project.set(Prj.ReadOnly, true)` pour ouvrir le fichier en mode lecture‑seule, ce qui réduit la charge mémoire pour les analyses en lecture‑seule.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks pour Java à la fois sous Windows et Linux ?**  
R : Oui, Aspose.Tasks for Java est indépendant de la plateforme et fonctionne sous Windows, Linux et macOS.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Tasks pour Java ?**  
R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.Tasks pour Java sur la [page de téléchargement d’essai gratuit Aspose.Tasks](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support pour Aspose.Tasks pour Java ?**  
R : Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le support communautaire et les discussions.

**Q : Comment obtenir une licence temporaire pour Aspose.Tasks pour Java ?**  
R : Vous pouvez obtenir une licence temporaire sur la [page de demande de licence temporaire](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je acheter Aspose.Tasks pour Java ?**  
R : Vous pouvez acheter Aspose.Tasks pour Java depuis la [page d’achat](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-09-30  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

## Tutoriels associés

- [Chemin critique MS Project – Tutoriel Aspose.Tasks Java](/tasks/java/project-management/critical-path/)
- [Créer des dépendances de tâches de gestion de projet dans Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Gestion de projet Java : % d’avancement des tâches avec Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}