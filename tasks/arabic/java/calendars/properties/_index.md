---
date: 2025-12-04
description: تعلم كيفية ضبط تقويم المشروع وإدارة خصائص تقويم MS Project في جافا باستخدام
  Aspose.Tasks. دليل خطوة بخطوة لعرض ساعات عمل التقويم وتخصيص الجداول.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تعيين تقويم المشروع باستخدام Aspose.Tasks للغة Java
url: /ar/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين تقويم المشروع باستخدام Aspose.Tasks للغة Java

## مقدمة
في هذا الدرس ستكتشف **how to set project calendar** برمجيًا باستخدام مكتبة Aspose.Tasks للغة Java. يتيح لك التحكم في خصائص التقويم **display calendar working hours**، تعريف أيام عمل مخصصة، ومزامنة جدول مشروعك مع القيود الواقعية. سنستعرض كل خطوة — من إعداد البيئة إلى التكرار عبر التقويمات وقراءة خصائصها — حتى تتمكن من إدارة تقويمات MS Project بثقة في تطبيقاتك.

## إجابات سريعة
- **What does “set project calendar” mean?** يعني إنشاء أو تحديث أوقات العمل في التقويم، التقويم الأساسي، وأنواع الأيام داخل ملف MS Project.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم الحصول على ترخيص تجاري للإنتاج.  
- **Can I display calendar working hours?** نعم — عن طريق قراءة كل `WeekDay` يمكنك إظهار الساعات لكل نوع يوم.  
- **Is this compatible with Maven/Gradle?** بالتأكيد — أضف ملف JAR الخاص بـ Aspose.Tasks كاعتماد.

## ما هو تقويم المشروع؟
يحدد تقويم المشروع أيام وساعات العمل للمهام والموارد والجدول الزمني العام للمشروع. في MS Project، يمكن للتقويمات أن ترث من تقويم أساسي، ويمكن لكل نوع يوم (مثل **Standard**, **Non‑working**) أن يمتلك وقت عمل خاص به. يتيح إدارة هذه الإعدادات برمجيًا إجراء تعديلات ديناميكية على الجدول الزمني دون الحاجة إلى تحرير يدوي.

## لماذا إدارة تقويم MS Project برمجيًا؟
- **Automation:** تعديل التقويمات عبر العديد من المشاريع باستخدام سكريبت واحد.  
- **Consistency:** فرض سياسات وقت العمل على مستوى المؤسسة.  
- **Integration:** مزامنة التقويمات مع الأنظمة الخارجية (الموارد البشرية، ERP).  
- **Visibility:** بسرعة **display calendar working hours** للتقارير أو تصحيح الأخطاء.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أن لديك:

- **Java Development Kit (JDK) 8+** مثبت ومُعَدّ `JAVA_HOME`.  
- **Aspose.Tasks for Java** مكتبة تم تحميلها من [download page](https://releases.aspose.com/tasks/java/). أضف ملف JAR إلى مسار الفئة في مشروعك أو إلى اعتمادات Maven/Gradle.  

## استيراد الحزم
أولاً، استورد الفئات الأساسية من Aspose.Tasks التي سنستخدمها طوال الدرس:

```java
import com.aspose.tasks.*;
```

## الخطوة 1: إعداد دليل البيانات
حدد المجلد الذي يحتوي على ملفات المشروع الخاصة بك. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: تعريف وحدات الوقت
أوقات العمل تُعبّر بالمللي ثانية. تعريف ثوابت قابلة لإعادة الاستخدام يجعل الشيفرة أسهل للقراءة.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## الخطوة 3: تحميل بيانات المشروع
أنشئ كائن `Project` بتحميل ملف XML لمشروع MS Project موجود (`.xml` أو `.mpp`). يتيح لنا ذلك الوصول إلى جميع التقويمات المخزنة في الملف.

```java
Project project = new Project(dataDir + "project.xml");
```

## الخطوة 4: التكرار عبر التقويمات وعرض ساعات العمل
الآن نقوم بالتكرار عبر كل تقويم، طباعة المعرف الفريد، الاسم، التقويم الأساسي، وساعات العمل لكل نوع يوم. يوضح ذلك **how to set project calendar** بالإضافة إلى كيفية **display calendar working hours**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### ما يفعله هذا الكود
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
  يقوم بتصفية التقويمات غير المسماة (بعض التقويمات الداخلية قد يكون لها اسم `null`).  
- **Prints UID and name** – مفيد لتحديد التقويم لاحقًا.  
- **Shows the base calendar** – إما “Self” (التقويم هو القاعدة الخاصة به) أو اسم التقويم الموروث.  
- **Loops through each `WeekDay`** لحساب وإخراج إجمالي ساعات العمل (`workingTime` بالمللي ثانية، لذا نقسم على `OneHour`).  

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | التقويم هو تقويم أساسي بحد ذاته (`isBaseCalendar()` يعيد `true`). | استخدم الفحص الثلاثي كما هو موضح (`cal.isBaseCalendar() ? "Self" : ...`). |
| عدم ظهور ساعات العمل | ملف المشروع يستخدم وحدة زمنية مختلفة (ticks). | تحقق من تنسيق الملف؛ Aspose.Tasks يحول إلى مللي ثانية، لكن تأكد من تحميل النوع الصحيح من الملف. |
| غير قادر على العثور على `project.xml` | مسار `dataDir` غير صحيح. | استخدم مسارًا مطلقًا أو `Paths.get(dataDir, "project.xml").toString()`. |

## الأسئلة المتكررة

**س: هل يمكنني تعديل خصائص التقويم برمجيًا باستخدام Aspose.Tasks؟**  
ج: نعم، توفر API وصولًا كاملاً للقراءة/الكتابة إلى التقويمات، مما يسمح لك بإضافة أو تعديل أو حذف أوقات العمل، الاستثناءات، وعلاقات التقويم الأساسي.

**س: هل هناك أي قيود على تخصيص التقويم باستخدام Aspose.Tasks؟**  
ج: المكتبة تعكس قدرات Microsoft Project، لذا يمكنك تخصيص جميع جوانب التقويم تقريبًا. قد تواجه بعض الاختلافات الطفيفة في إصدارات ملفات Project القديمة جدًا.

**س: هل يمكنني دمج إدارة التقويم في مشاريع Java الحالية؟**  
ج: بالتأكيد. ما عليك سوى إضافة ملف JAR الخاص بـ Aspose.Tasks إلى مسار البناء واستخدام نمط الشيفرة نفسه المعروض هنا.

**س: هل يدعم Aspose.Tasks وظائف إدارة مشاريع أخرى غير إدارة التقويم؟**  
ج: نعم، يغطي المهام، الموارد، التخصيصات، المخططات، الخطوط الأساسية، وأكثر—مما يجعله حلًا شاملاً لأتمتة المشاريع باستخدام Java.

**س: هل يتوفر دعم فني للمطورين الذين يستخدمون Aspose.Tasks؟**  
ج: نعم، توفر Aspose منتديات مخصصة، دعم عبر البريد الإلكتروني، ووثائق شاملة لجميع المستخدمين المرخصين.

## الخلاصة
باتباعك لهذا الدليل، أصبحت الآن تعرف **how to set project calendar**، وتستطيع قراءة و**display calendar working hours**، ودمج هذه القدرات في أي تطبيق Java باستخدام Aspose.Tasks. يتيح لك ذلك أتمتة تعديل الجداول الزمنية، فرض سياسات عمل متسقة، وبناء حلول إدارة مشاريع أكثر غنى.

---

**آخر تحديث:** 2025-12-04  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}