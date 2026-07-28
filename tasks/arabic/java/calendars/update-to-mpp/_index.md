---
date: 2026-02-05
description: تعلم كيفية إضافة العطلات إلى التقويم، وتعيين التقويم لمشروع، وحفظ ملف
  MS Project بصيغة MPP باستخدام Aspose.Tasks للغة Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إضافة العطلات إلى التقويم وحفظه كملف MPP باستخدام Aspose.Tasks
url: /ar/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة العطلات إلى التقويم وحفظه كملف MPP باستخدام Aspose.Tasks

## مقدمة

في إدارة المشاريع الحديثة غالبًا ما تحتاج إلى **إضافة عطلات إلى ملفات التقويم**، إنشاء **تقويم MS Project**، ثم مشاركة الجدول الزمني بصيغة MPP الأصلية. سواءً كنت تجمع جداول زمنية من مصادر متعددة أو تقوم بترحيل بيانات قديمة، فإن إنشاء تقويم برمجيًا يزيل الأخطاء اليدوية ويسرّع التسليم. يوضح هذا الدليل العملية الكاملة لإنشاء تقويم في MS Project، تخصيصه بالعطلات، **تعيين التقويم للمشروع**، وأخيرًا **تحويل المشروع إلى MPP** باستخدام Aspose.Tasks Java API.

## إجابات سريعة
- **ماذا يغطي هذا الدليل؟** إضافة عطلات إلى تقويم، تعيينه لمشروع، وحفظ النتيجة كملف MPP باستخدام Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى (JDK 8+).  
- **هل يمكنني تخصيص التقويم؟** نعم – يمكنك إضافة أوقات عمل، استثناءات، وعطلات.  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة لإنشاء تقويم أساسي.  

## ما هو “إنشاء تقويم MS Project”؟

إنشاء تقويم MS Project يعني تعريف أيام العمل، الساعات، والاستثناءات برمجيًا التي تُحدِّد جدولة المهام داخل ملف Microsoft Project. باستخدام Aspose.Tasks يمكنك **java create project calendar**، تعديلها، وحفظ التغييرات دون الحاجة لفتح واجهة Microsoft Project.

## لماذا نستخدم Aspose.Tasks لهذا الغرض؟

- **توافق كامل مع .NET/Java** – يعمل على أي منصة تدعم Java.  
- **لا حاجة إلى COM أو تثبيت Office** – مثالي لأتمتة الخادم **وتوليد الجداول الزمنية**.  
- **API غني** – يدعم كل خاصية في التقويم، بما في ذلك أسابيع العمل المخصصة والعطلات.  
- **إخراج مباشر إلى MPP** – يمكنك **save project as MPP** دون تحويلات وسيطة.

## المتطلبات المسبقة

1. **Java Development Kit (JDK) 8+** – تأكد من أن `java -version` يُظهر 1.8 أو أحدث.  
2. **Aspose.Tasks for Java** – حمّل أحدث JAR من [موقع Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA، Eclipse، أو أي محرر تفضله.  
4. **معرفة أساسية بـ Java** – إلمام بالفئات، الطرق، وملفات الإدخال/الإخراج.

## كيفية إضافة عطلات إلى التقويم

فيما يلي نستعرض كل خطوة، من إعداد البيئة إلى حفظ ملف MPP النهائي. كتل الشيفرة تبقى كما هي؛ تم توسيع الشروحات المحيطة لتوضيح العملية.

### الخطوة 1: استيراد الحزم المطلوبة

أولًا، استدعِ فئات Aspose.Tasks وأدوات Java.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### الخطوة 2: إعداد دليل البيانات

حدّد مكان وجود قالب الإدخال وملفات الإخراج. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 3: تعريف أسماء ملفات الإدخال والإخراج

سنحمّل ملف MPP موجود (أو مشروع فارغ) ونكتب النتيجة إلى ملف جديد.

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

إذا كنت تحتاج أوقات عمل محددة، عطلات، أو استثناءات، استدعِ الطريقة المساعدة الخاصة بك. يستخدم المثال `GetTestCalendar` كعنصر نائب.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **نصيحة احترافية:** يمكنك تعديل `cal1.getWeekDays()` مباشرةً لتحديد ساعات العمل لكل يوم من أيام الأسبوع، أو استخدام `cal1.getExceptions()` **لإضافة عطلات إلى التقويم**.

### الخطوة 6: تعيين التقويم للمشروع

أخبر المشروع باستخدام التقويم الجديد لجميع حسابات الجدولة.

```java
project.set(Prj.CALENDAR, cal1);
```

### الخطوة 7: حفظ المشروع كملف MPP

الآن **convert project to MPP** عبر حفظه باستخدام خيار `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### الخطوة 8: تأكيد إكمال العملية بنجاح

رسالة بسيطة في وحدة التحكم تُظهر أن العملية انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

## حالات الاستخدام الشائعة

- **توليد جدول زمني آلي** للمشاريع المتكررة (مثل السبرنت الأسبوعي).  
- **ترحيل تقاويم CSV أو Excel القديمة** إلى ملف MS Project متكامل.  
- **تقارير على الخادم** حيث تُعيد خدمة ويب ملف MPP عند الطلب.  

## استكشاف الأخطاء وإصلاحها والمشكلات الشائعة

| المشكلة | السبب | الحل |
|-------|-------|-----|
| `NullPointerException` عند `project.save` | `dataDir` يشير إلى مجلد غير موجود | تأكد من وجود الدليل أو أنشئه برمجيًا. |
| التقويم غير مُطبق على المهام | لا تزال المهام تشير إلى التقويم الافتراضي | بعد تعيين `Prj.CALENDAR`، حدّث أيضًا `Task.CALENDAR` لكل مهمة إذا تم تجاوزها مسبقًا. |
| ملف الإخراج حجمه 0 KB | عدم وجود أذونات كتابة | شغّل JVM بصلاحيات مناسبة أو اختر مسارًا قابلًا للكتابة. |

## الأسئلة المتكررة

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من MS Project؟**  
ج: نعم، يدعم Aspose.Tasks for Java مجموعة واسعة من إصدارات MS Project، من Project 2007 حتى أحدث إصدار، مما يضمن توافقًا سلسًا.

**س: هل يمكنني تخصيص التقويمات وفق متطلبات المشروع المحددة؟**  
ج: بالتأكيد. يمكنك تعريف أيام العمل، إعداد أسابيع عمل مخصصة، إضافة عطلات، وحتى إنشاء تقاويم متعددة داخل ملف مشروع واحد.

**س: هل يقدم Aspose.Tasks for Java دعمًا للمساعدة وحل المشكلات؟**  
ج: نعم، يمكنك الحصول على المساعدة من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، نسخة تجريبية كاملة الوظائف متاحة [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟**  
ج: يمكن طلب تراخيص مؤقتة عبر موقع Aspose [هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-02-05  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}