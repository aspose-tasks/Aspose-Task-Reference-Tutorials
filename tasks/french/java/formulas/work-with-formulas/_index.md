---
date: 2026-02-13
description: Apprenez à calculer le nombre de jours entre des dates, à créer un projet
  de test et à ajouter un champ personnalisé tout en manipulant des fichiers Microsoft
  Project à l’aide d’Aspose.Tasks pour Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Calculer le nombre de jours entre les dates avec Aspose.Tasks pour Java
url: /fr/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calculer les jours entre des dates avec Aspose.Tasks pour Java

## Introduction
Dans ce tutoriel, vous **calculerez les jours entre des dates** en créant un projet de test, en ajoutant un champ personnalisé et en utilisant les formules de Microsoft Project via la bibliothèque Aspose.Tasks pour Java. Que vous ayez besoin de générer des plannings, de calculer des échéances ou d’automatiser des rapports, Aspose.Tasks vous permet de manipuler les données d’un projet de façon programmatique sans installation de bureau. À la fin du guide, vous disposerez d’un exemple exécutable qui définit un attribut étendu, fixe une date limite pour une tâche et enregistre le projet au format MPP.

## Quick Answers
- **Que couvre le tutoriel ?** Création d’un projet de test, ajout d’un champ personnalisé, définition d’un attribut étendu et définition d’une date limite de tâche avec une formule pour calculer les jours entre des dates.  
- **Quelle bibliothèque est requise ?** Aspose.Tasks pour Java (dernière version).  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence est requise en production.  
- **Quel IDE puis‑je utiliser ?** Tout IDE Java (IntelliJ IDEA, Eclipse, VS Code) supportant JDK 8+.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour copier le code et l’exécuter.

## Qu’est‑ce que « calculate days between dates » dans Aspose.Tasks ?
Calculer les jours entre des dates signifie utiliser une formule de projet qui soustrait un champ de date (par ex., **Finish**) d’un autre (par ex., **Deadline**) et renvoie la différence numérique en jours. Cela est utile pour suivre les écarts de planning, mesurer le temps tampon ou générer des rapports personnalisés.

## Pourquoi utiliser Aspose.Tasks pour calculer les jours entre des dates ?
- **Couverture complète de l’API** – accès à chaque propriété de Project, Task et Resource.  
- **Pas d’installation d’Office requise** – fonctionne sur serveurs, pipelines CI et conteneurs Docker.  
- **Multiplateforme** – s’exécute sur Windows, Linux et macOS avec le même code Java.  
- **Moteur de formules robuste** – vous permet de définir des calculs tels que `[Deadline] - [Finish]` directement dans le fichier de projet.

## Comment définir une date limite pour une tâche
Définir une date limite est la première étape avant de pouvoir calculer l’intervalle. La date limite est stockée dans le champ `Tsk.DEADLINE` d’une tâche et peut être assignée à l’aide d’une instance `java.util.Calendar`.

## Comment définir un attribut étendu
Un attribut étendu est le champ personnalisé qui contiendra le résultat de votre formule. Vous le définissez une fois, lui attribuez un alias pour la lisibilité, puis y attachez une formule qui effectue la soustraction de dates.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

- **Java Development Kit (JDK) 8+** – téléchargez‑le depuis le site d’Oracle ou adoptez OpenJDK.  
- **Aspose.Tasks pour Java** – obtenez le dernier JAR depuis la [page de téléchargement Aspose.Tasks pour Java](https://releases.aspose.com/tasks/java/) et ajoutez‑le au classpath de votre projet ou aux dépendances Maven/Gradle.

## Import Packages
Tout d’abord, importez les classes dont nous aurons besoin :

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guide étape par étape

### Étape 1 : Créer un projet de test avec un champ personnalisé
Nous commençons par **créer un projet de test** et ajouter un champ personnalisé qui contiendra plus tard le résultat de notre formule.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Astuce :* `CreateTestProjectWithCustomField()` est une méthode d’assistance qui construit un planning minimal et enregistre un attribut étendu prêt à recevoir une formule.

### Étape 2 : Définir un attribut étendu (Ajouter un champ personnalisé)
Ensuite, nous **définissons un attribut étendu** – essentiellement le champ personnalisé – et lui attribuons un alias convivial. C’est ici que nous **ajoutons la logique du champ personnalisé**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** rend le champ lisible dans Project.  
- **Formula** calcule le nombre de jours entre la date *Finish* d’une tâche et sa *Deadline* – le cœur de *calculate days between dates*.

### Étape 3 : Définir la date limite d’une tâche (Ajouter la tâche Deadline & définir la date limite)
Nous **ajoutons les données de la tâche deadline** en définissant la propriété *Deadline* sur une tâche spécifique.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- L’instance `Calendar` définit le moment exact de la date limite.  
- `set(Tsk.DEADLINE, …)` **définit la date limite de la tâche** pour la tâche choisie.

### Étape 4 : Enregistrer le projet (Manipuler le fichier Microsoft Project)
Enfin, nous **manipulons Microsoft Project** en persistant les modifications dans un fichier MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Vous pouvez ouvrir `SaveFile.mpp` dans Microsoft Project pour voir le champ personnalisé, le résultat de la formule et la date limite reflétés dans le planning.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **La formule ne s’évalue pas** | Vérifiez que la chaîne `Formula` de l’attribut utilise les bons noms de champ (par ex., `[Deadline]`, `[Finish]`). |
| **Tâche introuvable** | Assurez‑vous que l’ID de tâche (`1` dans l’exemple) existe ; utilisez `project.getRootTask().getChildren().size()` pour déboguer. |
| **Exception de licence** | Appliquez une licence Aspose.Tasks valide avant d’appeler toute méthode API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## FAQ

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks propose des API pour .NET, Java et d’autres plateformes, vous permettant de **manipuler des fichiers Microsoft Project** dans le langage de votre choix.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Tasks ?**  
R : Absolument. Téléchargez un essai pleinement fonctionnel depuis la [page de téléchargement Aspose.Tasks](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks ?**  
R : La documentation officielle est hébergée sur [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q : Comment obtenir du support pour Aspose.Tasks ?**  
R : Rendez‑vous sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour poser vos questions et partager vos expériences avec la communauté.

**Q : Ai‑je besoin d’une licence temporaire pour l’évaluation ?**  
R : Une licence temporaire est disponible pour les tests à court terme ; vous pouvez en demander une [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-02-13  
**Testé avec :** Aspose.Tasks pour Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}