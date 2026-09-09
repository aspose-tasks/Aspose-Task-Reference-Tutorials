---
date: 2026-09-09
description: تعلم كيفية تحديد المهام المشتركة بين المشاريع باستخدام Aspose.Tasks for
  Java. استكشف التكامل السلس، الإدارة الفعّالة، وأمثلة من الواقع.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: تحديد المهام المشتركة بين المشاريع في Aspose.Tasks
og_description: تحديد المهام المشتركة بين المشاريع في Aspose.Tasks for Java. تعلم
  كيفية تعيين دليل المستندات، استرجاع معرفات المهام، وإدارة المشاريع المرتبطة بكفاءة.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: تحديد المهام المشتركة بين المشاريع في Aspose.Tasks – دليل Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: تحديد المهام المشتركة بين المشاريع في Aspose.Tasks
url: /ar/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديد المهام عبر المشاريع في Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي ستتعلم **كيفية تحديد المهام عبر المشاريع** باستخدام Aspose.Tasks للغة Java. سواءً كنت تدير مجموعة من الجداول الزمنية المتداخلة أو تحتاج إلى تدقيق الاعتماديات الخارجية، فإن الخطوات أدناه توضح لك كيفية العثور على المهام التي تشير إلى ملفات مشروع أخرى، واسترجاع معرّفاتها، والعمل معها برمجياً.

## إجابات سريعة
- **ماذا يعني “تحديد المهام عبر المشاريع”؟** يعني ذلك العثور على المهام التي تشير أو تعتمد على مهام في ملف مشروع آخر.  
- **أي طريقة تطبع معرّف المهمة؟** استخدم `externalTask.get(Tsk.ID)` لطباعة معرّف المهمة.  
- **كيف أضبط دليل المستند؟** عيّن مسار المجلد إلى متغيّر `String` (مثال: `dataDir`).  
- **أي خاصية تسترجع مهمة بواسطة UID؟** استدعِ `getChildren().getByUid(yourUid)`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Tasks للعمليات التجارية.

## ما هو “تحديد المهام عبر المشاريع”؟
يسمح لك تحديد المهام عبر المشاريع بتتبع العلاقات بين المهام الموزعة عبر ملفات Microsoft Project متعددة. من خلال العثور على المهام التي تشير أو تعتمد على جداول زمنية خارجية، يمكنك فهم كيفية تفاعل عناصر العمل عبر حدود المشروع، منع التكرار، والحفاظ على جداول زمنية دقيقة. هذه القدرة أساسية للمحافظ الكبيرة حيث تُشارك المهام أو تعتمد على جداول زمنية خارجية.

## لماذا نستخدم Aspose.Tasks للغة Java؟
يدعم Aspose.Tasks للغة Java **أكثر من 50 تنسيق إدخال وإخراج** (بما في ذلك MPP و MPX و XML و CSV) ويمكنه معالجة مشاريع تحتوي على **حتى 10,000 مهمة** دون تحميل الملف بالكامل في الذاكرة. تعمل المكتبة على أي منصة متوافقة مع JVM، لا تتطلب تثبيت Microsoft Project، وتوفر وصولاً كاملاً إلى API للمعرّفات، UID، المعرفات الخارجية، وبيانات الربط الوصفية.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

- بيئة تطوير Java تعمل (JDK 8 أو أعلى).  
- تثبيت Aspose.Tasks للغة Java. يمكنك تنزيله **[من هنا](https://releases.aspose.com/tasks/java/)**.  
- ملف ترخيص Aspose.Tasks صالح إذا كنت تخطط لتشغيل الكود في بيئة إنتاج.

## استيراد الحزم
تمثل الفئة `Project` ملف Microsoft Project، وتمثل الفئة `Task` مهمة فردية، وتوفر الفئة `Tsk` ثوابت حقول المهمة.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## الخطوة 1: ضبط دليل المستند
سلسلة `dataDir` تحتوي على مسار المجلد الذي يضم ملفات `.mpp` الخاصة بك.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## الخطوة 2: تحميل مشروع خارجي
`Project externalProject` يقوم بتحميل ملف المشروع الخارجي المحدد للفحص.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## الخطوة 3: استرجاع مهمة خارجية بواسطة UID
`externalProject.getChildren().getByUid(uid)` يسترجع مهمة من مجموعة مهام المشروع الخارجي باستخدام معرّفها الفريد.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## الخطوة 4: طباعة معرّف المهمة (حالة الاستخدام الأساسية)
`externalTask.get(Tsk.ID)` يُعيد المعرف الداخلي الذي تعينه Aspose.Tasks للمهمة المعطاة.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## الخطوة 5: طباعة معرّف المهمة الأصلي (الخارجي)
`externalTask.get(Tsk.ExternalID)` يجلب المعرف الأصلي للمهمة كما هو معرف في ملف المشروع المصدر.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

كرر الخطوات السابقة لأي مهام إضافية تحتاج إلى تتبعها عبر المشاريع.

## المشكلات الشائعة والنصائح
- **أخطاء المسار** – تأكد من أن `dataDir` ينتهي بالفاصل المناسب للملفات (`/` أو `\\`).  
- **عدم العثور على UID** – تحقق من وجود UID في المشروع الخارجي؛ استخدم `externalProject.getRootTask().getChildren().size()` لسرد UID المتاحة.  
- **استثناءات الترخيص** – سيؤدي عدم وجود ترخيص أو ترخيص غير صالح إلى رمي استثناء ترخيص أثناء التشغيل.  
- **المشاريع الكبيرة** – للمشاريع التي تتجاوز 5,000 مهمة، فكر في استخدام `ProjectReader` مع علامة `LoadOptions` لبث البيانات وتقليل استهلاك الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، يدعم Aspose.Tasks عدة لغات، بما في ذلك Java و .NET وغيرها.

**س: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.Tasks للغة Java؟**  
ج: راجع الوثائق **[من هنا](https://reference.aspose.com/tasks/java/)**.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks للغة Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية **[من هنا](https://releases.aspose.com/)**.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: احصل على ترخيص مؤقت **[من هنا](https://purchase.aspose.com/temporary-license/)**.

**س: هل تحتاج إلى مساعدة أو لديك أسئلة محددة؟**  
ج: زر منتدى دعم Aspose.Tasks **[من هنا](https://forum.aspose.com/c/tasks/15)**.

---

**آخر تحديث:** 2026-09-09  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.11 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose

## دروس ذات صلة

- [Create Project Management Task Dependencies in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Create MPP Project Java – Change Task Progress with Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}