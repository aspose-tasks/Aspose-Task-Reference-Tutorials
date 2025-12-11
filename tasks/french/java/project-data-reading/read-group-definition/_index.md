---
date: 2025-12-11
description: Apprenez à lire les données de définition de groupe à partir des fichiers
  Microsoft Project à l'aide d'Aspose.Tasks pour Java. Suivez notre tutoriel étape
  par étape.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lire les données de définition de groupe dans Aspose.Tasks
url: /fr/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les données de définition de groupe dans Aspose.Tasks

## Introduction
Aspose.Tasks for Java est une bibliothèque puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project facilement. Dans ce tutoriel, **vous apprendrez comment lire les données de définition de groupe** d’un fichier de projet étape par étape, afin de pouvoir extraire et travailler avec les informations de groupe de tâches dans vos applications Java.

## Quick Answers
- **Que signifie « read group definition » ?** Il s'agit d'extraire la définition des groupes de tâches (nom, critères, formatage) d'un fichier Microsoft Project.  
- **Quelle bibliothèque faut‑il ?** Aspose.Tasks for Java.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quels IDE sont pris en charge ?** Tout IDE Java tel qu'IntelliJ IDEA ou Eclipse.  
- **Combien de code est‑il nécessaire ?** Moins de 30 lignes de code Java pour charger un projet et afficher les détails du groupe.

## What is read group definition?
Une *définition de groupe* dans Microsoft Project décrit comment les tâches sont regroupées en fonction de critères (par ex., statut, priorité). Lire cette définition vous permet d’inspecter programmaticalement la logique de regroupement, les couleurs, les polices et l’ordre de tri appliqués dans le fichier de projet.

## Why read group definition data?
- **Automatisation :** Générer des rapports personnalisés qui reproduisent le regroupement que vous voyez dans Project.  
- **Migration :** Déplacer les règles de regroupement vers un autre projet ou un autre système de gestion de projet.  
- **Validation :** S’assurer que les groupes attendus existent avant d’exécuter des mises à jour en masse.  
- **Personnalisation :** Appliquer une logique métier supplémentaire basée sur la police ou les paramètres de couleur du groupe.

## Prerequisites
Avant de commencer, assurez‑vous d’avoir les éléments suivants :

1. **Java Development Kit (JDK)** – toute version récente (8 ou supérieure).  
2. **Aspose.Tasks for Java Library** – téléchargez‑la depuis [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, ou tout éditeur de votre choix.  

## Import Packages
First, import the core Aspose.Tasks package:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Data Directory
Define the folder that contains the `.mpp` file you want to inspect.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu vers l’emplacement de votre fichier de projet.

### Step 2: Load the Project File
Create a `Project` instance by pointing it to your `.mpp` file.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Task Groups Count
Print the total number of task groups defined in the project.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Step 4: Retrieve Specific Task Group Information
Grab a particular group (index 1 in this example) and display its name and the number of criteria it contains.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Step 5: Retrieve Group Criterion Information
Each group can have one or more criteria. The snippet below extracts details such as the field used for grouping, the grouping mode, cell color, and pattern.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Step 6: Check Parent Group
Sometimes a criterion belongs to a parent group. This check confirms the relationship.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Step 7: Retrieve Criterion's Font Information
Group criteria can have custom font styling. The following code prints the font family, size, style, and sorting direction.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | The criterion may not have a parent group. | Add a null‑check before comparing. |
| **File not found** | `dataDir` path is incorrect. | Use `Paths.get(dataDir, "project.mpp").toAbsolutePath()` to verify. |
| **License not set** | Aspose library runs in evaluation mode and may limit output. | Register your license with `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## Frequently Asked Questions

**Q : Puis‑je utiliser Aspose.Tasks for Java pour modifier des fichiers de projet ?**  
R : Oui, la bibliothèque offre des capacités complètes de lecture/écriture pour les fichiers Microsoft Project.

**Q : Aspose.Tasks for Java est‑il compatible avec toutes les versions des fichiers Microsoft Project ?**  
R : Il prend en charge les formats MPP, XML et d’autres formats courants de Project sur de nombreuses versions.

**Q : Comment gérer les erreurs lors de l’utilisation d’Aspose.Tasks for Java ?**  
R : Enveloppez les opérations de fichier dans des blocs `try‑catch` et inspectez `TasksException` pour obtenir des messages détaillés.

**Q : Aspose.Tasks for Java propose‑t‑il une prise en charge de l’exportation des données de projet vers d’autres formats ?**  
R : Absolument — vous pouvez exporter vers PDF, XLSX, CSV, et plus encore en utilisant les API d’exportation de la bibliothèque.

**Q : Où puis‑je trouver des ressources supplémentaires et de l’assistance pour Aspose.Tasks for Java ?**  
R : Consultez la [documentation Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/) pour les références complètes de l’API et le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour l’aide communautaire.

## Conclusion
Dans ce tutoriel, nous avons parcouru comment **lire les données de définition de groupe** d’un fichier Microsoft Project en utilisant Aspose.Tasks for Java. En suivant les étapes ci‑dessus, vous pouvez extraire les noms de groupe, les critères, le formatage et les relations de groupe parent, vous permettant de créer des rapports personnalisés, de migrer des paramètres ou d’automatiser la logique de validation dans vos applications Java.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}