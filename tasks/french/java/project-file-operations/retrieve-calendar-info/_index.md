---
date: 2025-12-20
description: Apprenez à utiliser Aspose.Tasks pour extraire les détails du calendrier
  du projet à partir des fichiers Microsoft Project en Java. Guide étape par étape
  avec des exemples de code.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment utiliser Aspose.Tasks pour récupérer les informations du calendrier
  MS Project
url: /fr/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser Aspose.Tasks pour récupérer les informations du calendrier MS Project

## Introduction
Dans ce tutoriel, **vous découvrirez comment utiliser Aspose.Tasks** pour récupérer programmétiquement les informations du calendrier à partir des fichiers Microsoft Project. Accéder aux données du calendrier telles que les jours ouvrés, les heures et les exceptions est essentiel lorsque vous devez **extraire les détails du calendrier du projet** pour des rapports, une intégration ou une logique de planification personnalisée. Parcourons le processus étape par étape.

## Quick Answers
- **Quelle bibliothèque ce tutoriel utilise‑t‑il ?** Aspose.Tasks for Java.  
- **Quel mot‑clé principal est couvert ?** *how to use aspose.tasks*.  
- **Que pouvez‑vous extraire ?** Les calendriers de projet, y compris les jours et heures de travail.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit est disponible ; une licence est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieure.

## Pourquoi extraire les informations du calendrier du projet ?
Les calendriers de projet déterminent les dates des tâches, les affectations de ressources et les calculs de la chronologie globale. En extrayant ces données, vous pouvez :
- Générer des rapports personnalisés reflétant les horaires de travail réels.  
- Synchroniser les chronologies de Microsoft Project avec des systèmes externes (ERP, BI, etc.).  
- Effectuer des analyses « what‑if » en modifiant les paramètres du calendrier de façon programmatique.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :
- Connaissances de base en programmation Java.  
- Java Development Kit (JDK) installé sur votre système.  
- Bibliothèque Aspose.Tasks for Java. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/tasks/java/).

## Import Packages
Tout d’abord, importez les classes Aspose.Tasks nécessaires dans votre projet Java.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Étape 1 : Définir le répertoire de données
Définissez le dossier contenant votre fichier *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu du dossier où se trouve **project.mpp**.

## Étape 2 : Définir les unités de temps
Créez des constantes qui aident à convertir la représentation interne du temps en heures lisibles par l’homme.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Ces valeurs sont exprimées en microsecondes, ce qui correspond à la façon dont Aspose.Tasks stocke le temps en interne.

## Étape 3 : Créer une instance de projet
Chargez le fichier Microsoft Project dans un objet `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Le constructeur `Project` analyse le fichier *.mpp* et rend toutes les données du projet, y compris les calendriers, accessibles via l’API.

## Étape 4 : Récupérer les informations des calendriers
Obtenez la collection des calendriers définis dans le projet.

```java
CalendarCollection alCals = project.getCalendars();
```

Un projet peut contenir plusieurs calendriers (standard, de ressources et personnalisés). Cette collection vous donne accès à chacun d’eux.

## Étape 5 : Parcourir les calendriers
Parcourez chaque calendrier, affichez son UID, son nom et les jours ouvrés avec les heures correspondantes.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

La boucle interne vérifie chaque objet `WeekDay`. Si le jour est marqué comme ouvré, il affiche le type de jour (Monday, Tuesday, …) ainsi que les heures de travail calculées.

## Étape 6 : Afficher le message de fin
Indiquez que le processus d’extraction est terminé.

```java
System.out.println("Process completed Successfully");
```

## Conclusion
En suivant ces étapes, **vous savez maintenant comment utiliser Aspose.Tasks pour extraire les informations du calendrier du projet** à partir d’un fichier MS Project en Java. Vous pouvez intégrer cette logique dans des applications plus vastes, automatiser les rapports ou synchroniser les plannings avec d’autres systèmes d’entreprise.

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks prend en charge plusieurs plateformes et langages de programmation, dont .NET, C++, Python et Java.

**Q : Une version d’essai gratuite est‑elle disponible pour Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis [ici](https://releases.aspose.com/).

**Q : Comment obtenir du support pour Aspose.Tasks ?**  
R : Vous pouvez obtenir du support sur le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks ?**  
R : Oui, des licences temporaires sont disponibles à l’achat [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks ?**  
R : Vous pouvez consulter la documentation [ici](https://reference.aspose.com/tasks/java/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}