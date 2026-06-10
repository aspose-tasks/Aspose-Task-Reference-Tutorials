---
date: 2026-06-10
description: Apprenez à créer un attribut étendu en Java, charger un fichier Microsoft
  Project, définir des valeurs numériques et enregistrer le projet au format XML à
  l'aide d'Aspose.Tasks for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Gérer les attributs de ressources étendus dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment créer un attribut étendu en Java avec Aspose.Tasks
url: /fr/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un attribut étendu en Java avec Aspose.Tasks

## Introduction
Dans ce guide pratique, vous allez **créer un attribut étendu en Java** pour un fichier Microsoft Project en utilisant Aspose.Tasks. Nous parcourrons le chargement d’un projet existant, la définition d’un nouvel attribut numérique, l’attribution d’une valeur à une ressource, et enfin la persistance des modifications sous forme de fichier XML. À la fin, vous disposerez d’un modèle de code réutilisable pouvant être intégré à n’importe quelle solution de gestion de projet basée sur Java.

## Réponses rapides
- **Qu'est‑ce qu'un attribut étendu ?**  
  Un champ défini par l'utilisateur (par ex., Âge, Niveau de compétence) qui stocke des données supplémentaires pour les ressources ou les tâches.  
- **Quelle API le crée ?**  
  Aspose.Tasks for Java fournit la classe `ExtendedAttributeDefinition` pour définir et gérer les attributs personnalisés.  
- **Ai‑je besoin d'une licence ?**  
  Une licence d'évaluation temporaire suffit pour le développement ; une licence complète est requise pour les déploiements en production.  
- **Puis‑je stocker des nombres ?**  
  Oui – utilisez `setNumericValue(BigDecimal)` pour attribuer des valeurs décimales précises.  
- **Comment persister les modifications ?**  
  Appelez `project.save(\"output.xml\", SaveFileFormat.Xml)` pour écrire le projet mis à jour au format XML.

## Qu'est‑ce qu'un attribut personnalisé ?
Un **attribut personnalisé** (également appelé attribut étendu) est une colonne supplémentaire que vous pouvez ajouter aux ressources ou aux tâches dans Microsoft Project. Il vous permet de capturer des données qui ne sont pas couvertes par les champs intégrés, comme l'âge des employés, le niveau de certification ou tout indicateur spécifique à l'entreprise.

## Pourquoi créer un attribut étendu en Java ?
Créer un attribut étendu en Java vous permet d'enrichir les données du projet de manière programmatique, assurant la cohérence entre les fichiers et permettant la génération de rapports automatisés. En définissant l'attribut une fois, vous pouvez l'appliquer à n’importe quel nombre de ressources ou de tâches sans saisie manuelle, ce qui fait gagner du temps et réduit les erreurs.

- **Adapter les données à votre organisation** – stockez tout indicateur qui vous importe sans solutions manuelles sous Excel.  
- **Permettre des rapports plus riches** – interrogez le champ personnalisé plus tard pour des tableaux de bord ou des analyses.  
- **Maintenir la cohérence** – appliquez programmétiquement la même définition à des dizaines de projets, éliminant les erreurs humaines.  
- **Testé en performance** – Aspose.Tasks traite des projets contenant jusqu’à 10 000 tâches et 5 000 ressources sans charger le fichier complet en mémoire, selon les références produit.

## Prérequis
1. **Java Development Kit** – JDK 8 ou version plus récente installé.  
2. **Aspose.Tasks for Java** – téléchargez la dernière version depuis [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, ou tout environnement de développement compatible Java.  

## Comment créer un attribut étendu en Java ?
Chargez votre projet, définissez l'attribut, attachez-le à une ressource, puis enregistrez le fichier – le tout en quelques étapes simples. Les sections suivantes détaillent chaque étape avec une explication concise suivie de l'espace réservé où votre code réel se trouve.

### Guide étape par étape

#### Importer les packages
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` et les classes associées se trouvent dans l'espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier Java.

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

#### Étape 1 : Définir le répertoire de données
`Paths` est une classe utilitaire qui fournit des méthodes pour obtenir un chemin de système de fichiers de manière indépendante de la plateforme.

```java
String dataDir = "Your Data Directory";
```

#### Étape 2 : Charger le fichier Microsoft Project
`Project` représente un fichier Microsoft Project en mémoire, permettant la lecture et l'écriture de son contenu.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Étape 3 : Définir l'attribut personnalisé
`ExtendedAttributeDefinition` définit le schéma d'un nouveau champ personnalisé qui peut être attaché aux ressources ou aux tâches.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Étape 4 : Définir la valeur numérique en Java
`ExtendedAttributeResource` contient la valeur d'un attribut personnalisé pour une instance de ressource spécifique.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Étape 5 : Ajouter une ressource et attacher l'attribut personnalisé
`Resource` modélise une ressource de projet telle qu'une personne, un équipement ou un matériau.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Étape 6 : Enregistrer le projet au format XML
`SaveFileFormat` répertorie les formats de sortie pris en charge pour l'enregistrement d'un projet, y compris XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Étape 7 : Afficher le résultat
`System.out.println` affiche une ligne de texte sur la sortie console standard.

```java
System.out.println("Process completed Successfully");
```

## Pièges courants et conseils
- **Conflits d'ID d'attribut** : Appelez toujours `project.getExtendedAttributes().getById(id)` avant de créer une nouvelle définition afin d'éviter les identifiants en double.  
- **Gestion de la précision** : Préférez `BigDecimal` plutôt que `float`/`double` pour des valeurs numériques exactes ; cela évite les erreurs d'arrondi dans les rapports.  
- **Fiabilité du chemin de fichier** : Utilisez `Paths.get(...).toAbsolutePath()` ou configurez le répertoire de travail de votre IDE pour éliminer `FileNotFoundException`.  

## Questions fréquemment posées

**Q : Puis‑je créer des attributs personnalisés pour les tâches ainsi que pour les ressources ?**  
A : Oui – utilisez `ExtendedAttributeTask` au lieu de `ExtendedAttributeResource` lors de la définition du schéma d'attribut.

**Q : Est‑il possible d'ajouter plusieurs attributs personnalisés à la fois ?**  
A : Absolument. Créez des objets `ExtendedAttributeDefinition` distincts pour chaque attribut et attachez‑les aux ressources ou aux tâches souhaitées.

**Q : Quels formats puis‑je utiliser pour enregistrer le projet ?**  
A : Aspose.Tasks prend en charge XML, MPP, PDF, HTML et plus de 30 formats supplémentaires. Dans cet exemple, nous avons utilisé `SaveFileFormat.Xml`.

**Q : Ai‑je besoin d'une licence pour les builds de développement ?**  
A : Une licence d'évaluation temporaire suffit pour les tests. Pour tout déploiement en production, une licence commerciale complète est requise.

**Q : Comment lire ultérieurement les valeurs des attributs personnalisés ?**  
A : Appelez `resource.getExtendedAttributes()` et parcourez la collection ; récupérez la valeur stockée avec `getNumericValue()` ou `getTextValue()`.

---

**Dernière mise à jour:** 2026-06-10  
**Testé avec:** Aspose.Tasks for Java 24.12  
**Auteur:** Aspose

## Tutoriels associés

- [Comment créer des ressources – Gestion des ressources avec Aspose.Tasks pour Java](/tasks/java/resource-management/)
- [Créer un champ personnalisé Aspose - Gérer les attributs étendus](/tasks/java/project-management/extended-attributes/)
- [Comment créer un projet – Définir de nouveaux attributs de tâche avec Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}