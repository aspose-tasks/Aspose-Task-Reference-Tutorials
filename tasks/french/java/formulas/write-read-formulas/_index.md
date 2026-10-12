---
date: 2026-10-10
description: Apprenez comment créer un champ personnalisé aspose en Java, appliquer
  une formule double du coût de tâche, et enregistrer le fichier de projet en utilisant
  Aspose.Tasks. Inclut la lecture des formules MS Project.
keywords:
- create custom field aspose
- double task cost formula
- add custom field formula
- calculate task cost
lastmod: 2026-10-10
linktitle: Exemple de formule de champ personnalisé – Enregistrer le fichier de projet
og_description: Apprenez comment créer un champ personnalisé aspose en Java, appliquer
  une formule double du coût de tâche, et enregistrer le fichier de projet en utilisant
  Aspose.Tasks. Inclut la lecture des formules MS Project.
og_image_alt: 'Guide: create custom field aspose and save project file with Aspose.Tasks
  Java'
og_title: Comment créer un champ personnalisé aspose et enregistrer le fichier de
  projet
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  headline: How to create custom field aspose and save project file
  type: TechArticle
- description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  name: How to create custom field aspose and save project file
  steps:
  - name: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
    text: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
  - name: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
    text: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of MS Project versions, from older
      .mpp formats to the latest releases, covering over 30 file format variations.
    question: Is Aspose.Tasks compatible with all versions of MS Project?
  - answer: Absolutely. The API is designed for seamless integration; just add the
      Aspose.Tasks JAR to your project’s classpath and start using the `Project` class.
    question: Can I integrate Aspose.Tasks into my existing Java project?
  - answer: The library supports most native MS Project formula syntax, including
      arithmetic, logical, and built‑in functions. Complex custom functions may require
      workarounds, but common calculations like **double task cost formula** work
      out of the box.
    question: Are there any limitations to the types of formulas I can create?
  - answer: Yes, the library runs on any platform that supports Java, including Windows,
      Linux, and macOS, and can handle projects up to 2 GB without loading the entire
      file into memory.
    question: Does Aspose.Tasks support multi‑platform deployment?
  - answer: Visit the [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)
      for community help, or open a support ticket if you have a commercial license.
    question: How can I get technical support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- custom field
- Aspose.Tasks
- Java project automation
title: Comment créer un champ personnalisé aspose et enregistrer le fichier de projet
url: /fr/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un champ personnalisé aspose et enregistrer le fichier de projet

## Introduction
Dans ce tutoriel, vous verrez un **exemple de formule de champ personnalisé** qui montre comment **enregistrer un fichier de projet**, écrire et lire des formules MS Project, et appliquer une **formule de double coût de tâche** en utilisant Aspose.Tasks pour Java. À la fin, vous comprendrez pourquoi les champs personnalisés sont puissants, comment intégrer des calculs directement dans un projet, et comment conserver ces modifications pour des rapports ultérieurs. L'objectif principal est **create custom field aspose** afin que vous puissiez automatiser les calculs de coûts dans tout flux de travail basé sur MS Project‑based workflow.

## Réponses rapides
- **What does “save project file” do?** Il écrit toutes les modifications en mémoire dans un fichier .mpp sur le disque.  
- **Can I add custom field formulas?** Oui – vous pouvez créer un champ personnalisé et attribuer une formule telle que « double task cost ».  
- **Do I need a license to run the code?** Un essai gratuit suffit pour l'évaluation ; une licence commerciale est requise pour la production.  
- **Which IDE works best?** Tout IDE Java (IntelliJ IDEA, Eclipse, VS Code) compilera l'exemple.  
- **Is the API compatible with the latest MS Project version?** Aspose.Tasks prend en charge tous les formats .mpp récents.

## Qu’est‑ce que “save project file” dans Aspose.Tasks ?
Enregistrer un fichier de projet signifie préserver l'état actuel de l'objet `Project` — y compris les tâches, les ressources et toutes les formules personnalisées — dans un fichier Microsoft Project physique (`.mpp`). Cette opération est essentielle après avoir modifié des données, comme l'ajout d'un champ personnalisé ou la modification des coûts des tâches. L'appel `save` écrit la structure complète du projet sur le disque, rendant les modifications disponibles pour les outils de reporting en aval.

## Pourquoi ajouter un champ personnalisé et créer une formule de champ personnalisé ?
Vous ajoutez un champ personnalisé lorsque vous devez stocker des informations que les champs intégrés ne couvrent pas. Attacher une formule — comme une **double task cost formula** — automatise les calculs, élimine les mises à jour manuelles et garantit que chaque fois que le coût de base change, la valeur dérivée se met à jour instantanément. Cette approche réduit les erreurs et maintient vos données de planification cohérentes entre les équipes.

## Prérequis
1. **Java Development Kit (JDK)** – Java 8 ou supérieur installé sur votre machine.  
2. **Aspose.Tasks for Java** – Téléchargez et installez depuis la [page de téléchargement Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Choisissez votre IDE préféré pour le développement Java (IntelliJ IDEA, Eclipse, VS Code, etc.).  

## Importation des packages
Les classes `Project`, `ExtendedAttribute` et les classes associées se trouvent dans l'espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier source afin que le compilateur puisse résoudre les types.

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Étape 1 : configurer le répertoire de données
Définissez le dossier où résident vos fichiers MS Project. C’est ici que vous chargerez le fichier source et, plus tard, **save project file**.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## Étape 2 : charger le fichier de projet
La classe `Project` représente un fichier Microsoft Project en mémoire, offrant un accès aux tâches, aux ressources et aux champs personnalisés. Charger le fichier vous fournit un modèle d’objet manipulable.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Étape 3 : ajouter un champ personnalisé et créer une formule de champ personnalisé
Dans cette étape nous **add a custom field** “Double Costs” et **create a custom field formula** qui multiplie le `[Cost]` de la tâche par 2, implémentant ainsi une **double task cost formula**. La méthode `setFormula` intègre le calcul directement dans le fichier de projet.

```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```

## Étape 4 : ajouter une tâche et définir le coût
Créez une nouvelle tâche, puis attribuez un coût de base de `100`. Lorsque le projet est enregistré, le champ personnalisé affichera automatiquement `200` grâce à la formule définie précédemment.

```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```

## Étape 5 : enregistrer le fichier de projet
La méthode `save` écrit le projet mis à jour, incluant le nouveau champ personnalisé et ses valeurs calculées, dans `saved.mpp`. Cela persiste les changements **create custom field aspose** pour tout consommateur en aval.

```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Formule non appliquée** | Le champ personnalisé n'a pas été ajouté à la collection `ExtendedAttributes` du projet. | Assurez‑vous que `project.getExtendedAttributes().add(attr);` est exécuté avant l'enregistrement. |
| **Fichier non trouvé** | Chemin `dataDir` incorrect. | Vérifiez que la chaîne du répertoire se termine par un séparateur de chemin (`/` ou `\\`). |
| **Le coût apparaît comme 0** | Le coût de la tâche n'est pas défini avant l'enregistrement. | Appelez `task.set(Tsk.COST, ...)` avant `project.save`. |

## Questions fréquemment posées
**Q : Aspose.Tasks est‑il compatible avec toutes les versions de MS Project ?**  
R : Oui, Aspose.Tasks prend en charge un large éventail de versions de MS Project, des anciens formats .mpp aux dernières versions, couvrant plus de 30 variantes de formats de fichiers.

**Q : Puis‑je intégrer Aspose.Tasks dans mon projet Java existant ?**  
R : Absolument. L'API est conçue pour une intégration transparente ; il suffit d'ajouter le JAR Aspose.Tasks au classpath de votre projet et de commencer à utiliser la classe `Project`.

**Q : Existe‑t‑il des limitations quant aux types de formules que je peux créer ?**  
R : La bibliothèque prend en charge la plupart des syntaxes de formules natives de MS Project, y compris les fonctions arithmétiques, logiques et intégrées. Les fonctions personnalisées complexes peuvent nécessiter des solutions de contournement, mais les calculs courants comme la **double task cost formula** fonctionnent immédiatement.

**Q : Aspose.Tasks prend‑il en charge le déploiement multiplateforme ?**  
R : Oui, la bibliothèque fonctionne sur toute plateforme supportant Java, y compris Windows, Linux et macOS, et peut gérer des projets jusqu’à 2 GB sans charger le fichier complet en mémoire.

**Q : Comment obtenir le support technique pour Aspose.Tasks ?**  
R : Consultez le [forum communautaire Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l'aide de la communauté, ou ouvrez un ticket de support si vous disposez d'une licence commerciale.

## Conclusion
Dans cet **custom field formula example** nous avons couvert comment **save project file**, **add a custom field**, et **create a double task cost formula** qui double automatiquement le coût de la tâche. En suivant ces étapes, vous pouvez automatiser les calculs, enrichir vos données de projet et garantir que toutes les modifications sont conservées pour les rapports et analyses futurs. La technique **create custom field aspose** est un moyen puissant d'étendre MS Project sans travail manuel sur feuille de calcul.

---

**Dernière mise à jour :** 2026-10-10  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un fichier MPP – Créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Comment créer un projet aspose.tasks – Définir les attributs d’une nouvelle tâche](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Lire les attributs de tâche étendus avec Aspose.Tasks pour Java](/tasks/java/task-properties/extended-task-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}