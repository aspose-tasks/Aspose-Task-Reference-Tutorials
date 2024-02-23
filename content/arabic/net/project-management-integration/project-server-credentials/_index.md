---
title: إدارة بيانات اعتماد خادم MS Project في Aspose.Tasks
linktitle: إدارة بيانات اعتماد خادم المشروع في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة بيانات اعتماد MS Project Server بسلاسة باستخدام Aspose.Tasks لـ .NET. تعزيز كفاءة إدارة المشروع.
type: docs
weight: 22
url: /ar/net/project-management-integration/project-server-credentials/
---
## مقدمة
في مجال إدارة المشاريع، يعد التنسيق الفعال والتواصل السلس أمرًا محوريًا لنجاح تنفيذ المشروع. يوفر Aspose.Tasks for .NET حلاً شاملاً لإدارة بيانات اعتماد Microsoft Project Server، مما يمكّن المستخدمين من الوصول إلى بيانات المشروع ومعالجتها بشكل آمن. يتعمق هذا البرنامج التعليمي في عملية إدارة بيانات اعتماد MS Project Server باستخدام Aspose.Tasks لـ .NET، وتوجيه المستخدمين خلال كل خطوة لضمان تجربة سلسة.
## المتطلبات الأساسية
قبل الشروع في رحلة إدارة بيانات اعتماد MS Project Server باستخدام Aspose.Tasks لـ .NET، تأكد من استيفاء المتطلبات الأساسية التالية:
### 1. تثبيت Aspose.Tasks لـ .NET
 للبدء، قم بتنزيل وتثبيت Aspose.Tasks لـ .NET من الملف المتوفر[رابط التحميل](https://releases.aspose.com/tasks/net/), اتبع تعليمات التثبيت لدمج المكتبة في بيئة .NET الخاصة بك بسلاسة.
### 2. الوصول إلى بيانات الاعتماد
اجمع بيانات الاعتماد اللازمة للوصول إلى خادم MS Project. يتضمن ذلك عنوان مجال SharePoint واسم المستخدم وكلمة المرور المرتبطة بخادم Project.

## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء المطلوبة للاستفادة من الوظائف التي يوفرها Aspose.Tasks لـ .NET بكفاءة.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## الخطوة 1: تحديد مسار دليل المستند
```csharp
String DataDir = "Your Document Directory";
```
## الخطوة 2: قم بتعيين عنوان مجال SharePoint واسم المستخدم وكلمة المرور
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## الخطوة 3: إنشاء بيانات اعتماد خادم المشروع
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## الخطوة 4: تحميل ملف المشروع
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## الخطوة 5: تهيئة مدير خادم المشروع
```csharp
var manager = new ProjectServerManager(credentials);
```
## الخطوة 6: إنشاء مشروع جديد
```csharp
manager.CreateNewProject(newProject);
```
## الخطوة 7: استرداد قائمة المشروع
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## الخطوة 8: التكرار من خلال قائمة المشاريع
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## خاتمة
تعد إدارة بيانات اعتماد MS Project Server بشكل فعال أمرًا بالغ الأهمية لإدارة المشاريع بشكل مبسط. يعمل Aspose.Tasks for .NET على تبسيط هذه العملية من خلال توفير مجموعة قوية من الوظائف. باتباع الدليل التفصيلي الموضح في هذا البرنامج التعليمي، يمكن للمستخدمين دمج Aspose.Tasks for .NET بسلاسة في مشاريعهم، مما يضمن الوصول الآمن إلى بيانات المشروع ومعالجتها.
## الأسئلة الشائعة
### س: هل Aspose.Tasks for .NET متوافق مع كافة إصدارات Microsoft Project Server؟
ج: تم تصميم Aspose.Tasks for .NET ليكون متوافقًا مع الإصدارات المختلفة من Microsoft Project Server، مما يضمن تعدد الاستخدامات والمرونة للمستخدمين.
### س: هل يمكنني دمج Aspose.Tasks لـ .NET في مشروع .NET الحالي الخاص بي؟
ج: نعم، يمكن دمج Aspose.Tasks لـ .NET بسلاسة في مشاريع .NET الحالية، مما يسهل إمكانات إدارة المشروع بكفاءة.
### س: هل يوفر Aspose.Tasks for .NET الدعم للوصول إلى موارد المشروع؟
ج: بالتأكيد، يقدم Aspose.Tasks for .NET دعمًا شاملاً للوصول إلى موارد المشروع ومعالجتها، مما يعزز كفاءة إدارة المشروع.
### س: هل هناك أي خيارات ترخيص متاحة لـ Aspose.Tasks لـ .NET؟
ج: نعم، يوفر Aspose.Tasks for .NET خيارات ترخيص مرنة، بما في ذلك التراخيص المؤقتة للأغراض التجريبية والتراخيص الكاملة للاستخدام التجاري.
### س: أين يمكنني طلب المساعدة أو الدعم فيما يتعلق بـ Aspose.Tasks لـ .NET؟
 ج: لأية استفسارات أو مساعدة فيما يتعلق بـ Aspose.Tasks لـ .NET، يمكنك زيارة منتدى الدعم على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).## إكمال كود المصدر