---
date: 2026-01-15
description: Узнайте, как работать с запланированными затратами бюджета в файлах Microsoft
  Project, используя Aspose.Tasks для Java. Следуйте нашему пошаговому руководству.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Запланированная работа с бюджетной стоимостью с Aspose.Tasks для Java
url: /ru/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# budgeted cost work scheduled with Aspose.Tasks for Java

## Introduction

Управление **budgeted cost work scheduled** (BCWS) является важным для поддержания проекта в графике и обеспечения того, чтобы финансовый прогноз соответствовал запланированной работе. В Microsoft Project BCWS представляет сумму денег, которую следовало бы потратить на работу, запланированную к определённой дате. Aspose.Tasks for Java предоставляет полный программный контроль над этими значениями, позволяя читать, изменять и формировать отчёты о затратах ресурсов без необходимости вручную открывать файл .mpp. В этом руководстве мы пройдём через полный пример, показывающий, как загрузить проект, пройтись по его ресурсам и отобразить budgeted cost work scheduled вместе с другими ключевыми метриками затрат.

## Quick Answers
- **What does BCWS mean?** Budgeted Cost Work Scheduled – the planned cost for work scheduled to date.  
- **Which API property retrieves BCWS?** `Rsc.BCWS` on a `Resource` object.  
- **Do I need a license to run the sample?** A free evaluation license works for testing; a full license is required for production.  
- **Can I modify BCWS values?** Yes, you can set `Rsc.BCWS` just like any other numeric field.  
- **Supported Project versions?** All Microsoft Project versions from 2000 to the latest .mpp format.

## What is budgeted cost work scheduled?

**Budgeted Cost Work Scheduled (BCWS)** — это показатель эффективности, отражающий стоимость, которую следовало бы понести за работу, запланированную к определённому моменту времени. Это фундаментальная часть Earned Value Management (EVM) и помогает менеджерам проектов сравнивать плановые и фактические расходы.

## Prerequisites

Перед тем как приступить к коду, убедитесь, что у вас есть:

1. Твёрдое понимание основ Java.  
2. Aspose.Tasks for Java, добавленный в ваш проект (Maven/Gradle или JAR).  
3. Файл Microsoft Project (`.mpp`), содержащий ресурсы с данными о затратах (например, *ResourceCosts.mpp*).

## Import Packages

First, import the Aspose.Tasks classes required for handling projects and resources:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Step 1: Define the Data Directory

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute or relative path where *ResourceCosts.mpp* resides.

## Step 2: Load the MS Project File

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

The `Project` constructor reads the .mpp file and builds an in‑memory representation that you can query.

## Step 3: Iterate Through Resources

```java
for (Resource res : prj.getResources()) {
```

This loop walks through every resource defined in the project, giving you access to its cost fields.

## Step 4: Check Resource Name and Costs

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Inside the `if` block we:

* Print the **total cost** (`Rsc.COST`).  
* Print the **actual cost of work performed** (`Rsc.ACWP`).  
* Print the **budgeted cost work scheduled** (`Rsc.BCWS`) – the primary metric we’re focusing on.  
* Print the **budgeted cost work performed** (`Rsc.BCWP`).

These four values give you a quick snapshot of where the project stands financially.

## Why monitoring budgeted cost work scheduled matters

* **Early warning:** If BCWS is significantly higher than the actual cost, you may be over‑allocating resources.  
* **Earned Value Analysis:** BCWS is a key input for calculating Cost Variance (CV) and Schedule Variance (SV).  
* **Forecasting:** Accurate BCWS data helps predict future cash‑flow needs and informs stakeholder reporting.

## Common Issues & Troubleshooting

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| `null` printed for BCWS | Resource has no cost rate table defined | Define a cost rate table for the resource in Microsoft Project or set it programmatically via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` when iterating resources | Project file corrupted or contains empty resource entries | Validate the .mpp file in Microsoft Project and remove empty resources |
| Unexpected values (e.g., negative BCWS) | Custom fields overriding standard cost fields | Ensure you’re accessing the standard `Rsc.BCWS` and not a custom field with the same name |

## Frequently Asked Questions

**Q: Can I update the BCWS value programmatically?**  
A: Yes. Use `res.set(Rsc.BCWS, newValue)` and then save the project with `prj.save("Updated.mpp")`.

**Q: Does Aspose.Tasks support multi‑currency projects?**  
A: Absolutely. Cost fields respect the currency settings defined in the Project file.

**Q: Is there a way to export these cost metrics to CSV?**  
A: You can iterate over the resources and write the values to a `StringBuilder` or use a CSV library to generate the file.

**Q: How does BCWS differ from BCWP?**  
A: BCWS is the planned cost for scheduled work, while BCWP (Budgeted Cost Work Performed) reflects the planned cost for work that has actually been completed.

**Q: Do I need a special license to read cost data?**  
A: The evaluation license provides full read/write access; a commercial license is required for production deployments.

## Conclusion

By leveraging Aspose.Tasks for Java, you gain precise, programmatic access to **budgeted cost work scheduled** and other vital cost metrics. This empowers you to build custom dashboards, automate Earned Value reports, and keep your projects financially on track—all without manual interaction with Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose