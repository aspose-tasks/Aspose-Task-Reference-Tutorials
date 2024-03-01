---
title: Récupérer les informations du calendrier MS Project dans Aspose.Tasks
linktitle: Récupérer les informations du calendrier dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment récupérer les informations du calendrier MS Project à l'aide d'Aspose.Tasks pour Java. Guide étape par étape pour accéder aux détails du calendrier par programmation.
type: docs
weight: 14
url: /fr/java/project-file-operations/retrieve-calendar-info/
---
## Introduction
Dans ce didacticiel, nous verrons comment récupérer des informations de calendrier à partir de fichiers Microsoft Project à l'aide de la bibliothèque Aspose.Tasks pour Java. Aspose.Tasks fournit des fonctionnalités puissantes pour manipuler les données du projet, notamment l'accès aux détails du calendrier tels que les jours et les heures de travail.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Connaissance de base de la programmation Java.
- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Tasks pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
## Importer des packages
Tout d’abord, vous devez importer les packages nécessaires dans votre code Java pour utiliser les fonctionnalités Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Décomposons maintenant l'exemple fourni en plusieurs étapes pour une meilleure compréhension.
## Étape 1 : Définir le répertoire de données
```java
String dataDir = "Your Data Directory";
```
 Remplacer`"Your Data Directory"` avec le chemin d'accès au répertoire des fichiers de votre projet.
## Étape 2 : Définir les unités de temps
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Ces constantes représentent des unités de temps en microsecondes.
## Étape 3 : Créer une instance de projet
```java
Project project = new Project(dataDir + "project.mpp");
```
 Cette ligne crée une instance du`Project` classe, en l'initialisant avec le chemin d'accès au fichier projet (`project.mpp`).
## Étape 4 : Récupérer les informations des calendriers
```java
CalendarCollection alCals = project.getCalendars();
```
Ici, nous récupérons une collection de calendriers présents dans le fichier projet.
## Étape 5 : Parcourir les calendriers
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Informations sur le calendrier
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Parcourir les jours de la semaine
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Temps en millisecondes
            double time = ts / (OneHour); // Convertir en heures
            if (wd.getDayWorking()) {
                // Afficher les jours et heures ouvrables
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Cette boucle parcourt chaque calendrier et imprime son UID, son nom et ses jours ouvrables avec les heures de travail respectives.
## Étape 6 : Afficher le message de fin
```java
System.out.println("Process completed Successfully");
```
Enfin, un message s'affiche indiquant la fin du processus.
## Conclusion
Dans ce didacticiel, nous avons appris à récupérer des informations de calendrier à partir de fichiers MS Project à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez accéder et manipuler efficacement les données du projet dans vos applications Java.

## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec d’autres langages de programmation ?
R : Oui, Aspose.Tasks prend en charge plusieurs plates-formes et langages de programmation, notamment .NET, C.++, Python et Java.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir de l'aide pour Aspose.Tasks ?
R : Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks ?
 R : Oui, des licences temporaires sont disponibles à l'achat[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je trouver une documentation détaillée pour Aspose.Tasks ?
 R : Vous pouvez vous référer à la documentation[ici](https://reference.aspose.com/tasks/java/).