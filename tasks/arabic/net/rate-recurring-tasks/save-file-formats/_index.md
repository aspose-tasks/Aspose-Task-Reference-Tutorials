---
title: حفظ ملفات مشروع MS بتنسيقات مختلفة في Aspose.Tasks
linktitle: حفظ الملفات بتنسيقات مختلفة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية حفظ ملفات MS Project بتنسيقات مختلفة باستخدام Aspose.Tasks لـ .NET. خطوات سهلة لإدارة المشاريع بكفاءة.
weight: 17
url: /ar/net/rate-recurring-tasks/save-file-formats/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ ملفات مشروع MS بتنسيقات مختلفة في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية حفظ ملفات Microsoft Project بتنسيقات مختلفة باستخدام Aspose.Tasks لـ .NET. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات قوية تسمح للمطورين بمعالجة ملفات المشروع وإدارتها برمجيًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Aspose.Tasks لـ .NET: قم بتنزيل Aspose.Tasks لـ .NET وتثبيته من[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio.
3. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في بداية ملف C# الخاص بك:
```csharp

using Aspose.Tasks.Saving;
```
## الخطوة 1: إنشاء كائن المشروع
أولاً، قم بإنشاء كائن Project وقم بتحميل ملف Microsoft Project الخاص بك.
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## الخطوة 2: حفظ المشروع بتنسيق CSV
الآن، دعونا نحفظ المشروع بتنسيق CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## الخطوة 3: استكشاف التنسيقات الأخرى
 يدعم Aspose.Tasks تنسيقات مختلفة لحفظ ملفات المشروع، مثل XML وPDF وXLSX والمزيد. يمكنك استكشاف هذه التنسيقات ببساطة عن طريق تغيير ملف`SaveFileFormat` المعلمة في`Save` طريقة.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
باتباع هذه الخطوات، يمكنك بسهولة حفظ ملفات Microsoft Project بتنسيقات مختلفة باستخدام Aspose.Tasks لـ .NET.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية حفظ ملفات MS Project بتنسيقات مختلفة باستخدام Aspose.Tasks لـ .NET. يعمل Aspose.Tasks على تبسيط عملية معالجة ملفات المشروع برمجيًا، مما يوفر المرونة والكفاءة للمطورين.
## الأسئلة الشائعة
### س: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟
ج: يدعم Aspose.Tasks تنسيقات Microsoft Project 2003 XML وMicrosoft Project 2007 MPP وMicrosoft Project 2010 MPP.
### س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل التراخيص المؤقتة متاحة لـ Aspose.Tasks؟
 ج: نعم، التراخيص المؤقتة متاحة لأغراض التقييم. يمكنك الحصول على واحدة[هنا](https://purchase.aspose.com/temporary-license/).
### س: ما هو سعر Aspose.Tasks؟
 ج: يمكن العثور على معلومات التسعير على صفحة شراء Aspose.Tasks[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
