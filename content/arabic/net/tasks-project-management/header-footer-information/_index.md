---
title: قم باستخراج معلومات الرأس والتذييل باستخدام Aspose.Tasks
linktitle: معلومات الرأس والتذييل في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعلم كيفية استخراج معلومات الرأس والتذييل من ملفات MS Project باستخدام Aspose.Tasks لـ .NET. حل سهل وفعال وصديق للمطورين.
type: docs
weight: 29
url: /ar/net/tasks-project-management/header-footer-information/
---
## مقدمة
Aspose.Tasks for .NET هي مكتبة قوية تسمح للمطورين بمعالجة ملفات Microsoft Project بسهولة. في هذا البرنامج التعليمي، سوف نتعلم كيفية استرداد معلومات الرأس والتذييل من ملفات MS Project باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Visual Studio: قم بتثبيت Visual Studio على نظامك.
2.  Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة .NET من[هنا](https://releases.aspose.com/tasks/net/).
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C#.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. سيسمح لك هذا بالوصول إلى الفئات والأساليب التي توفرها مكتبة Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## الخطوة 1: تهيئة كائن المشروع
 للبدء، تحتاج إلى تهيئة أ`Project` كائن عن طريق تحميل ملف MS Project موجود.
```csharp
// المسار إلى دليل المستندات.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## الخطوة 2: استرداد معلومات الرأس والتذييل
 بمجرد تحميل ملف المشروع، يمكنك استرداد معلومات الرأس والتذييل باستخدام الملف`PageInfo` ملكية.
```csharp
var info = project.DefaultView.PageInfo;
// معلومات الرأس
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// معلومات التذييل
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
باتباع هذه الخطوات البسيطة، يمكنك بسهولة استرداد معلومات الرأس والتذييل من ملفات MS Project باستخدام Aspose.Tasks لـ .NET.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية استخراج معلومات الرأس والتذييل من ملفات MS Project باستخدام Aspose.Tasks لـ .NET. تعمل هذه المكتبة القوية على تبسيط مهمة العمل مع ملفات المشروع في تطبيقات C#، مما يوفر للمطورين أدوات قوية للمعالجة.
### الأسئلة الشائعة
### هل يمكنني تعديل معلومات الرأس والتذييل باستخدام Aspose.Tasks؟
نعم، يمكنك تعديل معلومات الرأس والتذييل برمجيًا باستخدام Aspose.Tasks لـ .NET.
### هل يدعم Aspose.Tasks تنسيقات ملفات المشروع الأخرى إلى جانب MS Project؟
نعم، يدعم Aspose.Tasks العديد من تنسيقات ملفات المشروع، بما في ذلك MPP وXML وMPX.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Tasks؟
 يمكنك العثور على وثائق Aspose.Tasks[هنا](https://reference.aspose.com/tasks/net/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 يمكنك الحصول على الدعم لـ Aspose.Tasks بزيارة الموقع[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).