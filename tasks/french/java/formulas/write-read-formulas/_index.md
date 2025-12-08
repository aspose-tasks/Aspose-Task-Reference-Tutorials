---
date: 2025-12-07
description: Apprenez à enregistrer le fichier de projet, à écrire et lire les formules
  MS Project, et à ajouter des formules de champs personnalisés avec Aspose.Tasks
  pour Java.
language: fr
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Enregistrer le fichier de projet et écrire des formules MS Project avec Aspose.Tasks
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer le fichier de projet et écrire des formules MS Project avec Aspose.Tasks

## Introduction
Dans le domaine de la gestion de projet, la manipulation efficace des données est primordiale. Aspose.Tasks for Java est une solution robuste qui facilite la manipulation et l'extraction de données à partir des fichiers Microsoft Project. Une fonctionnalité puissante qu'elle offre est la capacité d'écrire et de lire des formules MS Project. **Vous apprendrez également à *save project file* après avoir appliqué ces formules**, garantissant que vos modifications sont conservées pour une analyse future. Ce tutoriel vous guidera à travers le processus d'exploitation de cette fonctionnalité pour améliorer vos tâches de gestion de projet.

## Réponses rapides
- **What does “save project file” do?** Il écrit toutes les modifications en mémoire dans un fichier .mpp sur le disque.  
- **Can I add custom field formulas?** Oui – vous pouvez créer un champ personnalisé et attribuer une formule telle que “double task cost”.  
- **Do I need a license to run the code?** Un essai gratuit suffit pour l'évaluation ; une licence commerciale est requise pour la production.  
- **Which IDE works best?** Tout IDE Java (IntelliJ IDEA, Eclipse, VS Code) compilera l'exemple.  
- **Is the API compatible with the latest MS Project version?** Aspose.Tasks prend en charge tous les formats .mpp récents.

## Qu’est‑ce que “save project file” dans Aspose.Tasks ?
Enregistrer un fichier de projet signifie persister l’état actuel de l’objet `Project` — y compris les tâches, les ressources et toutes les formules personnalisées — dans un fichier Microsoft Project physique (`.mpp`). Cette opération est essentielle après avoir modifié des données, comme l’ajout d’un champ personnalisé ou la modification des coûts des tâches.

## Pourquoi ajouter un champ personnalisé et créer une formule de champ personnalisé ?
Ajouter un champ personnalisé vous offre un conteneur flexible pour des informations supplémentaires qui ne sont pas couvertes par les champs par défaut. En associant une formule — comme celle qui **double task cost** — vous automatisez les calculs, réduisez les erreurs manuelles et maintenez la cohérence des données de votre planning.

## Prérequis
1. **Java Development Kit (JDK)** – Java 8 ou supérieur installé sur votre machine.  
2. **Aspose.Tasks for Java** – Téléchargez et installez depuis [here](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Choisissez votre IDE préféré pour le développement Java (IntelliJ IDEA, Eclipse, VS Code, etc.).

## Importation des packages
Pour commencer, importez les packages nécessaires dans votre projet Java :

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Étape 1 : Configurer le répertoire de données
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Définissez le dossier où résident vos fichiers MS Project. C’est ici que vous chargerez le fichier source et où vous **save project file** plus tard.

## Étape 2 : Charger le fichier de projet
```java
Project project = new Project(dataDir + "project.mpp");
```
Chargez le fichier Microsoft Project existant dans un objet `Project` afin de pouvoir lire ou modifier son contenu.

## Étape 3 : Ajouter un champ personnalisé et créer une formule de champ personnalisé
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
Dans cette étape, nous **add custom field** “Double Costs” et **create custom field formula** qui multiplie le `[Cost]` de la tâche par 2, doublant ainsi **double task cost**. La méthode `setFormula` intègre le calcul directement dans le fichier de projet.

## Étape 4 : Ajouter une tâche et définir le coût
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Créez une nouvelle tâche, puis attribuez un coût de base de `100`. Lorsque le projet est enregistré, le champ personnalisé affichera automatiquement `200` grâce à la formule définie précédemment.

## Étape 5 : Enregistrer le fichier de projet
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Enfin, **save project file** avec toutes les modifications. La méthode `save` écrit le projet mis à jour, y compris le nouveau champ personnalisé et ses valeurs calculées, dans `saved.mpp`.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Formula not applied** | Le champ personnalisé n’a pas été ajouté à la collection `ExtendedAttributes` du projet. | Assurez‑vous que `project.getExtendedAttributes().add(attr);` est exécuté avant l’enregistrement. |
| **File not found** | Chemin `dataDir` incorrect. | Vérifiez que la chaîne du répertoire se termine par un séparateur de chemin (`/` ou `\\`). |
| **Cost appears as 0** | Le coût de la tâche n’est pas défini avant l’enregistrement. | Appelez `task.set(Tsk.COST, ...)` avant `project.save`. |

## Questions fréquentes
**Q : Aspose.Tasks est‑il compatible avec toutes les versions de MS Project ?**  
A : Oui, Aspose.Tasks prend en charge une large gamme de versions de MS Project, des anciens formats .mpp aux dernières versions.

**Q : Puis‑je intégrer Aspose.Tasks dans mon projet Java existant ?**  
A : Absolument. L’API est conçue pour une intégration transparente ; il suffit d’ajouter le JAR Aspose.Tasks au classpath de votre projet.

**Q : Existe‑t‑il des limitations quant aux types de formules que je peux créer ?**  
A : La bibliothèque prend en charge la plupart des syntaxes de formules natives de MS Project, y compris les fonctions arithmétiques, logiques et intégrées. Les fonctions personnalisées complexes peuvent nécessiter des solutions de contournement.

**Q : Aspose.Tasks prend‑il en charge le déploiement multiplateforme ?**  
A : Oui, la bibliothèque fonctionne sur toute plateforme supportant Java, y compris Windows, Linux et macOS.

**Q : Comment obtenir le support technique pour Aspose.Tasks ?**  
A : Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l’aide de la communauté, ou ouvrez un ticket de support si vous disposez d’une licence commerciale.

## Conclusion
Dans ce tutoriel, nous avons vu comment **save project file**, **add custom field**, et **create a custom field formula** qui **double task cost** en utilisant Aspose.Tasks for Java. En suivant ces étapes, vous pouvez automatiser les calculs, enrichir les données de votre projet et garantir que toutes les modifications sont conservées pour les rapports et analyses futurs.

**Dernière mise à jour :** 2025-12-07  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}