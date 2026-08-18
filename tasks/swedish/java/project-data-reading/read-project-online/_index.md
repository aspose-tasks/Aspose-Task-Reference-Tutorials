---
date: 2026-02-18
description: Lär dig hur du läser MS Project Online‑data med Aspose Tasks Java. Den
  här guiden visar hur du hämtar projektlista, listar SharePoint‑projekt och får resursantalet.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java: Enkel läsning av MS Project Online-data'
url: /sv/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Enkel läsning av MS Project Online-data

## Introduction
I projektledningsvärlden är det avgörande att hantera Microsoft Project Online-data på ett effektivt sätt för smidiga processer. **aspose tasks java** erbjuder ett robust, lätt‑använt API som låter dig läsa Project Online-data utan att kämpa med låg‑nivå HTTP-anrop. I den här handledningen går vi igenom hur du hämtar en projektlista, **list SharePoint projects**, och **get resource count** från varje projekt — allt med bara några rader Java‑kod.

## Quick Answers
- **Vad gör aspose tasks java?** Den läser och manipulerar Microsoft Project‑filer och Project Online‑data programmässigt.  
- **Behöver jag en licens för att prova det?** En gratis provperiod finns tillgänglig; en licens krävs för produktionsanvändning.  
- **Vilka autentiseringsuppgifter krävs?** SharePoint‑domän, användarnamn och lösenord (eller Azure AD‑token).  
- **Kan jag lista SharePoint‑projekt?** Ja – använd `ProjectServerManager.getProjectList()` för att hämta dem.  
- **Hur får jag antalet resurser?** Läs in varje `Project`‑objekt och anropa `project.getResources().size()`.

## Vad är aspose tasks java?
**aspose tasks java** är ett utvecklar‑inriktat bibliotek som abstraherar komplexiteten i Microsoft Projects filformat och Project Server REST‑API. Det möjliggör att läsa, skapa och modifiera projektdata direkt från Java‑applikationer, vilket gör integration med befintliga företagsystem enkel.

## Varför använda aspose tasks java för att läsa MS Project Online?
- **Ingen manuell HTTP‑hantering** – biblioteket sköter autentisering och REST‑anrop.  
- **Stark typ‑säkerhet** – arbeta med `Project`, `ProjectInfo` och andra POJO‑klasser istället för rå JSON.  
- **Plattformsoberoende** – körs i alla JVM‑kompatibla miljöer.  
- **Rik funktionsuppsättning** – förutom läsning kan du också uppdatera uppgifter, resurser och tidslinjer.  
- **Utnyttjar internt Project Server REST‑API**, så du får ett stabilt, supportat kommunikationslager.

## Förutsättningar
1. **Java Development Kit (JDK)** – JDK 8 eller högre installerat.  
2. **Aspose.Tasks for Java‑biblioteket** – ladda ner det från [here](https://releases.aspose.com/tasks/java/).  
3. **Microsoft Project Online‑konto** – med behörighet att läsa projekt.  
4. **SharePoint‑domänadress** – där din Project Online‑instans finns.  
5. **Användarnamn och lösenord** – eller lämpliga Azure AD‑uppgifter för autentisering.

## Importera paket
Först importerar du de väsentliga Aspose.Tasks‑klasserna som vi kommer att använda genom hela handledningen:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Steg 1: Ange SharePoint‑domän, användarnamn och lösenord
Definiera anslutningsdetaljerna för din Project Online‑miljö. Ersätt platshållarvärdena med dina egna autentiseringsuppgifter.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Steg 2: Autentisera med Project Server‑uppgifter
Skapa ett `ProjectServerCredentials`‑objekt och initiera en `ProjectServerManager`. Denna manager hanterar alla efterföljande anrop till Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Steg 3: Hämta projektlista och visa information
Använd managern för att **hämta projektlistan** (dvs. lista SharePoint‑projekt) och skriv ut grundläggande detaljer som namn, skapandedatum och senast sparat datum.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Steg 4: Ladda enskilda projekt och skriv ut resursantal
För varje projekt som returnerades i föregående steg, ladda hela `Project`‑objektet — detta anrop **laddar projektdata** för det specifika ID‑t — och visa **resursantalet**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Authentication failed** | Fel domän, användarnamn eller lösenord. | Verifiera autentiseringsuppgifter och säkerställ att kontot har läsbehörighet för Project Online. |
| **SSLHandshakeException** | Java‑runtime saknar den erforderliga TLS‑versionen. | Uppdatera JDK till den senaste versionen eller aktivera TLS 1.2+. |
| **`reader.getProjectList()` returns empty** | Kontot har ingen åtkomst till några projekt. | Kontrollera behörigheter i Project Online eller använd ett administratörskonto. |
| **Large projects cause OutOfMemoryError** | Att ladda många projekt samtidigt förbrukar minnet. | Ladda projekt ett i taget och frigör referenser efter användning. |

## Vanliga frågor
**Q:** Kan jag använda aspose tasks java för att modifiera MS Project Online‑data?  
**A:** Ja, Aspose.Tasks erbjuder omfattande funktioner för både läsning **och** modifiering av Project Online‑data programmässigt.

**Q:** Stöder Aspose.Tasks andra filformat för projektledning?  
**A:** Absolut. Det stödjer MPP, XML, Primavera och många fler, vilket säkerställer kompatibilitet över olika projekt‑ekosystem.

**Q:** Finns det en gratis provperiod för Aspose.Tasks för Java?  
**A:** Ja, du kan få en gratis provperiod från [here](https://releases.aspose.com/) för att utforska funktionerna och möjligheterna i Aspose.Tasks.

**Q:** Var kan jag hitta omfattande dokumentation för Aspose.Tasks för Java?  
**A:** Du kan hänvisa till den detaljerade dokumentationen [here](https://reference.aspose.com/tasks/java/) för en komplett vägledning om hur du använder Aspose.Tasks i dina Java‑projekt.

**Q:** Vilka supportalternativ finns för Aspose.Tasks för Java?  
**A:** Om du stöter på problem eller har frågor kan du söka hjälp i Aspose.Tasks‑community‑forumet [here](https://forum.aspose.com/c/tasks/15).

---

**Senast uppdaterad:** 2026-02-18  
**Testad med:** Aspose.Tasks for Java 24.11 (senaste vid skrivande)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}