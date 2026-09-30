---
date: 2026-09-30
description: Apprenez à créer un attribut étendu de tâche en utilisant Aspose.Tasks
  pour Java, la principale bibliothèque de gestion de projet Java pour ajouter des
  champs de tâche personnalisés.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Comment créer un attribut étendu de tâche avec Aspose.Tasks Java
og_description: Apprenez à créer un attribut étendu de tâche en utilisant Aspose.Tasks
  pour Java, la principale bibliothèque de gestion de projet Java pour ajouter des
  champs de tâche personnalisés.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Comment créer un attribut étendu de tâche avec Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Comment créer un attribut étendu de tâche avec Aspose.Tasks Java
url: /fr/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un attribut étendu de tâche avec Aspose.Tasks Java

## Introduction
Dans ce tutoriel, vous apprendrez comment **créer un attribut étendu de tâche** dans un fichier Microsoft Project en utilisant Aspose.Tasks pour Java. L’ajout de champs personnalisés vous permet de capturer des données spécifiques au projet qui ne sont pas couvertes par les colonnes intégrées, vous offrant un contrôle plus fin sur les rapports et la planification des ressources. À la fin du guide, vous serez capable d’ajouter des attributs texte simple, avec recherche, et de durée à n’importe quelle tâche.

## Réponses rapides
- **Que signifie « attribut étendu » ?** C’est un champ personnalisé que vous définissez et attachez aux tâches, aux ressources ou aux affectations.  
- **Quelle bibliothèque ajoute cette fonctionnalité ?** Aspose.Tasks pour Java, une bibliothèque de gestion de projet Java.  
- **Ai‑je besoin d’une licence pour l’essayer ?** Oui – un essai gratuit de 30 jours est disponible sur le site Web d’Aspose.  
- **Puis‑je ajouter des valeurs de recherche ?** Absolument ; vous pouvez fournir une liste de valeurs autorisées pour les champs texte ou durée.  
- **L’API est‑elle compatible avec Java 8 et versions ultérieures ?** Oui, elle prend en charge Java 8+ et fonctionne sur tous les principaux systèmes d’exploitation.

## Qu’est‑ce qu’un attribut étendu de tâche ?
Un attribut étendu de tâche est une colonne définie par l’utilisateur qui stocke des informations supplémentaires pour chaque tâche dans un fichier Project. Il se comporte comme un champ intégré mais peut contenir n’importe quel type de données dont vous avez besoin, tel que texte, nombres, dates ou durées.

## Pourquoi utiliser Aspose.Tasks pour Java ?
Aspose.Tasks prend en charge **plus de 50 formats de fichiers** et peut traiter des projets contenant **plus de 10 000 tâches** sans nécessiter l’installation de Microsoft Project. La bibliothèque fonctionne entièrement hors ligne, garantissant la confidentialité des données et des performances déterministes pour les solutions à l’échelle de l’entreprise.

## Prérequis
- Connaissances de base en programmation Java.  
- La bibliothèque Aspose.Tasks pour Java installée. Vous pouvez la télécharger depuis le [site Web](https://releases.aspose.com/tasks/java/).  
- Un IDE Java (IntelliJ IDEA, Eclipse ou VS Code) configuré sur votre machine.

## Importer les packages
Les instructions `import` vous donnent accès aux classes principales dont vous aurez besoin, telles que `Project`, `ExtendedAttributeDefinition` et `ExtendedAttribute`.  

`Project` représente un fichier Microsoft Project et fournit des méthodes pour le lire, le modifier et l’enregistrer.  
`ExtendedAttributeDefinition` définit un champ personnalisé qui peut être attaché aux tâches, aux ressources ou aux affectations.  
`ExtendedAttribute` est une instance d’une définition qui contient la valeur réelle pour une entité spécifique.

## Comment ajouter un attribut étendu texte simple à une tâche ?
Pour ajouter un attribut étendu texte simple, vous chargez d’abord le projet, créez ensuite une définition de type Text, l’ajoutez à la collection du projet, créez une tâche, instanciez l’attribut à partir de la définition, définissez sa valeur texte, l’attachez à la tâche, puis enregistrez le projet.

### 1. Définir le chemin du répertoire du document
Spécifiez où se trouvent vos fichiers source et de sortie.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Créer un nouveau projet
Instanciez un objet `Project`, en chargeant éventuellement un fichier .mpp existant.

```java
String dataDir = "Your Document Directory";
```

### 3. Créer une définition d’attribut étendu de type Text1
Définissez le champ personnalisé comme une colonne texte simple nommée « Text1 ».

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Ajouter la définition à la collection d’attributs étendus du projet
Enregistrez la nouvelle définition afin que le projet la reconnaisse.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Ajouter une tâche au projet
Créez une tâche qui recevra le champ personnalisé.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Créer un attribut étendu à partir de la définition d’attribut
Générez une instance que vous pouvez lier à une tâche spécifique.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Attribuer une valeur à l’attribut étendu généré
Définissez le texte réel que vous souhaitez stocker, par ex., « Design Review ».

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Ajouter l’attribut étendu à la tâche
Attachez l’instance d’attribut à la collection `ExtendedAttributes` de la tâche.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Enregistrer le projet
Écrivez le projet mis à jour sur le disque dans le format souhaité.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Comment ajouter un attribut texte avec une option de recherche ?
Lors de l’ajout d’un attribut texte avec recherche, vous suivez les mêmes étapes que pour un attribut texte simple, mais avant d’ajouter la définition vous remplissez sa collection `LookupValues` avec les chaînes autorisées. Ces valeurs apparaissent sous forme de liste déroulante dans Microsoft Project, assurant la cohérence des données.

## Comment ajouter un attribut de durée avec une option de recherche ?
Pour ajouter un attribut de durée avec recherche, remplacez le type `Text1` par `Duration2` lors de la création de la définition, puis remplissez la collection `LookupValues` avec des chaînes de durée telles que « 1 jour », « 2 jours », etc. Après avoir ajouté la définition au projet, créez l’instance d’attribut, définissez une valeur de durée, attachez‑la à une tâche et enregistrez le fichier.

## Problèmes courants et dépannage
- **Les valeurs de recherche n’apparaissent pas** – Assurez‑vous d’ajouter chaque entrée de recherche à la collection `LookupValues` *avant* d’appeler `project.getExtendedAttributes().add(definition)`.  
- **La valeur de l’attribut n’est pas enregistrée** – Vérifiez que vous ajoutez l’instance `ExtendedAttribute` à la tâche *après* avoir défini sa valeur.  
- **La taille du fichier augmente de façon inattendue** – Lors du travail avec des projets très volumineux, envisagez d’appeler `project.setSaveOptions(new ProjectSaveOptions())` pour activer l’enregistrement incrémentiel.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks pour Java avec d’autres bibliothèques Java ?**  
R : Oui, Aspose.Tasks pour Java s’intègre parfaitement à tout écosystème Java, y compris Spring, Hibernate et Apache POI.

**Q : Aspose.Tasks pour Java convient‑il aux applications de gestion de projet à grande échelle ?**  
R : Absolument. La bibliothèque est conçue pour gérer des projets de plusieurs milliers de tâches et prend en charge le streaming afin de maintenir une faible consommation de mémoire.

**Q : Existe‑t‑il des considérations de licence pour l’utilisation d’Aspose.Tasks pour Java dans un projet commercial ?**  
R : Oui, vous avez besoin d’une licence commerciale valide. Vous pouvez consulter les détails sur le [site Web Aspose.Tasks](https://purchase.aspose.com/buy).

**Q : Comment obtenir du support ou de l’assistance pour Aspose.Tasks pour Java ?**  
R : Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l’aide de la communauté, ou ouvrez un ticket de support via votre compte Aspose.

**Q : Puis‑je essayer Aspose.Tasks pour Java avant de l’acheter ?**  
R : Oui, vous pouvez accéder à une version d’essai gratuite sur la page [Aspose.Tasks free trial](https://releases.aspose.com/).

---

**Last updated:** 2026-09-30  
**Tested with:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Tutoriels associés

- [Colonnes personnalisées et attributs étendus dans la gestion de projet Java](/tasks/java/project-management/extended-attributes/)
- [Lire les attributs de tâche étendus avec Aspose.Tasks pour Java](/tasks/java/task-properties/extended-task-attributes/)
- [Comment créer un projet aspose.tasks – Définir de nouveaux attributs de tâche](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}