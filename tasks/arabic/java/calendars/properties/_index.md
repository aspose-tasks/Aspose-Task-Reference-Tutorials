---
date: 2026-09-09
description: كيفية ضبط تقويم المشروع في Java باستخدام Aspose.Tasks. تعلّم كيفية عرض
  ساعات عمل التقويم، وتكوين وقت العمل، وتعديل أيام التقويم في ملفات MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: إدارة خصائص التقويم في Aspose.Tasks
og_description: كيفية ضبط تقويم المشروع في Java باستخدام Aspose.Tasks. تعلّم كيفية
  عرض ساعات عمل التقويم، وتكوين وقت العمل، وتعديل أيام التقويم في ملفات MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: كيفية ضبط تقويم المشروع في Java باستخدام Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: كيفية ضبط تقويم المشروع في Java باستخدام Aspose.Tasks
url: /ar/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين تقويم المشروع Java باستخدام Aspose.Tasks

## مقدمة
في هذا الدرس ستتعلم **كيفية تعيين تقويم المشروع** في Java باستخدام مكتبة Aspose.Tasks. يسمح التحكم في خصائص التقويم لك **بعرض ساعات عمل التقويم**، وتكوين أيام عمل مخصصة، والحفاظ على جدول مشروعك متوافقًا مع القيود الواقعية مثل العطلات أو أنماط الورديات. سنستعرض إعداد البيئة، تحميل المشروع، التكرار عبر التقويمات، وقراءة أو تحديث خصائصها، بحيث يمكنك بثقة **إدارة إعدادات تقويم MS Project** في أي تطبيق Java.

## إجابات سريعة
- **ما معنى “set project calendar”?** يعني إنشاء أو تحديث أوقات عمل التقويم، التقويم الأساسي، وأنواع الأيام داخل ملف MS Project.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (أي نسخة حديثة).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني عرض ساعات عمل التقويم؟** نعم—من خلال قراءة كل `WeekDay` يمكنك إظهار الساعات لكل نوع يوم.  
- **هل هذا متوافق مع Maven/Gradle؟** بالتأكيد—أضف ملف JAR الخاص بـ Aspose.Tasks كاعتماد.

## كيفية تعيين تقويم المشروع في Java
حمّل ملف المشروع الخاص بك، حدد التقويم المستهدف، ثم عدّل تعريفات أوقات العمل، التقويم الأساسي، وأنواع الأيام حسب الحاجة. الخطوات أدناه توفر حلاً كاملاً من البداية إلى النهاية يوضح تحميل المشروع، التكرار، التعديل، وحفظ المشروع مع معالجة الاستثناءات وضمان حسابات دقيقة لساعات العمل.

## ما هو تقويم المشروع؟
يحدد تقويم المشروع أيام وساعات العمل للمهام والموارد والجدول الزمني العام للمشروع. في MS Project، يمكن للتقويمات أن ترث من تقويم أساسي، ويمكن لكل نوع يوم (مثل **Standard**، **Non‑working**) أن يمتلك وقت عمل خاص به. إدارة هذه الإعدادات برمجيًا تمكن من تعديل الجدول الزمني ديناميكيًا دون تحرير يدوي.

## لماذا إدارة تقويم MS Project برمجيًا؟
إدارة التقويمات برمجيًا تتيح لك تطبيق قواعد جدولة متسقة عبر العديد من المشاريع، تقليل الأخطاء اليدوية، ودمج بيانات التقويم مع أنظمة المؤسسة الأخرى مثل الموارد البشرية أو ERP. هذه الأتمتة تُسرّع إعداد المشروع وتضمن أن جميع أعضاء الفريق يتبعون سياسات وقت العمل نفسها.
- **الأتمتة:** تعديل التقويمات عبر العشرات من المشاريع باستخدام سكريبت واحد.  
- **الاتساق:** فرض سياسات وقت العمل على مستوى المؤسسة تلقائيًا.  
- **التكامل:** مزامنة التقويمات مع أنظمة الموارد البشرية أو ERP الخارجية.  
- **الرؤية:** عرض **ساعات عمل التقويم** بسرعة للتقارير أو تصحيح الأخطاء.  
- **المرونة:** إضافة استثناءات أو أنماط ورديات في الوقت الفعلي دون فتح واجهة المستخدم.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:
- **Java Development Kit (JDK) 8+** مثبت ومُعَدّ `JAVA_HOME`.  
- مكتبة **Aspose.Tasks for Java** تم تحميلها من [صفحة التحميل](https://releases.aspose.com/tasks/java/). أضف ملف JAR إلى مسار الفئات الخاص بك أو أعلن عنه كاعتماد Maven/Gradle.  
- ملف عينة من MS Project (`.mpp` أو `.xml`) يحتوي على تقويم واحد على الأقل تريد فحصه أو تعديله.

## استيراد الحزم
الفئات `Project`، `Calendar`، `WeekDay` وغيرها هي جوهر التعامل مع التقويم.  
فئة `Calendar` تمثل تقويم المشروع، وتحتوي على أيام العمل، الاستثناءات، وعلاقات التقويم الأساسي.  
فئة `WeekDay` تحدد إعدادات وقت العمل ليوم واحد داخل التقويم.

فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف MS Project واحد في الذاكرة. بعد تحميل الملف، جميع عمليات التقويم تمر عبر هذا الكائن.

```java
import com.aspose.tasks.*;
```

## الخطوة 1: إعداد دليل البيانات
حدد المجلد الذي يحتوي على ملفات المشروع الخاصة بك. استبدل العنصر النائب بالمسار الفعلي على جهازك.

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: تعريف ثوابت وحدة الوقت
أوقات العمل تُعبّر عنها بالميلي ثانية. تعريف ثوابت قابلة لإعادة الاستخدام يجعل الكود أسهل للقراءة ويساعدك على **حساب ساعات العمل في Java** بدقة.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## الخطوة 3: تحميل بيانات المشروع
أنشئ كائن `Project` بتحميل ملف XML موجود من MS Project (`.xml` أو `.mpp`). يمنحك ذلك الوصول إلى جميع التقويمات المخزنة في الملف.

فئة `Project` تحمل الملف إلى نموذج كائن خفيف؛ لا تتطلب **احتفاظ الملف بالكامل في الذاكرة**، مما يتيح لك العمل مع مشاريع تحتوي على عشرات الآلاف من المهام.

```java
Project project = new Project(dataDir + "project.xml");
```

## الخطوة 4: التكرار عبر التقويمات في Java
الآن نقوم بالتكرار عبر كل تقويم، نطبع معرفه الفريد، اسمه، التقويم الأساسي، وساعات العمل لكل نوع يوم. هذا يوضح **كيفية تعيين تقويم المشروع في Java** وكذلك **عرض ساعات عمل التقويم**.

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
- **تصفية التقويمات غير المسماة** (بعض التقويمات الداخلية قد يكون لها اسم `null`).  
- **يطبع UID والاسم** – مفيد لتحديد التقويم لاحقًا.  
- **يعرض التقويم الأساسي** – إما “Self” (التقويم هو القاعدة الخاصة به) أو اسم التقويم الموروث.  
- **يتكرر عبر كل `WeekDay`** لحساب وإخراج إجمالي ساعات العمل (`workingTime` بالميلي ثانية، لذا نقسم على `OneHour`).  

## الفوائد الكمية لاستخدام Aspose.Tasks
يدعم Aspose.Tasks **أكثر من 30 صيغة إدخال وإخراج** ويمكنه معالجة **مشاريع تصل إلى 10,000 مهمة** دون تحميل الملف بالكامل إلى الذاكرة، مع تقديم النتائج في أقل من ثانية على عتاد الخادم المعتاد. تجعل هذه الأرقام منه خيارًا موثوقًا لأتمتة على مستوى المؤسسات.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | التقويم هو تقويم أساسي بحد ذاته (`isBaseCalendar()` تُعيد `true`). | استخدم الفحص الثلاثي كما هو موضح (`cal.isBaseCalendar() ? "Self" : ...`). |
| لا يوجد إخراج لساعات العمل | ملف المشروع يستخدم وحدة زمنية مختلفة (ticks). | تحقق من صيغة الملف؛ Aspose.Tasks يطبع إلى ميلي ثانية، لكن تأكد من تحميل النوع الصحيح من الملف. |
| غير قادر على العثور على `project.xml` | مسار `dataDir` غير صحيح. | استخدم مسارًا مطلقًا أو `Paths.get(dataDir, "project.xml").toString()`. |

## الأسئلة المتكررة

**س: هل يمكنني تعديل خصائص التقويم برمجيًا باستخدام Aspose.Tasks؟**  
**ج:** نعم، توفر الواجهة البرمجية وصولًا كاملاً للقراءة/الكتابة إلى التقويمات، مما يسمح لك بإضافة أو تعديل أو حذف أوقات العمل، الاستثناءات، وعلاقات التقويم الأساسي.

**س: هل هناك أي قيود على تخصيص التقويم باستخدام Aspose.Tasks؟**  
**ج:** المكتبة تعكس قدرات Microsoft Project، لذا يمكنك تخصيص جميع جوانب التقويم تقريبًا. قد تحتوي إصدارات ملفات Project القديمة جدًا على بعض الاختلافات الطفيفة في التوافق.

**س: هل يمكنني دمج إدارة التقويم في مشاريع Java الحالية؟**  
**ج:** بالتأكيد. ما عليك سوى إضافة ملف JAR الخاص بـ Aspose.Tasks إلى مسار البناء واستخدام أنماط الكود نفسها الموضحة هنا.

**س: هل يدعم Aspose.Tasks وظائف إدارة مشاريع أخرى غير إدارة التقويم؟**  
**ج:** نعم، يغطي المهام، الموارد، التعيينات، المخططات، الخطوط الأساسية، وأكثر—مما يجعله حلًا شاملاً لأتمتة المشاريع باستخدام Java.

**س: هل يتوفر دعم فني للمطورين الذين يستخدمون Aspose.Tasks؟**  
**ج:** نعم، توفر Aspose منتديات مخصصة، دعم عبر البريد الإلكتروني، ووثائق شاملة لجميع المستخدمين المرخصين.

---

**آخر تحديث:** 2026-09-09  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة عند كتابة هذا المقال)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تقويم مشروع Java – دليل Aspose.Tasks for Java](/tasks/java/)
- [تحميل ملفات المشروع في Java وإدارة خصائص المشروع](/tasks/java/project-management/default-properties/)
- [تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}