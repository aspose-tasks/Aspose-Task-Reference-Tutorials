---
title: قراءة البيانات الموزعة على الوقت للموارد في Aspose.Tasks
linktitle: قراءة البيانات الموزعة على الوقت للموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية استخراج البيانات الموزعة على الوقت من موارد MS Project باستخدام Aspose.Tasks لـ Java. البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 15
url: /ar/java/resource-management/read-timephased-data/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية قراءة البيانات الموزعة على الوقت لموارد MS Project باستخدام Aspose.Tasks لـ Java. توفر هذه المكتبة وظائف قوية لإدارة ملفات Microsoft Project برمجياً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) واتبع تعليمات التثبيت.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks لـ Java من[صفحة التحميل](https://releases.aspose.com/tasks/java/) واتبع تعليمات التثبيت المتوفرة في الوثائق.

## حزم الاستيراد
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## الخطوة 1: إعداد دليل البيانات
أولاً، قم بتحديد الدليل الذي يوجد به ملف MS Project الخاص بك.
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: قراءة ملف قالب مشروع MS
حدد اسم ملف قالب MS Project الخاص بك.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## الخطوة 3: قراءة ملف الإدخال كمشروع
اقرأ ملف الإدخال باستخدام Aspose.Tasks وقم بتحميله ككائن مشروع.
```java
Project project = new Project(dataDir + fileName);
```
## الخطوة 4: الحصول على الموارد عن طريق المعرف
استرداد المورد المطلوب من المشروع عن طريق المعرف الفريد (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## الخطوة 5: طباعة البيانات الموزعة على الوقت لعمل الموارد
طباعة البيانات الموزعة على الوقت لعمل الموارد.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## الخطوة 6: طباعة البيانات الموزعة على الوقت لتكلفة الموارد
طباعة البيانات الموزعة على الوقت لتكلفة الموارد.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية قراءة البيانات الموزعة على الوقت لموارد MS Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك استخراج المعلومات القيمة من ملفات مشروعك بكفاءة برمجيًا.
## الأسئلة الشائعة
### هل يستطيع Aspose.Tasks التعامل مع أنواع أخرى من ملفات المشاريع بخلاف Microsoft Project؟
نعم، يدعم Aspose.Tasks تنسيقات ملفات متنوعة، بما في ذلك MPP وXML وCSV.
### هل Aspose.Tasks متوافق مع بيئات تطوير Java المختلفة؟
نعم، Aspose.Tasks متوافق مع جميع بيئات تطوير Java الأساسية وأطر العمل.
### هل يمكنني معالجة بيانات المشروع باستخدام Aspose.Tasks؟
بالتأكيد، يوفر Aspose.Tasks واجهات برمجة تطبيقات واسعة النطاق لإنشاء بيانات المشروع وتعديلها وتحليلها.
### هل Aspose.Tasks مناسب للمشاريع على مستوى المؤسسة؟
نعم، يتم استخدام Aspose.Tasks على نطاق واسع في بيئات المؤسسات نظرًا لموثوقيته وقابلية التوسع.
### أين يمكنني العثور على الدعم إذا واجهت مشكلات أثناء استخدام Aspose.Tasks؟
 يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للحصول على المساعدة من المجتمع وفريق الدعم.