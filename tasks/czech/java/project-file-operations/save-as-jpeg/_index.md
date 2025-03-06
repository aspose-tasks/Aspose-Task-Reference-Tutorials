---
title: Převést MS Project jako JPEG v Aspose.Tasks
linktitle: Uložit projekt jako JPEG v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Naučte se snadno převádět soubory Microsoft Project na obrázky JPEG pomocí Aspose.Tasks for Java. Zvyšte svou produktivitu.
weight: 20
url: /cs/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převést MS Project jako JPEG v Aspose.Tasks

## Úvod
V tomto tutoriálu prozkoumáme, jak uložit soubor Microsoft Project jako obrázek JPEG pomocí Aspose.Tasks for Java. To může být užitečné zejména pro sdílení projektových vizualizací nebo integraci projektových dat do sestav nebo prezentací.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu. Nejnovější verzi si můžete stáhnout a nainstalovat z[webové stránky Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java: Stáhněte a nastavte Aspose.Tasks for Java podle pokynů uvedených v[dokumentace](https://reference.aspose.com/tasks/java/).

## Importujte balíčky
Nejprve importujte potřebné balíčky do souboru Java:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Krok 1: Definujte datový adresář
Nastavte cestu k datovému adresáři, kde se nachází váš soubor MS Project.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Načtěte soubor MS Project
Načtěte soubor MS Project pomocí Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Krok 3: Konfigurace kvality JPEG (volitelné)
 Pokud chcete upravit kvalitu JPEG, můžete ji nastavit pomocí`ImageSaveOptions` třída. Kvalita se pohybuje od 0 do 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Nastavte kvalitu JPEG na 50
```
## Krok 4: Uložte projekt jako JPEG
Uložte soubor MS Project jako obrázek JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Závěr
tomto tutoriálu jsme se naučili, jak uložit soubor Microsoft Project jako obrázek JPEG pomocí Aspose.Tasks for Java. Tato funkce umožňuje snadné sdílení a integraci projektových dat do různých dokumentů a prezentací.
## FAQ
### Otázka: Mohu upravit kvalitu obrázku JPEG?
 Odpověď: Ano, kvalitu můžete upravit pomocí`setJpegQuality()` metoda s rozsahem od 0 do 100.
### Otázka: Co když neuvedu kvalitu JPEG?
Odpověď: Pokud neurčíte kvalitu, použije se výchozí kvalita.
### Otázka: Je Aspose.Tasks for Java k použití zdarma?
 Odpověď: Aspose.Tasks for Java je komerční knihovna, ale její funkce můžete prozkoumat pomocí bezplatné zkušební verze. Navštivte[zkušební stránka zdarma](https://releases.aspose.com/) Pro více informací.
### Otázka: Kde mohu získat podporu pro Aspose.Tasks for Java?
Odpověď: Podporu můžete získat na fóru komunity Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks?
 Odpověď: Ano, můžete si zakoupit dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
