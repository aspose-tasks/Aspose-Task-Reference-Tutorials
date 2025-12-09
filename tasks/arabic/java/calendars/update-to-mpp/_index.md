---
date: 2025-12-03
description: تعلم كيفية إنشاء تقويم في MS Project، وتحويل المشروع إلى MPP، وحفظ مشروع
  MPP بسهولة باستخدام Aspose.Tasks للغة Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إنشاء تقويم في MS Project وحفظه كملف MPP باستخدام Aspose.Tasks
url: /ar/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تقويم MS Project وحفظه كملف MPP باستخدام Aspose.Tasks

## المقدمة

في إدارة المشاريع الحديثة غالبًا ما تحتاج إلى **إنشاء ملفات تقويم MS Project** ثم مشاركتها بصيغة MPP الأصلية. سواءً كنت تجمع جداول زمنية من مصادر متعددة أو تقوم بترحيل بيانات قديمة، فإن القدرة على إنشاء تقويم برمجيًا توفر الوقت وتُزيل الأخطاء اليدوية. يوضح هذا الدرس العملية الكاملة لإنشاء تقويم في MS Project، تخصيصه، وأخيرًا **تحويل المشروع إلى MPP** باستخدام Aspose.Tasks API للغة Java.

## إجابات سريعة
- **ما الذي يغطيه هذا الدرس؟** إنشاء تقويم في MS Project وحفظه كملف MPP باستخدام Aspose.Tasks للغة Java.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى (JDK 8+).  
- **هل يمكنني تخصيص التقويم؟** نعم – يمكنك إضافة أوقات عمل، استثناءات، وعطلات.  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة لإنشاء تقويم أساسي.

## ما هو “إنشاء تقويم MS Project”؟

إنشاء تقويم MS Project يعني تعريف أيام العمل، الساعات، والاستثناءات برمجيًا والتي تُحدد جدولة المهام داخل ملف Microsoft Project. باستخدام Aspose.Tasks يمكنك بناء، تعديل، وحفظ هذه التقويمات دون الحاجة لفتح واجهة Microsoft Project.

## لماذا نستخدم Aspose.Tasks لهذه المهمة؟

- **توافق كامل مع .NET/Java** – يعمل على أي منصة تدعم Java.  
- **لا حاجة إلى COM أو تثبيت Office** – مثالي للأتمتة على الخادم.  
- **API غني** – يدعم كل خاصية في التقويم، بما في ذلك أسابيع العمل المخصصة والعطلات.  
- **إخراج مباشر بصيغة MPP** – يمكنك **حفظ المشروع كملف MPP** دون تحويلات وسيطة.

## المتطلبات المسبقة

1. **مجموعة تطوير Java (JDK) 8+** – تأكد من أن `java -version` يُظهر 1.8 أو أحدث.  
2. **Aspose.Tasks للغة Java** – حمّل أحدث ملف JAR من [موقع Aspose](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – IntelliJ IDEA، Eclipse، أو أي محرر تفضله.  
4. **معرفة أساسية بـ Java** – إلمام بالفئات، الأساليب، وعمليات إدخال/إخراج الملفات.

## دليل خطوة بخطوة

### الخطوة 1: استيراد الحزم المطلوبة

أولًا، استدعِ فئات Aspose.Tasks وأدوات Java الضرورية.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### الخطوة 2: إعداد دليل البيانات

حدد مكان وجود قالب الإدخال والملفات الناتجة. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 3: تعريف أسماء ملفات الإدخال والإخراج

سنقوم بتحميل ملف MPP موجود (أو مشروع فارغ) وكتابة النتيجة إلى ملف جديد.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### الخطوة 4: تحميل المشروع وإضافة تقويم جديد

أنشئ كائن `Project` من الملف المصدر وأضف تقويمًا باسم **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### الخطوة 5: تخصيص التقويم (اختياري)

إذا كنت بحاجة إلى أوقات عمل محددة، عطلات، أو استثناءات، استدعِ طريقة المساعدة الخاصة بك. يستخدم المثال `GetTestCalendar` كعنصر نائب.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **نصيحة احترافية:** يمكنك تعديل `cal1.getWeekDays()` مباشرةً لتعيين ساعات العمل لكل يوم من أيام الأسبوع.

### الخطوة 6: ربط التقويم بالمشروع

أخبر المشروع باستخدام التقويم الجديد لجميع حسابات الجدولة.

```java
project.set(Prj.CALENDAR, cal1);
```

### الخطوة 7: حفظ المشروع كملف MPP

الآن **حوّل المشروع إلى MPP** عبر حفظه باستخدام خيار `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### الخطوة 8: تأكيد إكمال العملية بنجاح

رسالة بسيطة في وحدة التحكم تخبرك بأن العملية انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

## حالات الاستخدام الشائعة

- **إنشاء جدول زمني تلقائي** للمشاريع المتكررة (مثل السبرينت الأسبوعية).  
- **ترحيل تقاويم CSV أو Excel القديمة** إلى ملف MS Project متكامل.  
- **تقارير على الخادم** حيث تُعيد خدمة ويب ملف MPP عند الطلب.  

## استكشاف الأخطاء وإصلاحها ومخاطر الشائعة

| المشكلة | السبب | الحل |
|--------|-------|------|
| `NullPointerException` عند `project.save` | مسار `dataDir` يشير إلى مجلد غير موجود | تأكد من وجود الدليل أو أنشئه برمجيًا. |
| التقويم غير مطبق على المهام | لا تزال المهام تشير إلى التقويم الافتراضي | بعد ضبط `Prj.CALENDAR`، حدّث أيضًا `Task.CALENDAR` لكل مهمة إذا كانت مُعّرفة مسبقًا. |
| ملف الإخراج حجمه 0 KB | نقص أذونات الكتابة | شغّل JVM بصلاحيات مناسبة أو اختر مسارًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل Aspose.Tasks للغة Java متوافق مع إصدارات مختلفة من MS Project؟**  
ج: نعم، يدعم Aspose.Tasks للغة Java مجموعة واسعة من إصدارات MS Project، من Project 2007 حتى أحدث إصدار، مما يضمن توافقًا سلسًا.

**س: هل يمكنني تخصيص التقويمات وفقًا لمتطلبات مشروع محددة؟**  
ج: بالتأكيد. يمكنك تعريف أيام العمل، ضبط أسابيع عمل مخصصة، إضافة عطلات، وحتى إنشاء تقاويم متعددة داخل ملف مشروع واحد.

**س: هل يقدم Aspose.Tasks للغة Java دعمًا للمساعدة وحل المشكلات؟**  
ج: نعم، يمكنك الحصول على المساعدة من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Tasks للغة Java؟**  
ج: نعم، نسخة تجريبية كاملة الوظائف متاحة [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks للغة Java؟**  
ج: يمكن طلب تراخيص مؤقتة عبر موقع Aspose [هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2025-12-03  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}