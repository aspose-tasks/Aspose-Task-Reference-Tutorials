---
title: Zastavte a obnovte přiřazení zdrojů v Aspose.Tasks
linktitle: Zastavte a obnovte přiřazení zdrojů v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se, jak efektivně spravovat přiřazení zdrojů v Aspose.Tasks for Java s tímto podrobným tutoriálem.
weight: 23
url: /cs/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastavte a obnovte přiřazení zdrojů v Aspose.Tasks

## Úvod
V tomto tutoriálu se naučíme, jak zastavit a obnovit přiřazení zdrojů pomocí Aspose.Tasks for Java. Aspose.Tasks je výkonné Java API, které umožňuje vývojářům pracovat se soubory aplikace Microsoft Project, aniž by na jejich systémech potřebovali nainstalovaný Microsoft Project. Tento proces rozdělíme do zvládnutelných kroků, aby bylo snadné jej sledovat.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Tasks pro knihovnu Java staženy. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/java/).
- Základní znalost programování v Javě.
## Importujte balíčky
Nejprve importujme potřebné balíčky do našeho projektu Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Krok 1: Načtěte soubor projektu
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Data Directory";
// Načtěte soubor projektu
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 V tomto kroku načteme soubor projektu do a`Project` objekt pomocí cesty k souboru.
## Krok 2: Iterujte přes přiřazení zdrojů
```java
// Definujte minimální datum
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterujte přes přiřazení zdrojů
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Zde definujeme minimální datum a začneme iterovat každé přiřazení zdrojů v projektu.
## Krok 3: Zkontrolujte data ukončení a obnovení
```java
    // Zkontrolujte datum zastavení
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Zkontrolujte datum obnovení
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
V tomto kroku zkontrolujeme, zda data ukončení a obnovení každého přiřazení zdroje jsou před minimálním datem. Pokud jsou, vytiskneme „NA“, jinak vytiskneme příslušná data.
## Závěr
V tomto tutoriálu jsme se naučili, jak zastavit a obnovit přiřazení zdrojů v Aspose.Tasks for Java. Podle uvedených kroků můžete tuto funkci snadno implementovat do svých projektů Java.

## FAQ
### Mohu používat Aspose.Tasks bez nainstalovaného Microsoft Project?
Ano, Aspose.Tasks vám umožňuje pracovat se soubory aplikace Microsoft Project bez nutnosti instalace aplikace Microsoft Project ve vašem systému.
### Kde najdu další dokumentaci?
 Můžete najít podrobnou dokumentaci[tady](https://reference.aspose.com/tasks/java/).
### Je k dispozici bezplatná zkušební verze?
 Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat podporu, pokud narazím na nějaké problémy?
Můžete získat podporu od komunity[tady](https://forum.aspose.com/c/tasks/15).
### Mohu si zakoupit dočasnou licenci?
 Ano, můžete si zakoupit dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
