---
title: استرجع معلومات تقويم مشروع MS في Aspose.Tasks
linktitle: استرداد معلومات التقويم في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية استرداد معلومات تقويم MS Project باستخدام Aspose.Tasks لـ Java. دليل خطوة بخطوة للوصول إلى تفاصيل التقويم برمجياً.
type: docs
weight: 14
url: /ar/java/project-file-operations/retrieve-calendar-info/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية استرداد معلومات التقويم من ملفات Microsoft Project باستخدام مكتبة Aspose.Tasks لـ Java. يوفر Aspose.Tasks ميزات قوية لمعالجة بيانات المشروع، بما في ذلك الوصول إلى تفاصيل التقويم مثل أيام وساعات العمل.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Tasks لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم الضرورية في كود Java الخاص بك لاستخدام وظائف Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
الآن دعونا نقسم المثال المقدم إلى خطوات متعددة لفهم أفضل.
## الخطوة 1: قم بتعيين دليل البيانات
```java
String dataDir = "Your Data Directory";
```
 يستبدل`"Your Data Directory"` مع المسار إلى دليل ملفات المشروع الخاص بك.
## الخطوة 2: تحديد الوحدات الزمنية
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
تمثل هذه الثوابت الوحدات الزمنية بالميكروثانية.
## الخطوة 3: إنشاء مثيل المشروع
```java
Project project = new Project(dataDir + "project.mpp");
```
 يقوم هذا السطر بإنشاء مثيل لـ`Project` فئة، وتهيئتها بالمسار إلى ملف المشروع (`project.mpp`).
## الخطوة 4: استرداد معلومات التقاويم
```java
CalendarCollection alCals = project.getCalendars();
```
هنا، نقوم باسترداد مجموعة من التقويمات الموجودة في ملف المشروع.
## الخطوة 5: التكرار من خلال التقاويم
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // معلومات التقويم
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // التكرار خلال أيام الأسبوع
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // الوقت بالمللي ثانية
            double time = ts / (OneHour); // تحويل إلى ساعات
            if (wd.getDayWorking()) {
                // عرض أيام وساعات العمل
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
تتكرر هذه الحلقة خلال كل تقويم وتطبع المعرف الفريد (UID) والاسم وأيام العمل مع ساعات العمل المعنية.
## الخطوة 6: عرض رسالة الإكمال
```java
System.out.println("Process completed Successfully");
```
وأخيراً تظهر رسالة تشير إلى إتمام العملية.
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استرداد معلومات التقويم من ملفات MS Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك الوصول إلى بيانات المشروع ومعالجتها بكفاءة في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks مع لغات البرمجة الأخرى؟
ج: نعم، يدعم Aspose.Tasks منصات ولغات برمجة متعددة، بما في ذلك .NET وC++و بايثون و جافا.
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks؟
 ج: نعم، التراخيص المؤقتة متاحة للشراء[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني العثور على الوثائق التفصيلية الخاصة بـ Aspose.Tasks؟
 ج: يمكنك الرجوع إلى الوثائق[هنا](https://reference.aspose.com/tasks/java/).