---
title: خادم حفظ خيارات مشروع MS لـ Aspose.Tasks
linktitle: خيارات حفظ خادم المشروع لـ Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية حفظ خيارات Microsoft Project لـ Aspose.Tasks باستخدام تكامل Project Server. تعزيز سير عمل إدارة المشروع الخاص بك.
weight: 16
url: /ar/net/saving-options/project-server-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# خادم حفظ خيارات مشروع MS لـ Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في حفظ خيارات Microsoft Project لـ Aspose.Tasks باستخدام Project Server. Aspose.Tasks عبارة عن واجهة برمجة تطبيقات .NET قوية تتيح للمطورين العمل مع ملفات Microsoft Project برمجيًا. من خلال الاستفادة من إمكانات خادم Project، يمكننا دمج Aspose.Tasks بسلاسة في سير عمل إدارة المشروع لدينا. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Tasks لـ .NET: قم بتثبيت Aspose.Tasks لـ .NET من[رابط التحميل](https://releases.aspose.com/tasks/net/).
   
2. الوصول إلى خادم Project: ستحتاج إلى بيانات اعتماد الوصول وعنوان URL لمثيل خادم Project الخاص بك. إذا لم يكن لديك واحدة، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
3. ملف Microsoft Project: قم بإعداد ملف Microsoft Project (.mpp) الذي تريد حفظه باستخدام Aspose.Tasks.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية في مشروعك:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## الخطوة 1: تهيئة المشروع وبيانات الاعتماد
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 تأكد من استبدال`"Your Document Directory"`, `URL`, `Domain`, `UserName` ، و`Password` بقيمك الفعلية
## الخطوة 2: إنشاء مدير خادم المشروع
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## الخطوة 3: تحديد خيارات الحفظ
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 أضبط ال`ProjectGuid`, `ProjectName`, `Timeout` ، و`PollingInterval` وفقا لمتطلباتك.
## الخطوة 4: حفظ المشروع على الخادم
```csharp
manager.CreateNewProject(project, options);
```
سيؤدي هذا إلى حفظ المشروع على خادم Project بالخيارات المحددة.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية حفظ خيارات Microsoft Project لـ Aspose.Tasks باستخدام تكامل Project Server. باتباع هذه الخطوات، يمكنك دمج Aspose.Tasks بسلاسة في سير عمل إدارة المشروع لديك، مما يعزز الكفاءة والإنتاجية.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع إصدارات مختلفة من Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.
### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).
### س: هل يدعم Aspose.Tasks تعدد العمليات؟
ج: نعم، تم تصميم Aspose.Tasks ليكون آمنًا، مما يسمح بالوصول المتزامن إلى بيانات المشروع.
### س: هل يمكنني تخصيص خيارات الحفظ عند استخدام تكامل Project Server؟
ج: نعم، يمكنك تخصيص خيارات الحفظ مثل اسم المشروع، والمهلة، والفاصل الزمني للاستقصاء لتناسب متطلباتك.
### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks؟
 ج: يمكنك العثور على الدعم والمساعدة على[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
