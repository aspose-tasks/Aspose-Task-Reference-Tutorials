---
date: 2026-01-05
description: Apprenez à définir la date de début du projet et à enregistrer le XML
  MS Project à l’aide d’Aspose.Tasks pour Java. Guide étape par étape pour les développeurs
  Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Définir la date de début du projet avec Aspose.Tasks pour Java
url: /fr/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la date de début du projet avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous apprendrez **comment définir la date de début du projet** dans un fichier Microsoft Project et ensuite **enregistrer le XML de MS Project** à l'aide de la bibliothèque Aspose.Tasks pour Java. Que vous automatisiez un pipeline de reporting ou développiez un outil de gestion de projet personnalisé, maîtriser cette tâche vous fera gagner du temps et éliminera les erreurs manuelles.

## Quick Answers
- **Quelle est la méthode principale pour définir une date de début ?** Utilisez `project.set(Prj.START_DATE, …)`.
- **Quel format dois‑je utiliser pour exporter le fichier ?** Enregistrez‑le au format XML avec `SaveFileFormat.Xml`.
- **Ai‑je besoin d’une licence pour cette opération ?** Une version d’essai fonctionne, mais une licence complète supprime les filigranes.
- **Puis‑je modifier la date de début après avoir créé des tâches ?** Oui, mettez à jour la propriété du projet avant d’ajouter les tâches.
- **Cette fonctionnalité est‑elle compatible avec toutes les versions de MS Project ?** Aspose.Tasks prend en charge XML, MPP, et plus encore.

## What is “Set Project Start Date”?
Définir la date de début du projet établit le calendrier de référence à partir duquel toutes les calculs de planification des tâches commencent. C’est la première étape pour créer de manière programmatique un planning de projet fiable.

## Why use Aspose.Tasks for Java?
Aspose.Tasks fournit une API pure‑Java qui fonctionne sur n’importe quelle plateforme sans nécessiter l’installation de Microsoft Project. Elle vous permet de créer, modifier et exporter rapidement les données de projet, ce qui la rend idéale pour l’automatisation côté serveur.

## Prerequisites
1. **Java Development Kit (JDK)** – toute version récente du JDK.  
2. **Aspose.Tasks for Java** – téléchargez‑le depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou votre IDE Java préféré.

## Import Packages
First, import the necessary classes:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Step 1: Set Up Data Directory
Define where the generated files will be stored.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a Project Instance
Instantiate a new, empty project.

```java
Project project = new Project();
```

### Step 3: Set Project Information Properties
Here we **set the project start date** and related schedule properties.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Step 4: Save MS Project XML
Export the configured project to an XML file.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
- **Format de date incorrect :** assurez‑vous d’utiliser `java.util.Calendar` et d’appeler `getTime()` avant l’affectation.  
- **Fichier non enregistré :** vérifiez que `dataDir` pointe vers un dossier existant et accessible en écriture.  
- **Avertissements de licence :** la version d’essai ajoute des filigranes ; appliquez une licence valide pour les supprimer.

## Frequently Asked Questions

### Q: Puis‑je utiliser Aspose.Tasks pour Java pour lire des fichiers MS Project ?  
**A:** Oui, Aspose.Tasks pour Java offre des fonctionnalités robustes pour la lecture et l’écriture de fichiers MS Project.

### Q: Aspose.Tasks pour Java est‑il compatible avec différentes versions de MS Project ?  
**A:** Absolument, Aspose.Tasks pour Java prend en charge divers formats MS Project, garantissant une large compatibilité.

### Q: Existe‑t‑il des limitations à la version d’essai d’Aspose.Tasks pour Java ?  
**A:** La version d’essai vous permet d’explorer la bibliothèque mais ajoute des filigranes aux fichiers de sortie.

### Q: Comment obtenir du support pour Aspose.Tasks pour Java ?  
**A:** Vous pouvez demander de l’aide sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

### Q: Puis‑je acheter une licence temporaire pour Aspose.Tasks pour Java ?  
**A:** Oui, des licences temporaires sont disponibles pour une utilisation à court terme. Obtenez‑en une [ici](https://purchase.aspose.com/temporary-license/).

### Q: L’enregistrement au format XML préserve‑t‑il les champs personnalisés ?  
**A:** Oui, lorsque vous enregistrez avec `SaveFileFormat.Xml`, tous les attributs personnalisés et champs étendus sont conservés.

### Q: Puis‑je changer la date de début après avoir ajouté des tâches ?  
**A:** Vous pouvez mettre à jour la date de début à tout moment avant l’enregistrement ; il suffit d’appeler à nouveau `project.set(Prj.START_DATE, …)`.

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}