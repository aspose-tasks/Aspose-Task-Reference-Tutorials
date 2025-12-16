---
date: 2025-12-15
description: Leer hoe je MS Project Online-gegevens kunt lezen met Aspose Tasks Java.
  Deze gids laat zien hoe je de projectlijst kunt ophalen, SharePoint-projecten kunt
  weergeven en het aantal resources kunt verkrijgen.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose.Tasks Java - moeiteloos MS Project Online-gegevens lezen'
url: /nl/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: moeiteloos MS Project Online-gegevens lezen

## Introductie
In de wereld van projectmanagement is het efficiënt verwerken van Microsoft Project Online-gegevens cruciaal voor gestroomlijnde processen. **aspose tasks java** biedt een robuuste, gebruiksvriendelijke API waarmee u Project Online-gegevens kunt lezen zonder te worstelen met low‑level HTTP‑aanroepen. In deze tutorial lopen we stap voor stap door hoe u een projectlijst kunt ophalen, SharePoint-projecten kunt weergeven en het aantal resources per project kunt verkrijgen — allemaal met slechts een paar regels Java-code.

## Snelle antwoorden
- **Wat doet aspose tasks java?** Het leest en bewerkt Microsoft Project‑bestanden en Project Online‑gegevens programmatisch.  
- **Heb ik een licentie nodig om het te proberen?** Er is een gratis proefversie beschikbaar; een licentie is vereist voor productiegebruik.  
- **Welke inloggegevens zijn vereist?** SharePoint-domein, gebruikersnaam en wachtwoord (of Azure AD-token).  
- **Kan ik SharePoint-projecten weergeven?** Ja – gebruik `ProjectServerManager.getProjectList()` om ze op te halen.  
- **Hoe krijg ik het aantal resources?** Laad elk `Project`-object en roep `project.getResources().size()` aan.

## Wat is aspose tasks java?
**aspose tasks java** is een op ontwikkelaars gerichte bibliotheek die de complexiteit van Microsoft Project-bestandsformaten en Project Server REST‑API's abstraheert. Het stelt u in staat om projectgegevens direct vanuit Java-toepassingen te lezen, te maken en te wijzigen, waardoor integratie met bestaande enterprise-systemen eenvoudig wordt.

## Waarom aspose tasks java gebruiken voor het lezen van MS Project Online?
- **Geen handmatige HTTP‑afhandeling** – de bibliotheek regelt authenticatie en REST‑aanroepen.  
- **Sterke type‑veiligheid** – werk met `Project`, `ProjectInfo` en andere POJO's in plaats van ruwe JSON.  
- **Cross‑platform** – draait op elke JVM‑compatibele omgeving.  
- **Rijke functionaliteit** – naast lezen kunt u ook taken, resources en tijdlijnen bijwerken.

## Voorwaarden
Zorg ervoor dat u het volgende heeft voordat u begint:

1. **Java Development Kit (JDK)** – JDK 8 of hoger geïnstalleerd.  
2. **Aspose.Tasks for Java bibliotheek** – download deze van [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online-account** – met rechten om projecten te lezen.  
4. **SharePoint-domeinadres** – waar uw Project Online‑instantie zich bevindt.  
5. **Gebruikersnaam en wachtwoord** – of passende Azure AD-inloggegevens voor authenticatie.

## Pakketten importeren
Importeer eerst de essentiële Aspose.Tasks-klassen die we gedurende de tutorial zullen gebruiken:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Stap 1: SharePoint-domein, gebruikersnaam en wachtwoord instellen
Definieer de verbindingsdetails voor uw Project Online‑omgeving. Vervang de placeholder-waarden door uw eigen inloggegevens.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Stap 2: Authenticeren met Project Server-inloggegevens
Maak een `ProjectServerCredentials`-object aan en initialiseert een `ProjectServerManager`. Deze manager behandelt alle volgende aanroepen naar Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Stap 3: Projectlijst ophalen en informatie weergeven
Gebruik de manager om de **projectlijst op te halen** (SharePoint-projecten weergeven) en druk basisgegevens af zoals naam, aanmaakdatum en datum van laatste opslaan.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Stap 4: Individuele projecten laden en resource-aantal weergeven
Voor elk project dat in de vorige stap is geretourneerd, laad het volledige `Project`-object en toon het **resource-aantal**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Authenticatie mislukt** | Onjuist domein, gebruikersnaam of wachtwoord. | Controleer de inloggegevens en zorg ervoor dat het account leesrechten heeft voor Project Online. |
| **SSLHandshakeException** | Java-runtime mist de vereiste TLS‑versie. | Update de JDK naar de nieuwste release of schakel TLS 1.2+ in. |
| **`reader.getProjectList()` returns empty** | Account heeft geen toegang tot projecten. | Controleer de Project Online-rechten of gebruik een admin-account. |
| **Grote projecten veroorzaken OutOfMemoryError** | Het tegelijk laden van veel projecten verbruikt geheugen. | Laad projecten één voor één en maak referenties vrij na gebruik. |

## Veelgestelde vragen
### V: Kan ik aspose tasks java gebruiken om MS Project Online-gegevens te wijzigen?
A: Ja, Aspose.Tasks biedt uitgebreide mogelijkheden voor zowel het lezen **als** het wijzigen van Project Online-gegevens programmatisch.

### V: Ondersteunt Aspose.Tasks andere bestandsformaten voor projectmanagement?
A: Absoluut. Het ondersteunt MPP, XML, Primavera en nog veel meer, waardoor compatibiliteit met diverse project-ecosystemen wordt gegarandeerd.

### V: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor Java?
A: Ja, u kunt een gratis proefversie krijgen via [here](https://releases.aspose.com/) om de functies en mogelijkheden van Aspose.Tasks te verkennen.

### V: Waar kan ik uitgebreide documentatie vinden voor Aspose.Tasks voor Java?
A: U kunt de gedetailleerde documentatie raadplegen [here](https://reference.aspose.com/tasks/java/) voor uitgebreide begeleiding bij het gebruiken van Aspose.Tasks in uw Java-projecten.

### V: Welke ondersteuningsopties zijn beschikbaar voor Aspose.Tasks voor Java?
A: Als u problemen ondervindt of vragen heeft, kunt u hulp zoeken op het Aspose.Tasks-communityforum [here](https://forum.aspose.com/c/tasks/15).

---

**Laatst bijgewerkt:** 2025-12-15  
**Getest met:** Aspose.Tasks for Java 24.11 (laatste versie op het moment van schrijven)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}