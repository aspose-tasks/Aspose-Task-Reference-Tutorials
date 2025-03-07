---
title: دعم وظائف التقييم في صيغ Aspose.Tasks
linktitle: دعم وظائف التقييم في صيغ Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية دعم تقييم وظائف MS Project في صيغ Aspose.Tasks باستخدام Java. عزز إنتاجيتك باستخدام Aspose.Tasks.
weight: 10
url: /ar/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دعم وظائف التقييم في صيغ Aspose.Tasks


## مقدمة
Aspose.Tasks for Java هي مكتبة قوية تمكن المطورين من التعامل مع ملفات Microsoft Project برمجياً. إحدى ميزاته الرئيسية هي القدرة على دعم تقييم وظائف MS Project ضمن صيغ Aspose.Tasks. تتيح هذه الإمكانية للمستخدمين إجراء حسابات وتحليلات معقدة مباشرة داخل تطبيقات Java الخاصة بهم.
## المتطلبات الأساسية
قبل البدء في دمج وظائف MS Project في صيغ Aspose.Tasks، تأكد من أن لديك ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java على نظامك بالإضافة إلى IDE متوافق لتطوير Java مثل IntelliJ IDEA أو Eclipse.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks لـ Java وتضمينها في مشروع Java الخاص بك. يمكنك تنزيله من[صفحة تنزيل Aspose.Tasks لـ Java](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في فئة Java الخاصة بك للاستفادة من وظائف Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## الخطوة 1: إنشاء كائن مشروع جديد
 أولاً، قم بإنشاء جديد`Project`كائن للعمل مع:
```java
Project project = new Project();
```
يؤدي هذا إلى تهيئة مشروع فارغ جديد.
## الخطوة 2: تحديد سمة موسعة للمهام
بعد ذلك، حدد سمة موسعة للمهام. ستحتفظ هذه السمة بالبيانات المخصصة المرتبطة بالمهام:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 هنا، نقوم بإنشاء سمة موسعة من النوع`Number` مع اسم "Sine" للمهام.
## الخطوة 3: إضافة السمة الموسعة إلى المشروع
أضف تعريف السمة الموسعة إلى قائمة السمات الموسعة الخاصة بالمشروع:
```java
project.getExtendedAttributes().add(attr);
```
يؤدي هذا إلى إضافة السمة المخصصة إلى المشروع.
## الخطوة 4: إنشاء مهمة جديدة
الآن، لنقم بإنشاء مهمة جديدة داخل المشروع:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
يؤدي هذا إلى إضافة مهمة جديدة تسمى "المهمة" إلى المشروع.
## الخطوة 5: ربط السمة الموسعة بالمهمة
قم بربط السمة الموسعة التي تم إنشاؤها مسبقًا بالمهمة:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
يؤدي هذا إلى ربط السمة الموسعة "Sine" بالمهمة.

## خاتمة
في الختام، يعد دمج وظائف MS Project في صيغ Aspose.Tasks في Java عملية مباشرة. باتباع الخطوات المتوفرة، يمكنك الاستفادة بشكل فعال من إمكانيات Aspose.Tasks الخاصة بـ Java لمعالجة ملفات Microsoft Project وتحليلها برمجيًا.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع صيغ MS Project المعقدة؟
ج: نعم، يدعم Aspose.Tasks for Java تقييم مجموعة واسعة من وظائف MS Project، مما يسمح بإجراء حسابات معقدة داخل تطبيقات Java.
### س: هل يتوافق Aspose.Tasks for Java مع الإصدارات المختلفة من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وMPT وXML.
### س: هل يمكنني تجربة Aspose.Tasks لـ Java قبل الشراء؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ Java من موقع الويب[هنا](https://purchase.aspose.com/buy).
### س: كيف يمكنني الحصول على دعم Aspose.Tasks لـ Java؟
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل هناك ترخيص مؤقت متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من موقع Aspose[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
