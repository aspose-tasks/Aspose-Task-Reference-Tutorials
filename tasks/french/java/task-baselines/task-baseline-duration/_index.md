---
date: 2026-08-29
description: Apprenez à définir la baseline duration et à suivre l'avancement du projet
  avec Aspose.Tasks for Java. Ce guide étape par étape vous aide à gérer efficacement
  les task baselines.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Comment définir la baseline duration dans Aspose.Tasks for Java
og_description: Apprenez à définir la baseline duration et à suivre l'avancement du
  projet avec Aspose.Tasks for Java. Suivez ce guide détaillé pour gérer efficacement
  les task baselines.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Comment définir la baseline duration pour suivre l'avancement du projet
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Comment définir la baseline duration pour suivre l'avancement du projet
url: /fr/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la durée de la ligne de base pour suivre la progression du projet

## Introduction
Suivre la progression d’un projet commence par une ligne de base solide. Dans ce tutoriel, vous découvrirez **comment définir la durée de la ligne de base** pour les tâches dans les fichiers Microsoft Project à l’aide de la bibliothèque Aspose.Tasks pour Java, et comprendrez pourquoi établir une ligne de base tôt vous aide à surveiller le glissement du planning, les écarts de coûts et la surallocation des ressources tout au long du projet.

## Réponses rapides
- **Que signifie « set baseline » ?** Il enregistre le début, la fin et la durée d’origine d’une tâche afin que vous puissiez comparer les changements futurs.  
- **Quelle classe Aspose.Tasks crée un projet ?** La classe `Project` – vous apprendrez également comment **créer correctement une instance de projet**.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Une licence d’évaluation gratuite fonctionne pour les tests ; une licence commerciale est requise pour la production.  
- **Puis‑je récupérer les lignes de base intermédiaires ?** Oui, Aspose.Tasks vous permet d’interroger les lignes de base intermédiaires et leurs coûts fixes.  
- **Quelle version de Java est requise ?** Java 8 ou ultérieure est recommandée.  
- **Comment cela m’aide‑t‑il à suivre la progression du projet ?** Une fois la ligne de base définie, vous pouvez comparer instantanément les dates réelles avec le plan original en utilisant les fonctionnalités de reporting intégrées.

## Qu’est‑ce qu’une ligne de base de tâche et pourquoi la définir ?
Une ligne de base de tâche capture le planning prévu (date de début, date de fin et durée) à un moment donné. En définissant une ligne de base, vous créez un point de référence qui facilite la détection du glissement du planning, des dépassements de coûts et de la surallocation des ressources à mesure que le projet évolue.

## Pourquoi utiliser Aspose.Tasks pour la gestion des lignes de base ?
Aspose.Tasks fournit **une compatibilité .mpp complète** – vous pouvez lire et écrire des fichiers Microsoft Project natifs sans avoir besoin de Microsoft Office installé. L’API vous donne un accès programmatique à **plus de 50 formats d’entrée et de sortie**, prend en charge **les lignes de base intermédiaires 1‑10**, et peut gérer **des projets de plusieurs centaines de pages** sans charger le fichier entier en mémoire, ce qui est essentiel pour le traitement par lots haute performance.

## Prérequis
1. **Environnement de développement Java** – JDK 8+ installé et configuré.  
2. **Aspose.Tasks pour Java** – téléchargez la bibliothèque depuis la [page de téléchargement Aspose.Tasks pour Java](https://releases.aspose.com/tasks/java/).  
3. **IDE ou outil de construction** – Maven, Gradle, ou tout IDE de votre choix.

## Importer les packages
Les importations suivantes apportent les classes principales d’Aspose.Tasks nécessaires pour travailler avec les projets, les tâches, les lignes de base et les données temporelles.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Étape 1 : créer une instance de projet
La classe `Project` représente un fichier Microsoft Project en mémoire et constitue le point d’entrée pour toutes les opérations.

```java
Project project = new Project();
```

## Étape 2 : créer une ligne de base de tâche
Un `TaskBaseline` stocke le début, la fin et la durée prévus pour une tâche spécifique.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Étape 3 : afficher les informations de la ligne de base de la tâche
La méthode `getBaselines()` renvoie la collection des lignes de base associées à une tâche.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Étape 4 : vérifier la ligne de base intermédiaire et le coût fixe
`BaselineType` énumère les lignes de base principales et intermédiaires (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Étape 5 : imprimer les données temporelles
`TimephasedData` représente un morceau d’information de planification pour un intervalle de temps spécifique.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

En suivant ces étapes, vous pouvez **définir la durée de la ligne de base** pour n’importe quelle tâche et récupérer des informations détaillées sur la ligne de base à l’aide d’Aspose.Tasks pour Java, vous offrant ainsi un moyen fiable de **suivre la progression du projet** tout au long du cycle de vie du projet.

## Problèmes courants et solutions
- **La ligne de base n’apparaît pas dans MS Project :** Assurez‑vous d’avoir appelé `project.setBaseline(BaselineType.Baseline)` **après** avoir ajouté la tâche.  
- **NullPointerException sur `getBaselines()` :** Vérifiez que la tâche a été ajoutée au projet avant de définir la ligne de base.  
- **Incohérence d’unité de temps :** Utilisez `TimeUnitType` pour formater correctement la durée, surtout lorsque vous travaillez avec des calendriers personnalisés.

## FAQ

### Qu’est‑ce qu’une ligne de base de tâche dans MS Project ?
Une ligne de base de tâche dans MS Project est un instantané du planning initial prévu pour une tâche, incluant sa date de début, sa date de fin et sa durée.

### Pourquoi la gestion des lignes de base de tâche est‑elle importante ?
Gérer les lignes de base de tâche aide à comparer le planning prévu avec l’avancement réel du projet, facilitant ainsi un meilleur suivi et une prise de décision plus éclairée.

### Puis‑je modifier une ligne de base de tâche une fois qu’elle est définie ?
Oui, vous pouvez modifier les lignes de base de tâche dans MS Project pour refléter les changements du plan de projet. Cependant, il est essentiel de documenter toute déviation par rapport à la ligne de base originale.

### Aspose.Tasks prend‑il en charge d’autres fonctionnalités de gestion de projet ?
Oui, Aspose.Tasks propose un large éventail de fonctionnalités pour la gestion de projet, incluant la planification des tâches, l’allocation des ressources et la génération de diagrammes de Gantt.

### Où puis‑je trouver du support pour Aspose.Tasks ?
Vous pouvez trouver du support pour Aspose.Tasks sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), où vous pouvez poser des questions et interagir avec d’autres utilisateurs.

## Questions fréquemment posées supplémentaires
**Q : Dois‑je appeler `setBaseline` pour chaque tâche individuellement ?**  
**R : Non. Appeler `project.setBaseline(BaselineType.Baseline)` enregistre la ligne de base pour toutes les tâches du projet en une fois.**

**Q : Comment puis‑je définir une ligne de base intermédiaire pour une tâche spécifique ?**  
**R : Utilisez `project.setBaseline(BaselineType.Baseline1)` (ou Baseline2‑Baseline10) après avoir mis à jour le planning de la tâche.**

**Q : Est‑il possible d’exporter les données de ligne de base vers un CSV ?**  
**R : Oui. Parcourez `task.getBaselines()` et écrivez les champs souhaités dans un fichier CSV en utilisant les I/O Java standard.**

**Q : Puis‑je lire un fichier .mpp existant contenant déjà des lignes de base ?**  
**R : Absolument. Chargez le fichier avec `new Project("myproject.mpp")` puis accédez aux lignes de base de chaque tâche comme indiqué ci‑dessus.**

**Q : Aspose.Tasks gère‑t‑il les fichiers multi‑projets ?**  
**R : Aspose.Tasks fonctionne avec des fichiers .mpp à projet unique. Pour les scénarios multi‑projets, combinez les projets par programmation.**

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutoriels associés

- [Créer une liste de tâches Java – Ligne de base MS Project avec Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Créer un projet MPP Java – Modifier la progression des tâches avec Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Ligne de base de gestion de projet – Planification des tâches avec Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}