---
title: قم بتكوين التوقيع الرقمي لـ MS Project PDF باستخدام Aspose.Tasks
linktitle: تكوين تفاصيل التوقيع الرقمي لملف PDF في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين تفاصيل التوقيع الرقمي لـ Microsoft Project PDF باستخدام Aspose.Tasks لـ .NET. تأكد من أمان وصحة ملفات مشروعك.
type: docs
weight: 10
url: /ar/net/pdf-security-configuration/pdf-digital-signature-details/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية تكوين تفاصيل التوقيع الرقمي لـ Microsoft Project PDF باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، ستتمكن من دمج التوقيعات الرقمية بسلاسة في ملفات MS Project الخاصة بك، مما يضمن الأمان والأصالة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Aspose.Tasks for .NET: تأكد من تثبيت Aspose.Tasks for .NET في بيئة التطوير الخاصة بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. ملف Microsoft Project: قم بإعداد ملف Microsoft Project الذي تريد العمل معه وتأكد من إمكانية الوصول إليه من خلال دليل المشروع الخاص بك.
3. شهادة X.509: احصل على شهادة X.509 التي سيتم استخدامها للتوقيع الرقمي. إذا لم يكن لديك واحدة، يمكنك إنشاء شهادة موقعة ذاتيًا لأغراض الاختبار.
## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية في مشروع .NET الخاص بك للوصول إلى الفئات والأساليب المطلوبة من Aspose.Tasks.
```csharp
using Aspose.Tasks;
using System;
using System.Security.Cryptography;
using System.Security.Cryptography.X509Certificates;

using Aspose.Tasks.Saving;
```
الآن، دعونا نقسم المثال إلى عدة خطوات:
## الخطوة 1: قم بتحميل ملف Microsoft Project
```csharp
// المسار إلى دليل المستندات.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```
## الخطوة 2: تكوين خيارات حفظ PDF
```csharp
var options = new PdfSaveOptions();
```
## الخطوة 3: تحديد شهادة X.509
```csharp
var certificate = new X509Certificate2();
```
## الخطوة 4: إنشاء تفاصيل توقيع PDF
```csharp
var signatureDetails = new PdfDigitalSignatureDetails(
    // تحديد الشهادة
    certificate,
    // تحديد سبب للتوقيع
    "reason",
    // تحديد مكان التوقيع
    "location",
    // تحديد تاريخ التوقيع
    new DateTime(2019, 1, 1),
    // تحديد خوارزمية التجزئة للتوقيع
    PdfDigitalSignatureHashAlgorithm.Sha1);
```
## الخطوة 5: عرض تفاصيل التوقيع
```csharp
Console.WriteLine("Certificate: " + signatureDetails.Certificate);
Console.WriteLine("Reason: " + signatureDetails.Reason);
Console.WriteLine("Location: " + signatureDetails.Location);
Console.WriteLine("Signature Date: " + signatureDetails.SignatureDate);
Console.WriteLine("Hash Algorithm: " + signatureDetails.HashAlgorithm);
```
## الخطوة 6: تعيين تفاصيل التوقيع الرقمي
```csharp
// ضبط تفاصيل التوقيع الرقمي
options.DigitalSignatureDetails = signatureDetails;
```
## الخطوة 7: احفظ المشروع بتفاصيل التشفير
```csharp
// احفظ المشروع بتفاصيل التشفير المحددة
project.Save(DataDir + "WorkWithPdfEncryptionDetails_out.pdf", options);
```
## خاتمة
تهانينا! لقد نجحت في تكوين تفاصيل التوقيع الرقمي لـ Microsoft Project PDF باستخدام Aspose.Tasks لـ .NET. باتباع هذه الخطوات، يمكنك التأكد من أمان وصحة ملفات MS Project الخاصة بك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام شهادة موقعة ذاتيًا للتوقيع الرقمي؟
ج: نعم، يمكنك استخدام شهادة موقعة ذاتيًا لأغراض الاختبار. ومع ذلك، بالنسبة لبيئات الإنتاج، يوصى باستخدام شهادة موثوقة صادرة عن مرجع مصدق.
### س: هل يدعم Aspose.Tasks خوارزميات التجزئة الأخرى للتوقيع الرقمي؟
ج: نعم، يدعم Aspose.Tasks خوارزميات التجزئة المتنوعة للتوقيع الرقمي، بما في ذلك SHA-1 وSHA-256 وSHA-512.
### س: هل يمكنني تخصيص مظهر التوقيع الرقمي في ملف PDF؟
ج: نعم، يمكنك تخصيص مظهر التوقيع الرقمي، بما في ذلك النص والخط واللون والموضع، وفقًا لمتطلباتك.
### س: هل من الممكن إزالة التوقيع الرقمي أو تحديثه بمجرد تطبيقه؟
ج: لا، بمجرد تطبيق التوقيع الرقمي على ملف PDF، لا يمكن إزالته أو تحديثه. ومع ذلك، يمكنك إضافة توقيعات إضافية إذا لزم الأمر.
### س: هل هناك أي قيود على حجم أو تعقيد ملف Microsoft Project؟
ج: يمكن لـ Aspose.Tasks التعامل مع ملفات Microsoft Project ذات الأحجام والتعقيدات المختلفة دون قيود. ومع ذلك، قد يختلف الأداء وفقًا للأجهزة والموارد المتاحة.