---
title: Čtení a zápis stupnice sazeb pro přiřazení zdrojů v Aspose.Tasks
linktitle: Čtení a zápis stupnice sazeb pro přiřazení zdrojů v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně spravovat škálování sazeb přidělování zdrojů v Aspose.Tasks for Java s tímto komplexním tutoriálem.
type: docs
weight: 20
url: /cs/java/resource-assignments/read-write-rate-scale/
---
## Úvod
V tomto tutoriálu se ponoříme do správy škály sazeb přiřazení zdrojů pomocí Aspose.Tasks for Java, robustní knihovny pro programovou práci se soubory Microsoft Project. Podle těchto kroků budete moci efektivně manipulovat s nastavením sazebníku pro přiřazení prostředků ve vašich aplikacích Java.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK).
2.  Aspose.Tasks for Java Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for Java z[tady](https://releases.aspose.com/tasks/java/).

## Importujte balíčky
Nejprve musíte importovat potřebné balíčky pro práci s funkcemi Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Krok 1: Nastavte svůj projekt
Začněte nastavením svého projektu Java a zahrňte knihovnu Aspose.Tasks do svých závislostí.
## Krok 2: Načtěte soubor projektu
Načtěte soubor projektu, se kterým chcete pracovat, do své Java aplikace.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Krok 3: Přidejte úkol
Přidejte do projektu nový úkol.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Krok 4: Definujte zdroje
Definujte materiální a nehmotné zdroje a specifikujte jejich druhy.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Krok 5: Přiřaďte zdroje k úkolu
Přiřaďte dříve definované zdroje k úkolu spolu s jejich typy stupnice sazeb.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Krok 6: Uložte projekt
Uložte projekt s upravenými přiřazeními zdrojů.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Krok 7: Načtení přiřazení zdrojů
Znovu načtěte uložený projekt a načtěte přiřazení zdrojů, abyste ověřili nastavení sazebníku.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Závěr
Správa stupnice sazeb přiřazení zdrojů v Aspose.Tasks for Java je zásadní pro efektivní řízení projektu. Podle tohoto podrobného průvodce můžete plynule manipulovat s nastavením stupnice sazeb pro přiřazení prostředků ve vašich aplikacích Java.
## FAQ
### Q1: Mohu použít Aspose.Tasks pro Java s jakýmkoli Java IDE?
Odpověď: Ano, Aspose.Tasks for Java je kompatibilní se všemi hlavními Java IDE, včetně IntelliJ IDEA, Eclipse a NetBeans.
### Q2: Podporuje Aspose.Tasks jiné formáty souborů kromě MPP?
Odpověď: Ano, Aspose.Tasks podporuje různé formáty souborů, včetně MPP, XML a HTML.
### Q3: Je Aspose.Tasks vhodný pro řízení projektů na podnikové úrovni?
Odpověď: Aspose.Tasks nabízí komplexní funkce pro správu projektů jakéhokoli rozsahu, takže je vhodný pro řízení projektů na podnikové úrovni.
### Otázka 4: Mohu přizpůsobit přiřazení zdrojů dále nad rámec sazeb?
Odpověď: Ano, Aspose.Tasks poskytuje rozsáhlé možnosti pro přizpůsobení přiřazení zdrojů, včetně úprav nákladů, práce a trvání.
### Q5: Existuje komunitní fórum pro podporu Aspose.Tasks?
 Odpověď: Ano, můžete najít podporu a komunikovat s ostatními uživateli na fóru Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).