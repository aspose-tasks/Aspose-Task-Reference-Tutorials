---
date: 2026-02-13
description: تعلم كيفية إنشاء تقرير مشروع عن طريق إنشاء كائن مشروع في جافا، وإضافة
  سمات موسعة، واستخدام وظائف التقييم مع Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: إنشاء تقرير المشروع – إنشاء كائن المشروع جافا
url: /ar/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دعم دوال التقييم في صيغ Aspose.Tasks

## المقدمة
تتيح لك Aspose.Tasks for Java **generate project report** عن طريق إنشاء **project object** في Java وتقييم دوال Microsoft Project مباشرة داخل الكود الخاص بك. من خلال تضمين هذه الصيغ، يمكنك إجراء حسابات متقدمة، وإنشاء تقارير مخصصة، وأتمتة تحليل المشروع دون مغادرة بيئة التطوير. في هذا البرنامج التعليمي سنستعرض إنشاء كائن المشروع، إضافة سمة موسعة، واستخدام دوال التقييم **add custom field task**.

## إجابات سريعة
- **ما معنى “create project object java”؟** ينشئ نسخة `Project` في الذاكرة يمكنك التلاعب بها برمجياً.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (قم بالتحميل من الموقع الرسمي).  
- **هل أحتاج إلى ترخيص؟** يلزم وجود ترخيص مؤقت أو كامل لـ Aspose.Tasks للاستخدام في الإنتاج؛ يتوفر إصدار تجريبي مجاني.  
- **هل يمكنني استخدام الحقول المخصصة؟** نعم – يمكنك **add extended attribute** للمهام ومعاملتها كحقول مخصصة.  
- **هل هذا متوافق مع جميع صيغ ملفات Project؟** تدعم Aspose.Tasks صيغ MPP و MPT و XML.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:

1. **بيئة تطوير Java** – JDK 8+ وIDE مثل IntelliJ IDEA أو Eclipse.  
2. **مكتبة Aspose.Tasks for Java** – قم بتحميل وإدراج المكتبة من [صفحة تحميل Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أضف مساحة الاسم Aspose.Tasks إلى فئة Java الخاصة بك لتتمكن من العمل مع المشاريع، المهام، والسمات الموسعة:

```java
import com.aspose.tasks.*;
```

## إنشاء تقرير المشروع – Create Project Object Java
أنشئ كائن `Project` جديد. سيعمل هذا كحاوية لجميع المهام والموارد والبيانات المخصصة التي ستحددها.

```java
Project project = new Project();
```

السطر أعلاه **creates project object java** الذي يبدأ فارغًا وجاهزًا للتخصيص.

## كيفية إضافة سمة موسعة
عرّف سمة موسعة ستخزن بيانات رقمية مخصصة (مثل قيمة جيب الزاوية) لكل مهمة.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

هنا نقوم **add extended attribute** من النوع `Number` باسم “Sine” وربطه بالمهام.

## إضافة السمة الموسعة إلى المشروع
سجِّل تعريف السمة في المشروع بحيث يمكن لكل مهمة الإشارة إليه.

```java
project.getExtendedAttributes().add(attr);
```

## إنشاء مهمة جديدة
أضف مهمة بسيطة باسم “Task” تحت مهمة الجذر في المشروع.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## ربط السمة الموسعة بالمهمة
اربط السمة الموسعة التي عرّفتها مسبقًا بالمهمة التي تم إنشاؤها حديثًا.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

الآن تحتوي المهمة على حقل “Sine” مخصص يمكنك استخدامه في الصيغ أو الحسابات. هذا هو أيضًا الطريقة التي تقوم بها **add custom field task** برمجيًا.

## لماذا نستخدم دوال التقييم؟
تضمين دوال MS Project في صيغ Aspose.Tasks يتيح لك:

- إجراء حسابات فورية (مثال: `Sin([Start])`) دون أدوات خارجية.  
- الحفاظ على جميع منطق المشروع داخل قاعدة شفرة واحدة قابلة للصيانة.  
- إنشاء تقارير ديناميكية تعكس تغييرات البيانات في الوقت الفعلي، مما يساعدك على **generate project report** تلقائيًا.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Formula returns `NaN`** | تحقق من أن نوع الحقل المخصص يطابق النوع الرقمي المتوقع. |
| **Extended attribute not visible** | تأكد من أن تعريف السمة قد أُضيف إلى المشروع **قبل** إنشاء المهام. |
| **License exception** | قم بتثبيت ترخيص مؤقت أو كامل **Aspose.Tasks license**؛ قد يحد وضع التجربة بعض الميزات. |
| **Missing temporary license** | احصل على **temporary Aspose license** من موقع Aspose. |

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks for Java التعامل مع صيغ MS Project المعقدة؟**  
ج: نعم، يدعم Aspose.Tasks for Java تقييم مجموعة واسعة من دوال MS Project، مما يسمح بإجراء حسابات معقدة داخل تطبيقات Java.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: نعم، يدعم Aspose.Tasks for Java إصدارات متعددة من ملفات Microsoft Project، بما في ذلك صيغ MPP و MPT و XML.

**س: هل يمكنني تجربة Aspose.Tasks for Java قبل الشراء؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من Aspose.Tasks for Java من الموقع [هنا](https://purchase.aspose.com/buy).

**س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟**  
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**س: هل هناك ترخيص مؤقت متاح لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من موقع Aspose [هنا](https://purchase.aspose.com/temporary-license/).

## الخلاصة
باتباعك لهذه الخطوات، تعلمت كيفية **create project object**، **add extended attribute**، والاستفادة من دوال التقييم لتوليد **generate project report** تلقائيًا. يمكنك الآن توسيع هذا الأساس لبناء تحليلات مشروع أكثر غنى، لوحات تحكم مخصصة، أو أدوات جدولة آلية—كل ذلك مدعومًا بـ Aspose.Tasks for Java.

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}