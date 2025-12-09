---
date: 2025-12-09
description: Apprenez à créer un objet projet Java et à prendre en charge les fonctions
  d’évaluation dans les formules Aspose.Tasks en utilisant Java. Découvrez comment
  créer un attribut étendu pour les tâches.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Créer un objet de projet Java – Prise en charge des fonctions d'évaluation
  dans Aspose.Tasks
url: /fr/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Prise en charge des fonctions d'évaluation dans les formules Aspose.Tasks

## Introduction
Aspose.Tasks for Java vous permet de **create project object java** des instances et d'évaluer les fonctions Microsoft Project directement dans votre code Java. En intégrant ces formules, vous pouvez effectuer des calculs sophistiqués, générer des rapports personnalisés et automatiser l'analyse de projet sans quitter votre environnement de développement. Ce tutoriel vous guide à travers l'ensemble du processus — depuis la configuration de l'objet projet jusqu'à l'ajout d'un attribut étendu pouvant contenir des données personnalisées.

## Réponses rapides
- **Que signifie “create project object java” ?** Il crée une instance `Project` en mémoire que vous pouvez manipuler par programme.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (téléchargez depuis le site officiel).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production ; une version d’essai gratuite est disponible.  
- **Puis‑je utiliser des champs personnalisés ?** Oui – vous pouvez définir et attacher des attributs étendus aux tâches.  
- **Cette fonctionnalité est‑elle compatible avec tous les formats de fichiers Project ?** Aspose.Tasks prend en charge les formats MPP, MPT et XML.

## Prérequis
Avant de commencer, assurez-vous d'avoir :

1. **Environnement de développement Java** – JDK 8+ et un IDE tel qu'IntelliJ IDEA ou Eclipse.  
2. **Bibliothèque Aspose.Tasks for Java** – Téléchargez et incluez la bibliothèque depuis la [page de téléchargement d'Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importer les packages
Ajoutez l'espace de noms Aspose.Tasks à votre classe Java afin de pouvoir travailler avec les projets, les tâches et les attributs étendus :

```java
import com.aspose.tasks.*;
```

## Étape 1 : Créer un Project Object Java
Instanciez un nouvel objet `Project`. Celui‑ci servira de conteneur pour toutes les tâches, ressources et données personnalisées que vous définirez.

```java
Project project = new Project();
```

La ligne ci‑dessus **creates project object java** qui commence vide et prête à être personnalisée.

## Étape 2 : Comment créer un attribut étendu
Définissez un attribut étendu qui stockera des données numériques personnalisées (par ex., une valeur de sinus) pour chaque tâche.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Ici nous **create extended attribute** de type `Number` nommé « Sine » et l’associons aux tâches.

## Étape 3 : Ajouter l'attribut étendu au projet
Enregistrez la définition de l'attribut dans le projet afin que chaque tâche puisse s'y référer.

```java
project.getExtendedAttributes().add(attr);
```

## Étape 4 : Créer une nouvelle tâche
Ajoutez une tâche simple nommée « Task » sous la tâche racine du projet.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Étape 5 : Associer l'attribut étendu à la tâche
Liez l'attribut étendu précédemment défini à la tâche nouvellement créée.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

La tâche possède désormais un champ personnalisé « Sine » que vous pouvez utiliser dans des formules ou des calculs.

## Pourquoi utiliser les fonctions d'évaluation ?
Intégrer les fonctions MS Project dans les formules Aspose.Tasks vous permet de :
- Effectuer des calculs en temps réel (par ex., `Sin([Start])`) sans outils externes.  
- Conserver toute la logique du projet dans une base de code unique et maintenable.  
- Générer des rapports dynamiques reflétant les changements de données en temps réel.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **La formule renvoie `NaN`** | Vérifiez que le type du champ personnalisé correspond au type numérique attendu. |
| **L'attribut étendu n'est pas visible** | Assurez‑vous que la définition de l'attribut est ajoutée au projet **avant** de créer les tâches. |
| **Exception de licence** | Installez une licence temporaire ou complète ; le mode d'essai peut limiter certaines fonctionnalités. |

## Questions fréquemment posées

**Q : Aspose.Tasks for Java peut‑il gérer des formules MS Project complexes ?**  
A : Oui, Aspose.Tasks for Java prend en charge l'évaluation d'un large éventail de fonctions MS Project, permettant des calculs complexes au sein des applications Java.

**Q : Aspose.Tasks for Java est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
A : Oui, Aspose.Tasks for Java prend en charge diverses versions de fichiers Microsoft Project, y compris les formats MPP, MPT et XML.

**Q : Puis‑je essayer Aspose.Tasks for Java avant d'acheter ?**  
A : Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks for Java depuis le site web [ici](https://purchase.aspose.com/buy).

**Q : Comment obtenir du support pour Aspose.Tasks for Java ?**  
A : Vous pouvez obtenir du support sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Existe‑t‑il une licence temporaire disponible pour Aspose.Tasks for Java ?**  
A : Oui, vous pouvez obtenir une licence temporaire à des fins de test depuis le site Aspose [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2025-12-09  
**Testé avec :** Aspose.Tasks for Java 24.10  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}