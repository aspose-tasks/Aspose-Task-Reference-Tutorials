---
date: 2026-03-29
description: Apprenez comment modifier le nombre de jours par mois et gérer d’autres
  propriétés des jours de la semaine dans Aspose.Tasks pour Java. Personnalisez les
  dates de début de semaine, modifiez le calendrier du projet et enregistrez le projet
  au format XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Changer les jours par mois avec les propriétés Weekday d’Aspose.Tasks
url: /fr/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifier le nombre de jours par mois avec les propriétés de jour de semaine d'Aspose.Tasks

## Introduction
Aspose.Tasks for Java vous permet de **modifier le nombre de jours par mois** et d’ajuster finement d’autres paramètres de jour de semaine sans avoir besoin d’installer Microsoft Project. Que vous aligniez le calendrier d’un projet sur un mois fiscal non standard ou que vous ayez simplement besoin d’ajuster le jour de début de semaine, ce tutoriel vous guide à travers les scénarios les plus courants — récupérer le jour de début de semaine actuel, personnaliser la date de début de semaine, modifier le calendrier du projet et enregistrer le projet au format XML.

## Réponses rapides
- **Puis-je modifier le nombre de jours par mois ?** Oui, utilisez `Prj.DAYS_PER_MONTH` sur l’objet `Project`.  
- **Comment personnaliser la date de début de semaine ?** Définissez `Prj.WEEK_START_DAY` sur une valeur `DayType` (par ex., `DayType.Monday`).  
- **Quel format puis‑je utiliser pour exporter le projet ?** L’exemple enregistre le fichier au format XML avec `SaveFileFormat.Xml`.  
- **Une licence est‑elle requise pour une utilisation en production ?** Une licence valide d’Aspose.Tasks est nécessaire pour les déploiements non‑évaluatifs.  
- **Quels IDE sont pris en charge ?** Tout IDE Java tel qu’IntelliJ IDEA, Eclipse ou NetBeans fonctionne.

## Qu’est‑ce que « modifier le nombre de jours par mois » dans Aspose.Tasks ?
Modifier le nombre de jours par mois signifie mettre à jour la propriété `Prj.DAYS_PER_MONTH` d’une instance `Project`. Cette propriété indique au moteur combien de jours ouvrables il doit considérer chaque mois, ce qui influence directement la planification des tâches et les calculs de coûts.

## Pourquoi modifier les propriétés du calendrier du projet ?
Personnaliser le calendrier du projet—comme définir un jour de début de semaine différent ou modifier les minutes par jour—vous aide à :
- Aligner les plannings avec les semaines de travail régionales.  
- Modéliser des modèles de travail non standard (par ex., semaines de 4 jours).  
- Assurer des rapports précis pour les contrats qui utilisent des calendriers personnalisés.

## Prérequis
- **Java Development Kit (JDK)** – Installez le dernier JDK depuis Oracle.  
- **Bibliothèque Aspose.Tasks for Java** – Téléchargez‑la depuis le site officiel [ici](https://releases.aspose.com/tasks/java/).  
- **IDE de votre choix** – IntelliJ IDEA, Eclipse ou NetBeans.

## Importer les packages
Tout d’abord, importez les classes essentielles d’Aspose.Tasks :

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Étape 1 : Charger le fichier de projet
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Cela charge un fichier Microsoft Project existant (`project.mpp`) depuis le dossier que vous spécifiez.

## Étape 2 : Afficher les propriétés du jour de semaine
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Ici nous récupérons et affichons les paramètres actuels du jour de semaine, y compris le **jour de début de semaine** et le **nombre de jours par mois**.

## Étape 3 : Définir les propriétés du jour de semaine
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Dans cette étape, nous **modifions le nombre de jours par mois** à 24, définissons le début de la semaine le lundi, et ajustons les minutes par jour/semaine. Cela montre comment **modifier le calendrier du projet** de manière programmatique.

## Étape 4 : Enregistrer le projet
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Le projet modifié est sauvegardé en utilisant le format **enregistrer le projet au format XML**, ce qui est pratique pour l’intégration avec d’autres outils ou pour un stockage sous contrôle de version.

## Étape 5 : Afficher le résultat
```java
System.out.println("Process completed Successfully");
```
Une simple confirmation que les opérations se sont terminées sans erreurs.

## Comment personnaliser la date de début de semaine
Si votre organisation suit un calendrier commençant le dimanche, remplacez `DayType.Monday` par `DayType.Sunday`. La même propriété (`Prj.WEEK_START_DAY`) est utilisée, rendant le changement simple.

## Comment récupérer le jour de début de semaine
Vous pouvez appeler `project.get(Prj.WEEK_START_DAY)` à tout moment pour **récupérer l’information du jour de début de semaine**, comme montré à l’Étape 2.

## Comment modifier le calendrier du projet
Au‑delà du jour de début de semaine, vous pouvez également ajuster `Prj.MINUTES_PER_DAY` et `Prj.MINUTES_PER_WEEK` pour refléter des heures de travail personnalisées ou des modèles de poste.

## Problèmes courants et solutions
- **Valeur de type de jour incorrecte** – Assurez‑vous d’utiliser l’énumération `DayType` (par ex., `DayType.Monday`).  
- **Erreurs de chemin de fichier** – Vérifiez que `dataDir` se termine par le séparateur de fichiers approprié (`/` ou `\`).  
- **Licence non définie** – Si vous voyez des avertissements de licence, enregistrez votre licence Aspose.Tasks avant de créer l’objet `Project`.

## Questions fréquemment posées

**Q: Aspose.Tasks for Java peut‑il gérer des structures de projet complexes ?**  
A: Oui, Aspose.Tasks for Java offre un support complet pour gérer des structures de projet complexes avec aisance.

**Q: Aspose.Tasks for Java est‑il compatible avec différentes versions de fichiers Microsoft Project ?**  
A: Absolument, Aspose.Tasks for Java prend en charge diverses versions de fichiers Microsoft Project, garantissant la compatibilité sur toutes les plateformes.

**Q: Puis‑je intégrer Aspose.Tasks for Java dans mes applications Java existantes ?**  
A: Oui, Aspose.Tasks for Java offre des capacités d’intégration transparentes, vous permettant d’enrichir vos applications Java avec des fonctionnalités puissantes de gestion de projet.

**Q: Aspose.Tasks for Java fournit‑il de la documentation et du support ?**  
A: Oui, vous pouvez accéder à une documentation exhaustive et au support communautaire pour Aspose.Tasks for Java sur leur [site web](https://releases.aspose.com/).

**Q: Existe‑t‑il une version d’essai gratuite d’Aspose.Tasks for Java ?**  
A: Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.Tasks for Java depuis leur [site web](https://reference.aspose.com/tasks/java/) pour explorer ses fonctionnalités avant d’effectuer un achat.

---

**Dernière mise à jour :** 2026-03-29  
**Testé avec :** Aspose.Tasks for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}