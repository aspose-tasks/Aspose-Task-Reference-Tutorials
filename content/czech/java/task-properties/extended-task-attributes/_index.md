---
title: Rozšířené atributy úloh v Aspose.Tasks
linktitle: Rozšířené atributy úloh v Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Prozkoumejte rozšířené atributy úloh v Aspose.Tasks for Java. Podrobný průvodce, často kladené dotazy a podpora. Optimalizujte své projektové řízení ještě dnes!
type: docs
weight: 16
url: /cs/java/task-properties/extended-task-attributes/
---
## Úvod
Vítejte v naší komplexní příručce o využití rozšířených atributů úloh v Aspose.Tasks for Java. Aspose.Tasks je výkonná Java knihovna, která vám umožní bezproblémově pracovat s dokumenty Microsoft Project. V tomto tutoriálu se ponoříme do rozšířených atributů úloh a ukážeme, jak je můžete využít k vylepšení schopností řízení projektů.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programování v Javě.
- Na vašem počítači je nainstalována sada Java Development Kit (JDK).
- Integrované vývojové prostředí (IDE), jako je IntelliJ nebo Eclipse.
## Importujte balíčky
Začněte importem potřebných balíčků k zahájení vašeho projektu Aspose.Tasks:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Nyní si tento příklad rozdělíme do několika kroků, které vás provedou celým procesem:
## Krok 1: Přístup k úloze a rozšířeným atributům
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## Krok 2: Načtení ID pole a GUID hodnoty
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## Krok 3: Práce s různými typy atributů
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
Opakujte tyto kroky pro každý úkol v projektu, abyste prozkoumali a manipulovali s rozšířenými atributy úkolů.
## Závěr
Závěrem lze říci, že pochopení a využití rozšířených atributů úloh v Aspose.Tasks for Java může výrazně zlepšit vaše schopnosti projektového řízení. Tato příručka poskytuje pevný základ, který vám umožní začít na této cestě.
## Často kladené otázky
### Mohu upravit atributy rozšířených úloh programově?
Ano, můžete upravit atributy rozšířených úloh pomocí Aspose.Tasks for Java. Podrobné pokyny naleznete v dokumentaci.
### Je k dispozici zkušební verze?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu podporu pro Aspose.Tasks for Java?
 Pro podporu navštivte[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Jak mohu získat dočasnou licenci?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde si mohu zakoupit plnou verzi Aspose.Tasks for Java?
 Můžete si zakoupit plnou verzi[tady](https://purchase.aspose.com/buy).