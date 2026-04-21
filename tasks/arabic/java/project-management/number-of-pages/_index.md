---
date: 2025-12-31
description: تعلم كيفية الحصول على عدد الصفحات في Java باستخدام Aspose.Tasks، بما
  في ذلك كيفية تهيئة مشروع Java واسترجاع عدد الصفحات من ملفات Microsoft Project.
linktitle: Get Page Count Java with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: الحصول على عدد الصفحات في Java باستخدام Aspose.Tasks
url: /ar/java/project-management/number-of-pages/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على عدد الصفحات في Java باستخدام Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي ستكتشف كيفية **get page count java** باستخدام مكتبة Aspose.Tasks. سواء كنت بحاجة إلى إنشاء تقارير، تقسيم جداول مشاريع كبيرة إلى صفحات، أو مجرد استخراج بيانات وصفية، فإن معرفة العدد الدقيق للصفحات في ملف Microsoft Project أمر أساسي. سنستعرض العملية بالكامل — من إعداد البيئة إلى استدعاء API التي تُرجع عدد الصفحات.

## إجابات سريعة
- **ماذا يفعل “get page count java”؟** يُعيد العدد الإجمالي للصفحات القابلة للطباعة في ملف Project.  
- **أي فئة توفر عدد الصفحات؟** `Project.getPageCount()` (أو إصداراتها المتعددة).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **هل يمكنني تحديد مقياس الزمن؟** نعم، الإصدارات المتعددة تقبل `Timescale.Months` أو `Timescale.ThirdsOfMonths`.  
- **ما هي صيغ Project المدعومة؟** MPP، MPT، XML، وغيرها مما تدعمه Aspose.Tasks.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من أن المكونات التالية جاهزة:

### تثبيت Java Development Kit (JDK)
1. تحميل JDK: زر [موقع Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) لتنزيل أحدث نسخة من JDK المتوافقة مع نظام التشغيل الخاص بك.  
2. التثبيت: اتبع تعليمات التثبيت التي توفرها Oracle لتثبيت JDK على جهازك.

### تثبيت Aspose.Tasks
1. تحميل Aspose.Tasks for Java: انتقل إلى [صفحة التحميل](https://releases.aspose.com/tasks/java/) على موقع Aspose.  
2. الحصول على الترخيص: إذا كنت تنوي استخدام Aspose.Tasks في بيئة إنتاج، احصل على ترخيص من [صفحة الشراء](https://purchase.aspose.com/buy).

## استيراد الحزم
لبدء استخدام Aspose.Tasks في مشروع Java الخاص بك، تحتاج إلى استيراد الحزم الضرورية. إليك الطريقة خطوة بخطوة:

## الخطوة 1: إضافة تبعية Aspose.Tasks
تأكد من أنك أضفت Aspose.Tasks كاعتماد في مشروع Java الخاص بك. أدرج تبعية Maven التالية في ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>xx.xx</version> <!-- Replace xx.xx with the latest version -->
</dependency>
```

## الخطوة 2: استيراد فئات Aspose.Tasks
في شيفرة Java الخاصة بك، استورد الفئات المطلوبة من Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## كيفية تهيئة Project في Java باستخدام Aspose.Tasks
الخطوة العملية الأولى هي إنشاء كائن `Project` يمثل ملف Microsoft Project الخاص بك.

### الخطوة 1: تهيئة كائن Project
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir);
```
استبدل `"Your Data Directory"` بالمسار الكامل إلى ملف `.mpp` أو `.xml` الذي تريد تحليله. هذه الخطوة **initialize project java** تمنحك نموذج مشروع محمل بالكامل جاهز للعمليات اللاحقة.

### الخطوة 2: الحصول على عدد الصفحات
استرجع العدد الإجمالي للصفحات باستخدام النسخة البسيطة من `getPageCount()`:

```java
int iPages = project.getPageCount();
```
الآن المتغير `iPages` يحتوي على عدد الصفحات القابلة للطباعة للمقياس الزمني الافتراضي.

### الخطوة 3: الحصول على عدد الصفحات مع مقياس الزمن
إذا كنت تحتاج إلى عدد الصفحات لمقياس زمن محدد (مثل الأشهر أو ثلث الأشهر)، استخدم الطريقة المتعددة الإصدارات:

```java
// Get number of pages with Timescale.Months
iPages = project.getPageCount(0, Timescale.Months);
// Get number of pages with Timescale.ThirdsOfMonths
iPages = project.getPageCount(0, Timescale.ThirdsOfMonths);
```
هذه الإصدارات المتعددة تتيح لك ضبط التقسيم إلى صفحات بناءً على الطريقة التي تنوي عرض الجدول الزمني بها.

## المشكلات الشائعة والحلول
- **NullPointerException عند تحميل الملف:** تحقق من أن `dataDir` يشير إلى ملف Project صالح وأن الملف غير تالف.  
- **عدد الصفحات غير صحيح:** تأكد من أنك تستخدم نسخة مقياس الزمن المناسبة التي تتطابق مع العرض الذي تنوي طباعته.  
- **الترخيص غير موجود:** ضع ملف `Aspose.Tasks.lic` في جذر المشروع أو اضبط الترخيص برمجياً قبل إنشاء كائن `Project`.

## الأسئلة المتكررة

**س: هل Aspose.Tasks متوافق مع جميع إصدارات ملفات Microsoft Project؟**  
ج: يدعم Aspose.Tasks مجموعة واسعة من صيغ ملفات Microsoft Project، بما في ذلك MPP، MPT، وXML.

**س: هل يمكنني استخدام Aspose.Tasks في مشروع تجاري؟**  
ج: نعم، يمكنك استخدام Aspose.Tasks في المشاريع التجارية وغير التجارية بعد الحصول على الترخيص المناسب.

**س: هل يقدم Aspose.Tasks دعمًا للتكامل مع مكتبات Java الأخرى؟**  
ج: يوفر Aspose.Tasks وثائق شاملة ودعمًا، مما يجعله متوافقًا مع مختلف مكتبات وإطارات عمل Java.

**س: هل هناك منتدى مجتمع يمكنني من خلاله طلب المساعدة بخصوص استفسارات Aspose.Tasks؟**  
ج: نعم، يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للتفاعل مع المجتمع وطلب المساعدة بخصوص أي مشكلة أو استفسار.

**س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟**  
ج: بالتأكيد، يمكنك استكشاف ميزات ووظائف Aspose.Tasks بالحصول على نسخة تجريبية مجانية من خلال [الموقع الإلكتروني](https://releases.aspose.com/).

## الخاتمة
من خلال إتقان سير عمل **get page count java**، يمكنك تحديد عدد الصفحات التي سيشغلها جدول مشروع Microsoft Project برمجيًا، تخصيص خيارات الطباعة، ودمج منطق التقسيم إلى صفحات في حلول تقارير أكبر. استخدم الخطوات أعلاه لتقوم بـ **initialize project java**، استرجاع عدد الصفحات، وتعديل مقياس الزمن حسب الحاجة. Happy coding!

---

**آخر تحديث:** 2025-12-31  
**تم الاختبار مع:** Aspose.Tasks 24.12 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}