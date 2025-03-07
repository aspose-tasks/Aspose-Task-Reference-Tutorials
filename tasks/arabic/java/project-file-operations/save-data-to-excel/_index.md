---
title: حفظ بيانات مشروع MS إلى Excel في Aspose.Tasks
linktitle: حفظ البيانات في Excel في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية حفظ بيانات Microsoft Project في ملفات Excel باستخدام Aspose.Tasks لـ Java. التكامل السهل لمطوري جافا.
weight: 19
url: /ar/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ بيانات مشروع MS إلى Excel في Aspose.Tasks

## مقدمة
Aspose.Tasks for Java هي مكتبة قوية تسمح للمطورين بالعمل مع ملفات Microsoft Project برمجياً. سنرشدك في هذا البرنامج التعليمي خلال عملية حفظ البيانات من ملف مشروع إلى ملف Excel خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيل أحدث إصدار من JDK وتثبيته من موقع Oracle الإلكتروني.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks لـ Java من[رابط التحميل](https://releases.aspose.com/tasks/java/) وإدراجه في مشروع Java الخاص بك.

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم الضرورية في كود Java الخاص بك للعمل مع Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

دعنا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تحديد مسار دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"`مع المسار إلى دليل البيانات الخاص بك حيث يوجد ملف المشروع.
## الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "project5.mpp");
```
يقوم سطر التعليمات البرمجية هذا بتحميل ملف المشروع المسمى "project5.mpp" من دليل البيانات المحدد.
## الخطوة 3: احفظ المشروع باسم XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 هنا،`save` يتم استخدام الطريقة لحفظ ملف المشروع المحمل كملف Excel بالاسم "project1.xlsx" في نفس دليل البيانات. نحن نحدد`SaveFileFormat.Xlsx` المعلمة لحفظه بتنسيق XLSX.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية حفظ البيانات من ملف Microsoft Project إلى ملف Excel باستخدام Aspose.Tasks لـ Java. باتباع الخطوات المتوفرة، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks لـ Java لمعالجة بيانات المشروع برمجيًا؟
نعم، يوفر Aspose.Tasks for Java ميزات شاملة لمعالجة بيانات المشروع، بما في ذلك قراءة ملفات المشروع وكتابتها وتعديلها.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks لـ Java من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Tasks لـ Java؟
يمكنك العثور على الوثائق الخاصة بـ Aspose.Tasks لـ Java[هنا](https://reference.aspose.com/tasks/java/).
### كيف يمكنني الحصول على الدعم لأية مشكلات أو استفسارات تتعلق بـ Aspose.Tasks لـ Java؟
 يمكنك الحصول على الدعم من خلال زيارة منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 نعم، يمكنك شراء ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
