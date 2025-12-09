---
date: 2025-12-03
description: تعلم كيفية قراءة أسابيع العمل في Java من تقويم Microsoft Project باستخدام
  Aspose.Tasks. اتبع الدليل خطوة بخطوة مع أمثلة شفرة كاملة.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: قراءة أسابيع العمل Java من تقويم MS Project Aspose.Tasks
url: /ar/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة أسابيع العمل Java من تقويم MS Project باستخدام Aspose.Tasks

## المقدمة
في هذا الدرس ستقوم **بقراءة أسابيع العمل Java** من تقويم Microsoft Project باستخدام مكتبة Aspose.Tasks. سواءً كنت تبني أداة تقارير، أو تُزامن الجداول الزمنية، أو تُؤتمت استخراج بيانات المشروع، فإن القدرة على الوصول برمجياً إلى تعريفات أسابيع العمل توفر ساعات يدوية لا تُحصى. سنستعرض الإعداد المطلوب، ونُظهر لك الشيفرة الدقيقة لاسترجاع تفاصيل أسابيع العمل، ونشرح كل خطوة حتى تتمكن من تعديل الحل ليتناسب مع مشاريعك الخاصة.

## إجابات سريعة
- **ماذا يعني “read work weeks java”؟** يشير إلى استخراج تعريفات أسابيع العمل من ملف Project باستخدام كود Java.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (يتوفر نسخة تجريبية مجانية).  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **ما صيغ الملفات المدعومة؟** كل من *.mpp* وملفات Project XML مدعومة.  
- **كم يستغرق تنفيذ العملية؟** عادةً أقل من 10 دقائق بمجرد إعداد المكتبة.

## ما هو “read work weeks java”؟
قراءة أسابيع العمل في Java تعني استخدام Aspose.Tasks API للوصول إلى `WorkWeekCollection` لكائن تقويم داخل ملف Microsoft Project. كل `WorkWeek` يحتوي على تواريخ البدء/الانتهاء وتعريفات ساعات العمل اليومية التي تحدد كيفية جدولة الموارد.

## لماذا نقرأ أسابيع العمل Java من تقويم Microsoft Project؟
- **الأتمتة:** القضاء على النسخ واللصق اليدوي لبيانات الجدول.  
- **التكامل:** إمداد معلومات أسابيع العمل إلى أنظمة ERP، أو HR، أو تقارير مخصصة.  
- **الاتساق:** ضمان أن جميع الأدوات المتصلة تحترم نفس قواعد التقويم المعرفة في ملف Project.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أحدث مثبت.  
2. **Aspose.Tasks for Java** – حمّل أحدث ملف JAR من الموقع الرسمي: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. ملف **Project تجريبي** (`ReadWorkWeeksInformation.mpp`) موجود في مجلد معروف.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها للتعامل مع التقويمات وأسابيع العمل:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## الخطوة 1: إعداد مسار البيانات
عرّف المجلد الذي يحتوي على ملف `.mpp`. استبدل العنصر النائب بالمسار الفعلي على جهازك:

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: إنشاء كائن Project والوصول إلى التقويم
أنشئ كائن `Project`، اختر التقويم المطلوب (حسب UID)، واحصل على `WorkWeekCollection` الخاصة به:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **نصيحة محترف:** إذا لم تكن متأكدًا من UID التقويم، يمكنك التجول عبر `project.getCalendars()` وطباعة اسم كل تقويم وUID الخاص به.

## الخطوة 3: التجول عبر أسابيع العمل
استخدم حلقة لتكرار كل `WorkWeek` وعرض اسمه، تواريخ البدء/الانتهاء، وساعات العمل اليومية:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**ما ستراه:** سيتطبع في وحدة التحكم تسمية كل أسبوع عمل (مثلاً “Standard”)، نطاق تواريخ سريانه، ويمكنك التعمق إلى ساعات العمل الدقيقة لكل يوم.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| `NullPointerException` عند الوصول إلى `calendar` | UID غير صحيح أو التقويم غير موجود | تحقق من UID باستخدام `project.getCalendars().size()` وقم بسرد التقويمات المتاحة أولاً. |
| لا يوجد إخراج لأسابيع العمل | التقويم المختار لا يحتوي على أسابيع عمل مخصصة (يستخدم الافتراضي) | استخدم التقويم الافتراضي (`project.getDefaultCalendar()`) أو أنشئ أسبوع عمل برمجياً. |
| تنسيق التاريخ غير مناسب | `System.out.println` يستخدم تنسيق `java.util.Date` الافتراضي | استخدم `SimpleDateFormat` لتنسيق التواريخ حسب الحاجة. |

## الأسئلة المتكررة

**س: هل يمكن تعديل معلومات أسابيع العمل باستخدام Aspose.Tasks for Java؟**  
ج: نعم. توفر API طرقًا مثل `addWorkWeek()`، `removeWorkWeek()`، ومُعِدّلات الخصائص لتغيير الأسماء، التواريخ، وساعات العمل.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: بالتأكيد. يدعم ملفات MPP من Project 98 حتى أحدث الإصدارات، بالإضافة إلى ملفات Project XML.

**س: هل يمكن دمج Aspose.Tasks مع أطر عمل Java أخرى؟**  
ج: نعم. المكتبة مكتوبة بلغة Java بحتة، لذا يمكنك استخدامها مع Spring، Jakarta EE، أو أي إطار آخر.

**س: هل تتوفر نسخة تجريبية من Aspose.Tasks؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية لمدة 30 يومًا من الموقع الرسمي: [Aspose.Tasks trial](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم الخاص بـ Aspose.Tasks؟**  
ج: منتدى مجتمع Aspose هو أفضل مكان للحصول على المساعدة: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## الخاتمة
لقد أتقنت الآن **قراءة أسابيع العمل Java** باستخدام Aspose.Tasks. باتباع الخطوات أعلاه يمكنك سحب تعريفات أسابيع العمل برمجياً من أي تقويم MS Project، دمج تلك البيانات في تطبيقاتك، وأتمتة سير العمل المتعلق بالجدولة. لا تتردد في تجربة إنشاء أو تحديث أسابيع العمل—Aspose.Tasks يجعل ذلك بسيطًا.

---

**آخر تحديث:** 2025-12-03  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}