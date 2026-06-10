---
date: 2026-06-10
description: Apprenez comment lire le taux et comment écrire l'échelle de taux pour
  les affectations de ressources en utilisant Aspose.Tasks pour Java. Prise en charge
  des ressources matérielles, de plusieurs formats et de grands projets.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Lire et écrire l'échelle de taux pour les affectations de ressources dans
  Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment lire l'échelle de taux et écrire l'échelle de taux pour les affectations
  de ressources dans Aspose.Tasks
url: /fr/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire l'échelle de taux et écrire l'échelle de taux pour les affectations de ressources dans Aspose.Tasks

Dans ce tutoriel, vous découvrirez **comment lire les paramètres** d'échelle de taux et les ajuster pour les affectations de ressources à l'aide d'Aspose.Tasks pour Java. Que vous construisiez un planificateur, un outil de reporting ou que vous ayez simplement besoin d'automatiser les mises à jour de projet, maîtriser la manipulation de l'échelle de taux vous donne un contrôle granulaire sur les ressources matérielles et de travail.

## Réponses rapides
`ResourceAssignment` lie une tâche à une ressource et contient les données spécifiques à l'affectation.  
`Asn` contient des constantes pour les champs d'affectation, y compris `RATE_SCALE`.  
`RateScaleType` énumère les unités de temps possibles pour le dimensionnement du taux.  

- **Quelle est la classe principale pour la gestion des taux ?** `ResourceAssignment` avec la propriété `Asn.RATE_SCALE`.  
- **Quelle énumération définit les options d'échelle ?** `RateScaleType` (Day, Week, Month, etc.).  
- **Ai‑je besoin d'une licence pour exécuter l'exemple ?** Une licence d'évaluation gratuite suffit pour les tests ; une licence commerciale est requise en production.  
- **Puis‑je modifier l'échelle après l'enregistrement ?** Oui – rechargez le projet et modifiez `Asn.RATE_SCALE` comme indiqué.  
- **IDEs pris en charge ?** Tout IDE Java (IntelliJ IDEA, Eclipse, NetBeans) peut compiler le code.

## Comment lire l'échelle de taux pour les affectations de ressources ?
Chargez le projet, localisez le `ResourceAssignment` souhaité et appelez `getRateScale()` – cela renvoie une valeur `RateScaleType` qui indique si le taux est appliqué par jour, semaine, mois ou autre unité. La réponse est immédiate et ne nécessite que deux appels d'API, ce qui le rend idéal pour les scripts d'audit ou les affichages UI.

## Comment écrire l'échelle de taux pour les affectations de ressources ?
Créez ou récupérez un objet `ResourceAssignment`, définissez sa propriété `Asn.RATE_SCALE` sur le `RateScaleType` désiré (par ex., `RateScaleType.Week`), puis enregistrez le projet. Cette modification unique de propriété met automatiquement à jour les calculs de coûts et persiste dans tous les formats de fichier pris en charge. Après avoir défini l'échelle, il peut également être nécessaire d'ajuster le taux standard ou le taux supplémentaire de la ressource pour refléter la nouvelle unité de temps, garantissant ainsi l'exactitude des calculs de coûts.

## Qu'est-ce que l'échelle de taux ?
L'échelle de taux détermine l'unité de temps (jour, semaine, mois, etc.) à laquelle le taux de coût d'une ressource est appliqué. Ajuster l'échelle vous permet de modéliser avec précision la consommation de matériel ou l'effort de main‑d'œuvre. Par exemple, définir l'échelle sur Semaine signifie que le taux de coût est interprété comme un coût par semaine, et le coût total d'une tâche est calculé en fonction du nombre de semaines pendant lesquelles la ressource est affectée.

## Pourquoi lire et écrire l'échelle de taux ?
Lire l'échelle actuelle vous aide à auditer les plannings existants, tandis qu'écrire une nouvelle échelle vous permet d'aligner les ressources sur les politiques de facturation ou de consommation du projet. Ceci est particulièrement utile lors de la **définition des coûts des ressources matérielles** ou lorsque vous devez **définir l'échelle** pour des calendriers de travail non standard.

## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. **Environnement de développement Java** – JDK 8 ou supérieur installé.  
2. **Bibliothèque Aspose.Tasks pour Java** – Téléchargez et installez la bibliothèque depuis [here](https://releases.aspose.com/tasks/java/).

## Importer les packages
La classe `ResourceAssignment` représente un lien entre une tâche et une ressource, tandis que `RateScaleType` énumère les unités de temps possibles pour un taux. Importez les classes Aspose.Tasks nécessaires avant de commencer à coder.  

`Project` est l'objet principal qui charge et enregistre les fichiers Microsoft Project.  
`Resource` définit une ressource de projet telle que le travail ou le matériel.  
`ResourceType` enum spécifie si une ressource est de type travail ou matériel.  
`Task` représente un élément de travail dans le planning du projet.  
`SaveFileFormat` enum définit le format de sortie lors de l'enregistrement d'un projet.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Étape 1 : Configurer votre projet Java
Créez un projet Maven ou Gradle et ajoutez le JAR Aspose.Tasks à votre classpath. Cette étape garantit que le compilateur peut localiser les classes importées.

## Étape 2 : Charger le fichier de projet
Chargez le fichier Microsoft Project existant avec lequel vous souhaitez travailler.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Étape 3 : Ajouter une tâche
Créez une nouvelle tâche qui recevra plus tard des affectations de ressources.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Étape 4 : Définir les ressources
Ici nous **définissons une ressource matérielle** et une ressource de travail régulière. Remarquez l'utilisation de `ResourceType.Material` pour la ressource de type matériel.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Étape 5 : Affecter des ressources à la tâche
Nous **affectons maintenant des ressources à la tâche** et spécifions le **comment définir l'échelle** en utilisant `RateScaleType.Week`. Cela illustre à la fois la lecture et l'écriture de l'échelle de taux.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Étape 6 : Enregistrer le projet
Persistez les modifications dans un nouveau fichier afin de pouvoir vérifier ultérieurement l'échelle de taux enregistrée.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Étape 7 : Récupérer les affectations de ressources
Rechargez le projet enregistré et **lisez l'échelle** de taux pour confirmer qu'elle a été correctement écrite.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Pièges courants et conseils
- **UID Mismatch** – Lors de la récupération des affectations par UID, assurez‑vous que les valeurs UID correspondent à celles attribuées lors de la création.  
- **Incorrect Resource Type** – Utiliser `ResourceType.Material` pour une ressource de travail entraînera des calculs de taux inattendus.  
- **Saving Format** – Enregistrez toujours en utilisant `SaveFileFormat.Mpp` (ou un autre format pris en charge) pour préserver les champs personnalisés comme l'échelle de taux.  
- **Large Projects** – Aspose.Tasks peut traiter des fichiers contenant **plus de 500 pages** sans charger le document complet en mémoire, grâce à son architecture de streaming.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks pour Java avec n'importe quel IDE Java ?**  
R : Oui, Aspose.Tasks pour Java est compatible avec tous les principaux IDE Java, y compris IntelliJ IDEA, Eclipse et NetBeans.

**Q : Aspose.Tasks prend‑il en charge d'autres formats de fichier en plus du MPP ?**  
R : Oui, Aspose.Tasks prend en charge divers formats de fichier, dont MPP, XML et HTML.

**Q : Aspose.Tasks est‑il adapté à la gestion de projets de niveau entreprise ?**  
R : Absolument, Aspose.Tasks offre des fonctionnalités complètes pour gérer des projets de toute envergure, le rendant adapté à la gestion de projets de niveau entreprise.

**Q : Puis‑je personnaliser davantage les affectations de ressources au‑delà de l'échelle de taux ?**  
R : Oui, Aspose.Tasks fournit de vastes capacités pour personnaliser les affectations de ressources, incluant les ajustements de coût, de travail et de durée.

**Q : Existe‑t‑il un forum communautaire pour le support d'Aspose.Tasks ?**  
R : Oui, vous pouvez trouver du support et interagir avec d'autres utilisateurs sur le forum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-06-10  
**Testé avec :** Aspose.Tasks pour Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer des affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Comment modifier les affectations – Lire les ressources partagées avec Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Comment ajouter des notes aux affectations de ressources dans Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}