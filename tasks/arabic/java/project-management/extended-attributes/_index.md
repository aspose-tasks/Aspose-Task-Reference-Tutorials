---
title: التعامل مع السمات الموسعة في مشاريع Aspose.Tasks
linktitle: التعامل مع السمات الموسعة في مشاريع Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية التعامل مع السمات الموسعة في مشاريع Aspose.Tasks باستخدام Java بكفاءة. دليل خطوة بخطوة لإدارة المشاريع بشكل فعال.
weight: 13
url: /ar/java/project-management/extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التعامل مع السمات الموسعة في مشاريع Aspose.Tasks

## مقدمة
تعد إدارة السمات الموسعة في إدارة المشروع أمرًا ضروريًا لتخصيص بيانات المشروع وتحسينها. يوفر Aspose.Tasks for Java أدوات قوية للتعامل مع السمات الموسعة في ملفات MS Project بكفاءة. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مما يضمن استيعاب كل مفهوم بدقة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. المعرفة الأساسية ببرمجة جافا.
2. JDK (Java Development Kit) مثبت على نظامك.
3. تم تنزيل Aspose.Tasks لمكتبة Java وإعدادها في مشروع Java الخاص بك.
## حزم الاستيراد
أولاً، لنستورد الحزم الضرورية للبدء:
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## الخطوة 1: تحديد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 تأكد من الاستبدال`"Your Data Directory"` مع المسار إلى دليل بيانات المشروع الخاص بك.
## الخطوة 2: تحميل ملف المشروع
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 يقوم هذا السطر بتحميل ملف المشروع المسمى`"project5.mpp"`.
## الخطوة 3: الوصول إلى تعريفات السمات الموسعة
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
هنا، نقوم باسترداد مجموعة تعريفات السمات الموسعة من المشروع.
## الخطوة 4: إنشاء تعريف موسع للسمة
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 يقوم مقطع التعليمات البرمجية هذا بإنشاء تعريف سمة موسع للمهام، مع تحديد نوع الحقل المخصص كـ`Start` واسم السمة كما`"Start 7"`.
## الخطوة 5: إضافة تعريف إلى المشروع
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
نضيف تعريف السمة الموسع الذي تم إنشاؤه حديثًا إلى كل من المشروع ومجموعة تعريفات السمات.
## الخطوة 6: الوصول إلى المهمة والسمات الموسعة
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
هنا، نقوم باسترداد مهمة من المشروع والسمات الموسعة المرتبطة به.
## الخطوة 7: إنشاء مثيل السمة الموسعة
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
تقوم هذه الخطوة بإنشاء مثيل للسمة الموسعة بناءً على تعريف السمة المحددة مسبقًا.
## الخطوة 8: تعيين قيمة السمة
```java
Date date = new Date();
ea.setDateValue(date);
```
قمنا بتعيين قيمة السمة الموسعة، في هذه الحالة، قيمة التاريخ.
## الخطوة 9: إضافة سمة إلى المهمة
```java
eas.add(ea);
```
وأخيرًا، نضيف السمة الموسعة إلى المهمة.
## الخطوة 10: حفظ المشروع
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
يحفظ هذا السطر المشروع المعدل مع السمة الموسعة المضافة إلى ملف XML.
## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية التعامل مع السمات الموسعة في مشاريع Aspose.Tasks باستخدام Java. باتباع هذه الخطوات، يمكنك إدارة بيانات المشروع المخصصة بكفاءة، مما يعزز قدرات إدارة مشروعك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع لغات البرمجة الأخرى؟
ج: نعم، يدعم Aspose.Tasks لغات برمجة متعددة بما في ذلك Java و.NET وC++.
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من موقع Aspose.Tasks.
### س: هل يمكنني تخصيص أنواع السمات الموسعة؟
ج: بالتأكيد، يتيح لك Aspose.Tasks تحديد أنواع السمات الموسعة المخصصة التي تناسب احتياجات مشروعك.
### س: كيف يمكنني الوصول إلى وثائق Aspose.Tasks؟
 ج: يمكنك العثور على وثائق شاملة على موقع Aspose.Tasks[توثيق](https://reference.aspose.com/tasks/java/).
### س: هل يتوفر الدعم الفني لمستخدمي Aspose.Tasks؟
 ج: نعم، يمكنك الوصول إلى الدعم الفني من خلال منتدى Aspose.Tasks[موقع إلكتروني](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
