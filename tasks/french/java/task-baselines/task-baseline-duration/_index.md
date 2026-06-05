---
date: 2026-01-23
description: Apprenez à définir la durée de base et à créer une instance de projet
  à l’aide d’Aspose.Tasks pour Java. Ce guide étape par étape vous aide à gérer efficacement
  les bases de référence des tâches.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Comment définir la durée de base dans Aspose.Tasks pour Java
url: /fr/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la durée de la ligne de base dans Aspose.Tasks pour Java

## Introduction
Définir une ligne de base est une étape fondamentale pour suivre l’avancement du projet par rapport au plan initial. Dans ce tutoriel, vous apprendrez **comment définir la durée de la ligne de base** pour les tâches dans Microsoft Project en utilisantose.Tasks pour Java, et vous verrez pourquoi établir une ligne de base tôt peut vous faire gagner du temps et éviter des maux de tête plus tard.

## Réponses rapides
- **Que signifie « set baseline » ?** Cela enregistre le départ, la fin et la durée originaux d’une tâche afin que vous puissiez comparer les changements futurs.  
- **Quelle classe Aspose.Tasks crée un projet ?** La classe `Project` – vous apprendrez également comment **créer une instance de projet** correctement.  
- ** fonctionne pour les tests ; une licence commerciale est  
- **Puis-je récupérer des lignes de base intermédiaires  ?
Une ligne de base de tâche capture le planning prévu (date de début, date de fin et durée) à un moment donné. En définissant une ligne de base, vous créez un point de référence qui facilite la détection des dérives de planning, des dépassements de coûts et de la surallocation des ressources à mesure que le projet évolue.

## Pourquoi utiliser Aspose.Tasks pour la gestion des lignes de base ?
- **Compatibilité .mpp complète** – lire et écrire des fichiers Microsoft Project natifs sans Office installé.  
- **API riche** – accéder aux données de ligne de base, aux lignes de base intermédiaires et aux informations temporelles de façon programmatique.  
- **Multi‑plateforme** – fonctionne sous Windows, Linux et macOS avec n’importe quel JDK standard.

## Prérequis
1. **Environnement de développement Java** – JDK 8+ installé et configuré.  
2. **Aspose.Tasks pour Java** – téléchargez la bibliothèque depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **IDE ou outil de construction** – Maven, Gradle, ou tout IDE de votre choix.

## Importer les packages
Tout d'abord, importez les classes nécessaires dans votre projet Java :

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Étape 1 : créer une instance de projet
Créer une instance de projet est la base de toute manipulation ultérieure. Cette étape montre comment **créer une instance de projet** en utilisant Aspose.Tasks :

```java
Project project = new Project();
```

## Étape 2 : créer une ligne de base de tâche
Ajoutez une nouvelle tâche à la racine du projet et définissez sa ligne de base. Cela enregistre le planning original de la tâche :

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Étape 3 : afficher les informations de la ligne de base de tâche
Récupérez la ligne de base que vous venez de créer et affichez ses propriétés clés. Cela vous aide à vérifier que la ligne de base a été définie correctement :

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Étape 4 : vérifier la ligne de base intermédiaire et le coût fixe
Si vous travaillez avec des lignes de base intermédiaires, vous pouvez interroger si la ligne de base actuelle est intermédiaire et tout coût fixe associé :

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Étape 5 : imprimer les données temporelles
Les données temporelles montrent comment la ligne de base est répartie dans le temps. Parcourez la collection pour inspecter chaque entrée :

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

En suivant ces étapes, vous pouvez **définir la durée de la ligne de base** pour n’importe quelle tâche et récupérer des informations détaillées sur la ligne de base en utilisant Aspose.Tasks pour Java.

## Problèmes courants et solutions
- **La ligne de base n’apparaît pas dans MS Project :** Assurez‑vous d’avoir appelé `project.setBaseline(BaselineType.Baseline)` **après** avoir ajouté la tâche.  
- **NullPointerException sur `getBaselines()` :** Vérifiez que la tâche a été ajoutée au projet avant de définir la ligne de base.  
- **Incohérence d’unité de temps :** Utilisez `TimeUnitType` pour formater correctement la durée, surtout lorsque vous travaillez avec des calendriers personnalisés.

## FAQ

### Qu’est‑ce qu’une ligne de base de tâche dans MS Project ?
Une ligne de base de tâche dans MS Project est un instantané du planning prévu initial pour une tâche, incluant sa date de début, sa date de fin et sa durée.

### Pourquoi la gestion des lignes de base de tâche est‑elle importante ?
Gérer les lignes de base de tâche aide à comparer le planning prévu avec l’avancement réel du projet, facilitant un meilleur suivi et une prise de décision.

### Puis‑je modifier une ligne de base de tâche une fois définie ?
Oui, vous pouvez modifier les lignes de base de tâche dans MS Project pour refléter les changements du plan du projet. Cependant, il est essentiel de documenter toute déviation par rapport à la ligne de base originale.

### Aspose.Tasks prend‑il en charge d’autres fonctionnalités de gestion de projet ?
Oui, Aspose.Tasks propose un large éventail de fonctionnalités pour la gestion de projet, incluant la planification des tâches, l’allocation des ressources et la génération de diagrammes de Gantt.

### Où puis‑je trouver du support pour Aspose.Tasks ?
Vous pouvez trouver du support pour Aspose.Tasks sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), où vous pouvez poser des questions et interagir avec d’autres utilisateurs.

## Questions fréquentes supplémentaires
**Q:** Do I need to call `setBaseline` for each task individually?  
**A:** No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline for all tasks in the project at once.

**Q:** How can I set an interim baseline for a specific task?  
**A:** Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10) after updating the task’s schedule.

**Q:** Is it possible to export the baseline data to CSV?  
**A:** Yes. Iterate over `task.getBaselines()` and write the desired fields to a CSV file using standard Java I/O.

**Q:** Can I read an existing .mpp file that already contains baselines?  
**A:** Absolutely. Load the file with `new Project("myproject.mpp")` and then access each task’s baselines as shown above.

**Q:** Does Aspose.Tasks handle multi‑project files?  
**A:** Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios, combine the projects programmatically.

---

**Dernière mise à jour :** 2026-01-23  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}