---
title: مهمة البيانات الموزعة على الوقت في Aspose.Tasks
linktitle: مهمة البيانات الموزعة على الوقت في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: استكشف Aspose.Tasks لـ Java وإدارة البيانات الموزعة على الوقت للمهمة الرئيسية. قم بتنزيل المكتبة، واستمتع بالإصدار التجريبي المجاني، وقم بتبسيط عملية تتبع مشروعك.
type: docs
weight: 34
url: /ar/java/task-properties/task-timephased-data/
---
## مقدمة
في مجال إدارة المشاريع، يعد التتبع الدقيق لبيانات المهمة الموزعة على الوقت أمرًا بالغ الأهمية لتنفيذ المشروع بكفاءة. يظهر Aspose.Tasks for Java كأداة قوية لتبسيط هذه العملية، مما يوفر ميزات ومرونة قوية. سيرشدك هذا البرنامج التعليمي خلال استخدام Aspose.Tasks لـ Java لإدارة بيانات المهمة الموزعة على الوقت بشكل فعال.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- بيئة تطوير Java: تأكد من تثبيت Java على نظامك.
-  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks وتضمينها في مشروعك. يمكنك العثور على المكتبة[هنا](https://releases.aspose.com/tasks/java/).
- دليل المستندات: قم بإعداد دليل لمستندات مشروعك.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة لـ Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## الخطوة 1: تحديد تاريخ بدء المشروع
```java
Project project = new Project(dataDir + "project.xml");
// رمز إضافي لواردات الحزمة
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Explanation: قم بتهيئة عنصر التقويم، وقم بتعيين تاريخ البدء، ثم قم بتطبيقه على المشروع.
## الخطوة 2: تحديد المهمة والموارد
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Explanation: قم بتكوين مهمة ومورد، وتعيين معدلات العمل القياسي والعمل الإضافي.
## الخطوة 3: تحديد مدة المهمة
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Explanation: حدد مدة المهمة (على سبيل المثال، 6 أيام).
## الخطوة 4: تعيين المورد للمهمة
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Explanation: قم بتعيين المورد للمهمة.
## الخطوة 5: تكوين تعيين الموارد
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Explanation: قم بتعيين المعاملات مثل التوقف والاستئناف ومخطط العمل لتعيين المورد.
## الخطوة 6: تعيين خط الأساس
```java
project.setBaseline(BaselineType.Baseline);
```
التفسير: تحديد خط الأساس للمشروع.
## الخطوة 7: تحديث إكمال المهمة
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
شرح: قم بالإشارة إلى نسبة إنجاز المهمة.
## الخطوة 8: استرداد البيانات الموزعة على الوقت
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Explanation: قم باسترجاع البيانات الموزعة على الوقت للعمل المتبقي للمهمة.
## الخطوة 9: عرض البيانات الموزعة على الوقت
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// رمز إضافي لعرض القيم الأخرى
```
شرح: إخراج وعرض البيانات الموزعة على الوقت.
## خاتمة
تعد الإدارة الفعالة لبيانات المهمة الموزعة على الوقت أمرًا لا غنى عنه لنجاح المشروع. يعمل Aspose.Tasks for Java على تبسيط هذه العملية، مما يوفر مجموعة شاملة من الوظائف. باتباع هذا البرنامج التعليمي، يمكنك دمج Aspose.Tasks بسلاسة في مشروع Java الخاص بك، مما يضمن التحكم الدقيق في الجداول الزمنية للمشروع وتخصيص الموارد.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java في أي مشروع Java؟
ج: نعم، Aspose.Tasks for Java متوافق مع أي مشروع قائم على Java.
### س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks لـ Java؟
 ج: قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للدعم والمناقشات.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 ج: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني شراء Aspose.Tasks لـ Java؟
 ج: يمكنك شراء Aspose.Tasks لـ Java[هنا](https://purchase.aspose.com/buy).