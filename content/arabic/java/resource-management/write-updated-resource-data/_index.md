---
title: كتابة بيانات الموارد المحدثة في Aspose.Tasks
linktitle: كتابة بيانات الموارد المحدثة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحديث بيانات الموارد في ملفات MS Project بسهولة باستخدام Aspose.Tasks لـ Java.
type: docs
weight: 21
url: /ar/java/resource-management/write-updated-resource-data/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال تحديث بيانات موارد Microsoft Project باستخدام Aspose.Tasks لـ Java. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات Java قوية تسمح لك بمعالجة ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project على نظامك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  Aspose.Tasks لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
3. المعرفة الأساسية ببرمجة جافا.

## حزم الاستيراد

أولاً، تحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Tasks في كود Java الخاص بك. أضف عبارات الاستيراد التالية إلى ملف Java الخاص بك:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## الخطوة 1: إعداد دليل البيانات الخاص بك

حدد الدليل الذي توجد به ملفات البيانات الخاصة بك:

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: تحديد ملفات الإدخال والإخراج

حدد المسارات لملف إدخال MS Project والملف المحدث الناتج:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // ملف اختبار مع RSC واحد للتحديث
String resultFile = dataDir + "OutputMPP.mpp"; // ملف لكتابة مشروع اختبار
```

## الخطوة 3: تحميل المشروع

 قم بتحميل ملف MS Project إلى ملف`Project` هدف:

```java
Project project = new Project(file);
```

## الخطوة 4: إضافة مورد وتعيين السمات

أضف موردًا جديدًا إلى المشروع وقم بتعيين سماته مثل السعر القياسي ومعدل العمل الإضافي والمجموعة:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## الخطوة 5: احفظ المشروع

احفظ المشروع المحدث ببيانات الموارد المعدلة:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## خاتمة

في هذا البرنامج التعليمي، أوضحنا كيفية تحديث بيانات موارد MS Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك معالجة معلومات الموارد بكفاءة في ملفات MS Project برمجيًا.

## الأسئلة الشائعة

### س1: هل يمكنني تحديث موارد متعددة في نفس المشروع باستخدام Aspose.Tasks لـ Java؟

ج1: نعم، يمكنك تحديث موارد متعددة عن طريق التكرار عبرها وتعيين سماتها وفقًا لذلك.

### س2: هل يدعم Aspose.Tasks تنسيقات الملفات الأخرى إلى جانب MS Project؟

ج2: نعم، يدعم Aspose.Tasks تنسيقات ملفات متنوعة بما في ذلك XML وMPP والمزيد.

### س3: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من Java؟

ج3: Aspose.Tasks متوافق مع إصدارات Java 6 وما فوق.

### س4: هل يمكنني إجراء عمليات أخرى على ملفات MS Project باستخدام Aspose.Tasks؟

ج4: نعم، يمكنك تنفيذ نطاق واسع من العمليات مثل القراءة والكتابة ومعالجة المهام والموارد والتقويمات.

### س5: أين يمكنني العثور على مساعدة أو دعم إضافي لـ Aspose.Tasks؟

 ج5: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لأية مساعدة أو استفسار.
