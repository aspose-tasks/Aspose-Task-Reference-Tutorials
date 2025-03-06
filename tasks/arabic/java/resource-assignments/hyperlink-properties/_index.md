---
title: إدارة خصائص الارتباط التشعبي للواجبات في Aspose.Tasks
linktitle: إدارة خصائص الارتباط التشعبي لتعيينات الموارد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية إدارة خصائص الارتباط التشعبي لتعيينات الموارد في Aspose.Tasks لـ Java. تعزيز التعاون وإمكانية الوصول في إدارة المشاريع.
type: docs
weight: 16
url: /ar/java/resource-assignments/hyperlink-properties/
---
## مقدمة
يوفر Aspose.Tasks for Java ميزات قوية لإدارة مهام المشروع وموارده. في هذا البرنامج التعليمي، سنركز على كيفية إدارة خصائص الارتباط التشعبي لتعيينات الموارد باستخدام Aspose.Tasks. باتباع هذه الإرشادات خطوة بخطوة، ستتمكن من التعامل بكفاءة مع الارتباطات التشعبية المرتبطة بتعيينات موارد مشروعك.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
- مجموعة تطوير جافا المثبتة (JDK).
- الوصول إلى Aspose.Tasks لمكتبة Java.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
أولاً، تأكد من استيراد الحزم اللازمة للاستفادة من وظائف Aspose.Tasks في مشروع Java الخاص بك.
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## الخطوة 1: إنشاء مثيل المشروع
ابدأ بإنشاء مثيل مشروع جديد باستخدام Aspose.Tasks.
```java
Project prj = new Project();
```
## الخطوة 2: إضافة مهمة إلى المشروع
الآن، أضف مهمة إلى المشروع والتي سيتم ربطها بالارتباط التشعبي.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## الخطوة 3: إضافة مورد
بعد ذلك، قم بإضافة مورد إلى المشروع.
```java
Resource resource = prj.getResources().add("Resource 1");
```
## الخطوة 4: إنشاء تعيين الموارد
قم بإنشاء تعيين مورد وربطه بالمهمة والمورد.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## الخطوة 5: تعيين خصائص الارتباط التشعبي
قم بتعيين خصائص الارتباط التشعبي لتعيين المورد.
```java
assignment.set(Asn.HYPERLINK, "Click to visit our site");
assignment.set(Asn.HYPERLINK_ADDRESS, "https://Products.aspose.com");
assignment.set(Asn.HYPERLINK_SUB_ADDRESS, "/total/net");
```
## الخطوة 6: طباعة خصائص الارتباط التشعبي
قم بطباعة خصائص الارتباط التشعبي للتحقق من الإعداد.
```java
System.out.println("Hyperlink: " + assignment.get(Asn.HYPERLINK));
System.out.println("Hyperlink Address: " + assignment.get(Asn.HYPERLINK_ADDRESS));
System.out.println("Hyperlink Sub Address: " + assignment.get(Asn.HYPERLINK_SUB_ADDRESS));
```
## الخطوة 7: إكمال العملية
وأخيراً، قم بعرض رسالة تشير إلى إتمام العملية بنجاح.
```java
System.out.println("Process completed Successfully");
```

## خاتمة
في الختام، تعد إدارة خصائص الارتباط التشعبي لتعيينات الموارد في Aspose.Tasks لـ Java أمرًا مباشرًا وفعالاً. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة دمج الارتباطات التشعبية في مهام وموارد مشروعك، مما يعزز التعاون وإمكانية الوصول إلى المعلومات.
## الأسئلة الشائعة
### س: هل يمكنني إضافة ارتباطات تشعبية متعددة إلى تعيين مورد واحد؟
ج: نعم، يمكنك إضافة ارتباطات تشعبية متعددة إلى تعيين المورد عن طريق تكرار العملية الموضحة في هذا البرنامج التعليمي لكل ارتباط تشعبي.
### س: هل من الممكن تخصيص مظهر الارتباطات التشعبية في Aspose.Tasks؟
ج: يركز Aspose.Tasks بشكل أساسي على إدارة بيانات المشروع وخصائصه، بما في ذلك الارتباطات التشعبية. للتخصيص المتقدم لمظهر الارتباط التشعبي، قد تحتاج إلى استكشاف مكتبات أو أدوات إضافية.
### س: هل هناك أي قيود على طول الارتباطات التشعبية في Aspose.Tasks؟
ج: لا يفرض Aspose.Tasks قيودًا صارمة على طول الارتباطات التشعبية. ومع ذلك، فمن المستحسن إبقاء الارتباطات التشعبية موجزة وذات صلة لتحسين سهولة القراءة وسهولة الاستخدام.
### س: هل يمكنني إزالة الارتباطات التشعبية من تعيينات الموارد برمجياً؟
ج: نعم، يمكنك إزالة الارتباطات التشعبية من تعيينات الموارد عن طريق تعيين خصائص الارتباط التشعبي إلى سلاسل فارغة أو فارغة.
### س: هل يدعم Aspose.Tasks التحقق من صحة الارتباط التشعبي؟
ج: يركز Aspose.Tasks على إدارة خصائص الارتباط التشعبي بدلاً من التحقق من صحة الارتباطات التشعبية. ومع ذلك، يمكنك تنفيذ منطق التحقق المخصص داخل تطبيق Java الخاص بك لضمان سلامة الارتباط التشعبي.