---
title: صيغ مشروع MS مع Aspose.Tasks لجافا
linktitle: العمل مع الصيغ في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية التعامل مع ملفات MS Project في Java باستخدام مكتبة Aspose.Tasks. إنشاء السمات وتعديلها وحسابها بسهولة.
weight: 11
url: /ar/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# صيغ مشروع MS مع Aspose.Tasks لجافا

## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في العمل مع صيغ MS Project باستخدام Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة قوية تمكن المطورين من التعامل مع ملفات Microsoft Project برمجياً. بفضل ميزاته الشاملة، يمكنك بسهولة إنشاء ملفات المشروع وقراءتها وتعديلها وتحويلها في تطبيقات Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من إعداد المتطلبات الأساسية التالية:
### بيئة تطوير جافا
تأكد من تثبيت Java Development Kit (JDK) على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من موقع Oracle الإلكتروني.
### Aspose.مكتبة المهام
أنت بحاجة إلى إضافة مكتبة Aspose.Tasks إلى مشروع Java الخاص بك. يمكنك تحميل المكتبة من[صفحة تنزيل Aspose.Tasks لـ Java](https://releases.aspose.com/tasks/java/) وإدراجه في تبعيات مشروعك.

## حزم الاستيراد
قبل الغوص في الأمثلة، قم باستيراد الحزم الضرورية إلى كود Java الخاص بك:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

دعنا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: إنشاء مشروع اختبار باستخدام حقل مخصص
```java
Project project = CreateTestProjectWithCustomField();
```
 أولاً، قم بإنشاء مشروع اختباري بحقل مخصص باستخدام الملف`CreateTestProjectWithCustomField()` طريقة. ستُرجع هذه الطريقة كائن مشروع يمثل المشروع المنشأ حديثًا.
## الخطوة 2: تحديد تعريف السمة الموسعة
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
استرجع تعريف السمة الموسعة من المشروع وقم بتعيين الاسم المستعار والصيغة الخاصة به. في هذا المثال، نقوم بتعريف سمة لحساب عدد الأيام من تاريخ الانتهاء إلى الموعد النهائي.
## الخطوة 3: تحديد الموعد النهائي للمهمة
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
قم بإنشاء كائن تقويم وقم بتعيين تاريخ الموعد النهائي. ثم قم باسترداد مهمة من المشروع وقم بتعيين الموعد النهائي لها باستخدام كائن التقويم.
## الخطوة 4: احفظ المشروع
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
وأخيرًا، احفظ المشروع في ملف بالاسم والتنسيق المحددين. في هذه الحالة، نقوم بحفظه كملف MPP.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية العمل مع صيغ MS Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك التعامل بفعالية مع ملفات المشروع برمجيًا، وإضافة حقول مخصصة وحساب السمات بناءً على الصيغ.

## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع لغات البرمجة الأخرى؟
ج: نعم، يدعم Aspose.Tasks العديد من لغات البرمجة بما في ذلك Java و.NET والمزيد.
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Tasks؟
 ج: يمكنك العثور على الوثائق الخاصة بـ Aspose.Tasks[هنا](https://reference.aspose.com/tasks/java/).
### س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 ج: للحصول على الدعم، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
### س: هل أحتاج إلى ترخيص مؤقت لاستخدام Aspose.Tasks؟
ج: إذا كنت بحاجة إلى ميزات إضافية، يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
