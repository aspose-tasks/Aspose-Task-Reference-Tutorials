---
title: تحديد إصدار MS Project باستخدام Aspose.Tasks
linktitle: تحديد إصدار المشروع باستخدام Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحديد إصدار ملفات MS Project برمجياً باستخدام Aspose.Tasks لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
weight: 12
url: /ar/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديد إصدار MS Project باستخدام Aspose.Tasks

## مقدمة
سيرشدك هذا البرنامج التعليمي خلال استخدام Aspose.Tasks لـ Java لتحديد إصدار ملف MS Project خطوة بخطوة. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات Java قوية تسمح للمطورين بمعالجة ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لملف Java JAR: قم بتنزيل مكتبة Aspose.Tasks لـ Java من ملف[موقع إلكتروني](https://releases.aspose.com/tasks/java/) وإضافته إلى مشروع Java الخاص بك.
3. ملف MS Project: قم بإعداد ملف MS Project (تنسيق XML) للاختبار.

## حزم الاستيراد
قبل الغوص في الكود، فلنستورد الحزم الضرورية:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## الخطوة 1: إعداد المشروع
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى الدليل الذي يحتوي على ملف MS Project الخاص بك.
## الخطوة 2: تحميل المشروع
```java
Project project = new Project(dataDir + "input.xml");
```
 يستبدل`"input.xml"` باسم ملف MS Project الخاص بك.
## الخطوة 3: تحديد إصدار المشروع
```java
//عرض خاصية إصدار المشروع
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
يقوم مقتطف الكود هذا باسترداد وطباعة الإصدار وآخر تاريخ محفوظ لملف MS Project.
## الخطوة 4: عرض النتيجة
```java
//عرض نتيجة التحويل.
System.out.println("Process completed Successfully");
```
يشير هذا الخط إلى اكتمال العملية.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية تحديد إصدار ملف MS Project باستخدام Aspose.Tasks لـ Java. باتباع الدليل الموضح خطوة بخطوة، يمكنك العمل بكفاءة مع ملفات MS Project في تطبيقات Java الخاصة بك دون أي متاعب.

## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع لغات البرمجة الأخرى؟
ج: نعم، يدعم Aspose.Tasks لغات برمجة متعددة بما في ذلك .NET وJava وC++.
### س: هل Aspose.Tasks مناسب للمشاريع واسعة النطاق؟
ج: بالتأكيد، تم تصميم Aspose.Tasks للتعامل مع المشاريع من أي حجم بسهولة.
### س: هل يمكنني تخصيص بيانات المشروع باستخدام Aspose.Tasks؟
ج: نعم، يمكنك معالجة بيانات المشروع وتعديل المهام والموارد وغير ذلك الكثير باستخدام Aspose.Tasks.
### س: هل يتطلب Aspose.Tasks تثبيت Microsoft Project؟
ج: لا، Aspose.Tasks يعمل بشكل مستقل ولا يتطلب تثبيت Microsoft Project.
### س: هل يتوفر الدعم الفني لـ Aspose.Tasks؟
 ج: نعم، يمكنك الحصول على الدعم الفني من منتدى Aspose.Tasks على[هنا](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
