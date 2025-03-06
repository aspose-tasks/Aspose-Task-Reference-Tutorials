---
title: إنشاء بيانات موزعة على الوقت في Aspose.Tasks
linktitle: قم بإنشاء بيانات موزعة على الوقت لتعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إنشاء بيانات موزعة على الوقت لتعيينات الموارد باستخدام Aspose.Tasks لـ Java. قم بتحسين كفاءة إدارة المشاريع باستخدام هذا الدليل الشامل.
type: docs
weight: 24
url: /ar/java/resource-assignments/timephased-data-generation/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية إنشاء البيانات الموزعة على الوقت لتعيينات الموارد باستخدام Aspose.Tasks لـ Java. توفر البيانات الموزعة على الوقت رؤى قيمة حول كيفية تخصيص الموارد بمرور الوقت داخل المشروع، مما يساعد مديري المشاريع على اتخاذ قرارات مستنيرة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيل وتثبيت JDK من[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks لمكتبة Java: يجب أن يكون لديك مكتبة Aspose.Tasks لـ Java. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
أولاً، لنستورد الحزم اللازمة للعمل مع Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## الخطوة 1: اقرأ ملف MPP المصدر
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
// اقرأ ملف MPP المصدر
Project project = new Project(dataDir + "project.mpp");
```
## الخطوة 2: الحصول على المهام وتعيين الموارد
```java
// احصل على المهمة الأولى للمشروع
Task task = project.getRootTask().getChildren().getById(1);
// الحصول على تعيين الموارد الأول للمشروع
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## الخطوة 3: إنشاء بيانات موزعة على الوقت باستخدام محيط مسطح
```java
// الكفاف المسطح هو الكفاف الافتراضي
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## الخطوة 4: تغيير الكفاف إلى السلحفاة
```java
// تغيير الكفاف إلى السلحفاة
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## الخطوة 5: تغيير الكفاف إلى BackLoaded
```java
// تغيير الكفاف إلى BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## الخطوة 6: تغيير الكفاف إلى FrontLoaded
```java
// تغيير الكفاف إلى FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## الخطوة 7: تغيير الكفاف إلى الجرس
```java
// تغيير الكفاف إلى الجرس
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## الخطوة 8: تغيير الكفاف إلى EarlyPeak
```java
// تغيير الكفاف إلى EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## الخطوة 9: تغيير الكفاف إلى LatePeak
```java
// تغيير الكفاف إلى LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## الخطوة 10: تغيير الكفاف إلى DoublePeak
```java
// قم بتغيير الكفاف إلى DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية إنشاء بيانات موزعة على الوقت لتعيينات الموارد باستخدام Aspose.Tasks لـ Java. يمكن أن يساعد فهم خطوط العمل المختلفة مديري المشاريع على إدارة تخصيص الموارد والجدولة بشكل فعال في مشاريعهم.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks مع مكتبات Java الأخرى؟
نعم، يمكن دمج Aspose.Tasks مع مكتبات Java الأخرى لتعزيز قدرات إدارة المشروع.
### هل Aspose.Tasks مناسب لمشاريع المؤسسات واسعة النطاق؟
بالتأكيد، تم تصميم Aspose.Tasks للتعامل مع المشاريع بجميع أحجامها، بما في ذلك مشاريع المؤسسات واسعة النطاق.
### هل يوفر Aspose.Tasks الدعم لتنسيقات ملفات المشروع المختلفة؟
نعم، يدعم Aspose.Tasks العديد من تنسيقات ملفات المشروع، بما في ذلك MPP وXML وMPX.
### هل يمكنني تخصيص حدود العمل وفقًا لمتطلبات مشروعي؟
نعم، يسمح Aspose.Tasks للمستخدمين بتحديد حدود العمل المخصصة لتناسب احتياجات المشروع الخاصة بهم.
### هل يوجد منتدى مجتمعي حيث يمكنني الحصول على المساعدة فيما يتعلق بـ Aspose.Tasks؟
 نعم يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للدعم والمناقشات.