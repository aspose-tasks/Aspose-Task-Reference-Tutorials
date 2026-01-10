---
date: 2026-01-10
description: Apprenez à lire l’échelle tarifaire et à gérer les affectations de ressources
  dans Aspose.Tasks pour Java. Définissez une ressource matérielle, comment régler
  l’échelle et affecter des ressources à une tâche.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
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

Dans ce tutoriel, vous découvrirez **comment lire le taux** et ajuster les paramètres pour les affectations de ressources en utilisant Aspose.Tasks for Java. Que vous construisiez un planificateur, un outil de reporting, ou que vous ayez simplement besoin d'automatiser les mises à jour de projet, maîtriser la manipulation de l'échelle de taux vous donne un contrôle fin sur les ressources matérielles et de travail.

## Réponses rapides
- **Quelle est la classe principale pour la gestion des taux ?** `ResourceAssignment` avec la propriété `Asn.RATE_SCALE`.  
- **Quel enum définit les options d'échelle ?** `RateScaleType` (Day, Week, Month, etc.).  
- **Ai-je besoin d'une licence pour exécuter l'exemple ?** Une licence d'évaluation gratuite fonctionne pour les tests ; une licence commerciale est requise pour la production.  
- **Puis-je changer l'échelle après l'enregistrement ?** Oui – rechargez le projet et modifiez `Asn.RATE_SCALE` comme indiqué.  
- **IDE supportés ?** Tout IDE Java (IntelliJ IDEA, Eclipse, NetBeans) peut compiler le code.

## Qu'est-ce que l'échelle de taux ?
L'échelle de taux détermine l'unité de temps (jour, semaine, mois, etc.) à laquelle le taux de coût d'une ressource est appliqué. Ajuster l'échelle vous permet de modéliser avec précision la consommation de matériel ou l'effort de travail.

## Pourquoi lire et écrire l'échelle de taux ?
Lire l'échelle actuelle vous aide à auditer les plannings existants, tandis qu'écrire une nouvelle échelle vous permet d'aligner les ressources avec les politiques de facturation ou de consommation du projet. Cela est particulièrement utile lors de la **définition des coûts de ressources matérielles** ou lorsque vous devez **définir l'échelle** pour des calendriers de travail non standard.

## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. **Environnement de développement Java** – JDK 8 ou supérieur installé.  
2. **Bibliothèque Aspose.Tasks for Java** – Téléchargez et installez la bibliothèque depuis [here](https://releases.aspose.com/tasks/java/).

## Importer les packages
Tout d'abord, importez les classes Aspose.Tasks nécessaires.

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
Ici, nous **définissons une ressource matérielle** et une ressource de travail régulière. Notez l'utilisation de `ResourceType.Material` pour la ressource de type matériel.

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
Enregistrez les modifications dans un nouveau fichier afin de pouvoir vérifier ultérieurement l'échelle de taux stockée.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Étape 7 : Récupérer les affectations de ressources
Rechargez le projet enregistré et **lisez l'échelle de taux** pour confirmer qu'elle a été correctement écrite.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Pièges courants et conseils
- **Incohérence d'UID** – Lors de la récupération des affectations par UID, assurez-vous que les valeurs d'UID correspondent à celles attribuées lors de la création.  
- **Type de ressource incorrect** – Utiliser `ResourceType.Material` pour une ressource de travail entraînera des calculs de taux inattendus.  
- **Format d'enregistrement** – Enregistrez toujours en utilisant `SaveFileFormat.Mpp` (ou un autre format supporté) pour préserver les champs personnalisés comme l'échelle de taux.

## Conclusion
Gérer et inspecter l'échelle de taux pour les affectations de ressources dans Aspose.Tasks for Java est simple une fois que vous connaissez les classes et propriétés pertinentes. En suivant ce guide, vous pouvez **lire les informations de taux**, **définir des objets de ressource matérielle**, **définir l'échelle** et **affecter des ressources à la tâche** en toute confiance.

## Questions fréquemment posées

**Q : Puis-je utiliser Aspose.Tasks for Java avec n'importe quel IDE Java ?**  
R : Oui, Aspose.Tasks for Java est compatible avec tous les principaux IDE Java, y compris IntelliJ IDEA, Eclipse et NetBeans.

**Q : Aspose.Tasks prend‑il en charge d'autres formats de fichiers en plus de MPP ?**  
R : Oui, Aspose.Tasks prend en charge divers formats de fichiers, y compris MPP, XML et HTML.

**Q : Aspose.Tasks est‑il adapté à la gestion de projet de niveau entreprise ?**  
R : Absolument, Aspose.Tasks offre des fonctionnalités complètes pour gérer des projets de toute envergure, le rendant adapté à la gestion de projet de niveau entreprise.

**Q : Puis‑je personnaliser davantage les affectations de ressources au‑delà de l'échelle de taux ?**  
R : Oui, Aspose.Tasks offre de vastes possibilités de personnalisation des affectations de ressources, y compris les ajustements de coût, de travail et de durée.

**Q : Existe‑t‑il un forum communautaire pour le support d'Aspose.Tasks ?**  
R : Oui, vous pouvez trouver du support et interagir avec d'autres utilisateurs sur le forum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.Tasks for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}