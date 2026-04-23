---
date: 2026-02-13
description: Apprenez à créer une nouvelle activité, définir le répertoire de données
  et enregistrer le projet au format MPP dans Aspose.Tasks Java. Ce guide étape par
  étape couvre également la personnalisation des champs de tableau.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment créer une nouvelle activité et définir le répertoire de données Aspose.Tasks
url: /fr/java/project-configuration/configure-gantt-chart/
weight: 10
---

 "Q : Puis-je utiliser Aspose.Tasks avec d'autres langages de programmation ?" Answer: "Oui, Aspose.Tasks est disponible pour plusieurs langages de programmation dont .NET, Java et C++."

Similarly others.

## Conclusion
Translate.

Last Updated etc keep same.

Now produce final content with shortcodes and code blocks unchanged.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une nouvelle activité et définir le répertoire de données Aspose.Tasks

## Introduction
Dans ce tutoriel, vous apprendrez **comment définir le répertoire de données**, comment **créer une nouvelle activité**, et comment **enregistrer le projet au format MPP** tout en configurant la vue du diagramme Gantt MS Project dans les projets Aspose.Tasks en Java. Aspose.Tasks est une API Java robuste qui vous permet de manipuler les fichiers Microsoft Project de manière programmatique. À la fin de ce guide, vous serez capable de **personnaliser les champs de tableau**, d’ajuster le répertoire de données, et de visualiser votre projet exactement comme vous le souhaitez.

## Quick Answers
- **Quelle est la première étape ?** Définissez le chemin du répertoire de données où résident vos fichiers de projet.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (téléchargeable depuis le site officiel).  
- **Puis-je ajouter des attributs personnalisés ?** Oui – vous pouvez définir des attributs étendus et les afficher dans le diagramme de Gantt.  
- **Ai-je besoin d’une licence pour les tests ?** Une licence temporaire est disponible à des fins d’évaluation.  
- **Quel IDE fonctionne le mieux ?** Tout IDE Java (IntelliJ IDEA, Eclipse, NetBeans) fonctionnera.

## Qu’est‑ce que le “set data directory” et pourquoi est‑ce important ?
Définir le répertoire de données indique à Aspose.Tasks où lire et écrire les fichiers de projet. Sans un chemin correct, l’API ne peut pas localiser vos fichiers `.mpp`, ce qui entraîne des erreurs **FileNotFound**. Définir ce répertoire au début de votre code rend le reste du flux de travail propre et reproductible.

## Pourquoi personnaliser les champs de tableau dans un diagramme de Gantt ?
Les champs de tableau personnalisés vous permettent d’afficher des informations supplémentaires – comme des attributs personnalisés, des données de ressources ou des notes spécifiques au projet – directement dans la vue Gantt. Cela rend le diagramme plus informatif pour les parties prenantes et réduit le besoin de basculer entre plusieurs rapports.

## Comment créer une nouvelle activité ?
Créer une nouvelle activité (tâche) est l’une des opérations principales lors de la construction ou de la mise à jour d’un planning de projet. En ajoutant des tâches de façon programmatique, vous pouvez automatiser la génération de plans de projet complexes, intégrer des données provenant d’autres systèmes, ou appliquer des modifications en masse sans édition manuelle.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – toute version récente (8+).  
2. **Bibliothèque Aspose.Tasks** – téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, ou tout éditeur compatible Java que vous préférez.

## Import Packages
Tout d’abord, importez l’espace de noms Aspose.Tasks afin de pouvoir travailler avec ses classes :

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
Définissez le dossier qui contient vos fichiers de projet. Il s’agit de l’étape **set data directory** sur laquelle se concentre le tutoriel.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu du dossier où `project.mpp` est stocké.

### Step 2: Load Project File
Créez une instance `Project` en chargeant un fichier Microsoft Project existant.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Add New Activity
Insérez une nouvelle tâche (activité) à la racine du projet. Cela montre **comment créer une nouvelle activité** de façon programmatique.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Step 4: Define Custom Attribute
Créez une définition d’attribut personnalisé que vous pourrez ensuite associer aux tâches.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Step 5: Add Custom Attribute to Task
Attribuez l’attribut nouvellement défini à la tâche que vous avez créée.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Step 6: Customize Table – **customize table fields**
Ajoutez l’attribut personnalisé comme colonne dans le tableau du diagramme de Gantt, en spécifiant la largeur, le titre et l’alignement.

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

### Step 7: Save Project
Enregistrez les modifications dans un nouveau fichier qui pourra être ouvert dans Microsoft Project. Cette étape **enregistre le projet au format MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Common Issues and Solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **FileNotFoundException** lors du chargement du projet | Le chemin du **set data directory** est incorrect ou il manque une barre oblique finale. | Vérifiez que `dataDir` pointe vers le dossier exact et incluez le séparateur de fichiers approprié (`/` ou `\\`). |
| L'attribut personnalisé n'est pas visible dans la vue Gantt | Le champ du tableau a été ajouté à un mauvais indice ou la largeur de la colonne est trop petite. | Assurez‑vous que `table.getTableFields().add(3, attrField);` utilise un indice valide et ajustez `setWidth` si nécessaire. |
| LicenseException lors de l'enregistrement | Aucune licence valide n’a été appliquée pour une utilisation en production. | Appliquez une licence temporaire ou permanente avant d’appeler `project.save()`. |

## Frequently Asked Questions

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks est disponible pour plusieurs langages de programmation dont .NET, Java et C++.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger un essai gratuit depuis [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support pour Aspose.Tasks ?**  
R : Vous pouvez obtenir du support et poser des questions sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q : Comment puis‑je acheter une licence pour Aspose.Tasks ?**  
R : Vous pouvez acheter une licence depuis [ici](https://purchase.aspose.com/buy).

**Q : Ai‑je besoin d’une licence temporaire à des fins de test ?**  
R : Oui, vous pouvez obtenir une licence temporaire depuis [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous avez maintenant appris comment **définir le répertoire de données**, **créer une nouvelle activité**, définir et associer un attribut personnalisé, et **enregistrer le projet au format MPP** tout en **personnalisant les champs de tableau** dans une vue de diagramme de Gantt à l’aide d’Aspose.Tasks pour Java. Ces étapes vous donnent un contrôle complet sur la façon dont les données du projet sont affichées, rendant vos diagrammes de Gantt plus informatifs et adaptés aux besoins de vos parties prenantes.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}