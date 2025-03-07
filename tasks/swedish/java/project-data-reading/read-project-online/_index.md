---
title: Enkel MS Project Online Data Reading med Aspose.Tasks
linktitle: Läsa projekt onlinedata i Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Lär dig hur du enkelt läser Microsoft Project Online-data med Aspose.Tasks för Java. Förbättra dina projektledningsmöjligheter.
weight: 13
url: /sv/java/project-data-reading/read-project-online/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enkel MS Project Online Data Reading med Aspose.Tasks

## Introduktion
När det gäller projektledning är hantering av Microsoft Project Online-data effektivt avgörande för en strömlinjeformad verksamhet. Aspose.Tasks för Java tillhandahåller en robust lösning för att enkelt läsa sådana data. Den här handledningen går ut på att utnyttja Aspose.Tasks för att komma åt och manipulera MS Project Online-data sömlöst.
## Förutsättningar
Innan du dyker in i den här handledningen, se till att du har följande:
1. Java Development Kit (JDK): Installera JDK för att kompilera och köra Java-program.
2.  Aspose.Tasks for Java Library: Ladda ner och inkludera Aspose.Tasks-biblioteket i ditt Java-projekt. Du kan skaffa den från[här](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online-konto: Skaffa giltiga referenser för åtkomst till MS Project Online-data.
4. SharePoint-domänadress: SharePoint-domänadressen där dina MS Project Online-data finns.
5. Användarnamn och lösenord: Inloggningsuppgifter för autentisering av åtkomst till MS Project Online.
## Importera paket
Importera de nödvändiga Aspose.Tasks-paketen för sömlös integration i ditt Java-projekt:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Steg 1: Ställ in SharePoint-domänadress, användarnamn och lösenord
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Byta ut`"https://contoso.sharepoint.com"` med din SharePoint-domänadress,`"admin@contoso.onmicrosoft.com"` med ditt användarnamn och`"MyPassword"` med ditt lösenord.
## Steg 2: Autentisera med inloggningsuppgifter för Project Server
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Skapa`ProjectServerCredentials` objekt med SharePoint-domänadressen, användarnamnet och lösenordet. Initiera sedan`ProjectServerManager` med dessa meriter.
## Steg 3: Hämta projektlista och visa information
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Iterera genom projektlistan erhållen från`reader.getProjectList()` och visa projektdetaljer som namn, skapelsedatum och senast sparade datum.
## Steg 4: Ladda individuella projekt och antal outputresurser
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 För varje projekt, ladda det med`reader.getProject(p.getId())` och mata ut projektnamnet tillsammans med antalet associerade resurser.

## Slutsats
Aspose.Tasks för Java förenklar processen att läsa MS Project Online-data, och erbjuder utvecklare en kraftfull verktygsuppsättning för att effektivisera projektledningsuppgifter. Genom att följa denna handledning kan du effektivt integrera Aspose.Tasks i dina Java-applikationer för att enkelt komma åt och manipulera projektdata.
## FAQ's
### F: Kan jag använda Aspose.Tasks för Java för att ändra MS Project Online-data?
S: Ja, Aspose.Tasks tillhandahåller omfattande möjligheter för att inte bara läsa utan också modifiera MS Project Online-data programmatiskt.
### F: Stöder Aspose.Tasks andra filformat för projekthantering?
S: Absolut, Aspose.Tasks stöder olika filformat inklusive MPP, XML och mer, vilket säkerställer kompatibilitet med olika projektledningssystem.
### F: Finns det en gratis testversion tillgänglig för Aspose.Tasks för Java?
 S: Ja, du kan utnyttja en gratis provperiod från[här](https://releases.aspose.com/) för att utforska funktionerna och funktionerna i Aspose.Tasks.
### F: Var kan jag hitta omfattande dokumentation för Aspose.Tasks för Java?
 S: Du kan hänvisa till den detaljerade dokumentationen[här](https://reference.aspose.com/tasks/java/)för omfattande vägledning om hur du använder Aspose.Tasks i dina Java-projekt.
### F: Vilka supportalternativ finns tillgängliga för Aspose.Tasks för Java?
 S: Om du stöter på några problem eller har frågor kan du söka hjälp från Aspose.Tasks communityforum[här](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
