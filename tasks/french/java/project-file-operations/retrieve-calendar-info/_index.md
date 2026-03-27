---
date: 2026-03-27
description: Apprenez à utiliser Aspose et Aspose.Tasks pour extraire les détails
  du calendrier de projet à partir des fichiers Microsoft Project en Java. Guide étape
  par étape avec des exemples de code.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Comment utiliser Aspose.Tasks pour récupérer les informations du calendrier
  MS Project
url: /fr/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser Aspose.Tasks pour récupérer les informations du calendrier MS Project

## Introduction
Dans ce tutoriel, **vous découvrirez comment utiliser Aspose.Tasks** pour récupérer de façon programmatique les informations de calendrier à partir des fichiers Microsoft Project. Accéder aux données de calendrier telles que les jours ouvrés, les heures et les exceptions est essentiel lorsque vous devez **extraire le calendrier du projet** pour des rapports, une intégration ou une logique de planification personnalisée. Parcourons le processus étape par étape, et vous verrez exactement **comment utiliser Aspose** pour extraire ces données d’un fichier *.mpp*.

## Quick Answers
- **Quelle bibliothèque ce tutoriel utilise‑t‑il ?** Aspose.Tasks for Java.  
- **Quel mot‑clé principal est couvert ?** *how to use aspose*.  
- **Que pouvez‑vous extraire ?** Les calendriers de projet, y compris les jours et heures de travail.  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite est disponible ; une licence est requise pour la production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur.

## Qu’est‑ce qu’Aspose.Tasks et pourquoi l’utiliser ?
Aspose.Tasks est une puissante API Java qui permet aux développeurs de lire, écrire et manipuler les fichiers Microsoft Project sans avoir besoin de Microsoft Project lui‑même. En utilisant Aspose.Tasks vous pouvez **how to extract calendar** les informations, automatiser les calculs de planning et intégrer les données de projet avec d’autres systèmes d’entreprise — le tout depuis du code Java pur.

## Pourquoi extraire les informations du calendrier du projet ?
Les calendriers de projet pilotent les dates des tâches, les affectations de ressources et les calculs de chronologie globale. En extrayant ces données vous pouvez :
- Générer des rapports personnalisés reflétant les horaires de travail réels.  
- Synchroniser les chronologies de Microsoft Project avec des systèmes externes (ERP, BI, etc.).  
- Effectuer des analyses « what‑if » en modifiant les paramètres du calendrier de façon programmatique.  
- **Extract MS Project calendar** les données pour les migrer vers d’autres outils de planification.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Des connaissances de base en programmation Java.  
- Le Java Development Kit (JDK) installé sur votre système.  
- La bibliothèque Aspose.Tasks for Java. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/java/).

## Import Packages
Tout d’abord, importez les classes Aspose.Tasks nécessaires dans votre projet Java.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Étape 1 : Définir le répertoire de données
Définissez le dossier qui contient votre fichier *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Remplacez `"Your Data Directory"` par le chemin absolu du dossier où **project.mpp** réside.

## Étape 2 : Définir les unités de temps
Créez des constantes qui aident à convertir la représentation interne du temps en heures lisibles par l’homme.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Ces valeurs sont exprimées en microsecondes, c’est ainsi qu’Aspose.Tasks stocke le temps en interne.

## Étape 3 : Créer une instance de Project
Chargez le fichier Microsoft Project dans un objet `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Le constructeur `Project` analyse le fichier *.mpp* et rend toutes les données du projet, y compris les calendriers, accessibles via l’API.

## Étape 4 : Récupérer les informations des calendriers
Obtenez la collection des calendriers définis dans le projet.

```java
CalendarCollection alCals = project.getCalendars();
```

Un projet peut contenir plusieurs calendriers (standard, ressources et personnalisés). Cette collection vous donne accès à chacun d’eux.

## Étape 5 : Parcourir les calendriers
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

La boucle interne vérifie chaque objet `WeekDay`. Si le jour est marqué comme ouvré, il imprime le type de jour (Monday, Tuesday, …) avec les heures de travail calculées.

## Étape 6 : Afficher le message de fin
Signalez que le processus d’extraction est terminé.

```java
System.out.println("Process completed Successfully");
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Aucun calendrier retourné** | Le fichier de projet peut ne pas contenir de calendriers personnalisés. | Vérifiez que le *.mpp* définit réellement des calendriers ou ouvrez-le dans Microsoft Project pour confirmer. |
| **Heures de travail incorrectes** | Les constantes de conversion de temps sont incorrectes pour une version différente de Project. | Ajustez `OneSec`, `OneMin`, `OneHour` si vous travaillez avec une version plus récente d'Aspose.Tasks qui modifie l’unité de temps interne. |
| **`NullPointerException` sur `cal.getName()`** | Certains objets calendrier peuvent être nuls. | Ajoutez une vérification de null avant d’accéder aux propriétés (déjà démontré). |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.Tasks avec d’autres langages de programmation ?**  
R : Oui, Aspose.Tasks prend en charge plusieurs plateformes et langages de programmation, notamment .NET, C++, Python et Java.

**Q : Existe‑t‑il une version d’essai gratuite d’Aspose.Tasks ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite [ici](https://releases.aspose.com/).

**Q : Comment puis‑je obtenir du support pour Aspose.Tasks ?**  
R : Vous pouvez obtenir du support via le forum communautaire Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

**Q : Puis‑je acheter une licence temporaire pour Aspose.Tasks ?**  
R : Oui, des licences temporaires sont disponibles à l’achat [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Tasks ?**  
R : Vous pouvez consulter la documentation [ici](https://reference.aspose.com/tasks/java/).

## Conclusion
En suivant ces étapes, **vous savez maintenant comment utiliser Aspose.Tasks pour extraire les informations du calendrier du projet** à partir d’un fichier MS Project en Java. Vous pouvez intégrer cette logique dans des applications plus vastes, automatiser les rapports ou synchroniser les plannings avec d’autres systèmes d’entreprise. Rappelez‑vous, maîtriser **how to use aspose** ouvre la porte à de nombreux scénarios avancés d’automatisation de la gestion de projet.

---

**Dernière mise à jour :** 2026-03-27  
**Testé avec :** Aspose.Tasks for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}