---
title: استخراج معلومات مشروع MS في Aspose.Tasks
linktitle: استخراج معلومات المشروع في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية استخراج معلومات MS Project بسهولة باستخدام Aspose.Tasks لـ .NET. انغمس في برنامجنا التعليمي الشامل.
weight: 20
url: /ar/net/project-management-integration/project-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخراج معلومات مشروع MS في Aspose.Tasks

## مقدمة
هل تتطلع إلى استخراج المعلومات بكفاءة من ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET؟ في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة. ولكن قبل أن نتعمق في تفاصيل التنفيذ، دعنا نتأكد أولاً من أن لديك كل ما تحتاجه.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
### 1. Aspose.Tasks لـ .NET
 تأكد من تثبيت Aspose.Tasks لمكتبة .NET. إذا لم تكن قد قمت بذلك بالفعل، فيمكنك تنزيله من[Aspose.Tasks لموقع ويب .NET](https://releases.aspose.com/tasks/net/).
### 2. بيانات اعتماد SharePoint
ستحتاج إلى بيانات الاعتماد للوصول إلى SharePoint حيث يتم تخزين ملفات MS Project الخاصة بك. تأكد من أن لديك المعلومات التالية:
- عنوان مجال SharePoint
- اسم المستخدم
- كلمة المرور
## استيراد مساحات الأسماء
بمجرد الانتهاء من ترتيب متطلباتك الأساسية، فقد حان الوقت لاستيراد مساحات الأسماء الضرورية إلى مشروعك.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
الآن دعونا نقسم عملية استخراج معلومات MS Project إلى خطوات متعددة.
## الخطوة 1: تقديم بيانات الاعتماد
أولاً، تحتاج إلى توفير بيانات اعتماد SharePoint الخاصة بك للوصول إلى Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## الخطوة 2: تهيئة مدير خادم المشروع
 بعد ذلك، قم بتهيئة أ`ProjectServerManager` المثال مع بيانات الاعتماد المقدمة.
```csharp
var reader = new ProjectServerManager(credentials);
```
## الخطوة 3: استرداد قائمة المشروع
الآن، يمكنك استرداد قائمة المشاريع من خادم المشروع.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## الخطوة 4: طباعة معلومات المشروع
وأخيرًا، قم بمراجعة قائمة المشاريع وطباعة معلوماتها.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية استخراج معلومات MS Project باستخدام Aspose.Tasks لـ .NET. ومن خلال هذه المعرفة، يمكنك الآن دمج هذه الوظيفة في تطبيقات .NET الخاصة بك بسلاسة.
## الأسئلة الشائعة
### س١: هل يمكنني استخدام Aspose.Tasks لـ .NET مع أي إصدار من Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks for .NET إصدارات مختلفة من Microsoft Project، بما في ذلك 2003 و2007 و2010 و2013 و2016 و2019.
### س2: هل Aspose.Tasks لـ .NET متوافق مع نظامي التشغيل Windows وLinux؟
ج: نعم، Aspose.Tasks for .NET متوافق مع كل من نظامي التشغيل Windows وLinux، مما يجعله متعدد الاستخدامات لبيئات التطوير المختلفة.
### س3: هل يمكنني استخراج تبعيات المهام باستخدام Aspose.Tasks لـ .NET؟
ج: بالتأكيد! يوفر Aspose.Tasks for .NET وظائف قوية ليس فقط لاستخراج معلومات المشروع الأساسية ولكن أيضًا تبعيات المهام والتفاصيل المعقدة الأخرى.
### س 4: هل يقدم Aspose.Tasks لـ .NET الدعم الفني؟
 ج: نعم، يمكنك الحصول على الدعم الفني لـ Aspose.Tasks لـ .NET من خلال[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)حيث يمكنك طرح الأسئلة وطلب المساعدة من الخبراء.
### س5: هل يمكنني تجربة Aspose.Tasks لـ .NET قبل شرائه؟
 ج: بالتأكيد! يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Tasks لـ .NET من[صفحة الإصدارات](https://releases.aspose.com/)مما يسمح لك باستكشاف ميزاته قبل اتخاذ قرار الشراء.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
