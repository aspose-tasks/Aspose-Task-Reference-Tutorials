---
title: النسبة المئوية للحسابات الكاملة للمهام في Aspose.Tasks
linktitle: النسبة المئوية للحسابات الكاملة للمهام في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: استكشف Aspose.Tasks لـ Java وقم بتبسيط تتبع تقدم المشروع. قم بحساب النسب المئوية للمهام بسهولة لإدارة المشروعات بكفاءة.
type: docs
weight: 25
url: /ar/java/task-properties/percentage-complete-calculations/
---
## مقدمة
مرحبًا بك في دليلنا المتعمق حول إتقان حسابات النسبة المئوية للمهام باستخدام Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة Java قوية مصممة للعمل مع ملفات Microsoft Project، وتقدم مجموعة قوية من الميزات لإدارة المشاريع. في هذا البرنامج التعليمي، سوف نركز على حسابات النسبة المئوية للإكتمال، مما يوفر لك المعرفة اللازمة لمراقبة وتحليل تقدم المشروع بشكل فعال.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
- بيئة تطوير Java: تأكد من تثبيت Java على نظامك.
-  مكتبة Aspose.Tasks: قم بتنزيل مكتبة Aspose.Tasks لـ Java من[هذا الرابط](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
لنبدأ باستيراد الحزم اللازمة لمشروع Aspose.Tasks for Java الخاص بك. قم بتضمين مقتطف الكود التالي في مشروعك:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
الآن، دعونا نقسم كل خطوة مع شرح مفصل.
## الخطوة 1: استيراد الحزم
في الخطوة الأولى، نقوم باستيراد الحزم اللازمة لإعداد مشروع Aspose.Tasks الخاص بنا.
## الخطوة 2: إعداد دليل المستندات
 حدد المسار إلى دليل المستندات الخاص بك باستخدام ملف`dataDir`عامل. تأكد من وجود ملف Microsoft Project، مثل "Software Development.mpp"، في هذا الدليل.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
```
## الخطوة 3: تحميل المشروع
 تهيئة جديدة`Project` الكائن وقم بتحميل ملف Microsoft Project الخاص بك إلى مثيل المشروع.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## الخطوة 4: استرداد مجموعة المهام
 احصل على المهمة الجذرية للمشروع واسترجاع أبنائها كمجموعة باستخدام`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## الخطوة 5: اكتمال نسبة الطباعة
قم بمراجعة كل مهمة في المجموعة وطباعة النسبة المئوية للإكمال، والنسبة المئوية لاكتمال العمل، والنسبة المئوية الفعلية للإكمال.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
كرر هذه الخطوات لكل مهمة في مشروعك للحصول على معلومات حول التقدم المحرز في كل مهمة.
## خاتمة
تهانينا! لقد أتقنت بنجاح حسابات النسبة المئوية للمهام باستخدام Aspose.Tasks لـ Java. تعمل هذه المكتبة القوية على تمكين المطورين من إدارة وتحليل التقدم المحرز في المشروع بكفاءة.
## الأسئلة الشائعة
### س: أين يمكنني العثور على وثائق Aspose.Tasks؟
 الوثائق متاحة[هنا](https://reference.aspose.com/tasks/java/).
### س: كيف يمكنني تنزيل مكتبة Aspose.Tasks لـ Java؟
 يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/java/).
### س: هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 قم بزيارة منتدى الدعم[هنا](https://forum.aspose.com/c/tasks/15).
### س: كيف يمكنني الحصول على ترخيص مؤقت؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).