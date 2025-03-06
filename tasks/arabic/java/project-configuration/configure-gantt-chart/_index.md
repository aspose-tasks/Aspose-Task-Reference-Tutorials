---
title: تكوين عرض مخطط جانت في مشاريع Aspose.Tasks
linktitle: تكوين عرض مخطط جانت في مشاريع Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تكوين عرض مخطط مشروع Gantt MS في Aspose.Tasks باستخدام Java. قم بتخصيص المشروع وتصوره في مخطط جانت خطوة بخطوة.
weight: 10
url: /ar/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تكوين عرض مخطط جانت في مشاريع Aspose.Tasks

## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية تكوين طريقة عرض مخطط مشروع Gantt MS في مشاريع Aspose.Tasks باستخدام Java. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات Java قوية تتيح لك العمل مع ملفات Microsoft Project برمجيًا. باتباع هذه الخطوات، ستتمكن من تخصيص طريقة عرض مخطط جانت وفقًا لمتطلبات مشروعك.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
2.  مكتبة Aspose.Tasks: قم بتنزيل وتثبيت مكتبة Aspose.Tasks. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة تطوير متكاملة (IDE) من اختيارك. يستخدم هذا البرنامج التعليمي IntelliJ IDEA، ولكن يمكنك استخدام أي IDE يناسبك.
## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Tasks في مشروع Java الخاص بك. أضف عبارات الاستيراد التالية إلى ملف Java الخاص بك:
```java
import com.aspose.tasks.*;
```
الآن، دعنا نقسم عملية تكوين طريقة عرض مخطط مشروع Gantt MS إلى إرشادات خطوة بخطوة:
## الخطوة 1: إعداد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى دليل بيانات المشروع الخاص بك.
## الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "project.mpp");
```
قم بتحميل ملف المشروع الخاص بك (`project.mpp` في هذا المثال) باستخدام`Project` فئة من Aspose.Tasks.
## الخطوة 3: إضافة نشاط جديد
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 قم بإنشاء مهمة جديدة في مشروعك باستخدام`Task` class وإضافته إلى أطفال المهمة الجذرية.
## الخطوة 4: تحديد السمة المخصصة
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 حدد سمة مخصصة جديدة باستخدام`ExtendedAttributeDefinition`class وإضافته إلى السمات الموسعة للمشروع.
## الخطوة 5: إضافة سمة مخصصة إلى المهمة
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 أضف السمة المخصصة إلى المهمة التي تم إنشاؤها باستخدام`createExtendedAttribute` طريقة.
## الخطوة 6: تخصيص الجدول
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
قم بتخصيص الجدول عن طريق إضافة حقل سمة النص بالعرض والعنوان والمحاذاة المحددة.
## الخطوة 7: حفظ المشروع
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
احفظ المشروع باستخدام عرض مخطط مشروع Gantt MS الذي تم تكوينه. يمكن فتح الملف الناتج في Microsoft Project 2010.
## خاتمة
تهانينا! لقد نجحت في تكوين عرض مخطط مشروع Gantt MS في مشاريع Aspose.Tasks باستخدام Java. يمكنك الآن تخصيص سمات المشروع وتصورها في مخطط جانت وفقًا لاحتياجات مشروعك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع لغات البرمجة الأخرى؟
ج: نعم، Aspose.Tasks متاح للعديد من لغات البرمجة بما في ذلك .NET، وJava، وC++.
### س: هل هناك أي نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks؟
ج: يمكنك العثور على الدعم وطرح الأسئلة على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
### س: كيف يمكنني شراء ترخيص Aspose.Tasks؟
 ج: يمكنك شراء ترخيص من[هنا](https://purchase.aspose.com/buy).
### س: هل أحتاج إلى ترخيص مؤقت لأغراض الاختبار؟
 ج: نعم، يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
