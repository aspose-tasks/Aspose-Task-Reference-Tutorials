---
title: قراءة بيانات تعريف المجموعة في Aspose.Tasks
linktitle: قراءة بيانات تعريف المجموعة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية قراءة بيانات تعريف المجموعة من ملفات Microsoft Project باستخدام Aspose.Tasks لـ Java. اتبع البرنامج التعليمي خطوة بخطوة.
weight: 10
url: /ar/java/project-data-reading/read-group-definition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة بيانات تعريف المجموعة في Aspose.Tasks

## مقدمة
Aspose.Tasks for Java هي مكتبة قوية تتيح للمطورين التعامل مع ملفات Microsoft Project بسهولة. في هذا البرنامج التعليمي، سنتعرف على عملية قراءة بيانات تعريف المجموعة من ملف المشروع خطوة بخطوة باستخدام Aspose.Tasks لـ Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): اختر IDE المفضل لديك مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
أولاً، لنستورد الحزم اللازمة لبدء العمل مع Aspose.Tasks لـ Java.
```java
import com.aspose.tasks.*;
```
## الخطوة 1: إعداد دليل البيانات الخاص بك
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى الدليل الذي يحتوي على ملف المشروع الخاص بك.
## الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "project.mpp");
```
 قم بتحميل ملف المشروع الخاص بك باستخدام`Project` منشئ الفئة، وتمرير المسار إلى ملف المشروع الخاص بك.
## الخطوة 3: استرداد عدد مجموعات المهام
```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```
 استرداد عدد مجموعات المهام في المشروع باستخدام`getTaskGroups()` طريقة.
## الخطوة 4: استرداد معلومات مجموعة المهام
```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```
استرداد معلومات حول مجموعة مهام محددة، مثل اسمها وعدد معايير المجموعة.
## الخطوة 5: استرداد معلومات معيار المجموعة
```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```
استرجع معلومات حول معايير المجموعة، مثل الحقل والمجموعة ولون الخلية والنمط.
## الخطوة 6: التحقق من المجموعة الأصلية
```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```
تحقق مما إذا كانت المجموعة الأصلية مساوية لمجموعة المهام.
## الخطوة 7: استرداد معلومات الخط الخاص بالمعيار
```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```
استرداد معلومات الخط للمعيار، مثل عائلة الخط وحجمه ونمطه وترتيب الفرز.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية قراءة بيانات تعريف المجموعة من ملف Microsoft Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك استخراج معلومات مجموعة المهام واستخدامها بشكل فعال في تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java لتعديل ملفات المشروع؟
ج: نعم، يوفر Aspose.Tasks for Java ميزات شاملة لقراءة ملفات Microsoft Project وتعديلها برمجيًا.
### س: هل Aspose.Tasks for Java متوافق مع كافة إصدارات ملفات Microsoft Project؟
ج: يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وXML.
### س: كيف يمكنني التعامل مع الأخطاء أثناء العمل مع Aspose.Tasks لـ Java؟
ج: يمكنك تنفيذ آليات معالجة الأخطاء باستخدام كتل محاولة الالتقاط للتعامل بأمان مع الاستثناءات التي قد تحدث أثناء معالجة الملف.
### س: هل يقدم Aspose.Tasks for Java الدعم لتصدير بيانات المشروع إلى تنسيقات أخرى؟
ج: نعم، يتيح لك Aspose.Tasks for Java تصدير بيانات المشروع إلى تنسيقات مثل PDF وXLSX وCSV.
### س: أين يمكنني العثور على موارد ودعم إضافيين لـ Aspose.Tasks لـ Java؟
 ج: يمكنك زيارة[Aspose.Tasks لوثائق جافا](https://reference.aspose.com/tasks/java/) للحصول على أدلة شاملة والرجوع إلى[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
