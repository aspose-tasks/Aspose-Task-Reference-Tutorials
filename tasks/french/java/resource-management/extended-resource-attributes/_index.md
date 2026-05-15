---
date: 2026-01-13
description: Apprenez à créer un attribut personnalisé, charger un fichier Microsoft Project,
  définir une valeur numérique en Java, puis enregistrer le projet au format XML avec
  Aspose.Tasks pour Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment créer un attribut personnalisé dans MS Project avec Aspose.Tasks
url: /fr/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un attribut personnalisé dans MS Project avec Aspose.Tasks

## Introduction
Dans ce tutoriel, **vous découvrirez comment créer un attribut personnalisé** pour les ressources dans un fichier Microsoft Project en utilisant Aspose.Tasks pour Java. Nous parcourrons le chargement d'un fichier Microsoft Project, la définition d'un nouvel attribut numérique, l'attribution d'une valeur, et enfin l'enregistrement du projet au format XML. À la fin, vous disposerez d'un exemple clair et pratique que vous pourrez adapter à vos propres solutions de gestion de projet.

## Quick Answers
- **Que signifie « attribut personnalisé » ?**  
  Un champ défini par l'utilisateur qui stocke des informations supplémentaires (par ex., Âge, Niveau de compétence) pour une ressource ou une tâche.  
- **Quelle bibliothèque gère cela ?**  
  Aspose.Tasks for Java fournit une API fluide pour créer et gérer les attributs personnalisés.  
- **Ai‑je besoin d'une licence ?**  
  Une licence temporaire gratuite suffit pour l'évaluation ; une licence complète est requise pour la production.  
- **Puis‑je définir des valeurs numériques ?**  
  Oui – utilisez `setNumericValue` avec un `BigDecimal` (par ex., `30.5345`).  
- **Comment le projet est‑il enregistré ?**  
  Le fichier modifié peut être enregistré au format XML en utilisant `SaveFileFormat.Xml`.

## What is a Custom Attribute?
Un **attribut personnalisé** (également appelé attribut étendu) est une colonne supplémentaire que vous pouvez ajouter aux ressources ou aux tâches dans Microsoft Project. Il vous permet de capturer des données qui ne sont pas couvertes par les champs intégrés, comme l'âge d'un employé, le niveau de certification, ou tout autre indicateur spécifique à l'entreprise.

## Why Create a Custom Attribute in MS Project?
- **Adapter les données du projet** aux besoins de votre organisation.  
- **Permettre des rapports avancés** en stockant des valeurs qui pourront être interrogées ultérieurement.  
- **Maintenir la cohérence** entre plusieurs projets en appliquant programmatique la même définition d'attribut.

## Prerequisites
Avant de commencer, assurez-vous d'avoir :

1. **Environnement de développement Java** – JDK 8 ou supérieur installé.  
2. **Aspose.Tasks for Java** – Téléchargez la dernière version depuis [ici](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, ou tout IDE compatible Java.  

## Step‑by‑Step Guide

### Import Packages
Tout d'abord, importez les classes Aspose.Tasks dont vous aurez besoin. Elles fournissent les fonctionnalités de base pour gérer les projets, les ressources et les attributs étendus.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Step 1: Define Data Directory
Définissez le dossier où se trouve votre fichier de projet source et où la sortie sera écrite.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load Microsoft Project File
Créez une instance `Project` en chargeant le fichier existant. Il s'agit de l'étape **load Microsoft project file** qui vous donne un accès complet à son contenu.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Step 3: Define the Custom Attribute
Nous allons définir un nouvel attribut numérique appelé **Age**. L'API vérifie si la définition existe déjà ; sinon, elle en crée une.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Step 4: Set Numeric Value in Java
Créez une instance de l'attribut pour une ressource spécifique et attribuez‑lui une valeur numérique en utilisant `setNumericValue`. Cela démontre **set numeric value java** en action.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Step 5: Add Resource and Attach the Custom Attribute
Ajoutez une nouvelle ressource nommée **R1** et attachez‑lui l'attribut personnalisé créé précédemment.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Step 6: Save Project as XML
Enfin, persistez les modifications en enregistrant le projet. Il s'agit de l'étape **save project as xml**, qui produit une représentation XML propre du fichier mis à jour.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Step 7: Display Result
Affichez une confirmation conviviale afin de savoir que le processus s'est terminé sans erreurs.

```java
System.out.println("Process completed Successfully");
```

En suivant ces étapes, vous avez réussi à **créer un attribut personnalisé**, charger un fichier Microsoft Project, définir une valeur numérique avec Java, et enregistrer le projet au format XML.

## Common Pitfalls & Tips
- **Conflits d'ID d'attribut** : Vérifiez toujours `getById` avant de créer une nouvelle définition afin d'éviter les ID en double.  
- **Gestion de la précision** : `BigDecimal` conserve la précision décimale ; évitez d'utiliser `float` ou `double` pour des valeurs exactes.  
- **Chemins de fichiers** : Utilisez des chemins absolus ou configurez le répertoire de travail de votre IDE pour éviter `FileNotFoundException`.  

## Frequently Asked Questions

**Q : Puis‑je créer des attributs personnalisés pour les tâches ainsi que pour les ressources ?**  
R : Oui – utilisez `ExtendedAttributeTask` au lieu de `ExtendedAttributeResource` lors de la définition de l'attribut.

**Q : Est‑il possible d'ajouter plusieurs attributs personnalisés en même temps ?**  
R : Absolument. Créez des objets `ExtendedAttributeDefinition` séparés pour chaque attribut et attachez‑les aux ressources ou tâches souhaitées.

**Q : Dans quels formats puis‑je enregistrer le projet ?**  
R : Aspose.Tasks prend en charge XML, MPP et plusieurs autres formats comme PDF et HTML. Dans cet exemple, nous avons utilisé `SaveFileFormat.Xml`.

**Q : Dois‑je licencier Aspose.Tasks pour les builds de développement ?**  
R : Une licence temporaire suffit pour l'évaluation. Pour les déploiements en production, une licence complète est requise.

**Q : Comment lire ultérieurement les valeurs des attributs personnalisés ?**  
R : Utilisez `resource.getExtendedAttributes()` pour parcourir les attributs attachés et récupérer leurs valeurs avec `getNumericValue()` ou `getTextValue()`.

## Conclusion
Créer un **attribut personnalisé** dans Microsoft Project avec Aspose.Tasks pour Java est simple une fois que vous avez compris le flux de travail : charger le projet, définir l'attribut, définir sa valeur, l'attacher à une ressource, puis enregistrer le fichier. Cette approche vous permet d'étendre les modèles de données de projet de manière programmatique, offrant des rapports plus riches et une intégration plus étroite avec vos processus métier.

---

**Dernière mise à jour :** 2026-01-13  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}