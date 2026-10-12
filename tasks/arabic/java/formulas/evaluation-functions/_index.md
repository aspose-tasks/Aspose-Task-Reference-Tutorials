---
date: 2026-10-10
description: تعلم كيفية إضافة extended attribute في Aspose.Tasks، واستخدام evaluation
  functions، وإنشاء تقارير المشروع باستخدام مكتبة إدارة المشاريع Java هذه.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: دعم evaluation functions في صيغ Aspose.Tasks
og_description: تعلم كيفية إضافة extended attribute في Aspose.Tasks، واستخدام evaluation
  functions، وإنشاء تقارير المشروع باستخدام مكتبة إدارة المشاريع Java هذه.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: كيفية إضافة extended attribute في صيغ Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: كيفية إضافة extended attribute في صيغ Aspose.Tasks
url: /ar/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة سمة موسعة في صيغ Aspose.Tasks

## مقدمة
Aspose.Tasks for Java هي **مكتبة إدارة مشاريع Java** تتيح لك إنشاء تقارير المشروع عن طريق إنشاء كائن `Project` في Java وتقييم وظائف Microsoft Project مباشرة داخل الشيفرة الخاصة بك. من خلال تضمين هذه الصيغ، يمكنك إجراء حسابات متقدمة، وإنشاء تقارير مخصصة، وأتمتة تحليل المشروع دون مغادرة بيئة التطوير. في هذا البرنامج التعليمي سنستعرض إنشاء كائن مشروع، إضافة سمة موسعة، واستخدام وظائف التقييم **لإضافة بيانات حقل مخصص للمهمة**.

## إجابات سريعة
- **ماذا يعني “create project object java”?** إنه ينشئ مثيل `Project` في الذاكرة يمكنك التلاعب به برمجياً.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (قم بالتنزيل من الموقع الرسمي).  
- **هل أحتاج إلى ترخيص؟** يتطلب ترخيص مؤقت أو كامل لـ Aspose.Tasks للاستخدام في الإنتاج؛ يتوفر نسخة تجريبية مجانية.  
- **هل يمكنني استخدام الحقول المخصصة؟** نعم – يمكنك **إضافة سمة موسعة** إلى المهام ومعاملتها كحقول مخصصة.  
- **هل هذا متوافق مع جميع صيغ ملفات Project؟** Aspose.Tasks يدعم 3 صيغ رئيسية (MPP، MPT، XML) وأكثر من 50 صيغة إدخال/إخراج إضافية.

## المتطلبات المسبقة
قبل البدء، تأكد من أنك تمتلك:

1. **بيئة تطوير Java** – JDK 8+ وIDE مثل IntelliJ IDEA أو Eclipse.  
2. **مكتبة Aspose.Tasks for Java** – قم بتنزيل وإدراج المكتبة من [صفحة تنزيل Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
Add the Aspose.Tasks namespace to your Java class so you can work with projects, tasks, and extended attributes:

```java
import com.aspose.tasks.*;
```

## إنشاء تقرير المشروع – create project object java
فئة `Project` تمثل ملف Microsoft Project في الذاكرة، وتعرض المهام والموارد والبيانات المخصصة. إنشاء نسخة من هذه الفئة يمنحك حاوية لجميع عناصر المشروع التي ستحددها.

```java
Project project = new Project();
```

السطر أعلاه **creates project object java** يبدأ فارغًا وجاهزًا للتخصيص.

## كيفية إضافة سمة موسعة
فئة `ExtendedAttributeDefinition` تعرف حقلًا مخصصًا يمكن إرفاقه بالمهام. لإضافة سمة موسعة، أنشئ نسخة من هذه الفئة بنوع `Number`، وامنحها اسمًا مستعارًا مثل “Sine”، أضفها إلى مجموعة `ExtendedAttributes` الخاصة بالمشروع، ثم اربطها بكل مهمة تحتاج إلى الحقل المخصص.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

هنا نقوم **add extended attribute** من النوع `Number` باسم “Sine” وربطها بالمهام.

## إضافة السمة الموسعة إلى المشروع
سجّل تعريف السمة مع المشروع بحيث يمكن لكل مهمة الإشارة إليه.

```java
project.getExtendedAttributes().add(attr);
```

## إنشاء مهمة جديدة
`Task` تمثل عنصر عمل في المشروع ويمكن أن تحتوي على حقول مخصصة.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## إضافة حقل مخصص للمهمة إلى المشروع
اربط السمة الموسعة المعرفة مسبقًا بالمهمة التي تم إنشاؤها حديثًا، مما يمنح المهمة حقلًا مخصصًا “Sine” يمكنك استخدامه في الصيغ أو الحسابات.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

الآن تحتوي المهمة على حقل مخصص “Sine” يمكنك استخدامه في الصيغ أو الحسابات. هذا هو أيضًا الطريقة التي يمكنك من خلالها **add custom field task** البيانات برمجيًا.

## لماذا نستخدم وظائف التقييم؟
تسمح لك وظائف التقييم بتضمين صيغ Microsoft Project الأصلية (مثل `Sin([Start])`) مباشرة في Aspose.Tasks، مما يتيح حسابات فورية دون معالجة خارجية. هذا يبقي جميع منطق المشروع في مكان واحد، يقلل من أخطاء مزامنة البيانات، ويسرّع إنشاء التقارير. Aspose.Tasks يدعم تقييم أكثر من 100 دالة من MS Project، موفرًا محرك حسابات شامل داخل Java.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **الصيغة تُرجع `NaN`** | تحقق من أن نوع الحقل المخصص يطابق النوع الرقمي المتوقع. |
| **السمة الموسعة غير مرئية** | تأكد من إضافة تعريف السمة إلى المشروع **قبل** إنشاء المهام. |
| **استثناء الترخيص** | قم بتثبيت ترخيص مؤقت أو كامل **Aspose.Tasks license**؛ قد يحد وضع التجربة بعض الميزات. |
| **غياب الترخيص المؤقت** | احصل على **temporary Aspose license** من موقع Aspose. |

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks for Java التعامل مع صيغ MS Project المعقدة؟**  
نعم، Aspose.Tasks for Java يدعم تقييم مجموعة واسعة من دوال MS Project، مما يسمح بحسابات معقدة داخل تطبيقات Java.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
نعم، Aspose.Tasks for Java يدعم إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك صيغ MPP و MPT و XML.

**س: هل يمكنني تجربة Aspose.Tasks for Java قبل الشراء؟**  
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks for Java من الموقع [صفحة شراء Aspose.Tasks for Java](https://purchase.aspose.com/buy).

**س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟**  
يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks [منتدى مجتمع Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**س: هل هناك ترخيص مؤقت متاح لـ Aspose.Tasks for Java؟**  
نعم، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من موقع Aspose [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).

## الخلاصة
باتباعك هذه الخطوات، تعلمت كيفية **create project object**، **add extended attribute**، واستخدام وظائف التقييم **generate project report** تلقائيًا. يمكنك الآن توسيع هذا الأساس لبناء تحليلات مشروع أكثر غنى، لوحات تحكم مخصصة، أو أدوات جدولة آلية—كل ذلك مدعومًا بـ Aspose.Tasks for Java.

---

**آخر تحديث:** 2026-10-10  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose

## دروس ذات صلة

- [الأعمدة المخصصة والسمات الموسعة في إدارة مشاريع Java](/tasks/java/project-management/extended-attributes/)
- [قراءة السمات الموسعة للمهام باستخدام Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [كيفية استخدام Aspose.Tasks for Java – إضافة سمات موسعة لتعيينات الموارد](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}