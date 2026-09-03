---
date: 2026-05-31
description: Lär dig hur du får projektversion och hämtar datum för senaste sparning
  från MS Project‑filer med Aspose.Tasks för Java. Steg‑för‑steg‑guide med kodexempel.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Bestäm projektversion med Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Hur man får projektversion – Aspose Tasks Java‑handledning
url: /sv/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man hämtar projektversion – Aspose Tasks Java-handledning

I den här **Aspose Tasks Java-handledningen** lär du dig **hur du får projektversionen** för en Microsoft Project‑fil och även hur du **hämtar datum för senaste sparning** med Aspose.Tasks‑biblioteket för Java. Att känna till filversionen och spar‑tidsstämpeln hjälper dig undvika kompatibilitetsproblem, upprätthålla migrationspolicyer och hålla korrekta audit‑loggar. Vi går igenom varje steg—från miljöinställning till utskrift av version och datum—så att du kan bädda in denna kontroll i vilken Java‑applikation som helst med förtroende.

## Snabba svar
- **Vad täcker den här handledningen?** Att bestämma MS Project‑filens version och datum för senaste sparning med Aspose.Tasks för Java.  
- **Behöver jag ha Microsoft Project installerat?** Nej, Aspose.Tasks fungerar oberoende av Microsoft Project.  
- **Vilka filformat stöds?** XML‑baserade Project‑filer såsom MPP och XML stöds fullt ut.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för en grundläggande versionskontroll.  
- **Krävs en licens?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktionsbruk.

## Vad är Aspose Tasks Java-handledning?
`Aspose.Tasks` Java‑handledningen är en kort, praktisk guide som visar hur du interagerar med Microsoft Project‑data programmässigt. Den visar hur du läser, ändrar och analyserar projektinformation utan att behöva Microsoft Project installerat på servern. Dessutom täcker den inläsning av filer, åtkomst till egenskaper och sparande av ändringar, vilket möjliggör automatisering av projektledningsuppgifter på ett effektivt sätt.

## Varför använda Aspose.Tasks för att bestämma projektversion?
Aspose.Tasks tillhandahåller **exakt versionsmetadata** och **tidstämplar för senaste sparning** på alla operativsystem som stödjer Java. Det bearbetar filer på upp till **500 sidor på under 2 sekunder** på en standard‑2,5 GHz‑CPU, vilket gör det idealiskt för batch‑automatisering och storskaliga migrationsscenario.

## Förutsättningar
Innan vi börjar, se till att du har:

1. **Java Development Kit (JDK)** – version 8 eller nyare.  
2. **Aspose.Tasks för Java JAR** – ladda ner från [webbplatsen](https://releases.aspose.com/tasks/java/) och lägg till den i ditt projekts classpath.  
3. **MS Project‑fil** – en XML‑baserad Project‑fil (t.ex. `input.xml`) som du vill undersöka.  

> **Proffstips:** Förvara projektfilen i en dedikerad `data`‑mapp för att hålla sökvägar organiserade och undvika oavsiktliga överskrivningar.

## Importera paket
Först importerar du de väsentliga Aspose.Tasks‑klasserna:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Hur man ställer in projektkatalogen
För att korrekt lokalisera dina projektfiler, skapa en dedikerad katalog inom din applikationsstruktur och lagra alla indatafiler där. Detta håller koden ren och undviker sökvägsrelaterade fel vid inläsning av filer. Använd ett tydligt variabelnamn för katalogsökvägen, som kan vara absolut eller relativt till projektroten.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Ersätt `"Your Data Directory"` med den absoluta eller relativa sökvägen där `input.xml` finns.

## Hur man laddar projektet
`Project` är det primära Aspose.Tasks‑objektet som representerar en Microsoft Project‑fil i minnet och ger dig åtkomst till alla projekt‑egenskaper och samlingar. Efter att du skapat `Project`‑instansen kan du fråga dess fält, iterera över uppgifter eller modifiera data innan du sparar filen tillbaka till disk.

```java
Project project = new Project(dataDir + "input.xml");
```

Om din fil har ett annat namn, justera `"input.xml"` därefter.

## Hur man bestämmer projektversion
`Prj.SAVE_VERSION` är en egenskap som indikerar versionsnumret för Microsoft Project som sparade filen. `Prj.LAST_SAVED` är en egenskap som lagrar datum och tid då filen senast sparades. `Prj.SAVE_VERSION` returnerar den numeriska versionen av Microsoft Project‑applikationen som sparade filen (t.ex. 12 för Project 2010). `Prj.LAST_SAVED` ger exakt datum och tid för den senaste sparningsoperationen.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Dessa värden låter dig programmässigt verkställa versionsspecifika affärsregler eller generera audit‑rapporter.

## Hur man visar resultatet
Efter att ha hämtat version‑ och senaste‑sparningsinformationen vill du vanligtvis skriva ut den till konsolen eller en loggfil. Använd `System.out.println` för att visa värdena, formatera datumet efter behov. Detta bekräftar att extraktionen lyckades och ger omedelbar återkoppling under utveckling eller i automatiserade skript.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|--------|-----|
| `NullPointerException` på `project.get(...)` | Filen hittades inte eller felaktig sökväg | Verifiera `dataDir` och filnamn; använd en absolut sökväg för testning. |
| Oväntat versionsnummer (t.ex. 0) | Laddar en icke‑Project‑XML‑fil | Säkerställ att filen är en giltig Microsoft Project‑fil (MPP/XML). |
| Licensundantag | Använder provversion utan giltig licens i produktion | Applicera din Aspose.Tasks‑licens (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Vanliga frågor

**Q: Kan jag använda Aspose.Tasks med andra programmeringsspråk?**  
A: Ja, Aspose.Tasks stödjer .NET, Java och C++ bland andra.

**Q: Är Aspose.Tasks lämplig för storskaliga projekt?**  
A: Absolut; den kan bearbeta projekt med flera hundra sidor på sekunder utan att ladda hela filen i minnet.

**Q: Kan jag anpassa projektdata med Aspose.Tasks?**  
A: Ja, du kan modifiera uppgifter, resurser, kalendrar och alla andra projekteelement via API‑et.

**Q: Kräver Aspose.Tasks Microsoft Project‑installation?**  
A: Nej, biblioteket fungerar oberoende och kräver inte Microsoft Project på värdmaskinen.

**Q: Finns teknisk support för Aspose.Tasks?**  
A: Ja, du kan få hjälp i Aspose.Tasks‑forumet [här](https://forum.aspose.com/c/tasks/15).

**Ytterligare Q&A**

**Q: Hur hämtar jag andra projektegenskaper (t.ex. författare, företag)?**  
A: Använd `project.get(Prj.AUTHOR)` eller `project.get(Prj.COMPANY)` på samma sätt som du hämtar versionen.

**Q: Kan jag kontrollera versionen av en MPP (binär) fil?**  
A: Ja, Aspose.Tasks laddar `.mpp`‑filer direkt; `Prj.SAVE_VERSION`‑egenskapen fungerar även för binära format.

**Q: Finns det ett sätt att programatiskt uppgradera en äldre projektfil till en nyare version?**  
A: Ladda den äldre filen och spara den sedan med `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks skriver filen i det senaste formatet som standard.

## Slutsats
Du har nu lärt dig **hur du får projektversionen** och **hämtar datum för senaste sparning** från MS Project‑filer med Aspose.Tasks för Java. Inkludera dessa kodsnuttar i automatiseringspipeline, rapportverktyg eller migrationsverktyg för att garantera att du alltid vet exakt vilken Project‑version du hanterar.

---

**Senast uppdaterad:** 2026-05-31  
**Testat med:** Aspose.Tasks för Java 24.11  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Ställ in projektets startdatum i MS Project med Aspose.Tasks för Java](/tasks/java/project-properties/write-project-info/)
- [Läs Microsoft Project‑databas med Aspose.Tasks för Java](/tasks/java/project-data-reading/read-project-database/)
- [Spara projekt som mall, CSV och text med Aspose.Tasks för Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}