---
title: Sledujte přesčasy, zbývající náklady a práci v Aspose.Tasks
linktitle: Sledujte přesčasy, zbývající náklady a práci v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se sledovat přesčasy, zbývající náklady a práci v projektech Java pomocí Aspose.Tasks. Snadné kroky pro efektivní řízení projektů.
weight: 18
url: /cs/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sledujte přesčasy, zbývající náklady a práci v Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíme, jak používat Aspose.Tasks pro Javu ke sledování přesčasů, zbývajících nákladů a práce na projektu. To může být neocenitelné pro projektové manažery a vedoucí týmů, aby zajistili, že projekty zůstanou na správné cestě a v rámci rozpočtu.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK): Aspose.Tasks for Java vyžaduje Java SE 6 nebo novější.
2.  Aspose.Tasks for Java Library: Stáhněte a nainstalujte knihovnu z[tady](https://releases.aspose.com/tasks/java/).
3. Integrované vývojové prostředí (IDE): Jakékoli Java IDE, jako je Eclipse, IntelliJ IDEA nebo NetBeans.

## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho souboru Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Krok 1: Nastavte Data Directory
Definujte adresář, kde je umístěn soubor projektu:
```java
String dataDir = "Your Data Directory";
```
 Nahradit`"Your Data Directory"` s cestou k souboru vašeho projektu.
## Krok 2: Načtěte projekt
 Instantovat a`Project` objekt a načtěte soubor projektu:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Nahradit`"ResourceAssignmentOvertimes.mpp"` s názvem souboru vašeho projektu.
## Krok 3: Iterujte přes přiřazení zdrojů
Projděte si každé přiřazení zdrojů v projektu:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Krok 4: Tisk přesčasových nákladů a práce
Získejte a vytiskněte přesčasové náklady a práci pro každé přiřazení zdrojů:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Krok 5: Vytiskněte zbývající náklady a práci
Načtěte a vytiskněte zbývající náklady a práci pro každé přiřazení zdrojů:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Krok 6: Vytiskněte zbývající přesčasové náklady a práci
Získejte a vytiskněte zbývající přesčasové náklady a práci pro každé přiřazení zdrojů:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Závěr
Sledování přesčasů, zbývajících nákladů a práce na projektu je zásadní pro úspěšné řízení projektu. S Aspose.Tasks for Java můžete snadno přistupovat k těmto informacím a sledovat je, čímž zajistíte, že vaše projekty zůstanou podle plánu a v rámci rozpočtu.
## FAQ
### Mohu použít Aspose.Tasks pro Javu s jinými Java knihovnami?
Ano, Aspose.Tasks for Java je kompatibilní s dalšími Java knihovnami a frameworky.
### Podporuje Aspose.Tasks různé formáty souborů projektu?
Ano, Aspose.Tasks podporuje různé formáty projektových souborů včetně MPP, XML a dalších.
### Je k dispozici zkušební verze?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Kde najdu podporu, pokud narazím na problémy?
 Můžete navštívit fórum Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15) pro podporu.
### Jak si mohu zakoupit licenci pro Aspose.Tasks?
 Licenci si můžete zakoupit od[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
