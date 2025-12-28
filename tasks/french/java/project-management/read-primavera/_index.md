---
date: 2025-12-28
description: Apprenez à lire les fichiers XML Primavera dans MS Project à l'aide d'Aspose.Tasks
  pour Java, permettant un échange de données fluide et une amélioration de la gestion
  de projet.
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment lire le XML Primavera dans MS Project avec Aspose.Tasks pour Java
url: /fr/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire MS Project depuis Primavera avec Aspose.Tasks pour Java

## Introduction
Dans la gestion de projet moderne, déplacer des données entre outils sans perte de détail est essentiel. Ce tutoriel vous montre **comment lire primavera xml** fichiers et les importer dans Microsoft Project en utilisant Aspose.Tasks pour Java. À la fin, vous pourrez extraire les propriétés de tâche spécifiques à Primavera, rendant l'analyse multiplateforme simple et efficace.

## Quick Answers
- **Que fait Aspose.Tasks pour Java ?** Il lit et écrit de nombreux formats de fichiers de projet, y compris Primavera XML et Microsoft Project (MPP).  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour l'évaluation ; une licence est requise pour une utilisation en production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur est requis.  
- **Puis-je lire d'autres formats en plus de Primavera XML ?** Oui, Aspose.Tasks prend en charge MPP, XML et bien d'autres.  
- **Cette approche convient‑elle aux grands projets d'entreprise ?** Absolument — Aspose.Tasks est conçu pour des scénarios haute performance et de niveau entreprise.

## Qu'est‑ce que lire primavera xml ?
Lire Primavera XML signifie analyser l'export XML d'Oracle Primavera P6 afin de récupérer les données de planification du projet — tâches, durées, ressources et attributs spécifiques à Primavera — pour qu'elles puissent être utilisées par d'autres outils comme Microsoft Project.

## Pourquoi utiliser Aspose.Tasks pour Java pour lire primavera xml ?
- **Fidélité totale :** Toutes les propriétés spécifiques à Primavera sont conservées.  
- **Aucune dépendance externe :** Bibliothèque pure Java, aucune installation de Primavera ou MS Project n'est nécessaire.  
- **Scalable :** Gère efficacement les grands projets contenant des milliers de tâches.  
- **Cross‑platform :** Fonctionne sous Windows, Linux et macOS.

## Prérequis
Avant de commencer, assurez‑vous d'avoir les éléments suivants :
1. **Java Development Kit (JDK)** – Java 8 ou plus récent installé.  
2. **Aspose.Tasks for Java** – Téléchargez‑le depuis [ici](https://releases.aspose.com/tasks/java/).  
3. Un fichier Primavera XML (par ex., `PrimaveraProject.xml`) que vous souhaitez lire.

## Comment lire un fichier de projet Java avec Aspose.Tasks ?
Voici un guide étape par étape qui vous accompagne tout au long du processus.

### Import Packages
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Step 1: Set up Data Directory
```java
String dataDir = "Your Data Directory";
```
Remplacez `"Your Data Directory"` par le chemin absolu où se trouve votre fichier Primavera XML.

### Step 2: Read Project from Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Mettez à jour `"PrimaveraProject.xml"` avec le nom de fichier réel de votre export Primavera.

### Step 3: Iterate Through Tasks and Retrieve Primavera‑Specific Properties
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

## Common Issues and Solutions
- **Erreur fichier non trouvé :** Vérifiez que `dataDir` se termine par un séparateur de chemin (`/` ou `\\`) et que le nom du fichier XML est correct.  
- **Propriétés Primavera manquantes :** Assurez‑vous que l'XML a été exporté avec tous les champs requis ; les versions plus anciennes de Primavera peuvent omettre certains attributs.  
- **Performance sur les gros fichiers :** Envisagez d'augmenter la taille du tas JVM (`-Xmx2g` ou plus) pour les projets contenant des dizaines de milliers de tâches.

## Frequently Asked Questions
### Q : Puis‑je modifier les propriétés spécifiques à Primavera des tâches en utilisant Aspose.Tasks pour Java ?
R : Oui, Aspose.Tasks pour Java fournit des API permettant de modifier les propriétés spécifiques à Primavera des tâches selon les besoins.

### Q : Aspose.Tasks pour Java prend‑il en charge la lecture d'autres formats de fichiers de projet ?
R : Oui, Aspose.Tasks pour Java prend en charge la lecture de divers formats de fichiers de projet, y compris MPP, XML et Primavera XML.

### Q : Aspose.Tasks pour Java est‑il adapté aux applications de gestion de projet de niveau entreprise ?
R : Absolument, Aspose.Tasks pour Java offre des fonctionnalités robustes et une grande évolutivité, ce qui le rend adapté aux applications de gestion de projet de niveau entreprise.

### Q : Puis‑je extraire les informations de ressources des projets Primavera en utilisant Aspose.Tasks pour Java ?
R : Oui, Aspose.Tasks pour Java vous permet d'extraire les informations de ressources ainsi que les détails des tâches à partir des projets Primavera.

### Q : Où puis‑je trouver un support supplémentaire ou de la documentation pour Aspose.Tasks pour Java ?
R : Vous pouvez trouver une documentation complète et accéder aux forums de support sur la page [documentation Aspose.Tasks pour Java](https://reference.aspose.com/tasks/java/).

## Conclusion
Vous avez maintenant appris **comment lire primavera xml** et extraire des informations détaillées sur les tâches dans une application Java en utilisant Aspose.Tasks. Cette capacité comble le fossé entre Primavera et Microsoft Project, vous offrant une visibilité complète sur toutes les plateformes et améliorant l'efficacité globale de la gestion de projet.

---

**Dernière mise à jour :** 2025-12-28  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}