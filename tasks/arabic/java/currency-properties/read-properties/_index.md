---
title: اقرأ خصائص العملة في مشاريع Aspose.Tasks
linktitle: اقرأ خصائص العملة في مشاريع Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية استخراج معلومات العملة من ملفات MS Project باستخدام Aspose.Tasks لـ Java. دليل خطوة بخطوة المقدمة.
weight: 10
url: /ar/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# اقرأ خصائص العملة في مشاريع Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سوف نتعلم كيفية استخدام Aspose.Tasks لـ Java لقراءة خصائص العملة من ملفات Microsoft Project. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات Java قوية تمكن المطورين من التعامل مع مستندات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project. باتباع الخطوات الموضحة أدناه، ستتمكن من استخراج المعلومات المتعلقة بالعملة دون عناء.
## المتطلبات الأساسية
قبل متابعة هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks for Java JAR: قم بتنزيل مكتبة Aspose.Tasks for Java من[هنا](https://releases.aspose.com/tasks/java/) وإدراجه في مشروع Java الخاص بك.
## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية إلى فئة Java الخاصة بك:
```java
import com.aspose.tasks.*;
```
## الخطوة 1: قم بإعداد دليل المشروع الخاص بك
أولاً، قم بإعداد دليل المشروع الخاص بك حيث يوجد ملف Microsoft Project الخاص بك. يمكنك تحديد مسار الدليل هذا كما يلي:
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار الفعلي إلى دليل المشروع الخاص بك.
## الخطوة 2: إنشاء مثيل قارئ المشروع
 إنشاء مثيل أ`Project` الكائن عن طريق توفير المسار إلى ملف Microsoft Project الخاص بك:
```java
Project project = new Project(dataDir + "project.mpp");
```
 تأكد من الاستبدال`"project.mpp"` باسم ملف MS Project الخاص بك.
## الخطوة 3: عرض خصائص العملة
استرداد وعرض خصائص العملة من ملف المشروع:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
يقوم مقطع التعليمات البرمجية هذا بجلب معلومات مثل رمز العملة والأرقام والرمز وموضع الرمز من ملف MS Project وطباعتها على وحدة التحكم.
## الخطوة 4: إكمال العملية
وأخيرًا، اطبع رسالة تشير إلى إتمام العملية بنجاح:
```java
System.out.println("Process completed Successfully");
```
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية قراءة خصائص العملة من ملفات Microsoft Project باستخدام Aspose.Tasks لـ Java. باتباع الخطوات الموضحة، يمكنك بسهولة استخراج المعلومات المتعلقة بالعملة من ملفات مشروعك برمجيًا، مما يتيح التكامل السلس في تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### س: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟
ج: يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، بما في ذلك ملفات MPP التي تم إنشاؤها بواسطة MS Project 2003-2021.
### س: هل يمكنني تعديل خصائص العملة باستخدام Aspose.Tasks؟
ج: نعم، Aspose.Tasks يسمح لك بقراءة وتعديل خصائص العملة في ملفات MS Project برمجياً.
### س: هل Aspose.Tasks مناسب للاستخدام التجاري؟
 ج: نعم، Aspose.Tasks هي مكتبة تجارية مصممة للاستخدام المهني. يمكنك شراء ترخيص[هنا](https://purchase.aspose.com/buy).
### س: هل يقدم Aspose.Tasks نسخة تجريبية مجانية؟
 ج: نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Tasks[هنا](https://releases.aspose.com/).
### س: أين يمكنني طلب المساعدة أو الدعم بخصوص Aspose.Tasks؟
 ج: يمكنك زيارة منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15) لأية مساعدة أو استفسار.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
