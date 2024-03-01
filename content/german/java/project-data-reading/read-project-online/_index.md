---
title: Müheloses Lesen von MS Project-Online-Daten mit Aspose.Tasks
linktitle: Lesen von Projekt-Onlinedaten in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java mühelos Microsoft Project Online-Daten lesen. Erweitern Sie Ihre Projektmanagementfähigkeiten.
type: docs
weight: 13
url: /de/java/project-data-reading/read-project-online/
---
## Einführung
Im Bereich des Projektmanagements ist der effiziente Umgang mit Microsoft Project Online-Daten für einen reibungslosen Betrieb von entscheidender Bedeutung. Aspose.Tasks für Java bietet eine robuste Lösung zum mühelosen Lesen solcher Daten. Dieses Tutorial befasst sich mit der Nutzung von Aspose.Tasks für den nahtlosen Zugriff auf und die Bearbeitung von MS Project Online-Daten.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java Development Kit (JDK): Installieren Sie JDK, um Java-Programme zu kompilieren und auszuführen.
2.  Aspose.Tasks für Java-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek herunter und fügen Sie sie in Ihr Java-Projekt ein. Sie können es erwerben bei[Hier](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online-Konto: Erhalten Sie gültige Anmeldeinformationen für den Zugriff auf MS Project Online-Daten.
4. SharePoint-Domänenadresse: Die SharePoint-Domänenadresse, unter der sich Ihre MS Project Online-Daten befinden.
5. Benutzername und Passwort: Anmeldeinformationen zur Authentifizierung des Zugriffs auf MS Project Online.
## Pakete importieren
Importieren Sie in Ihr Java-Projekt die erforderlichen Aspose.Tasks-Pakete für eine nahtlose Integration:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Schritt 1: Legen Sie die SharePoint-Domänenadresse, den Benutzernamen und das Passwort fest
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
 Ersetzen`"https://contoso.sharepoint.com"` mit Ihrer SharePoint-Domänenadresse,`"admin@contoso.onmicrosoft.com"` mit Ihrem Benutzernamen und`"MyPassword"` mit Ihrem Passwort.
## Schritt 2: Authentifizieren Sie sich mit Project Server-Anmeldeinformationen
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
 Erstellen`ProjectServerCredentials` Objekt mit der SharePoint-Domänenadresse, dem Benutzernamen und dem Passwort. Dann initialisieren`ProjectServerManager` mit diesen Zeugnissen.
## Schritt 3: Projektliste abrufen und Informationen anzeigen
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
 Durchlaufen Sie die von erhaltene Projektliste`reader.getProjectList()` und zeigen Sie Projektdetails wie Name, Erstellungsdatum und letztes Speicherdatum an.
## Schritt 4: Laden Sie einzelne Projekte und geben Sie die Ressourcenanzahl aus
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
 Laden Sie es für jedes Projekt mit`reader.getProject(p.getId())` und geben Sie den Projektnamen zusammen mit der Anzahl der zugehörigen Ressourcen aus.

## Abschluss
Aspose.Tasks für Java vereinfacht das Lesen von MS Project Online-Daten und bietet Entwicklern ein leistungsstarkes Toolset zur Rationalisierung von Projektmanagementaufgaben. Wenn Sie diesem Tutorial folgen, können Sie Aspose.Tasks effizient in Ihre Java-Anwendungen integrieren, um problemlos auf Projektdaten zuzugreifen und diese zu bearbeiten.
## FAQs
### F: Kann ich Aspose.Tasks für Java verwenden, um MS Project Online-Daten zu ändern?
A: Ja, Aspose.Tasks bietet umfangreiche Funktionen nicht nur zum Lesen, sondern auch zum programmgesteuerten Ändern von MS Project Online-Daten.
### F: Unterstützt Aspose.Tasks andere Projektmanagement-Dateiformate?
A: Auf jeden Fall unterstützt Aspose.Tasks verschiedene Dateiformate, darunter MPP, XML und mehr, und gewährleistet so die Kompatibilität mit verschiedenen Projektmanagementsystemen.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für Java?
 A: Ja, Sie können eine kostenlose Testversion nutzen[Hier](https://releases.aspose.com/) um die Features und Funktionalitäten von Aspose.Tasks zu erkunden.
### F: Wo finde ich eine umfassende Dokumentation für Aspose.Tasks für Java?
 A: Sie können sich auf die ausführliche Dokumentation beziehen[Hier](https://reference.aspose.com/tasks/java/)Für umfassende Anleitungen zur Verwendung von Aspose.Tasks in Ihren Java-Projekten.
### F: Welche Supportoptionen stehen für Aspose.Tasks für Java zur Verfügung?
 A: Wenn Sie auf Probleme stoßen oder Fragen haben, können Sie sich an das Aspose.Tasks-Community-Forum wenden[Hier](https://forum.aspose.com/c/tasks/15).