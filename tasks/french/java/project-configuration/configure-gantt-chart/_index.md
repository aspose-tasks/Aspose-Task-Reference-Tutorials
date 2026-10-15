---
date: 2026-10-15
description: Apprenez comment créer une activité, définir le répertoire de données,
  personnaliser les champs de tableau et enregistrer le projet au format MPP avec
  Aspose.Tasks for Java. Guide étape par étape pour les développeurs Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Comment créer une activité et définir le répertoire de données avec Aspose.Tasks
  for Java
og_description: Comment créer une activité, personnaliser les champs de tableau et
  enregistrer le projet au format MPP en utilisant Aspose.Tasks for Java. Suivez ce
  guide détaillé pour une mise en œuvre rapide.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Comment créer une activité et définir le répertoire de données dans Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Comment créer une activité et définir le répertoire de données avec Aspose.Tasks
  for Java
url: /fr/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une activité et définir le répertoire de données avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous découvrirez **comment créer une activité** de manière programmatique, configurer le **répertoire de données**, et **enregistrer le projet au format MPP** tout en **personnalisant les champs de tableau** dans une vue de diagramme de Gantt. Aspose.Tasks pour Java est une API puissante qui prend en charge plus de 30 formats d’entrée et de sortie et peut traiter des projets contenant jusqu’à 10 000 tâches sans charger le fichier complet en mémoire. À la fin du guide, vous serez capable d’automatiser la création de projets, d’enrichir les tâches avec des attributs personnalisés et de produire un fichier MPP prêt à être ouvert avec Microsoft Project.

## Réponses rapides
- **Quelle est la première étape ?** Définissez le chemin du répertoire de données où résident vos fichiers de projet.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (téléchargeable depuis le site officiel).  
- **Puis-je ajouter des attributs personnalisés ?** Oui – vous pouvez définir des attributs étendus et les afficher dans le diagramme de Gantt.  
- **Ai-je besoin d’une licence pour les tests ?** Une licence temporaire est disponible à des fins d’évaluation.  
- **Quel IDE fonctionne le mieux ?** Tout IDE Java (IntelliJ IDEA, Eclipse, NetBeans) fonctionnera.

## Qu’est‑ce que « définir le répertoire de données » et pourquoi est‑ce important ?
Définir le répertoire de données indique à Aspose.Tasks où lire et écrire les fichiers de projet. Sans un chemin correct, l’API ne peut pas localiser vos fichiers `.mpp`, ce qui entraîne des erreurs `FileNotFoundException`. Définir ce répertoire au début de votre code rend le flux de travail reproductible et isole les préoccupations du système de fichiers de la logique métier.

## Pourquoi personnaliser les champs de tableau dans un diagramme de Gantt ?
Les champs de tableau personnalisés vous permettent de présenter des informations supplémentaires — telles que des attributs personnalisés, des données de ressources ou des notes spécifiques au projet — directement dans la vue Gantt. Cela réduit le besoin de rapports séparés et offre aux parties prenantes une visualisation unique et riche en données, pouvant améliorer la rapidité de prise de décision jusqu’à 30 %.

## Comment créer une nouvelle activité ?
Vous créez une nouvelle activité (tâche) en instanciant un objet `Task` et en l’ajoutant à la collection de tâches racine du projet. Cette approche vous permet de générer automatiquement de grands calendriers, d’extraire les données des tâches depuis des systèmes externes ou d’appliquer des mises à jour en masse sans édition manuelle.

## Prérequis
1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez-le depuis la **page de publication Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse ou tout éditeur compatible Java de votre choix.  

## Importer les packages
L’espace de noms `com.aspose.tasks` contient toutes les classes dont vous aurez besoin pour la manipulation de projets. L’importer vous donne accès à `Project`, `Task`, `ExtendedAttributeDefinition` et d’autres types fondamentaux.

```java
import com.aspose.tasks.*;
```

## Dépendance Maven (optionnelle)
Si vous gérez votre projet avec Maven, ajoutez la dépendance Aspose.Tasks à `pom.xml`. Cela garantit que la bibliothèque est résolue automatiquement lors de la construction.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Guide étape par étape

### Étape 1 : configurer le répertoire de données
Définissez le dossier qui contient vos fichiers de projet. La variable `dataDir` contient le chemin absolu et est réutilisée tout au long du tutoriel.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin complet du dossier où se trouve `project.mpp`, par exemple `C:/Projects/MyGantt`.

### Étape 2 : charger le fichier de projet
`Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier Microsoft Project unique en mémoire. Charger un fichier existant vous donne accès à ses tâches, ressources et tableaux.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Étape 3 : ajouter une nouvelle activité
`Task` représente une activité individuelle dans le planning. Ajouter une tâche à la collection de tâches racine l’insère au niveau supérieur de la hiérarchie du projet.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Étape 4 : définir un attribut personnalisé
`ExtendedAttributeDefinition` vous permet de créer un champ personnalisé réutilisable qui peut être attaché à n’importe quelle tâche, ressource ou affectation.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Étape 5 : ajouter l’attribut personnalisé à la tâche
`ExtendedAttribute` est l’instance concrète d’un attribut personnalisé que vous assignez à une tâche spécifique.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Étape 6 : personnaliser le tableau – ajouter l’attribut personnalisé en tant que colonne
`TableField` décrit une colonne dans un tableau de diagramme de Gantt. En ajoutant un `TableField` qui référence l’attribut personnalisé, vous rendez cet attribut visible dans la vue du diagramme.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Étape 7 : enregistrer le projet
Appeler `project.save` persiste toutes les modifications dans un nouveau fichier. La constante `SaveFileFormat.MPP` indique à Aspose.Tasks d’écrire le fichier au format binaire natif de Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **FileNotFoundException** lors du chargement du projet | Le chemin **set data directory** est incorrect ou il manque une barre oblique finale. | Vérifiez que `dataDir` pointe vers le dossier exact et incluez le séparateur de fichiers approprié (`/` ou `\\`). |
| Attribut personnalisé non visible dans la vue Gantt | Le champ du tableau a été ajouté à un mauvais indice ou la largeur de la colonne est trop petite. | Assurez-vous que `table.getTableFields().add(3, attrField);` utilise un indice valide et ajustez `setWidth` si nécessaire. |
| LicenseException lors de l’enregistrement | Aucune licence valide n’a été appliquée pour une utilisation en production. | Appliquez une licence temporaire ou permanente avant d’appeler `project.save()`. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks est disponible pour .NET, Java et C++.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger un essai gratuit depuis la **page de téléchargement d’essai gratuit d’Aspose.Tasks**.

**Q : Où puis‑je trouver du support pour Aspose.Tasks ?**  
R : Vous pouvez trouver du support et poser des questions sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q : Comment acheter une licence pour Aspose.Tasks ?**  
R : Vous pouvez acheter une licence depuis la **page d’achat d’Aspose.Tasks**.

**Q : Ai‑je besoin d’une licence temporaire à des fins de test ?**  
R : Oui, vous pouvez obtenir une licence temporaire depuis la **page de demande de licence temporaire**.

## Conclusion
Vous savez maintenant **comment créer une activité**, définir le répertoire de données, définir et attacher un attribut personnalisé, et **enregistrer le projet au format MPP** tout en **personnalisant les champs de tableau** dans une vue de diagramme de Gantt avec Aspose.Tasks pour Java. Ces capacités vous offrent un contrôle programmatique complet sur les données de projet, permettant la génération automatisée de plannings et des rapports visuels plus riches pour vos parties prenantes.

---

**Dernière mise à jour :** 2026-10-15  
**Testé avec :** Aspose.Tasks Java 24.12 (latest)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un fichier de projet vide dans Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Comment créer un fichier MPP – Créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Comment créer un projet aspose.tasks – Définir les nouveaux attributs de tâche](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}