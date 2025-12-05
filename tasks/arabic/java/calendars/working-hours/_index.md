---
date: 2025-12-05
description: تعلم كيفية تحديد أيام العمل وحساب مدة المهمة عن طريق استخراج ساعات العمل
  من تقاويم MS Project باستخدام Aspose.Tasks للغة Java.
language: ar
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تحديد أيام العمل وساعات العمل باستخدام Aspose.Tasks
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديد أيام العمل وساعات العمل باستخدام Aspose.Tasks

## المقدمة
إدارة تقاويم المشروع هي جزء أساسي من التخطيط الناجح للمشروعات. في هذا الدرس ستقوم **بتحديد أيام العمل** لأي مهمة و**باستخراج ساعات العمل** من تقويم MS Project باستخدام Aspose.Tasks للغة Java. بنهاية الدليل ستكون قادرًا على **حساب مدة المهمة**، تخصيص ساعات العمل، وتحميل ملف MPP **بشكل موثوق** لاسترجاع البيانات التي تحتاجها.

## إجابات سريعة
- **ماذا يعني “تحديد أيام العمل”؟** يعني ذلك التعرف على تواريخ التقويم التي تُعتبر أيام عمل للمهمة المحددة.  
- **أي مكتبة يجب أن أستخدم؟** Aspose.Tasks للغة Java توفر واجهة برمجة تطبيقات كاملة للعمل مع ملفات MS Project.  
- **كم يستغرق تنفيذ ذلك؟** عادةً 10–15 دقيقة لاستخراج أساسي.  
- **هل أحتاج إلى ترخيص؟** يتوفر نسخة تجريبية مجانية؛ يتطلب الاستخدام في الإنتاج ترخيصًا تجاريًا.  
- **هل يمكنني تخصيص ساعات العمل؟** نعم – يمكنك تعديل التقاويم، إضافة العطلات، وتحديد فترات عمل مخصصة.

## ما هو “تحديد أيام العمل”؟
عند جدولة مهمة، يحدد تقويم المشروع أي الأيام هي أيام عمل وأيها غير عمل (عطلات نهاية الأسبوع، العطلات). يعني تحديد أيام العمل الاستعلام عن هذا التقويم لمعرفة متى يمكن أن يتم العمل بدقة، وهو أمر أساسي لحساب **مدة المهمة** بشكل صحيح.

## لماذا تستخدم Aspose.Tasks لاسترجاع ساعات العمل؟
- **لا حاجة إلى Microsoft Project** – العمل مع ملفات .MPP على أي منصة.  
- **دعم كامل للتقويم** – يشمل التقويم الافتراضي، تقويم الموارد، وتقويم المهمة.  
- **أداء عالي** – معالجة المشاريع الكبيرة بسرعة.  
- **توثيق شامل** – أمثلة ومرجع API متوفران بسهولة.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أعلى.  
2. **Aspose.Tasks للغة Java** – حمّل أحدث ملف JAR من [هنا](https://releases.aspose.com/tasks/java/).  
3. معرفة أساسية ببرمجة Java.  

## استيراد الحزم
أولاً، استورد مساحة الاسم الأساسية لـ Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## الخطوة 1: تحميل ملف MPP
حمّل ملف المشروع الخاص بك (خطوة **load mpp file**) حتى تتمكن من العمل مع تقاويمه:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## الخطوة 2: استرجاع معلومات المهمة والتقويم
اختر المهمة التي تريد تحليلها واحصل على التقويم المرتبط بها. هنا نسترجع **ساعات العمل** للمهمة:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## الخطوة 3: تحديد تاريخ البدء والانتهاء
حدد نافذة الوقت التي تريد **تحديد أيام العمل** لها:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## الخطوة 4: التكرار عبر التواريخ
قم بالتكرار عبر كل تاريخ في مدة المهمة. سيساعدنا هذا التكرار على **تخصيص ساعات العمل** لاحقًا إذا لزم الأمر:

```java
java.util.Calendar tempDate = calStartDate;
```

## الخطوة 5: حساب المدة
أثناء التكرار نتحقق ما إذا كان كل يوم يوم عمل، نجمع ساعات العمل، وأخيرًا نحسب مدة المهمة بالدقائق، الساعات، والأيام:

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

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Task returns `null` for calendar** | تأكد من أن المهمة لديها تقويم فعليًا؛ وإلا فإنها ترث التقويم الافتراضي للمشروع. |
| **Incorrect duration because of holidays** | تحقق من أن العطلات معرفة في تقويم المهمة أو في تقويم المشروع الأساسي. |
| **Time zone mismatch** | استخدم `java.util.TimeZone` لمزامنة المنطقة الزمنية للتقويم مع نظامك إذا لزم الأمر. |

## الأسئلة المتكررة
### س: هل يمكن لـ Aspose.Tasks للغة Java التعامل مع هياكل مشاريع معقدة؟
ج: نعم، توفر Aspose.Tasks للغة Java دعمًا شاملاً للتعامل مع هياكل مشاريع معقدة، بما في ذلك المهام والموارد والتقاويم.

### س: هل Aspose.Tasks للغة Java متوافق مع إصدارات مختلفة من MS Project؟
ج: بالتأكيد، تدعم Aspose.Tasks للغة Java إصدارات متعددة من MS Project، مما يضمن التوافق عبر بيئات مختلفة.

### س: هل يمكنني تخصيص ساعات العمل والعطلات في تقاويم المشروع؟
ج: نعم، يمكنك بسهولة تخصيص ساعات العمل والعطلات وفقًا لمتطلبات مشروعك باستخدام واجهات برمجة تطبيقات Aspose.Tasks للغة Java.

### س: هل تقدم Aspose.Tasks للغة Java دعمًا ووثائق؟
ج: نعم، توفر Aspose.Tasks للغة Java وثائق واسعة ومنتديات دعم مخصصة لمساعدة المطورين على الاستفادة من ميزاتها بفعالية.

### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks للغة Java؟
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks للغة Java من [هنا](https://releases.aspose.com/).

## الخاتمة
في هذا الدليل أظهرنا كيفية **تحديد أيام العمل**، **استخراج ساعات العمل**، و**حساب مدة المهمة** من تقويم MS Project باستخدام Aspose.Tasks للغة Java. باتباع الخطوات أعلاه يمكنك أتمتة تحليل الجداول الزمنية، تخصيص التقاويم، والحفاظ على خطط مشروعك دقيقة ومحدثة.

---

**آخر تحديث:** 2025-12-05  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}