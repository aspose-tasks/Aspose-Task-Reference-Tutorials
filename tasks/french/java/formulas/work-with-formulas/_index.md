---
date: 2025-12-07
description: Apprenez à **créer un projet de test** et **ajouter un champ personnalisé**
  tout en manipulant les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Créer un projet de test et utiliser des formules avec Aspose.Tasks pour Java
url: /fr/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un projet de test et utiliser les formules avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous allez **créer des fichiers de projet de test**, ajouter un champ personnalisé et travailler avec les formules MS Project en utilisant la bibliothèque Aspose.Tasks pour Java. Aspose.Tasks facilite la **manipulation des données Microsoft Project** de façon programmatique—que vous ayez besoin de générer des plannings, de calculer des dates ou d’automatiser des rapports. À la fin du guide, vous disposerez d’un exemple exécutable qui définit un attribut étendu, fixe une date limite pour une tâche et enregistre le projet sous forme de fichier MPP.

## Quick Answers
- **What does the tutorial cover?** Création d’un projet de test, ajout d’un champ personnalisé, définition d’un attribut étendu et définition d’une date limite de tâche avec une formule.  
- **Which library is required?** Aspose.Tasks for Java (dernière version).  
- **Do I need a license?** Un essai gratuit suffit pour le développement ; une licence est requise pour la production.  
- **What IDE can I use?** Tout IDE Java (IntelliJ IDEA, Eclipse, VS Code) qui supporte JDK 8+.  
- **How long does the implementation take?** Environ 10‑15 minutes pour copier le code et l’exécuter.

## What is a “Test Project” in Aspose.Tasks?
Un **projet de test** est un fichier Microsoft Project léger créé programmatique pour démontrer ou valider une fonctionnalité. Il contient un jeu minimal de tâches, de ressources et de champs personnalisés que vous pouvez manipuler sans impacter les données de projet réelles.

## Why Use Aspose.Tasks to Manipulate Microsoft Project?
- **Full API coverage** – accès à chaque propriété de Project, Task et Resource.  
- **No Office installation required** – fonctionne sur serveurs, pipelines CI et conteneurs Docker.  
- **Cross‑platform** – s’exécute sous Windows, Linux et macOS avec le même code Java.  
- **Robust formula engine** – calcule les dates, durées et champs personnalisés directement dans le fichier projet.

## Prerequisites
Avant de commencer, assurez‑vous de disposer de :

- **Java Development Kit (JDK) 8+** – téléchargez‑le depuis le site d’Oracle ou adoptez OpenJDK.  
- **Aspose.Tasks for Java** – obtenez le JAR le plus récent depuis la [page de téléchargement Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) et ajoutez‑le au classpath de votre projet ou aux dépendances Maven/Gradle.

## Import Packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Test Project with a Custom Field
We begin by **creating test project** and adding a custom field that will later hold our formula result.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Conseil pro :* `CreateTestProjectWithCustomField()` est une méthode d’assistance qui construit un planning minimal et enregistre un attribut étendu prêt pour l’affectation de formule.

### Step 2: Define an Extended Attribute (Add Custom Field)
Next, we **define extended attribute** – essentially the custom field – and give it a friendly alias. This is where we **add custom field** logic.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** rend le champ lisible dans Project.  
- **Formula** calcule le nombre de jours entre la date *Finish* d’une tâche et sa *Deadline*.

### Step 3: Set Deadline for a Task (Add Deadline Task & Set Task Deadline)
Now we **add deadline task** data by setting the *Deadline* property on a specific task.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- L’instance `Calendar` définit le moment exact de la date limite.  
- `set(Tsk.DEADLINE, …)` **sets task deadline** pour la tâche sélectionnée.

### Step 4: Save the Project (Manipulate Microsoft Project File)
Finally, we **manipulate Microsoft Project** by persisting the changes to an MPP file.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Vous pouvez ouvrir `SaveFile.mpp` dans Microsoft Project pour voir le champ personnalisé, le résultat de la formule et la date limite reflétés dans le planning.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Formula not evaluating** | Ensure the attribute’s `Formula` string uses correct field names (e.g., `[Deadline]`, `[Finish]`). |
| **Task not found** | Verify the task ID (`1` in the example) exists; use `project.getRootTask().getChildren().size()` to debug. |
| **License exception** | Apply a valid Aspose.Tasks license before calling any API methods (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing you to **manipulate Microsoft Project** files in the language of your choice.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Absolutely. Download a fully functional trial from the [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: How can I get support for Aspose.Tasks?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to ask questions and share experiences with the community.

**Q: Do I need a temporary license for evaluation?**  
A: A temporary license is available for short‑term testing; you can request one [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}