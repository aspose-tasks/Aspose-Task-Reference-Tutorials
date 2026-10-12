---
date: 2026-10-10
description: Apprenez comment ajouter un attribut étendu dans Aspose.Tasks, utiliser
  les fonctions d'évaluation et générer des rapports de projet avec cette bibliothèque
  de gestion de projet Java.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Prise en charge des fonctions d'évaluation dans les formules Aspose.Tasks
og_description: Apprenez comment ajouter un attribut étendu dans Aspose.Tasks, utiliser
  les fonctions d'évaluation et générer des rapports de projet avec cette bibliothèque
  de gestion de projet Java.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Comment ajouter un attribut étendu dans les formules Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Comment ajouter un attribut étendu dans les formules Aspose.Tasks
url: /fr/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un attribut étendu dans les formules Aspose.Tasks

## Introduction
Aspose.Tasks for Java est une **bibliothèque de gestion de projet Java** qui vous permet de générer des rapports de projet en créant un objet `Project` en Java et en évaluant les fonctions Microsoft Project directement dans votre code. En intégrant ces formules, vous pouvez effectuer des calculs sophistiqués, générer des rapports personnalisés et automatiser l’analyse de projet sans quitter votre environnement de développement. Dans ce tutoriel, nous parcourrons la création d’un objet projet, l’ajout d’un attribut étendu et l’utilisation des fonctions d’évaluation pour **ajouter des données de champ personnalisé aux tâches**.

## Réponses rapides
- **Que signifie « create project object java » ?** Cela crée une instance `Project` en mémoire que vous pouvez manipuler programmatiquement.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (téléchargez‑la depuis le site officiel).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète Aspose.Tasks est requise pour une utilisation en production ; une version d’essai gratuite est disponible.  
- **Puis‑je utiliser des champs personnalisés ?** Oui – vous pouvez **ajouter un attribut étendu** aux tâches et les traiter comme des champs personnalisés.  
- **Cette solution est‑elle compatible avec tous les formats de fichiers Project ?** Aspose.Tasks prend en charge les 3 formats majeurs (MPP, MPT, XML) et plus de 50 formats d’entrée/sortie supplémentaires.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Environnement de développement Java** – JDK 8+ et un IDE tel qu’IntelliJ IDEA ou Eclipse.  
2. **Bibliothèque Aspose.Tasks for Java** – Téléchargez et incluez la bibliothèque depuis la [page de téléchargement Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importer les packages
Ajoutez l’espace de noms Aspose.Tasks à votre classe Java afin de pouvoir travailler avec les projets, les tâches et les attributs étendus :

```java
import com.aspose.tasks.*;
```

## Générer un rapport de projet – créer un objet projet java
La classe `Project` représente un fichier Microsoft Project en mémoire, exposant les tâches, les ressources et les données personnalisées. Instancier cette classe vous fournit un conteneur pour tous les éléments du projet que vous définirez.

```java
Project project = new Project();
```

La ligne ci‑dessus **crée un objet projet java** qui commence vide et prêt à être personnalisé.

## Comment ajouter un attribut étendu
La classe `ExtendedAttributeDefinition` définit un champ personnalisé qui peut être attaché aux tâches. Pour ajouter un attribut étendu, créez une instance de cette classe avec le type `Number`, attribuez‑lui un alias tel que « Sine », ajoutez‑la à la collection `ExtendedAttributes` du projet, puis liez‑la à chaque tâche qui nécessite le champ personnalisé.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Ici nous **ajoutons un attribut étendu** de type `Number` nommé « Sine » et l’associons aux tâches.

## Ajouter l’attribut étendu au projet
Enregistrez la définition de l’attribut dans le projet afin que chaque tâche puisse s’y référer.

```java
project.getExtendedAttributes().add(attr);
```

## Créer une nouvelle tâche
`Task` représente un élément de travail dans le projet et peut contenir des champs personnalisés.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Ajouter un champ personnalisé à la tâche du projet
Liez l’attribut étendu précédemment défini à la tâche nouvellement créée, donnant à la tâche un champ personnalisé « Sine » que vous pouvez utiliser dans des formules ou des calculs.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Désormais la tâche possède un champ personnalisé « Sine » que vous pouvez exploiter dans des formules ou des calculs. C’est également ainsi que vous **ajoutez des données de champ personnalisé aux tâches** de façon programmatique.

## Pourquoi utiliser les fonctions d’évaluation ?
Les fonctions d’évaluation vous permettent d’intégrer des formules natives Microsoft Project (par ex., `Sin([Start])`) directement dans Aspose.Tasks, permettant des calculs en temps réel sans traitement externe. Cela centralise toute la logique du projet, réduit les erreurs de synchronisation des données et accélère la génération de rapports. Aspose.Tasks prend en charge l’évaluation de plus de 100 fonctions MS Project, offrant un moteur de calcul complet dans Java.

## Problèmes courants et solutions
| Problème | Solution |
|-------|----------|
| **La formule renvoie `NaN`** | Vérifiez que le type du champ personnalisé correspond au type numérique attendu. |
| **L’attribut étendu n’est pas visible** | Assurez‑vous que la définition de l’attribut est ajoutée au projet **avant** la création des tâches. |
| **Exception de licence** | Installez une licence temporaire ou complète **Aspose.Tasks** ; le mode d’essai peut limiter certaines fonctionnalités. |
| **Licence temporaire manquante** | Obtenez une **licence temporaire Aspose** depuis le site Aspose. |

## Questions fréquemment posées

**Q : Aspose.Tasks for Java peut‑il gérer des formules MS Project complexes ?**  
R : Oui, Aspose.Tasks for Java prend en charge l’évaluation d’un large éventail de fonctions MS Project, permettant des calculs complexes au sein d’applications Java.

**Q : Aspose.Tasks for Java est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Oui, Aspose.Tasks for Java supporte diverses versions de fichiers Microsoft Project, y compris les formats MPP, MPT et XML.

**Q : Puis‑je essayer Aspose.Tasks for Java avant d’acheter ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.Tasks for Java depuis la page [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q : Comment obtenir du support pour Aspose.Tasks for Java ?**  
R : Vous pouvez obtenir de l’aide sur le forum communautaire Aspose.Tasks : [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q : Existe‑t‑il une licence temporaire disponible pour Aspose.Tasks for Java ?**  
R : Oui, vous pouvez obtenir une licence temporaire à des fins de test depuis le site Aspose : [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Conclusion
En suivant ces étapes, vous avez appris à **créer un objet projet**, **ajouter un attribut étendu** et à exploiter les fonctions d’évaluation pour **générer automatiquement un rapport de projet**. Vous pouvez maintenant étendre cette base pour créer des analyses de projet plus riches, des tableaux de bord personnalisés ou des outils de planification automatisés—tout cela propulsé par Aspose.Tasks for Java.

---

**Dernière mise à jour :** 2026-10-10  
**Testé avec :** Aspose.Tasks for Java 24.10  
**Auteur :** Aspose

## Tutoriels associés

- [Colonnes personnalisées et attributs étendus en gestion de projet Java](/tasks/java/project-management/extended-attributes/)
- [Lire les attributs de tâche étendus avec Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [Comment utiliser Aspose.Tasks for Java – Ajouter des attributs étendus aux affectations de ressources](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}