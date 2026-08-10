---
date: 2026-04-24
description: Apprenez à utiliser Aspose.Tasks Java pour importer des fichiers XML
  Primavera dans MS Project, permettant un échange de données fluide et une meilleure
  gestion de projet.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Lire le projet depuis Primavera dans Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Lire le XML Primavera dans MS Project
url: /fr/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire MS Project depuis Primavera avec Aspose.Tasks pour Java

## Introduction
Dans le monde actuel de la gestion de projet à rythme rapide, vous devez souvent déplacer des plannings entre Primavera P6 et Microsoft Project sans perdre de détails. Ce tutoriel montre **comment lire des fichiers Primavera XML** et les importer dans MS Project à l’aide de **aspose tasks java**. À la fin du guide, vous pourrez extraire les propriétés spécifiques de Primavera dans une application Java, vous offrant une source unique de vérité pour l’analyse, le reporting ou l’automatisation supplémentaire.

## Réponses rapides
- **Que fait Aspose.Tasks pour Java ?** Il lit et écrit de nombreux formats de fichiers de projet, y compris Primavera XML et Microsoft Project (MPP).  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour l'évaluation ; une licence est requise pour une utilisation en production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur est requis.  
- **Puis-je importer d'autres formats en plus de Primavera XML ?** Oui, aspose tasks java prend également en charge MPP, XML et bien d'autres.  
- **Cette approche convient‑elle aux grands projets d'entreprise ?** Absolument — Aspose.Tasks est conçu pour des scénarios haute performance et de niveau entreprise.

## aspose tasks java – Lecture de Primavera XML
Lire un fichier Primavera XML signifie analyser l'export XML d'Oracle Primavera P6 afin de récupérer les données du planning du projet — tâches, durées, ressources et attributs spécifiques à Primavera — pour qu'elles puissent être utilisées par d'autres outils comme Microsoft Project.

## Pourquoi utiliser Aspose.Tasks pour Java pour lire Primavera XML ?
- **Fidélité totale :** Toutes les propriétés spécifiques à Primavera sont conservées.  
- **Aucune dépendance externe :** Bibliothèque pure Java, aucune nécessité d'installations Primavera ou MS Project.  
- **Scalable :** Gère efficacement les grands projets contenant des milliers de tâches.  
- **Cross‑platform :** Fonctionne sous Windows, Linux et macOS.

## Prérequis
Avant de commencer, assurez‑vous d'avoir les éléments suivants :
1. **Java Development Kit (JDK)** – Java 8 ou version plus récente installé.  
2. **Aspose.Tasks for Java** – Téléchargez‑le depuis [here](https://releases.aspose.com/tasks/java/).  
3. Un fichier Primavera XML (par ex., `PrimaveraProject.xml`) que vous souhaitez lire.

## Comment lire un fichier de projet Java avec Aspose.Tasks ?
Voici un guide étape par étape qui vous accompagne tout au long du processus.

### Importation des packages
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Étape 1 : Configurer le répertoire de données
Remplacez `"Your Data Directory"` par le chemin absolu où se trouve votre fichier Primavera XML.
```java
String dataDir = "Your Data Directory";
```

### Étape 2 : Lire le projet depuis Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Mettez à jour `"PrimaveraProject.xml"` avec le nom de fichier réel de votre export Primavera.

### Étape 3 : Parcourir les tâches et récupérer les propriétés spécifiques à Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Cette boucle affiche les détails spécifiques à Primavera de chaque tâche, tels que l'ID d'activité, la séquence WBS, les types de durée, la ventilation des coûts, etc.

## Problèmes courants et solutions
- **Erreur fichier non trouvé :** Vérifiez que `dataDir` se termine par un séparateur de chemin (`/` ou `\\`) et que le nom du fichier XML est correct.  
- **Propriétés Primavera manquantes :** Assurez‑vous que l'XML a été exporté avec tous les champs requis ; les versions plus anciennes de Primavera peuvent omettre certains attributs.  
- **Performance sur les gros fichiers :** Envisagez d'augmenter la taille du tas JVM (`-Xmx2g` ou plus) pour les projets contenant des dizaines de milliers de tâches.

## Questions fréquemment posées
### Q : Puis‑je modifier les propriétés spécifiques à Primavera des tâches avec Aspose.Tasks pour Java ?
R : Oui, Aspose.Tasks pour Java fournit des API permettant de modifier les propriétés spécifiques à Primavera des tâches selon les besoins.

### Q : Aspose.Tasks pour Java prend‑il en charge la lecture d'autres formats de fichiers de projet ?
R : Oui, Aspose.Tasks pour Java prend en charge la lecture de divers formats de fichiers de projet, y compris MPP, XML et Primavera XML.

### Q : Aspose.Tasks pour Java convient‑il aux applications de gestion de projet de niveau entreprise ?
R : Absolument, Aspose.Tasks pour Java offre des fonctionnalités robustes et une grande évolutivité, ce qui le rend adapté aux applications de gestion de projet de niveau entreprise.

### Q : Puis‑je extraire les informations de ressources des projets Primavera avec Aspose.Tasks pour Java ?
R : Oui, Aspose.Tasks pour Java vous permet d'extraire les informations de ressources ainsi que les détails des tâches à partir des projets Primavera.

### Q : Où puis‑je trouver un support supplémentaire ou la documentation pour Aspose.Tasks pour Java ?
R : Vous pouvez trouver une documentation complète et accéder aux forums de support sur la page [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## Conclusion
Vous avez maintenant appris **comment lire des fichiers primavera xml** et extraire des informations détaillées sur les tâches dans une application Java en utilisant **aspose tasks java**. Cette capacité comble le fossé entre Primavera et Microsoft Project, vous offrant une visibilité complète sur les plateformes et améliorant l'efficacité globale de la gestion de projet.

---

**Dernière mise à jour :** 2026-04-24  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}