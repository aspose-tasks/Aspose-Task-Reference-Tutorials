---
title: استرداد رموز المخطط التفصيلي لمشروع MS في Aspose.Tasks
linktitle: استرداد رموز المخطط التفصيلي في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية استرداد رموز مخطط Microsoft Project برمجياً باستخدام Aspose.Tasks لـ Java. تعزيز قدرات إدارة المشروع الخاص بك.
weight: 15
url: /ar/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استرداد رموز المخطط التفصيلي لمشروع MS في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنتعلم كيفية استرداد رموز المخطط التفصيلي لـ Microsoft Project باستخدام Aspose.Tasks لـ Java. توفر رموز المخطط التفصيلي في MS Project طريقة منظمة لتصنيف وتنظيم مهام المشروع والموارد والواجبات. Aspose.Tasks هي مكتبة Java قوية تسمح للمطورين بمعالجة وإدارة ملفات Microsoft Project برمجياً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من إعداد المتطلبات الأساسية التالية:
### 1. بيئة تطوير جافا
تأكد من تثبيت Java Development Kit (JDK) على نظامك. يمكنك تنزيل JDK وتثبيته من موقع Oracle الإلكتروني.
### 2. Aspose.مكتبة المهام
 قم بتنزيل مكتبة Aspose.Tasks وتضمينها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[Aspose.Tasks لصفحة تنزيل Java](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية من Aspose.Tasks في كود Java الخاص بك:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
لنقم الآن بتقسيم رمز المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تحميل المشروع
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 في هذه الخطوة، نقوم بتحميل ملف Microsoft Project إلى ملف`Project` كائن باستخدام اسم الملف المقدم.
## الخطوة 2: استرداد رموز المخطط التفصيلي
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
نحن نكرر من خلال كل تعريف رمز المخطط التفصيلي في المشروع.
## الخطوة 3: الوصول إلى خصائص التعليمات البرمجية للمخطط التفصيلي
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
نقوم باسترداد وطباعة خصائص مختلفة لتعريف رمز المخطط التفصيلي مثل الاسم المستعار ومعرف الحقل واسم الحقل.
## الخطوة 4: التحقق من الرمز المخصص للمؤسسة
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
نحن نتحقق مما إذا كان رمز المخطط التفصيلي هو رمز مخصص للمؤسسة ونطبع النتيجة وفقًا لذلك.
## الخطوة 5: عرض أقنعة التعليمات البرمجية للمخطط التفصيلي
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
نحن نكرر كل قناع مرتبط برمز المخطط التفصيلي ونطبع مستواه وقيمة القناع.
## الخطوة 6: عرض قيم رمز المخطط التفصيلي
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
نحن نكرر كل قيمة من قيم التعليمات البرمجية التفصيلية ونطبع وصفها ومعرف القيمة والقيمة والنوع.
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استرداد رموز المخطط التفصيلي لـ MS Project باستخدام Aspose.Tasks لـ Java. باتباع الخطوات المقدمة، يمكنك الوصول إلى رموز المخطط التفصيلي ومعالجتها بشكل فعال في تطبيقات Java الخاصة بك، مما يتيح إمكانات إدارة المشاريع المتقدمة.
## الأسئلة الشائعة
### س1: هل يمكنني استخدام Aspose.Tasks لـ Java لتعديل رموز المخطط التفصيلي في ملف المشروع؟
ج: نعم، يوفر Aspose.Tasks for Java واجهات برمجة التطبيقات لتعديل رموز المخطط التفصيلي في ملفات MS Project برمجيًا.
### س2: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ Java من[موقع Aspose.Tasks](https://releases.aspose.com/).
### س3: كيف يمكنني الحصول على الدعم الفني لـ Aspose.Tasks لـ Java؟
 ج: يمكنك الحصول على الدعم الفني بزيارة الموقع[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) ونشر استفساراتك هناك.
### س4: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك شراء ترخيص مؤقت لـ Aspose.Tasks لـ Java من[صفحة الشراء](https://purchase.aspose.com/temporary-license/).
### س5: أين يمكنني العثور على الوثائق الكاملة لـ Aspose.Tasks لـ Java؟
 ج: يمكنك الرجوع إلى[توثيق](https://reference.aspose.com/tasks/java/) للحصول على معلومات تفصيلية حول استخدام Aspose.Tasks لـ Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
