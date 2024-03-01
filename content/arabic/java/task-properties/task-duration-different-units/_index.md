---
title: مدة المهمة في وحدات مختلفة باستخدام Aspose.Tasks
linktitle: مدة المهمة في وحدات مختلفة باستخدام Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: استكشف إدارة مدة المهمة في مشاريع Java باستخدام Aspose.Tasks. حساب المدد بدقة وتحويلها بالدقائق والأيام والساعات والأسابيع والأشهر.
type: docs
weight: 32
url: /ar/java/task-properties/task-duration-different-units/
---
## مقدمة
في مجال إدارة المشاريع، يعد فهم وإدارة مدة المهمة جانبًا بالغ الأهمية. يوفر Aspose.Tasks for Java مجموعة أدوات قوية للتعامل مع هذا الأمر بكفاءة. في هذا البرنامج التعليمي، سنرشدك خلال استرداد فترات المهام في وحدات مختلفة باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت مجموعة أدوات تطوير Java (JDK).
-  Aspose.Tasks لمكتبة جافا. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/java/)
- الفهم الأساسي لبرمجة جافا
## حزم الاستيراد
في مشروع Java الخاص بك، قم بتضمين مكتبة Aspose.Tasks. أضف عبارة الاستيراد التالية في بداية الكود الخاص بك:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من تضمين مكتبة Aspose.Tasks في تبعيات مشروعك.
## الخطوة الثانية: اقرأ قالب المشروع
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قراءة ملف قالب مشروع MS
String fileName = dataDir + "project.xml";
// اقرأ ملف الإدخال كـ Project
Project project = new Project(fileName);
```
 تأكد من الاستبدال`"Your Document Directory"` مع المسار الفعلي لملفات المشروع الخاص بك.
## الخطوة 3: استرداد مهمة
```java
// احصل على مهمة لحساب مدتها بتنسيقات مختلفة
Task task = project.getRootTask().getChildren().getById(1);
```
 هنا نحصل على مهمة من المشروع. يُعدِّل`getById(1)` بناءً على معرف مهمة مشروعك.
## الخطوة 4: المدة بالدقائق
```java
// احصل على المدة بالدقائق
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
تحسب هذه الخطوة مدة المهمة بالدقائق.
## الخطوة 5: المدة بالأيام
```java
// احصل على المدة بالأيام
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
تحسب هذه الخطوة مدة المهمة بالأيام.
## الخطوة 6: المدة بالساعات
```java
// احصل على المدة بالساعات
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
تحسب هذه الخطوة مدة المهمة بالساعات.
## الخطوة 7: المدة بالأسابيع
```java
// احصل على المدة بالأسابيع
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
تحسب هذه الخطوة مدة المهمة بالأسابيع.
## الخطوة 8: المدة بالأشهر
```java
// احصل على المدة بالأشهر
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
تحسب هذه الخطوة مدة المهمة بالأشهر.
## خاتمة
أصبحت إدارة فترات المهام أمرًا بسيطًا باستخدام Aspose.Tasks لـ Java. لقد أرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مما يوفر لك الوضوح بشأن وحدات زمنية مختلفة.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java مع أي Java IDE؟
نعم، Aspose.Tasks for Java متوافق مع أي بيئة تطوير متكاملة لـ Java (IDE).
### س: كيف يمكنني الحصول على معرف المهمة في ملف Microsoft Project؟
يمكنك فحص ملف المشروع أو استخدام Aspose.Tasks API لاسترداد معرفات المهام برمجيًا.
### س: هل Aspose.Tasks مناسب للتعامل مع المشاريع واسعة النطاق؟
قطعاً. تم تصميم Aspose.Tasks للتعامل بكفاءة مع المشاريع ذات الأحجام المختلفة.
### س: أين يمكنني العثور على مزيد من الوثائق؟
 قم بزيارة[توثيق](https://reference.aspose.com/tasks/java/)للموارد الشاملة.
### س: هل يمكنني تجربة Aspose.Tasks لـ Java قبل الشراء؟
 نعم، يمكنك استكشاف أ[تجربة مجانية](https://releases.aspose.com/) لتقييم قدراتها.