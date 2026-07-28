---
date: 2026-02-05
description: تعلم كيفية تحديد أيام العمل وحساب مدة المهمة عن طريق استخراج ساعات العمل
  من تقاويم MS Project باستخدام Aspose.Tasks للـ Java.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تحديد أيام العمل وساعات العمل باستخدام Aspose.Tasks
url: /ar/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديد أيام العمل وساعات العمل باستخدام Aspose.Tasks

## المقدمة
إدارة تقاويم المشروع هي جزء أساسي من تخطيط المشروع الناجح. في هذا الدرس ستقوم **بتحديد أيام العمل** لأي مهمة و**باستخراج ساعات العمل** من تقويم MS Project باستخدام Aspose.Tasks for Java. في نهاية الدليل ستتمكن من **حساب مدة المهمة**، تخصيص ساعات العمل، و**تحميل ملف MPP** بشكل موثوق لاسترجاع البيانات التي تحتاجها. ستتعرف أيضًا على كيفية **قراءة ملفات MS Project** دون الحاجة إلى تثبيت Microsoft Project، مما يجعل الأتمتة ممكنة على أي منصة.

## إجابات سريعة
- **ماذا يعني “تحديد أيام العمل”؟** يعني ذلك تحديد أي تواريخ التقويم تُعتبر أيام عمل للمهمة المعطاة.  
- **أي مكتبة يجب أن أستخدم؟** Aspose.Tasks for Java توفر API متكامل للعمل مع ملفات MS Project.  
- **كم يستغرق تنفيذ ذلك؟** عادةً 10–15 دقيقة لاستخراج أساسي.  
- **هل أحتاج إلى ترخيص؟** يتوفر إصدار تجريبي مجاني؛ يلزم الحصول على ترخيص تجاري للاستخدام الإنتاجي.  
- **هل يمكنني تخصيص ساعات العمل؟** نعم – يمكنك تعديل التقاويم، إضافة العطلات، وتحديد نطاقات زمنية مخصصة للعمل.  

## ما هو “تحديد أيام العمل”؟
عند جدولة مهمة، يحدد تقويم المشروع أي الأيام هي أيام عمل وأيها غير عمل (عطلات نهاية الأسبوع، العطلات). يعني تحديد أيام العمل استعلام ذلك التقويم لمعرفة متى يمكن أن يحدث العمل بالضبط، وهو أمر أساسي لحساب **مدة المهمة** بدقة.

## لماذا نستخدم Aspose.Tasks لاسترجاع ساعات العمل؟
- **لا حاجة إلى Microsoft Project** – يمكنك قراءة ملفات MS Project مباشرةً من كود Java.  
- **دعم كامل للتقويم** – يشمل التقويمات الافتراضية، تقويمات الموارد، وتقويمات المهام.  
- **أداء عالي** – معالجة المشاريع الكبيرة بسرعة.  
- **توثيق شامل** – أمثلة ومرجع API متوفران بسهولة.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أعلى.  
2. **Aspose.Tasks for Java** – حمّل أحدث ملف JAR من [here](https://releases.aspose.com/tasks/java/).  
3. معرفة أساسية ببرمجة Java.  

## استيراد الحزم
أولاً، استورد مساحة الاسم الأساسية لـ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## كيفية تحميل ملف MPP باستخدام Aspose.Tasks؟
تحميل ملف المشروع هو الخطوة الأولى لأي تحليل تقويم. تسمح لك API **بتحميل ملف MPP** بسطر واحد من الكود، دون الحاجة إلى واجهة MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## استرجاع معلومات المهمة والتقويم
اختر المهمة التي تريد تحليلها واحصل على التقويم المرتبط بها. هنا نُسترجع **ساعات العمل** للمهمة:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## تحديد تاريخ البداية والنهاية
قم بإعداد نافذة الوقت التي تريد **تحديد أيام العمل** لها. استخدام تواريخ بدء وانتهاء المهمة يضمن تقييم الفترة ذات الصلة فقط.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## التكرار عبر التواريخ
قم بالتكرار عبر كل تاريخ في مدة المهمة. سيساعدنا هذا التكرار على **تخصيص ساعات العمل** لاحقًا إذا لزم الأمر:

```java
java.util.Calendar tempDate = calStartDate;
```

## حساب المدة
أثناء التكرار نتحقق مما إذا كان كل يوم يوم عمل، نجمع ساعات العمل، وأخيرًا نحسب مدة المهمة بالدقائق، الساعات، والأيام. يوضح هذا الخطوة كيفية **حساب أيام العمل** و**حساب مدة المهمة** برمجيًا.

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## كيفية تخصيص ساعات العمل والعطلات
يتيح لك Aspose.Tasks تعديل نطاقات الوقت العامل في التقويم وإضافة استثناءات مثل العطلات. يمكنك استدعاء `taskCalendar.addWorkingTime()` أو `taskCalendar.addException()` لتكييف الجدول مع سياسات مؤسستك. هذا مفيد عندما لا يتطابق جدول 9‑5 الافتراضي مع الواقع.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Task returns `null` for calendar** | تأكد من أن المهمة فعليًا لديها تقويم مُعيّن؛ وإلا فإنها ترث التقويم الافتراضي للمشروع. |
| **Incorrect duration because of holidays** | تحقق من تعريف العطلات في تقويم المهمة أو في التقويم الأساسي للمشروع. |
| **Time zone mismatch** | استخدم `java.util.TimeZone` لمزامنة المنطقة الزمنية للتقويم مع نظامك إذا لزم الأمر. |

## الأسئلة المتكررة
### س: هل يمكن لـ Aspose.Tasks for Java التعامل مع هياكل المشاريع المعقدة؟
ج: نعم، توفر Aspose.Tasks for Java دعمًا شاملاً للتعامل مع هياكل المشاريع المعقدة، بما في ذلك المهام والموارد والتقاويم.

### س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من MS Project؟
ج: بالتأكيد، تدعم Aspose.Tasks for Java إصدارات متعددة من MS Project، مما يضمن التوافق عبر بيئات مختلفة.

### س: هل يمكنني تخصيص ساعات العمل والعطلات في تقاويم المشروع؟
ج: نعم، يمكنك بسهولة تخصيص ساعات العمل والعطلات وفقًا لمتطلبات مشروعك باستخدام واجهات Aspose.Tasks for Java.

### س: هل يقدم Aspose.Tasks for Java الدعم والوثائق؟
ج: نعم، يوفر Aspose.Tasks for Java وثائقًا واسعة ومنتديات دعم مخصصة لمساعدة المطورين على الاستفادة من ميزاته بفعالية.

### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks for Java من [here](https://releases.aspose.com/).

## الخاتمة
في هذا الدليل أظهرنا كيفية **تحديد أيام العمل**، **استخراج ساعات العمل**، و**حساب مدة المهمة** من تقويم MS Project باستخدام Aspose.Tasks for Java. باتباع الخطوات أعلاه يمكنك أتمتة تحليل الجدول الزمني، تخصيص التقاويم، والحفاظ على خطط مشروعك دقيقة ومحدثة. الآن لديك الأدوات ل**قراءة بيانات MS Project**، **تحميل ملف MPP**، وإجراء حسابات دقيقة للمدة دون الحاجة إلى Microsoft Project نفسه.

---

**آخر تحديث:** 2026-02-05  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت كتابة هذا الدليل)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}