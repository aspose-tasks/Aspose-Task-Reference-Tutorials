---
date: 2026-02-13
description: Apprenez à générer un rapport de projet en créant un objet projet en
  Java, en ajoutant des attributs étendus et en utilisant des fonctions d’évaluation
  avec Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Générer le rapport de projet – Créer l'objet projet Java
url: /fr/java/formulas/evaluation-functions/
weight: 10
---

 dashboards, or automated scheduling tools—all powered by Aspose.Tasks for Java."

Translate.

- "Last Updated:" keep date.

- "Tested With:" keep.

- "Author:" keep.

- End shortcodes.

Make sure to keep all markdown formatting.

Now produce final output with same shortcodes at top and bottom.

Let's craft.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Prise en charge des fonctions d'évaluation dans les formules Aspose.Tasks

## Introduction
Aspose.Tasks for Java vous permet de **generate project report** en créant un **project object** en Java et en évaluant les fonctions Microsoft Project directement dans votre code. En incorporant ces formules, vous pouvez exécuter des calculs sophistiqués, générer des rapports personnalisés et automatiser l’analyse de projet sans quitter votre environnement de développement. Dans ce tutoriel, nous parcourrons la création d’un objet projet, l’ajout d’un attribut étendu et l’utilisation des fonctions d’évaluation pour **add custom field task** des données.

## Réponses rapides
- **Que signifie « create project object java » ?** Il crée une instance `Project` en mémoire que vous pouvez manipuler programmatiquement.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (télécharger depuis le site officiel).  
- **Ai-je besoin d’une licence ?** Une licence temporaire ou complète d’Aspose.Tasks est requise pour une utilisation en production ; un essai gratuit est disponible.  
- **Puis-je utiliser des champs personnalisés ?** Oui – vous pouvez **add extended attribute** aux tâches et les traiter comme des champs personnalisés.  
- **Est‑ce compatible avec tous les formats de fichiers Project ?** Aspose.Tasks prend en charge les formats MPP, MPT et XML.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Environnement de développement Java** – JDK 8+ et un IDE tel qu’IntelliJ IDEA ou Eclipse.  
2. **Bibliothèque Aspose.Tasks for Java** – Téléchargez et incluez la bibliothèque depuis la [page de téléchargement Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importer les packages
Ajoutez l’espace de noms Aspose.Tasks à votre classe Java afin de pouvoir travailler avec les projets, les tâches et les attributs étendus :

```java
import com.aspose.tasks.*;
```

## Générer un rapport de projet – Créer un objet projet Java
Instanciez un nouvel objet `Project`. Il servira de conteneur pour toutes les tâches, ressources et données personnalisées que vous définirez.

```java
Project project = new Project();
```

La ligne ci‑dessus **creates project object java** qui commence vide et prête à être personnalisée.

## Comment ajouter un attribut étendu
Définissez un attribut étendu qui stockera des données numériques personnalisées (par ex., une valeur de sinus) pour chaque tâche.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Ici nous **add extended attribute** de type `Number` nommé « Sine » et l’associons aux tâches.

## Ajouter l’attribut étendu au projet
Enregistrez la définition de l’attribut dans le projet afin que chaque tâche puisse y faire référence.

```java
project.getExtendedAttributes().add(attr);
```

## Créer une nouvelle tâche
Ajoutez une tâche simple nommée « Task » sous la tâche racine du projet.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Associer l’attribut étendu à la tâche
Liez l’attribut étendu précédemment défini à la tâche nouvellement créée.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

La tâche possède maintenant un champ personnalisé « Sine » que vous pouvez utiliser dans des formules ou des calculs. C’est également ainsi que vous **add custom field task** des données programmatiquement.

## Pourquoi utiliser les fonctions d’évaluation ?
Intégrer les fonctions MS Project dans les formules Aspose.Tasks vous permet de :

- Effectuer des calculs en temps réel (par ex., `Sin([Start])`) sans outils externes.  
- Conserver toute la logique du projet dans une base de code unique et maintenable.  
- Générer des rapports dynamiques qui reflètent les changements de données en temps réel, vous aidant à **generate project report** automatiquement.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **La formule renvoie `NaN`** | Vérifiez que le type du champ personnalisé correspond au type numérique attendu. |
| **Attribut étendu non visible** | Assurez‑vous que la définition de l’attribut est ajoutée au projet **before** la création des tâches. |
| **Exception de licence** | Installez une licence temporaire ou complète d’**Aspose.Tasks** ; le mode d’essai peut limiter certaines fonctionnalités. |
| **Licence temporaire manquante** | Obtenez une **temporary Aspose license** depuis le site Aspose. |

## Questions fréquentes

**Q : Aspose.Tasks for Java peut‑il gérer des formules MS Project complexes ?**  
R : Oui, Aspose.Tasks for Java prend en charge l’évaluation d’un large éventail de fonctions MS Project, permettant des calculs complexes dans les applications Java.

**Q : Aspose.Tasks for Java est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
R : Oui, Aspose.Tasks for Java prend en charge diverses versions de fichiers Microsoft Project, y compris les formats MPP, MPT et XML.

**Q : Puis‑je essayer Aspose.Tasks for Java avant d’acheter ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.Tasks for Java depuis le site web [here](https://purchase.aspose.com/buy).

**Q : Comment obtenir du support pour Aspose.Tasks for Java ?**  
R : Vous pouvez obtenir du support via le forum communautaire Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q : Une licence temporaire est‑elle disponible pour Aspose.Tasks for Java ?**  
R : Oui, vous pouvez obtenir une licence temporaire pour les tests depuis le site Aspose [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
En suivant ces étapes, vous avez appris comment **create project object**, **add extended attribute**, et exploiter les fonctions d’évaluation pour **generate project report** automatiquement. Vous pouvez maintenant étendre cette base pour créer des analyses de projet plus riches, des tableaux de bord personnalisés ou des outils de planification automatisés—tout cela propulsé par Aspose.Tasks for Java.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}