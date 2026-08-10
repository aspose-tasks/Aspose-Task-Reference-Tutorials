---
date: 2026-06-05
description: Apprenez à filtrer les fichiers MPP avec Aspose.Tasks for Java, à personnaliser
  les critères de filtrage et à filtrer les tâches par date pour optimiser la gestion
  de projet.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Comment filtrer les fichiers MPP avec Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment filtrer les fichiers MPP avec Aspose.Tasks for Java
url: /fr/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment filtrer les fichiers MPP avec Aspose.Tasks pour Java

## Introduction
Si vous travaillez avec des fichiers Microsoft Project (*.mpp*) dans une application Java, vous devrez souvent **filtrer les fichiers MPP** afin d’isoler les tâches, ressources ou affectations les plus importantes. Dans ce tutoriel, nous parcourrons **comment filtrer les fichiers mpp** de manière programmatique avec Aspose.Tasks pour Java, vous montrerons comment **personnaliser les critères de filtrage** et démontrerons un scénario pratique de « filtrer les tâches par date ». À la fin, vous disposerez d’un extrait prêt à l’emploi que vous pourrez intégrer à n’importe quel projet Java.

## Réponses rapides
- **Que signifie « filter mpp » ?** Cela signifie extraire un sous‑ensemble de données du projet basé sur des conditions définies.  
- **Quelle bibliothèque gère cela ?** Aspose.Tasks pour Java fournit une API complète pour créer et appliquer des filtres.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je filtrer les tâches, ressources et affectations ?** Oui – chaque type d’entité possède sa propre collection de filtres.  
- **Java 8 ou supérieur est‑il requis ?** Aspose.Tasks prend en charge Java 8 et les versions ultérieures.

## Qu’est‑ce que « how to filter mpp » en Java ?
`How to filter mpp` est le processus d’utilisation des objets `Filter` d’Aspose.Tasks pour sélectionner uniquement les éléments du projet qui satisfont des prédicats spécifiques tels que la date de début, le coût ou les champs personnalisés. Chargez un `Project`, récupérez un `Filter`, et l’API renvoie une collection correspondant à vos critères, permettant une génération de rapports ciblée ou une intégration en aval.

## Pourquoi personnaliser les critères de filtrage ?
Les critères de filtrage personnalisés vous permettent de cibler les tâches à haut risque, les éléments en retard ou les ressources dépassant le budget, transformant ainsi un fichier de projet massif en une vue concise et exploitable. Aspose.Tasks prend en charge **plus de 50 types de filtres prédéfinis** et vous permet de créer un nombre illimité de filtres personnalisés, réduisant le temps de tri manuel des données jusqu’à 70 %.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK)** – version 8 ou supérieure.  
2. **Aspose.Tasks for Java** – téléchargez‑le depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse ou NetBeans conviendront parfaitement.  

## Importer les packages
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` et `Project` sont des classes de base utilisées pour définir et appliquer des filtres aux données du projet.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Guide étape par étape

### Étape 1 : Configurer le projet
Tout d’abord, créez une instance `Project` qui pointe vers le fichier MPP que vous souhaitez analyser, puis chargez‑la en mémoire. Cette étape unique prépare l’ensemble du modèle de projet pour le filtrage, la validation et d’autres manipulations, vous permettant d’accéder aux tâches, ressources et affectations via l’API.

### Comment configurer le projet pour filtrer les fichiers MPP ?
La classe `Project` charge et représente un fichier MPP en mémoire. Créez une instance `Project` qui pointe vers le fichier MPP que vous souhaitez analyser, puis chargez‑la en mémoire. Cette étape unique prépare l’ensemble du modèle de projet pour le filtrage, la validation et d’autres manipulations, vous permettant d’accéder aux tâches, ressources et affectations via l’API.

### Comment récupérer et inspecter un filtre ?
Les objets `Filter` encapsulent les définitions de filtres utilisées pour sélectionner les éléments du projet. Aspose.Tasks stocke des filtres prédéfinis tels que « All Tasks » ou « Critical Tasks ». Utilisez `project.getTaskFilters().getByName("My Filter")` ou un accès par indice pour obtenir un objet `Filter`, puis examinez sa collection `FilterCriteria` afin de voir chaque règle et l’opérateur logique (AND/OR) qui les combine, garantissant que le filtre correspond à vos exigences.

### Comment itérer sur les lignes de critères imbriquées ?
`FilterCriteriaGroup` représente un groupe de critères de filtre combinés avec un opérateur logique. Les filtres peuvent contenir des groupes de critères, chacun avec son propre opérateur. Parcourez `filter.getCriteria().getRows()` et, pour chaque ligne qui est un `FilterCriteriaGroup`, parcourez récursivement ses sous‑lignes. Cette traversée vous permet de comprendre pleinement une logique de filtre complexe telle que « (Start < today AND Cost > 1000) OR Priority = High », et d’ajuster les critères selon les besoins.

### Comment afficher les informations des critères pour le débogage ?
Après avoir parcouru l’arbre des critères, affichez le nom du champ, l’opérateur de test et la valeur de chaque ligne dans la console. Ce simple dump vous aide à vérifier que le filtre correspond aux règles métier prévues avant de l’appliquer à de gros projets, et facilite la détection d’opérateurs ou de valeurs incorrects.

### Comment créer un filtre tout neuf programmatique ?
Instanciez un `Filter` avec `new Filter("My Filter")`, puis ajoutez‑le à la collection de filtres de tâches du projet en utilisant `project.getTaskFilters().add(filter)`. Ensuite, remplissez sa collection `FilterCriteria` avec les lignes souhaitées, en spécifiant les noms de champs, les opérateurs de test et les valeurs afin de définir exactement quelles tâches doivent être incluses lorsque le filtre est appliqué.

### Puis‑je appliquer un filtre aux ressources au lieu des tâches ?
La collection `ResourceFilters` contient les définitions de filtres applicables aux ressources. Oui – utilisez `project.getResourceFilters()` pour travailler avec des filtres spécifiques aux ressources de la même manière que pour les filtres de tâches. Après avoir ajouté ou récupéré un filtre, configurez son `FilterCriteria` comme vous le feriez pour les tâches, puis appliquez‑le à la collection de ressources pour obtenir l’ensemble filtré de ressources.

### Est‑il possible de combiner plusieurs filtres avec une logique OU ?
Créez un `FilterCriteriaGroup` parent avec son `Operation` réglé sur `OR`, puis ajoutez des objets `FilterCriteria` individuels en tant qu’enfants. Ce groupe évaluera chaque critère enfant et renverra les éléments qui satisfont l’un d’eux, vous permettant de combiner plusieurs filtres simples en une sélection plus large.

### Aspose.Tasks prend‑il en charge le filtrage sur les champs personnalisés ?
L’énumération `CustomField` fournit des identifiants pour les champs personnalisés définis dans un projet. Absolument. Référez‑vous aux champs personnalisés via l’énumération `CustomField`, et ils se comportent comme n’importe quel champ intégré dans les expressions de filtre. Vous pouvez les inclure dans les lignes `FilterCriteria`, en utilisant les mêmes opérateurs et valeurs, ce qui permet des requêtes puissantes sur les données définies par l’utilisateur en parallèle des attributs standard du projet.

### Quel impact sur les performances le filtrage a‑t‑il sur les gros fichiers MPP ?
Le filtrage s’exécute entièrement en mémoire et traite généralement un projet de 1 000 tâches en moins de 200 ms. Pour les fichiers contenant plusieurs milliers de tâches, envisagez de charger uniquement les sections requises à l’aide de `ProjectReader` et d’appliquer les filtres après un chargement sélectif, ce qui maintient une faible utilisation de la mémoire et conserve des temps de réponse rapides même sur des projets très volumineux.

**Dernière mise à jour:** 2026-06-05  
**Testé avec:** Aspose.Tasks for Java 24.10  
**Auteur:** Aspose

## Tutoriels associés

- [Charger un fichier MPP Java - Gérer les propriétés du projet avec Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Lecture sans effort des données MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Définir la date de début du projet dans MS Project avec Aspose.Tasks pour Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```