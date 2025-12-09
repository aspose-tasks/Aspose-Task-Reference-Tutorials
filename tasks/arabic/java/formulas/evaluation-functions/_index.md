---
date: 2025-12-09
description: تعرّف على كيفية إنشاء كائن مشروع Java ودعم وظائف التقييم في صيغ Aspose.Tasks
  باستخدام Java. اكتشف كيفية إنشاء سمة موسعة للمهام.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: إنشاء كائن مشروع Java – دعم وظائف التقييم في Aspose.Tasks
url: /ar/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دعم وظائف التقييم في صيغ Aspose.Tasks

## المقدمة
تتيح لك Aspose.Tasks for Java **create project object java** وإنشاء مثيلات وتقييم وظائف Microsoft Project مباشرة داخل شفرة Java الخاصة بك. من خلال تضمين هذه الصيغ، يمكنك إجراء حسابات متقدمة، إنشاء تقارير مخصصة، وأتمتة تحليل المشروع دون مغادرة بيئة التطوير. يشرح هذا الدرس العملية بالكامل — من إعداد كائن المشروع إلى إضافة سمة موسعة يمكنها احتواء بيانات مخصصة.

## إجابات سريعة
- **ماذا يعني “create project object java”؟** إنه ينشئ مثيل `Project` في الذاكرة يمكنك التلاعب به برمجيًا.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (download from the official site).  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص مؤقت أو كامل للاستخدام في بيئة الإنتاج؛ يتوفر نسخة تجريبية مجانية.  
- **هل يمكنني استخدام الحقول المخصصة؟** نعم – يمكنك تعريف وإرفاق سمات موسعة للمهام.  
- **هل هذا متوافق مع جميع صيغ ملفات Project؟** تدعم Aspose.Tasks صيغ MPP و MPT و XML.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **بيئة تطوير Java** – JDK 8+ وIDE مثل IntelliJ IDEA أو Eclipse.  
2. **مكتبة Aspose.Tasks for Java** – قم بتحميل المكتبة وإدراجها من [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أضف مساحة الاسم Aspose.Tasks إلى فئة Java الخاصة بك لتتمكن من العمل مع المشاريع والمهام والسمات الموسعة:

```java
import com.aspose.tasks.*;
```

## الخطوة 1: إنشاء كائن مشروع Java
قم بإنشاء كائن `Project` جديد. سيعمل هذا كحاوية لجميع المهام والموارد والبيانات المخصصة التي ستحددها.

```java
Project project = new Project();
```

السطر أعلاه **creates project object java** يبدأ فارغًا وجاهزًا للتخصيص.

## الخطوة 2: كيفية إنشاء سمة موسعة
عرّف سمة موسعة ستخزن بيانات رقمية مخصصة (مثل قيمة جيب الزاوية) لكل مهمة.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

هنا نقوم **create extended attribute** من النوع `Number` باسم “Sine” وربطه بالمهام.

## الخطوة 3: إضافة السمة الموسعة إلى المشروع
سجِّل تعريف السمة مع المشروع بحيث يمكن لكل مهمة الإشارة إليها.

```java
project.getExtendedAttributes().add(attr);
```

## الخطوة 4: إنشاء مهمة جديدة
أضف مهمة بسيطة باسم “Task” تحت مهمة الجذر في المشروع.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## الخطوة 5: ربط السمة الموسعة بالمهمة
اربط السمة الموسعة التي تم تعريفها مسبقًا بالمهمة التي تم إنشاؤها حديثًا.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

الآن تحتوي المهمة على حقل “Sine” مخصص يمكنك استخدامه في الصيغ أو الحسابات.

## لماذا نستخدم وظائف التقييم؟
تضمين وظائف MS Project في صيغ Aspose.Tasks يتيح لك:

- إجراء حسابات فورية (مثل `Sin([Start])`) دون الحاجة إلى أدوات خارجية.  
- إبقاء جميع منطق المشروع داخل قاعدة شفرة واحدة قابلة للصيانة.  
- إنشاء تقارير ديناميكية تعكس تغيّر البيانات في الوقت الحقيقي.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Formula returns `NaN`** | تحقق من أن نوع الحقل المخصص يطابق النوع الرقمي المتوقع. |
| **Extended attribute not visible** | تأكد من إضافة تعريف السمة إلى المشروع **قبل** إنشاء المهام. |
| **License exception** | قم بتثبيت ترخيص مؤقت أو كامل؛ قد تقيّد وضع التجربة بعض الميزات. |

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks for Java التعامل مع صيغ MS Project المعقدة؟**  
ج: نعم، تدعم Aspose.Tasks for Java تقييم مجموعة واسعة من وظائف MS Project، مما يسمح بإجراء حسابات معقدة داخل تطبيقات Java.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: نعم، تدعم Aspose.Tasks for Java إصدارات متعددة من ملفات Microsoft Project، بما في ذلك صيغ MPP و MPT و XML.

**س: هل يمكنني تجربة Aspose.Tasks for Java قبل الشراء؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من Aspose.Tasks for Java من الموقع [here](https://purchase.aspose.com/buy).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks for Java؟**  
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks عبر الرابط [here](https://forum.aspose.com/c/tasks/15).

**س: هل هناك ترخيص مؤقت متاح لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من موقع Aspose عبر الرابط [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}