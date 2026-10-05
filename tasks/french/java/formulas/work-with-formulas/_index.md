---
date: 2026-10-05
description: Apprenez comment créer un projet de test et calculer le nombre de jours
  entre les dates en utilisant Aspose.Tasks for Java, ajouter un custom field et manipuler
  les fichiers MPP efficacement.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Travailler avec les formules dans Aspose.Tasks
og_description: Créer un projet de test et calculer le nombre de jours entre les dates
  en utilisant Aspose.Tasks for Java. Ce guide montre comment ajouter un custom field,
  définir les task deadlines et enregistrer le projet en tant que fichier MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Créer un projet de test et calculer le nombre de jours entre les dates
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Créer un projet de test et calculer le nombre de jours entre les dates
url: /fr/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un projet de test et calculer les jours entre les dates

Dans ce tutoriel, vous **créerez un projet de test** et **calculerez les jours entre les dates** en ajoutant un champ personnalisé, en définissant un attribut étendu et en appliquant une formule Microsoft Project via la bibliothèque Aspose.Tasks pour Java. Que vous ayez besoin de générer des plannings, de calculer des échéances ou d’automatiser des rapports, Aspose.Tasks vous permet de manipuler les données de Project de manière programmatique sans installation de bureau, prenant en charge plus de 50 formats d’entrée et de sortie et gérant des fichiers de plusieurs centaines de pages en mode mémoire efficace.

## Réponses rapides
- **Quel est le contenu du tutoriel ?** Il montre comment créer un projet de test, définir un attribut étendu, définir une date limite pour une tâche et utiliser une formule pour calculer les jours entre les dates.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks for Java (latest version).  
- **Ai-je besoin d’une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour une utilisation en production.  
- **Quel IDE puis‑je utiliser ?** Tout IDE Java (IntelliJ IDEA, Eclipse, VS Code) qui prend en charge JDK 8+.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour copier le code et l’exécuter.

## Qu’est‑ce que « calculate days between dates » dans Aspose.Tasks ?
Dans Aspose.Tasks, une formule est une chaîne qui peut référencer des champs de tâche et effectuer des calculs. `[Deadline] - [Finish]` est la syntaxe de formule qu’Aspose.Tasks utilise pour renvoyer la différence numérique en jours entre deux champs de date. Le résultat est stocké sous forme de valeur numérique représentant des jours entiers, que vous pouvez afficher dans un champ personnalisé ou utiliser dans d’autres calculs.

## Pourquoi utiliser Aspose.Tasks pour calculer les jours entre les dates ?
Aspose.Tasks offre une **couverture complète de l’API** pour chaque propriété de Project, Task et Resource, fonctionne sous Windows, Linux et macOS, et **ne nécessite pas Microsoft Project ou Office** installé. Le moteur peut traiter des projets contenant **plus de 500 tâches** en moins d’une seconde sur du matériel serveur typique, ce qui le rend idéal pour les pipelines CI, les conteneurs Docker et le traitement par lots à haut volume.

## Comment définir une date limite pour une tâche
java.util.Calendar est une classe Java qui représente un moment précis dans le temps. Vous définissez une date limite en assignant une valeur `java.util.Calendar` au champ `Tsk.DEADLINE` d’une tâche. Après avoir créé l’instance Calendar, définissez son année, mois et jour à la date limite souhaitée, puis appelez `task.set(Tsk.DEADLINE, calendar);`. La date limite est stockée dans le fichier de projet et peut être utilisée dans des formules telles que `[Deadline] - [Finish]`.

## Comment définir un attribut étendu
Un attribut étendu est un champ personnalisé qui stocke le résultat de votre formule. Vous le créez une fois, lui attribuez un alias convivial et y attachez l’expression `[Deadline] - [Finish]` afin que chaque tâche puisse calculer automatiquement l’intervalle. Créez‑le en instanciant `ExtendedAttribute`, en définissant son Alias, en assignant la formule, puis en l’ajoutant à la collection du projet.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

- **Java Development Kit (JDK) 8+** – téléchargez depuis le site d’Oracle ou adoptez OpenJDK.  
- **Aspose.Tasks for Java** – obtenez le dernier JAR depuis la [page de téléchargement Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) et ajoutez‑le au classpath de votre projet ou aux dépendances Maven/Gradle.

## Importer les packages
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guide étape par étape

### Étape 1 : Créer un projet de test avec un champ personnalisé
Nous commençons par **créer un projet de test** et ajouter un champ personnalisé qui contiendra ensuite le résultat de notre formule.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Astuce :* `CreateTestProjectWithCustomField()` est une méthode d’assistance qui construit un planning minimal et enregistre un attribut étendu prêt pour l’affectation de formule.

### Étape 2 : Définir un attribut étendu (ajouter un champ personnalisé)
Ensuite, nous **définissons un attribut étendu** – essentiellement le champ personnalisé – et lui attribuons un alias convivial. C’est ici que nous **ajoutons la logique du champ personnalisé**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** rend le champ lisible dans Project.  
- **Formula** calcule le nombre de jours entre la date *Finish* d’une tâche et sa *Deadline* – le cœur de *calculate days between dates*.

### Étape 3 : Définir la date limite pour une tâche (ajouter une tâche de date limite & définir la date limite de la tâche)
Nous **ajoutons maintenant les données de tâche de date limite** en définissant la propriété *Deadline* sur une tâche spécifique.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- L’instance `Calendar` définit le moment exact de la date limite.  
- `set(Tsk.DEADLINE, …)` **définit la date limite de la tâche** pour la tâche choisie.

### Étape 4 : Enregistrer le projet (manipuler le fichier Microsoft Project)
Enfin, nous **manipulons Microsoft Project** en enregistrant les modifications dans un fichier MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Vous pouvez ouvrir `SaveFile.mpp` dans Microsoft Project pour voir le champ personnalisé, le résultat de la formule et la date limite reflétés dans le planning.

## Problèmes courants et solutions
| Issue | Solution |
|-------|----------|
| **Formule ne s’évalue pas** | Assurez‑vous que la chaîne `Formula` de l’attribut utilise les noms de champs corrects (par ex., `[Deadline]`, `[Finish]`). |
| **Tâche non trouvée** | Vérifiez que l’ID de la tâche (`1` dans l’exemple) existe ; utilisez `project.getRootTask().getChildren().size()` pour déboguer. |
| **Exception de licence** | Appliquez une licence Aspose.Tasks valide avant d’appeler toute méthode API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
A: Oui, Aspose.Tasks fournit des API pour .NET, Java et d’autres plateformes, vous permettant de manipuler les fichiers Microsoft Project dans le langage de votre choix.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Tasks ?**  
A: Absolument. Téléchargez un essai pleinement fonctionnel depuis la [page de téléchargement Aspose.Tasks](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks ?**  
A: La documentation officielle est hébergée sur [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q : Comment puis‑je obtenir du support pour Aspose.Tasks ?**  
A: Visitez le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour poser des questions et partager des expériences avec la communauté.

**Q : Ai‑je besoin d’une licence temporaire pour l’évaluation ?**  
A: Une licence temporaire est disponible pour des tests à court terme ; vous pouvez en demander une depuis la [page de demande de licence temporaire](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-10-05  
**Testé avec :** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un fichier MPP – Créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Définir la date de début du projet dans MS Project en utilisant Aspose.Tasks pour Java](/tasks/java/project-properties/write-project-info/)
- [Comment créer un attribut étendu en Java avec Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}