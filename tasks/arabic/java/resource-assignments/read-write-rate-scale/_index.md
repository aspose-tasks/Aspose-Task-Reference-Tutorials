---
title: مقياس معدل القراءة والكتابة لتعيينات الموارد في Aspose.Tasks
linktitle: مقياس معدل القراءة والكتابة لتعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إدارة مقياس معدل تعيينات الموارد بشكل فعال في Aspose.Tasks لـ Java باستخدام هذا البرنامج التعليمي الشامل.
type: docs
weight: 20
url: /ar/java/resource-assignments/read-write-rate-scale/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعمق في إدارة مقياس معدل تعيينات الموارد باستخدام Aspose.Tasks for Java، وهي مكتبة قوية للعمل مع ملفات Microsoft Project برمجيًا. باتباع هذه الخطوات، ستتمكن من التعامل بشكل فعال مع إعدادات مقياس المعدل لتعيينات الموارد في تطبيقات Java الخاصة بك.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java من[هنا](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة للعمل مع وظائف Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإعداد مشروع Java الخاص بك وقم بتضمين مكتبة Aspose.Tasks في تبعياتك.
## الخطوة 2: تحميل ملف المشروع
قم بتحميل ملف المشروع الذي تريد العمل به في تطبيق Java الخاص بك.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## الخطوة 3: إضافة مهمة
أضف مهمة جديدة إلى مشروعك.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## الخطوة 4: تحديد الموارد
تعريف الموارد المادية وغير المادية وتحديد أنواعها.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## الخطوة 5: تعيين الموارد للمهمة
قم بتعيين الموارد المحددة مسبقًا للمهمة مع أنواع مقياس المعدل الخاص بها.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## الخطوة 6: احفظ المشروع
احفظ المشروع بتعيينات الموارد المعدلة.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## الخطوة 7: استرداد تعيينات الموارد
قم بإعادة تحميل المشروع المحفوظ واسترداد تعيينات الموارد للتحقق من إعدادات مقياس المعدل.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## خاتمة
تعد إدارة مقياس معدل تعيينات الموارد في Aspose.Tasks لـ Java أمرًا ضروريًا لإدارة المشاريع بشكل فعال. باتباع هذا الدليل التفصيلي خطوة بخطوة، يمكنك التعامل بسهولة مع إعدادات مقياس المعدل لتعيينات الموارد في تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### س١: هل يمكنني استخدام Aspose.Tasks لـ Java مع أي Java IDE؟
ج: نعم، Aspose.Tasks for Java متوافق مع جميع بيئات تطوير Java الأساسية، بما في ذلك IntelliJ IDEA وEclipse وNetBeans.
### س2: هل يدعم Aspose.Tasks تنسيقات الملفات الأخرى إلى جانب MPP؟
ج: نعم، يدعم Aspose.Tasks تنسيقات ملفات متنوعة، بما في ذلك MPP وXML وHTML.
### س3: هل Aspose.Tasks مناسب لإدارة المشاريع على مستوى المؤسسة؟
ج: بالتأكيد، يوفر Aspose.Tasks ميزات شاملة لإدارة المشاريع بأي حجم، مما يجعلها مناسبة لإدارة المشاريع على مستوى المؤسسة.
### س4: هل يمكنني تخصيص تعيينات الموارد بما يتجاوز مقياس السعر؟
ج: نعم، يوفر Aspose.Tasks إمكانات واسعة النطاق لتخصيص تعيينات الموارد، بما في ذلك تعديلات التكلفة والعمل والمدة.
### س5: هل يوجد منتدى مجتمعي لدعم Aspose.Tasks؟
 ج: نعم، يمكنك العثور على الدعم والتفاعل مع المستخدمين الآخرين في منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).