---
date: 2025-11-29
description: تعلم كيفية استرداد استثناءات التقويم من MS Project باستخدام Aspose.Tasks
  للـ Java. يقدم هذا الدليل التعليمي لـ Aspose.Tasks Java أمثلة برمجية خطوة بخطوة.
language: ar
linktitle: Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial
second_title: Aspose.Tasks Java API
title: استرجاع استثناءات التقويم باستخدام Aspose.Tasks – برنامج تعليمي لـ asp tasks
  java
url: /java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استرجاع استثناءات التقويم باستخدام Aspose.Tasks – دليل asp tasks java

## المقدمة
في هذا **asp tasks java tutorial** ستتعلم كيفية استرجاع استثناءات التقويم من ملف Microsoft Project باستخدام مكتبة Aspose.Tasks للغة Java. تمثل استثناءات التقويم فترات غير عمل مثل العطلات أو قواعد وقت العمل المخصصة، والقدرة على قراءتها برمجياً أمر أساسي لتسوية الموارد، وإعداد التقارير، ومنطق الجدولة المخصص. سنستعرض العملية بالكامل خطوة بخطوة، حتى تتمكن من دمج هذه القدرة في تطبيقات Java الخاصة بك بثقة.

## إجابات سريعة
- **ماذا يغطي هذا الدليل؟** استرجاع استثناءات التقويم من ملف MPP باستخدام Aspose.Tasks للغة Java.  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة لإعداد أساسي.  
- **المتطلبات المسبقة؟** JDK، Aspose.Tasks للغة Java، وبيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **الإصدارات المدعومة من Project؟** جميع صيغ MS Project الرئيسية (MPP، MPT، XML).

## ما هو asp tasks java tutorial؟
**asp tasks java tutorial** يشرح كيفية استخدام واجهة برمجة تطبيقات Aspose.Tasks داخل مشاريع Java. يقدم أمثلة شفرة ملموسة، شرحاً لأفضل الممارسات، وسيناريوهات واقعية حتى يتمكن المطورون من معالجة ملفات Project دون الحاجة إلى تثبيت Microsoft Project.

## لماذا نسترجع استثناءات التقويم؟
فهم استثناءات التقويم يتيح لك:
- إنشاء جداول زمنية دقيقة للمشروع تحترم العطلات وجداول العمل المخصصة.
- بناء أدوات تقارير مخصصة تُظهر الأيام غير العاملة.
- مزامنة تقاويم Project مع أنظمة خارجية (مثل ERP، HR).

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:

1. **Java Development Kit (JDK)** – تأكد من تثبيت JDK 8 أو أحدث.
2. **Aspose.Tasks للغة Java** – حمّل وثبّت Aspose.Tasks للغة Java من [هنا](https://releases.aspose.com/tasks/java/).
3. **بيئة تطوير متكاملة (IDE)** – يمكنك استخدام أي IDE تفضله، مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
أولاً، تحتاج إلى استيراد الحزم الضرورية للعمل مع Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## الخطوة 1: إعداد دليل البيانات الخاص بك
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **نصيحة احترافية:** استخدم مسارًا مطلقًا أو مسارًا نسبيًا إلى مجلد موارد المشروع لتجنب `FileNotFoundException`.

## الخطوة 2: تحميل ملف MS Project
```java
Project project = new Project(dataDir + "project.mpp");
```

هذا السطر يخلق كائن `Project` جديدًا بتحميل ملف MS Project المحدد بالمسار.

## الخطوة 3: استرجاع استثناءات التقويم
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

هنا، نقوم بالتكرار عبر كل تقويم في المشروع ثم عبر كل استثناء تقويم داخل ذلك التقويم. نطبع تواريخ البداية والنهاية لكل استثناء.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **لا يتم طباعة أي ناتج** | ملف المشروع لا يحتوي على أي استثناءات تقويم. | تحقق من أن التقويم في MS Project يحتوي على استثناءات معرفة (مثل العطلات). |
| **`NullPointerException`** | مسار `dataDir` غير صحيح أو الملف غير موجود. | أعد فحص مسار الدليل وتأكد من وجود `project.mpp`. |
| **اختلاف المنطقة الزمنية** | التواريخ تُعرض بتوقيت UTC. | استخدم `calExc.getFromDate().toLocalDateTime()` لتحويلها إلى التوقيت المحلي إذا لزم الأمر. |

## الأسئلة المتكررة
### هل يمكن لـ Aspose.Tasks التعامل مع إصدارات مختلفة من ملفات MS Project؟
نعم، يدعم Aspose.Tasks إصدارات متعددة من ملفات MS Project، بما في ذلك صيغ MPP، MPT، وXML.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على توثيق Aspose.Tasks للغة Java؟
يمكنك الرجوع إلى الوثائق [هنا](https://reference.aspose.com/tasks/java/).

### كيف يمكنني الحصول على دعم لـ Aspose.Tasks؟
يمكنك الحصول على الدعم من منتدى المجتمع [هنا](https://forum.aspose.com/c/tasks/15).

### هل هناك خيار للحصول على تراخيص مؤقتة لـ Aspose.Tasks؟
نعم، يمكنك الحصول على تراخيص مؤقتة من [هنا](https://purchase.aspose.com/temporary-license/).

**أسئلة وإجابات إضافية**

**س:** *هل يمكنني تعديل استثناءات التقويم بعد استرجاعها؟*  
**ج:** بالتأكيد. استخدم `CalendarException.setFromDate()` و `setToDate()` لتعديل التواريخ، ثم احفظ المشروع باستخدام `project.save(...)`.

**س:** *هل يحتفظ Aspose.Tasks بالحقول المخصصة على التقويمات؟*  
**ج:** نعم، جميع الحقول المخصصة والسمات الموسعة تُحفظ عند تحميل وحفظ المشروع.

## الخاتمة
في هذا **asp tasks java tutorial** تعلمنا كيفية استرجاع استثناءات التقويم من MS Project باستخدام Aspose.Tasks للغة Java. باتباع هذه الخطوات البسيطة، يمكنك دمج هذه الوظيفة بسهولة في تطبيقات Java الخاصة بك، مما يتيح ميزات جدولة أغنى وتحليلات مشروع أكثر دقة.

---

**آخر تحديث:** 2025-11-29  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}