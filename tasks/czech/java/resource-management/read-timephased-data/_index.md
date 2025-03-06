---
title: Číst časově uspořádaná data pro zdroje v Aspose.Tasks
linktitle: Číst časově uspořádaná data pro zdroje v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se extrahovat časově uspořádaná data ze zdrojů MS Project pomocí Aspose.Tasks for Java. Výukový program krok za krokem.
weight: 15
url: /cs/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Číst časově uspořádaná data pro zdroje v Aspose.Tasks

## Úvod
V tomto tutoriálu vás provedeme procesem čtení časově uspořádaných dat pro prostředky MS Project pomocí Aspose.Tasks for Java. Tato knihovna poskytuje výkonné funkce pro programovou správu souborů Microsoft Project.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[webová stránka](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) a postupujte podle pokynů k instalaci.
2.  Aspose.Tasks for Java Library: Stáhněte si knihovnu Aspose.Tasks for Java z[stránka ke stažení](https://releases.aspose.com/tasks/java/) a postupujte podle pokynů k instalaci uvedených v dokumentaci.

## Importujte balíčky
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Krok 1: Nastavte Data Directory
Nejprve definujte adresář, kde se nachází váš soubor MS Project.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Přečtěte si soubor šablony projektu MS Project
Zadejte název souboru šablony MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Krok 3: Přečtěte si vstupní soubor jako projekt
Přečtěte si vstupní soubor pomocí Aspose.Tasks a načtěte jej jako objekt projektu.
```java
Project project = new Project(dataDir + fileName);
```
## Krok 4: Získejte zdroj podle ID
Získejte požadovaný zdroj z projektu podle jeho jedinečného identifikátoru (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Krok 5: Tisk časově uspořádaných dat pro práci se zdroji
Vytiskněte časově uspořádaná data pro práci se zdroji.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Krok 6: Tisk časově uspořádaných dat pro náklady na zdroje
Vytiskněte časově uspořádaná data pro náklady na zdroje.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Závěr
V tomto tutoriálu jsme se naučili číst časově uspořádaná data pro zdroje MS Project pomocí Aspose.Tasks pro Java. Pomocí těchto kroků můžete efektivně extrahovat cenné informace ze souborů projektu programově.
## FAQ
### Dokáže Aspose.Tasks zpracovat jiné typy souborů projektu kromě Microsoft Project?
Ano, Aspose.Tasks podporuje různé formáty souborů, včetně MPP, XML a CSV.
### Je Aspose.Tasks kompatibilní s různými vývojovými prostředími Java?
Ano, Aspose.Tasks je kompatibilní se všemi hlavními Java IDE a frameworky.
### Mohu manipulovat s daty projektu pomocí Aspose.Tasks?
Aspose.Tasks rozhodně poskytuje rozsáhlá API pro vytváření, úpravu a analýzu projektových dat.
### Je Aspose.Tasks vhodný pro projekty na podnikové úrovni?
Ano, Aspose.Tasks je široce používán v podnikových prostředích díky své spolehlivosti a škálovatelnosti.
### Kde najdu podporu, pokud při používání Aspose.Tasks narazím na problémy?
 Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za pomoc od komunity a podpůrného týmu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
