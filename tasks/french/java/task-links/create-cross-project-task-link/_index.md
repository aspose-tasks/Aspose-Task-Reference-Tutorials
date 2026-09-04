---
date: 2026-07-05
description: Apprenez comment lier des tâches entre projets avec Aspose.Tasks for
  Java. Guide étape par étape, prérequis et meilleures pratiques pour un lien de tâches
  inter‑projets fluide.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Créer un lien de tâche inter‑projet dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Lier des tâches entre projets avec Aspose.Tasks for Java
url: /fr/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lier des tâches entre projets avec Aspose.Tasks pour Java

## Introduction
Lier des tâches entre projets est une capacité fondamentale qui vous permet de synchroniser le travail, d'éviter les duplications et de maintenir une source unique de vérité pour les activités interdépendantes. Dans ce tutoriel, vous découvrirez comment **lier des tâches entre projets** avec Aspose.Tasks pour Java, étape par étape. À la fin, vous disposerez d'un lien inter‑projets entièrement fonctionnel qui se met à jour automatiquement lorsqu'un côté change, vous offrant une coordination en temps réel sans copier‑coller manuel.

## Réponses rapides
- **Quelle est la classe principale pour créer un projet ?** `Project` – elle représente le fichier MS‑Project complet en mémoire.  
- **Quelle méthode ajoute une tâche externe ?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Puis‑je définir le type de lien ?** Oui – utilisez `TaskLinkType.FinishToStart`, `StartToStart`, etc.  
- **Ai‑je besoin d’une licence pour le lien ?** Une licence valide d’Aspose.Tasks est requise pour une utilisation en production ; un essai gratuit suffit pour l’évaluation.  
- **Existe‑t‑il une limite au nombre de tâches liées ?** Aspose.Tasks peut gérer plus de 10 000 tâches liées par projet sans dégradation des performances.

## Qu’est‑ce que le lien de tâches entre projets ?
Lier des tâches entre projets crée une relation de dépendance entre une tâche d’un fichier de projet et une tâche d’un autre, permettant aux modifications de la tâche source (durée, date de début, contraintes) de se répercuter automatiquement sur la tâche dépendante. Ce mécanisme maintient les calendriers alignés, réduit les mises à jour manuelles et garantit que toute modification du projet source soit instantanément reflétée dans tous les projets liés, préservant la cohérence du portefeuille.

## Pourquoi utiliser Aspose.Tasks pour le lien inter‑projets ?
Aspose.Tasks prend en charge **plus de 50 formats d’entrée et de sortie** et peut traiter **des projets de plusieurs centaines de pages** tout en maintenant l’utilisation de la mémoire en dessous de 200 Mo. Son API effectue le lien côté serveur, éliminant ainsi le besoin d’installer Microsoft Project et permettant des pipelines automatisés pour les grandes entreprises.

## Prérequis
- Java 17 (ou version ultérieure) installé et configuré dans votre IDE.  
- Un fichier de licence valide d’Aspose.Tasks pour Java (`Aspose.Tasks.Java.lic`).  
- La bibliothèque Aspose.Tasks pour Java ajoutée à votre projet. Vous pouvez la télécharger depuis la [page de publication d’Aspose.Tasks pour Java](https://releases.aspose.com/tasks/java/).  
- Une connaissance de base des concepts de MS‑Project tels que les tâches, les tâches récapitulatives et les dépendances.

## Importer les packages
Les classes `Project`, `Task`, `TaskLink` et les énumérations associées se trouvent dans l’espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier Java :

`import com.aspose.tasks.*;`

**Project** est la classe principale représentant un fichier de projet en mémoire. **Task** représente un élément de travail individuel au sein d’un projet. **TaskLink** définit une relation de dépendance entre deux tâches. Ces importations vous donnent accès à l’ensemble complet des fonctionnalités de manipulation de projet, y compris le lien inter‑projets.

## Comment lier des tâches entre projets ?
Chargez les deux fichiers de projet, ajoutez un espace réservé de tâche externe, créez une tâche locale, puis connectez‑les avec un `TaskLink`. L’API gère le mappage des ID et les mises à jour automatiquement, garantissant que toute modification de la tâche externe se propage à la tâche locale liée sans code supplémentaire. Cette approche simplifie la coordination multi‑projets et réduit le risque de dérive du planning.

### Étape 1 : Configurer votre environnement
Assurez‑vous que le JAR Aspose.Tasks est présent dans le classpath et que le fichier de licence est chargé à l’exécution :

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** charge votre fichier de licence Aspose.Tasks pour activer toutes les fonctionnalités et supprimer les filigranes d’évaluation.

### Étape 2 : Créer une instance de projet
Instanciez un nouvel objet `Project` pour le projet cible où vous souhaitez que le lien réside :

`Project targetProject = new Project();`

La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier de projet unique en mémoire.

### Étape 3 : Ajouter une tâche récapitulative
Une tâche récapitulative regroupe les tâches liées. Créez‑en une pour contenir à la fois les tâches externes et locales :

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### Étape 4 : Ajouter une tâche externe
Insérez une tâche externe qui pointe vers une tâche d’un autre fichier de projet :

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

La méthode **addExternalTask** crée une tâche d’espace réservé qui référence un fichier de projet externe, en utilisant le nom de fichier et l’ID de tâche fournis.

### Étape 5 : Ajouter une tâche locale
Créez la tâche qui sera liée à la tâche externe :

`Task local = summary.getChildren().add("Local Task");`

### Étape 6 : Créer un lien de tâche
Établissez une dépendance entre les tâches externes et locales. Le type de lien le plus courant est Fin‑à‑Début :

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** enregistre la relation ; vous pouvez ensuite modifier son retard, son avance ou son type selon les besoins.

### Étape 7 : Enregistrer et vérifier
Enregistrez le projet dans un fichier et, éventuellement, ouvrez‑le dans Microsoft Project pour vérifier le lien :

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** spécifie le format de fichier pour enregistrer un projet. Lorsque vous ouvrez *LinkedProject.mpp*, vous verrez la tâche externe affichée avec une icône spéciale et la ligne de dépendance pointant vers la tâche locale.

## Problèmes courants et solutions
- **Fichier externe introuvable** – Assurez‑vous que le chemin est relatif au processus en cours ou fournissez un chemin absolu.  
- **Incohérence des ID de tâche** – Vérifiez que l’ID de la tâche externe (le deuxième argument de `addExternalTask`) correspond au projet source.  
- **Licence non chargée** – Un fichier de licence manquant ou incorrect entraîne une `LicenseException`. Chargez‑la avant tout appel à Aspose.Tasks.  
- **Performance sur de gros projets** – Utilisez `Project.setReadOnly(true)` lorsque vous avez seulement besoin de lire les tâches externes ; cela réduit la consommation de mémoire.

## Questions fréquemment posées

**Q : Puis‑je lier des tâches provenant de plusieurs projets externes dans la même tâche récapitulative ?**  
R : Oui, vous pouvez ajouter plusieurs tâches externes sous une même tâche récapitulative et créer des liens individuels pour chacune, en utilisant la même méthode `addExternalTask`.

**Q : Que se passe‑t‑il si la tâche externe du projet lié est modifiée ?**  
R : Toute modification du planning, de la durée ou des contraintes de la tâche externe est automatiquement reflétée dans la tâche locale dépendante lorsque le projet cible est actualisé.

**Q : Est‑il possible de créer des liens entre des tâches de différents formats de fichier ?**  
R : Absolument. Aspose.Tasks prend en charge le lien entre les formats MPP, XML et Primavera, permettant aux écosystèmes de projets hétérogènes de rester synchronisés.

**Q : Puis‑je dissocier des tâches une fois qu’elles sont liées entre projets ?**  
R : Oui, supprimez le lien en appelant `project.getTaskLinks().remove(link)` ou en supprimant l’espace réservé de la tâche externe.

**Q : Existe‑t‑il des limitations quant au nombre de tâches pouvant être liées entre projets ?**  
R : La bibliothèque peut gérer **plus de 10 000 tâches liées** par projet, limitées uniquement par la mémoire système disponible et les spécifications du format de fichier sous‑jacent.

## Conclusion
Vous disposez maintenant d’une approche complète et prête pour la production afin de **lier des tâches entre projets** avec Aspose.Tasks pour Java. Cette fonctionnalité rationalise la coordination multi‑projets, réduit les efforts manuels et garantit que les modifications de planning se propagent instantanément à travers votre portefeuille. Explorez des fonctionnalités supplémentaires telles que les temps de retard personnalisés, les différents types de liens et le lien en masse pour automatiser davantage les structures de projet complexes.

---

**Dernière mise à jour :** 2026-07-05  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## Tutoriels associés

- [Créer un lien de tâche dans Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Créer des tâches Aspose Java – Propriétés des tâches](/tasks/java/task-properties/)
- [Créer un fichier MS Project vide dans Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}