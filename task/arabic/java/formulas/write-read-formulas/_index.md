---
title: كتابة وقراءة صيغ مشروع MS في Aspose.Tasks
linktitle: كتابة وقراءة الصيغ في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعلم كيفية كتابة وقراءة صيغ MS Project بكفاءة باستخدام Aspose.Tasks لـ Java. تعزيز مهارات إدارة المشروع الخاص بك.
type: docs
weight: 12
url: /ar/java/formulas/write-read-formulas/
---
## مقدمة
في مجال إدارة المشاريع، يعد التعامل الفعال مع البيانات أمرًا بالغ الأهمية. يعد Aspose.Tasks for Java حلاً قويًا يسهل معالجة البيانات واستخراجها من ملفات Microsoft Project. إحدى الميزات القوية التي يقدمها هي القدرة على كتابة وقراءة صيغ MS Project. سيرشدك هذا البرنامج التعليمي خلال عملية الاستفادة من هذه الوظيفة لتحسين مهام إدارة مشروعك.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل Aspose.Tasks لـ Java وتثبيته من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): اختر IDE المفضل لديك لتطوير Java.

## استيراد الحزم
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## الخطوة 1: إعداد دليل البيانات
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
```
في هذه الخطوة، حدد الدليل الذي توجد به ملفات MS Project الخاصة بك.
## الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "project.mpp");
```
هنا، قم بتحميل ملف MS Project إلى ملف`Project` كائن للتلاعب.
## الخطوة 3: تحديد الصيغة المخصصة
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
تتضمن هذه الخطوة إنشاء حقل مخصص بصيغة تعمل على مضاعفة تكلفة المهمة.
## الخطوة 4: إضافة مهمة وتعيين التكلفة
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
هنا، تتم إضافة مهمة جديدة، ويتم تعيين تكلفتها على 100.
## الخطوة 5: حفظ ملف المشروع
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
وأخيرا، احفظ ملف المشروع المعدل.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية كتابة وقراءة صيغ MS Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك معالجة بيانات المشروع بكفاءة لتلبية متطلباتك المحددة.
## الأسئلة الشائعة
### هل Aspose.Tasks متوافق مع جميع إصدارات MS Project؟
يوفر Aspose.Tasks التوافق مع الإصدارات المختلفة من MS Project، مما يضمن المرونة للمستخدمين.
### هل يمكنني دمج Aspose.Tasks في مشروع Java الحالي الخاص بي؟
قطعاً! يوفر Aspose.Tasks تكاملًا سلسًا مع مشاريع Java من خلال الاستخدام البسيط لواجهة برمجة التطبيقات (API).
### هل هناك أي قيود على أنواع الصيغ التي يمكنني إنشاؤها؟
مع Aspose.Tasks، لديك مرونة واسعة في صياغة صيغ مخصصة تناسب احتياجات مشروعك.
### هل يدعم Aspose.Tasks النشر متعدد المنصات؟
نعم، يدعم Aspose.Tasks النشر عبر منصات متعددة، مما يعزز تعدد استخداماته.
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Tasks؟
 للحصول على المساعدة الفنية ودعم المجتمع، قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).