---
title: إدارة خصائص تقويم مشروع MS في Aspose.Tasks
linktitle: إدارة خصائص التقويم في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إدارة خصائص تقويم MS Project في Java باستخدام Aspose.Tasks. يوفر هذا إرشادات خطوة بخطوة للتقويم ضمن تطبيقات Java الخاصة بك.
type: docs
weight: 10
url: /ar/java/calendars/properties/
---
## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إدارة خصائص تقويم MS Project باستخدام Aspose.Tasks لـ Java. من خلال فهم كيفية التعامل مع خصائص التقويم، يمكنك تخصيص جداول المشروع لتلبية متطلبات محددة بكفاءة.
## المتطلبات الأساسية
قبل المتابعة، تأكد من توفر المتطلبات الأساسية التالية:
### تثبيت مجموعة تطوير جافا (JDK).
تأكد من تثبيت Java Development Kit (JDK) على نظامك.
### Aspose.Tasks لمكتبة جافا
 قم بتنزيل وإعداد Aspose.Tasks لمكتبة Java من[صفحة التحميل](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية:
```java
import com.aspose.tasks.*;
```

## الخطوة 1: إعداد دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى دليل البيانات الخاص بك.
## الخطوة 2: تحديد الوحدات الزمنية
```java
long OneSec = 1000; // 1000 مللي ثانية
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
هنا، نحدد الوحدات الزمنية للراحة.
## الخطوة 3: تحميل بيانات المشروع
```java
Project project = new Project(dataDir + "project.xml");
```
قم بتحميل بيانات MS Project من ملف XML المحدد.
## الخطوة 4: التكرار من خلال التقاويم
```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // أظهر ما إذا كان يحتوي على تقويم أساسي
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // كرر خلال أيام الأسبوع
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```
تتكرر هذه الحلقة خلال كل تقويم في المشروع، وتعرض خصائصه مثل UID والاسم والتقويم الأساسي وساعات العمل لكل نوع يوم.

## خاتمة
باتباع هذا البرنامج التعليمي، تعلمت كيفية إدارة خصائص تقويم MS Project باستخدام Aspose.Tasks لـ Java. تمكنك هذه المعرفة من تخصيص جداول المشروع بشكل فعال، مما يضمن التوافق مع متطلبات المشروع.
## الأسئلة الشائعة
### س: هل يمكنني تعديل خصائص التقويم برمجيًا باستخدام Aspose.Tasks؟
ج: نعم، يوفر Aspose.Tasks واجهات برمجة تطبيقات شاملة لمعالجة خصائص التقويم ديناميكيًا داخل تطبيقات Java.
### س: هل هناك أي قيود على تخصيص التقويم باستخدام Aspose.Tasks؟
ج: يوفر Aspose.Tasks مرونة واسعة النطاق في إدارة التقويم، مع الحد الأدنى من القيود على خيارات التخصيص.
### س: هل يمكنني دمج وظيفة إدارة التقويم في مشاريع Java الحالية؟
ج: بالتأكيد! يمكنك دمج ميزات إدارة التقويم الخاصة بـ Aspose.Tasks بسلاسة في مشاريع Java الخاصة بك، مما يعزز إمكانات جدولة المشروع.
### س: هل يدعم Aspose.Tasks وظائف إدارة المشروعات الأخرى إلى جانب إدارة التقويم؟
ج: نعم، يقدم Aspose.Tasks نطاقًا واسعًا من الوظائف لإدارة المهام والموارد وهياكل المشاريع، مما يجعله حلاً شاملاً لإدارة المشاريع في Java.
### س: هل يتوفر الدعم الفني للمطورين الذين يستخدمون Aspose.Tasks؟
ج: نعم، يمكن للمطورين الوصول إلى الدعم الفني من خلال منتدى Aspose.Tasks، مما يضمن المساعدة في أي استفسارات أو مشكلات تتم مواجهتها أثناء التنفيذ.