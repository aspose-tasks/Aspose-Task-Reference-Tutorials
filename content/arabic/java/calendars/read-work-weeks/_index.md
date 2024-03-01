---
title: اقرأ أسابيع العمل من MS Project Calendar باستخدام Aspose.Tasks
linktitle: اقرأ أسابيع العمل من التقويم باستخدام Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية قراءة أسابيع العمل من تقويم MS Project باستخدام Aspose.Tasks لـ Java. احصل على تعليمات خطوة بخطوة في هذا البرنامج التعليمي الشامل.
type: docs
weight: 15
url: /ar/java/calendars/read-work-weeks/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية استخدام Aspose.Tasks لـ Java لقراءة معلومات أسابيع العمل من تقويم Microsoft Project. Aspose.Tasks هي مكتبة Java قوية تسمح لك بمعالجة وإدارة مستندات Microsoft Project برمجياً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل وتثبيت Aspose.Tasks لمكتبة Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
أولاً، لنستورد الحزم اللازمة للبدء في استخدام الكود الخاص بنا:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## الخطوة 1: إعداد دليل البيانات الخاص بك
قم بإعداد مسار الدليل حيث يوجد ملف MS Project الخاص بك:
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: إنشاء مثيل المشروع والوصول إلى التقويم
قم بإنشاء مثيل جديد لفئة المشروع والوصول إلى مجموعة التقويم وأسابيع العمل:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## الخطوة 3: التكرار خلال أسابيع العمل
كرر عملية جمع أسابيع العمل واعرض معلوماتها:
```java
for (WorkWeek workWeek : collection) {
    // عرض اسم أسبوع العمل، من وإلى التواريخ
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // الوصول إلى أيام الأسبوع وأوقات العمل
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // مزيد من أوقات العمل العملية إذا لزم الأمر
    }
}
```
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية قراءة معلومات أسابيع العمل من تقويم Microsoft Project باستخدام Aspose.Tasks لـ Java. تتيح هذه المكتبة القوية معالجة سلسة لملفات المشروع، مما يسمح للمطورين بأتمتة المهام المختلفة بكفاءة.
## الأسئلة الشائعة
### هل يمكنني تعديل معلومات أسابيع العمل باستخدام Aspose.Tasks لـ Java؟
نعم، يوفر Aspose.Tasks واجهات برمجة التطبيقات لتعديل أو إضافة أو حذف أسابيع العمل والمعلومات المرتبطة بها.
### هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات Microsoft Project؟
نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وXML.
### هل يمكنني دمج Aspose.Tasks مع أطر عمل Java الأخرى؟
بالتأكيد، يمكن دمج Aspose.Tasks بسلاسة مع أطر عمل Java ومكتباتها الأخرى لتحسين الوظائف.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Tasks؟
يمكنك العثور على الدعم والمساعدة في منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).