---
title: احصل على ساعات العمل من التقويم باستخدام Aspose.Tasks
linktitle: احصل على ساعات العمل من التقويم باستخدام Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: استخرج ساعات العمل من تقويمات MS Project بسهولة باستخدام Aspose.Tasks لـ Java. تبسيط مهام إدارة المشروع.
type: docs
weight: 13
url: /ar/java/calendars/working-hours/
---
## مقدمة
تعد إدارة تقاويم المشروع واستخراج ساعات العمل أمرًا ضروريًا لإدارة المشروع بشكل فعال. يوفر Aspose.Tasks for Java وظائف قوية لاسترداد ساعات العمل من تقويمات MS Project دون عناء. في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل Aspose.Tasks لمكتبة Java وإضافتها إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
3. الفهم الأساسي للغة البرمجة جافا.
## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة للعمل مع Aspose.Tasks لـ Java:
```java
import com.aspose.tasks.*;
```
## الخطوة 1: تحميل ملف المشروع
ابدأ بتحميل ملف MS Project الخاص بك:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## الخطوة 2: استرداد معلومات المهمة والتقويم
استخراج تفاصيل المهمة والتقويم من المشروع:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## الخطوة 3: تحديد تاريخي البدء والانتهاء
قم بإعداد تاريخي البدء والانتهاء للمهمة:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## الخطوة 4: التكرار عبر التواريخ
التكرار عبر التواريخ خلال مدة المهمة:
```java
java.util.Calendar tempDate = calStartDate;
```
## الخطوة 5: حساب المدة
حساب المدة بالدقائق والساعات والأيام:
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
## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية استرداد ساعات العمل من تقويم MS Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك إدارة جداول المشروع بكفاءة وحساب فترات المهام بسهولة.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع هياكل المشاريع المعقدة؟
ج: نعم، يوفر Aspose.Tasks for Java دعمًا شاملاً للتعامل مع هياكل المشروع المعقدة، بما في ذلك المهام والموارد والتقويمات.
### س: هل Aspose.Tasks for Java متوافق مع الإصدارات المختلفة من MS Project؟
ج: بالتأكيد، يدعم Aspose.Tasks for Java إصدارات مختلفة من MS Project، مما يضمن التوافق عبر البيئات المختلفة.
### س: هل يمكنني تخصيص ساعات العمل والعطلات في تقاويم المشروع؟
ج: نعم، يمكنك بسهولة تخصيص ساعات العمل والإجازات وفقًا لمتطلبات مشروعك باستخدام Aspose.Tasks لواجهات برمجة تطبيقات Java.
### س: هل يقدم Aspose.Tasks لـ Java الدعم والوثائق؟
ج: نعم، يوفر Aspose.Tasks for Java وثائق مكثفة ومنتديات دعم مخصصة لمساعدة المطورين في استخدام ميزاته بفعالية.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks لـ Java من[هنا](https://releases.aspose.com/).