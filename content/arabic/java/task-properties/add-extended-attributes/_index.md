---
title: أضف السمات الموسعة إلى المهام في Aspose.Tasks
linktitle: أضف السمات الموسعة إلى المهام في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: اكتشف قوة Aspose.Tasks Java في تخصيص ملفات Microsoft Project ذات السمات الموسعة. تعزيز قدرات إدارة المشروع الخاص بك دون عناء.
type: docs
weight: 11
url: /ar/java/task-properties/add-extended-attributes/
---
## مقدمة
يعد تعزيز قدرات إدارة مشروعك أمرًا بالغ الأهمية لتتبع المهام وإدارة الموارد بكفاءة. يوفر Aspose.Tasks for Java حلاً قويًا لمطوري Java للتعامل مع ملفات Microsoft Project بسلاسة. في هذا البرنامج التعليمي، سنستكشف كيفية إضافة سمات موسعة إلى المهام باستخدام Aspose.Tasks لـ Java، مما يسمح لك بتخصيص بيانات مشروعك وتنظيمها وفقًا لمتطلباتك المحددة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
-  تم تثبيت Aspose.Tasks لمكتبة Java. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/tasks/java/).
- بيئة تطوير متكاملة لـ Java (IDE) مثبتة على نظامك.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة للوصول إلى وظائف Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة:
## 1. إضافة سمة نص عادي
1. قم بتعيين مسار دليل المستند:
```java
String dataDir = "Your Document Directory";
```
2. إنشاء مشروع جديد:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. إنشاء تعريف سمة موسع لنوع النص 1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. أضف التعريف إلى مجموعة السمات الموسعة للمشروع:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. إضافة مهمة إلى المشروع:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. إنشاء سمة موسعة من تعريف السمة:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. قم بتعيين قيمة للسمة الموسعة التي تم إنشاؤها:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. أضف السمة الموسعة إلى المهمة:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. احفظ المشروع:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. إضافة سمة النص مع خيار البحث
اتبع نفس الخطوات المذكورة أعلاه، مع استبدال النص 1 بالنص 2 وتخصيص قيم البحث.
## 3. إضافة سمة المدة مع خيار البحث
اتبع نفس الخطوات المذكورة أعلاه، مع استبدال النص 1 بالمدة 2 وتخصيص قيم البحث.
## خاتمة
باتباع هذا الدليل التفصيلي، تعلمت كيفية الاستفادة من Aspose.Tasks لـ Java لإضافة سمات موسعة إلى المهام في ملفات Microsoft Project الخاصة بك. يتيح لك هذا التخصيص تصميم نهج إدارة المشروع الخاص بك، مما يعزز المرونة والكفاءة.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java مع مكتبات Java الأخرى؟
ج: نعم، يمكن دمج Aspose.Tasks for Java بسلاسة في مشاريع Java الخاصة بك، ويعمل بشكل جيد مع مكتبات Java الأخرى.
### س: هل Aspose.Tasks for Java مناسب لتطبيقات إدارة المشاريع واسعة النطاق؟
ج: بالتأكيد، تم تصميم Aspose.Tasks for Java للتعامل مع المشاريع ذات الأحجام المختلفة، بما في ذلك التطبيقات واسعة النطاق.
### س: هل هناك أي اعتبارات ترخيص لاستخدام Aspose.Tasks لـ Java في مشروع تجاري؟
 ج: نعم، تأكد من مراجعة معلومات الترخيص المتوفرة في[موقع Aspose.Tasks](https://purchase.aspose.com/buy).
### س: كيف يمكنني الحصول على الدعم أو المساعدة فيما يتعلق بـ Aspose.Tasks لـ Java؟
 ج: قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع والمناقشات.
### س: هل يمكنني تجربة Aspose.Tasks لـ Java قبل الشراء؟
 ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).