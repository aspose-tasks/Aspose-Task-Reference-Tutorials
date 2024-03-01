---
title: حساب النسب المئوية لتخصيص الموارد باستخدام Aspose.Tasks
linktitle: حساب النسب المئوية لتعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية حساب النسب المئوية لتعيينات الموارد بكفاءة في مشاريع Java باستخدام Aspose.Tasks، مما يبسط مهام إدارة المشروع.
type: docs
weight: 13
url: /ar/java/resource-assignments/calculate-percentages/
---
## مقدمة
في إدارة المشاريع، يعد حساب تخصيصات الموارد بدقة أمرًا بالغ الأهمية لضمان إنجاز المهام في الوقت المناسب والتخصيص الفعال للموارد. يوفر Aspose.Tasks for Java أدوات قوية لتسهيل هذه العملية، مما يسمح للمطورين بحساب النسب المئوية لتعيينات الموارد بسهولة.
## المتطلبات الأساسية
قبل الغوص في حساب النسب المئوية لتعيينات الموارد باستخدام Aspose.Tasks لـ Java، تأكد من أن لديك ما يلي:
### بيئة تطوير جافا
 تأكد من تثبيت Java Development Kit (JDK) على نظامك. يمكنك تنزيله من[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks لمكتبة جافا
 قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/tasks/java/).
### بيئة التطوير المتكاملة (IDE)
اختر IDE الذي تفضله مثل IntelliJ IDEA أو Eclipse أو NetBeans للبرمجة. 

## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في كود Java الخاص بك:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## الخطوة 1: قم بإعداد دليل البيانات الخاص بك
تأكد من أن لديك دليلًا مخصصًا حيث توجد بيانات مشروعك. ستستخدم هذا الدليل للوصول إلى ملفات مشروعك.
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: تحميل ملف المشروع
 إنشاء مثيل أ`Project` كائن وتحميل ملف المشروع الخاص بك باستخدام دليل البيانات المحدد.
```java
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
## الخطوة 3: التكرار من خلال تعيينات الموارد
قم بالمراجعة عبر كافة تعيينات الموارد في المشروع للوصول إلى تفاصيل كل مهمة.
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // تنفيذ العمليات على كل تعيين الموارد
}
```
## الخطوة 4: حساب النسبة المئوية للعمل المكتمل
استرداد النسبة المئوية للعمل المكتمل لكل تعيين مورد باستخدام Aspose.Tasks.
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    System.out.println(ra.get(Asn.PERCENT_WORK_COMPLETE).toString());
}
```

## خاتمة
باتباع هذه الخطوات البسيطة، يمكنك بسهولة حساب النسب المئوية لتعيينات الموارد في Aspose.Tasks لـ Java، وتبسيط سير عمل إدارة المشروع الخاص بك وضمان الاستخدام الأمثل للموارد.
## الأسئلة الشائعة
### س: هل يمكن لـ Aspose.Tasks التعامل مع هياكل المشروع المعقدة؟
ج: نعم، يدعم Aspose.Tasks التعامل مع هياكل المشاريع المعقدة بسهولة، مما يسمح لك بإدارة المشاريع على أي نطاق.
### س: هل Aspose.Tasks مناسب لإدارة المشاريع على مستوى المؤسسة؟
ج: بالتأكيد، يوفر Aspose.Tasks ميزات قوية مصممة لإدارة المشاريع على مستوى المؤسسة، بما في ذلك تخصيص الموارد والجدولة وإعداد التقارير.
### س: هل يمكنني دمج Aspose.Tasks مع مكتبات Java الأخرى؟
ج: بالتأكيد، يمكن دمج Aspose.Tasks بسلاسة مع مكتبات Java الأخرى لتعزيز قدرات إدارة مشروعك.
### س: هل توفر Aspose.Tasks دعمًا للعملاء؟
 ج: نعم، يقدم Aspose.Tasks دعمًا مخصصًا للعملاء من خلال المنتدى الخاص بهم. يمكنك العثور على المساعدة[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 ج: نعم، يمكنك استكشاف Aspose.Tasks من خلال الإصدار التجريبي المجاني المتاح[هنا](https://releases.aspose.com/).