---
date: 2026-10-10
description: تعلم كيفية إنشاء حقل مخصص Aspose في Java، وتطبيق صيغة تكلفة مهمة مزدوجة،
  وحفظ ملف المشروع باستخدام Aspose.Tasks. يتضمن قراءة صيغ MS Project.
keywords:
- create custom field aspose
- double task cost formula
- add custom field formula
- calculate task cost
lastmod: 2026-10-10
linktitle: مثال على صيغة الحقل المخصص – حفظ ملف المشروع
og_description: تعلم كيفية إنشاء حقل مخصص Aspose في Java، وتطبيق صيغة تكلفة مهمة مزدوجة،
  وحفظ ملف المشروع باستخدام Aspose.Tasks. يتضمن قراءة صيغ MS Project.
og_image_alt: 'Guide: create custom field aspose and save project file with Aspose.Tasks
  Java'
og_title: كيفية إنشاء حقل مخصص Aspose وحفظ ملف المشروع
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  headline: How to create custom field aspose and save project file
  type: TechArticle
- description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  name: How to create custom field aspose and save project file
  steps:
  - name: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
    text: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
  - name: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
    text: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of MS Project versions, from older
      .mpp formats to the latest releases, covering over 30 file format variations.
    question: Is Aspose.Tasks compatible with all versions of MS Project?
  - answer: Absolutely. The API is designed for seamless integration; just add the
      Aspose.Tasks JAR to your project’s classpath and start using the `Project` class.
    question: Can I integrate Aspose.Tasks into my existing Java project?
  - answer: The library supports most native MS Project formula syntax, including
      arithmetic, logical, and built‑in functions. Complex custom functions may require
      workarounds, but common calculations like **double task cost formula** work
      out of the box.
    question: Are there any limitations to the types of formulas I can create?
  - answer: Yes, the library runs on any platform that supports Java, including Windows,
      Linux, and macOS, and can handle projects up to 2 GB without loading the entire
      file into memory.
    question: Does Aspose.Tasks support multi‑platform deployment?
  - answer: Visit the [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)
      for community help, or open a support ticket if you have a commercial license.
    question: How can I get technical support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- custom field
- Aspose.Tasks
- Java project automation
title: كيفية إنشاء حقل مخصص Aspose وحفظ ملف المشروع
url: /ar/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء حقل مخصص Aspose وحفظ ملف المشروع

## مقدمة
في هذا البرنامج التعليمي سترى **custom field formula example** الذي يوضح كيفية **save a project file**، كتابة وقراءة صيغ MS Project، وتطبيق **double task cost formula** باستخدام Aspose.Tasks for Java. في النهاية ستفهم لماذا الحقول المخصصة قوية، وكيفية تضمين الحسابات مباشرةً في المشروع، وكيفية حفظ تلك التغييرات للتقارير المستقبلية. التركيز الأساسي هو على **create custom field aspose** حتى تتمكن من أتمتة حسابات التكلفة في أي سير عمل يعتمد على MS Project.

## إجابات سريعة
- **What does “save project file” do?** يكتب جميع التغييرات الموجودة في الذاكرة إلى ملف .mpp على القرص.  
- **Can I add custom field formulas?** نعم – يمكنك إنشاء حقل مخصص وتعيين صيغة مثل “double task cost”.  
- **Do I need a license to run the code?** نسخة تجريبية مجانية تعمل للتقييم؛ يلزم وجود ترخيص تجاري للإنتاج.  
- **Which IDE works best?** أي بيئة تطوير Java (IntelliJ IDEA، Eclipse، VS Code) ستقوم بترجمة العينة.  
- **Is the API compatible with the latest MS Project version?** Aspose.Tasks يدعم جميع صيغ .mpp الحديثة.

## ما هو “save project file” في Aspose.Tasks؟
حفظ ملف المشروع يعني الحفاظ على الحالة الحالية لكائن `Project` — بما في ذلك المهام والموارد وأي صيغ مخصصة — إلى ملف Microsoft Project فعلي (`.mpp`). هذه العملية ضرورية بعد تعديل البيانات، مثل إضافة حقل مخصص أو تغيير تكاليف المهام. استدعاء `save` يكتب بنية المشروع بالكامل إلى القرص، مما يجعل التغييرات متاحة لأدوات التقارير اللاحقة.

## لماذا إضافة حقل مخصص وإنشاء صيغة حقل مخصص؟
تضيف حقلًا مخصصًا عندما تحتاج إلى تخزين معلومات لا تغطيها الحقول المدمجة. إرفاق صيغة — مثل تلك التي **double task cost** — ي automatisations الحسابات، يلغي التحديثات اليدوية، ويضمن أنه في كل مرة يتغير فيها التكلفة الأساسية، يتم تحديث القيمة المشتقة فورًا. هذا النهج يقلل الأخطاء ويحافظ على اتساق بيانات الجدول الزمني عبر الفرق.

## المتطلبات المسبقة
1. **Java Development Kit (JDK)** – Java 8 أو أعلى مثبت على جهازك.  
2. **Aspose.Tasks for Java** – قم بتنزيله وتثبيته من [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – اختر بيئة التطوير المفضلة لديك لتطوير Java (IntelliJ IDEA، Eclipse، VS Code، إلخ).  

## استيراد الحزم
توجد الفئات `Project` و `ExtendedAttribute` والفئات المرتبطة في مساحة الاسم `com.aspose.tasks`. استوردها في أعلى ملف المصدر الخاص بك حتى يتمكن المترجم من حل الأنواع.

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## الخطوة 1: إعداد دليل البيانات
حدد المجلد الذي توجد فيه ملفات MS Project الخاصة بك. هذا هو المكان الذي ستحمّل منه الملف المصدر ولاحقًا **save project file**.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## الخطوة 2: تحميل ملف المشروع
تمثل الفئة `Project` ملف Microsoft Project في الذاكرة، وتوفر الوصول إلى المهام والموارد والحقول المخصصة. تحميل الملف يمنحك نموذج كائن قابل للتلاعب.

```java
Project project = new Project(dataDir + "project.mpp");
```

## الخطوة 3: إضافة حقل مخصص وإنشاء صيغة حقل مخصص
في هذه الخطوة **add a custom field** “Double Costs” و **create a custom field formula** التي تضرب `[Cost]` للمهام في 2، مما يطبق فعليًا **double task cost formula**. طريقة `setFormula` تدمج الحساب مباشرةً في ملف المشروع.

```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```

## الخطوة 4: إضافة مهمة وتعيين التكلفة
أنشئ مهمة جديدة، ثم عيّن تكلفة أساسية قدرها `100`. عند حفظ المشروع، سيعرض الحقل المخصص تلقائيًا `200` بسبب الصيغة المعرفة مسبقًا.

```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```

## الخطوة 5: حفظ ملف المشروع
طريقة `save` تكتب المشروع المحدث، بما في ذلك الحقل المخصص الجديد والقيم المحسوبة، إلى `saved.mpp`. هذا يحفظ تغييرات **create custom field aspose** لأي مستهلكين لاحقين.

```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```

## المشكلات الشائعة والحلول
| Issue | Reason | Fix |
|-------|--------|-----|
| **Formula not applied** | لم يتم إضافة الحقل المخصص إلى مجموعة `ExtendedAttributes` للمشروع. | تأكد من تنفيذ `project.getExtendedAttributes().add(attr);` قبل الحفظ. |
| **File not found** | مسار `dataDir` غير صحيح. | تحقق من أن سلسلة الدليل تنتهي بفاصل مسار (`/` أو `\\`). |
| **Cost appears as 0** | لم يتم تعيين تكلفة المهمة قبل الحفظ. | استدعِ `task.set(Tsk.COST, ...)` قبل `project.save`. |

## الأسئلة المتكررة
**Q: Is Aspose.Tasks compatible with all versions of MS Project?**  
A: نعم، Aspose.Tasks يدعم مجموعة واسعة من إصدارات MS Project، من صيغ .mpp القديمة إلى الإصدارات الأخيرة، ويغطي أكثر من 30 تنوعًا في صيغ الملفات.

**Q: Can I integrate Aspose.Tasks into my existing Java project?**  
A: بالتأكيد. تم تصميم الـ API للتكامل السلس؛ فقط أضف ملف Aspose.Tasks JAR إلى مسار الفئة (classpath) في مشروعك وابدأ باستخدام الفئة `Project`.

**Q: Are there any limitations to the types of formulas I can create?**  
A: المكتبة تدعم معظم صيغ صيغ MS Project الأصلية، بما في ذلك العمليات الحسابية، المنطقية، والدوال المدمجة. قد تتطلب الدوال المخصصة المعقدة حلولًا بديلة، لكن الحسابات الشائعة مثل **double task cost formula** تعمل مباشرةً.

**Q: Does Aspose.Tasks support multi‑platform deployment?**  
A: نعم، المكتبة تعمل على أي منصة تدعم Java، بما في ذلك Windows وLinux وmacOS، ويمكنها معالجة مشاريع تصل إلى 2 GB دون تحميل الملف بالكامل إلى الذاكرة.

**Q: How can I get technical support for Aspose.Tasks?**  
A: زر [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع، أو افتح تذكرة دعم إذا كان لديك ترخيص تجاري.

## الخلاصة
في هذا **custom field formula example** غطينا كيفية **save project file**، **add a custom field**، و **create a double task cost formula** التي تضاعف تكلفة المهمة تلقائيًا. باتباع هذه الخطوات يمكنك أتمتة الحسابات، إثراء بيانات مشروعك، وضمان حفظ جميع التغييرات للتقارير والتحليل المستقبلي. تقنية **create custom field aspose** هي طريقة قوية لتوسيع MS Project دون الحاجة إلى عمل يدوي على جداول البيانات.

---

**آخر تحديث:** 2026-10-10  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بتنسيق MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [كيفية إنشاء مشروع Aspose.Tasks – تعيين سمات مهمة جديدة](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [قراءة سمات المهمة الموسعة باستخدام Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}