---
title: Moeiteloos MS Project online gegevens lezen met Aspose.Tasks
linktitle: Online projectgegevens lezen in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Leer hoe u moeiteloos Microsoft Project Online-gegevens kunt lezen met Aspose.Tasks voor Java. Verbeter uw projectmanagementmogelijkheden.
type: docs
weight: 13
url: /nl/java/project-data-reading/read-project-online/
---
## Invoering
Op het gebied van projectmanagement is het efficiënt omgaan met Microsoft Project Online-gegevens cruciaal voor gestroomlijnde activiteiten. Aspose.Tasks voor Java biedt een robuuste oplossing voor het moeiteloos lezen van dergelijke gegevens. Deze tutorial gaat dieper in op het gebruik van Aspose.Tasks om naadloos toegang te krijgen tot MS Project Online-gegevens en deze te manipuleren.
## Vereisten
Voordat u in deze zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:
1. Java Development Kit (JDK): Installeer JDK om Java-programma's te compileren en uit te voeren.
2.  Aspose.Tasks voor Java-bibliotheek: Download de Aspose.Tasks-bibliotheek en neem deze op in uw Java-project. Je kunt het verkrijgen via[hier](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online-account: verkrijg geldige referenties voor toegang tot MS Project Online-gegevens.
4. SharePoint-domeinadres: het SharePoint-domeinadres waar uw MS Project Online-gegevens zich bevinden.
5. Gebruikersnaam en wachtwoord: referenties voor het verifiëren van toegang tot MS Project Online.
## Pakketten importeren
Importeer in uw Java-project de benodigde Aspose.Tasks-pakketten voor een naadloze integratie:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Stap 1: Stel het SharePoint-domeinadres, de gebruikersnaam en het wachtwoord in
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Vervangen`"https://contoso.sharepoint.com"` met uw SharePoint-domeinadres,`"admin@contoso.onmicrosoft.com"` met uw gebruikersnaam, en`"MyPassword"` met uw wachtwoord.
## Stap 2: Verifieer met Project Server-referenties
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Creëren`ProjectServerCredentials` object met het SharePoint-domeinadres, de gebruikersnaam en het wachtwoord. Initialiseer vervolgens`ProjectServerManager` met deze legitimatiebewijzen.
## Stap 3: Projectlijst ophalen en informatie weergeven
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Blader door de projectlijst verkregen van`reader.getProjectList()` en projectdetails weergeven, zoals naam, aanmaakdatum en laatst opgeslagen datum.
## Stap 4: Laad individuele projecten en voer het aantal bronnen uit
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Voor elk project laadt u het met behulp van`reader.getProject(p.getId())` en voer de projectnaam uit samen met het aantal bijbehorende bronnen.

## Conclusie
Aspose.Tasks voor Java vereenvoudigt het proces van het lezen van MS Project Online-gegevens en biedt ontwikkelaars een krachtige toolset om projectbeheertaken te stroomlijnen. Door deze tutorial te volgen, kunt u Aspose.Tasks efficiënt integreren in uw Java-applicaties, zodat u gemakkelijk projectgegevens kunt openen en manipuleren.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor Java gebruiken om MS Project Online-gegevens te wijzigen?
A: Ja, Aspose.Tasks biedt uitgebreide mogelijkheden om niet alleen MS Project Online-gegevens te lezen, maar ook programmatisch te wijzigen.
### Vraag: Ondersteunt Aspose.Tasks andere bestandsindelingen voor projectbeheer?
A: Absoluut, Aspose.Tasks ondersteunt verschillende bestandsformaten, waaronder MPP, XML en meer, waardoor compatibiliteit met diverse projectmanagementsystemen wordt gegarandeerd.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor Java?
 A: Ja, u kunt profiteren van een gratis proefperiode van[hier](https://releases.aspose.com/) om de kenmerken en functionaliteiten van Aspose.Tasks te verkennen.
### Vraag: Waar kan ik uitgebreide documentatie vinden voor Aspose.Tasks voor Java?
 A: U kunt de gedetailleerde documentatie raadplegen[hier](https://reference.aspose.com/tasks/java/)voor uitgebreide begeleiding bij het gebruik van Aspose.Tasks in uw Java-projecten.
### Vraag: Welke ondersteuningsopties zijn beschikbaar voor Aspose.Tasks voor Java?
 A: Als u problemen ondervindt of vragen heeft, kunt u hulp zoeken op het Aspose.Tasks-communityforum[hier](https://forum.aspose.com/c/tasks/15).