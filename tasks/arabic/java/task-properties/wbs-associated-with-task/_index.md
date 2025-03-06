---
title: WBS المرتبطة بالمهمة في Aspose.Tasks
linktitle: WBS المرتبطة بالمهمة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: إتقان WBS باستخدام Aspose.Tasks لـ Java - تعلم كيفية قراءة رموز WBS للمهام وإعادة ترقيمها. تعزيز كفاءة إدارة المشروع!
weight: 36
url: /ar/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS المرتبطة بالمهمة في Aspose.Tasks

## مقدمة
مرحبًا بك في عالم إدارة المشاريع باستخدام Aspose.Tasks لـ Java! في هذا البرنامج التعليمي، سنتعمق في تعقيدات هيكل تنظيم العمل (WBS) المرتبط بالمهام باستخدام Aspose.Tasks لـ Java. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيساعدك هذا الدليل على التنقل عبر أساسيات إدارة رموز WBS بكفاءة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  تم تنزيل Aspose.Tasks لمكتبة Java وإضافتها إلى مشروعك. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
تأكد من استيراد الحزم اللازمة لبدء مشروعك:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## قراءة رموز WBS
لنبدأ بقراءة رموز WBS المرتبطة بالمهام. اتبع الخطوات التالية:
## الخطوة 1: تحميل المشروع
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## الخطوة 2: جمع المهام
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## الخطوة 3: التحليل والتخصيص
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
يقوم هذا المقتطف بقراءة وتخصيص رموز WBS المرتبطة بالمهام في مشروعك.
## إعادة ترقيم رموز WBS للمهمة
الآن، دعنا نستكشف إعادة ترقيم رموز WBS للمهام:
## الخطوة 1: تحميل المشروع
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## الخطوة 2: حدد كافة المهام
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## الخطوة 3: إخراج رموز WBS الأولية
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## الخطوة 4: إعادة ترقيم رموز WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## الخطوة 5: إخراج رموز WBS المحدثة
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
باتباع هذه الخطوات، يمكنك إعادة ترقيم رموز WBS للمهام الموجودة في مشروعك بشكل فعال.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية العمل مع رموز WBS باستخدام Aspose.Tasks لـ Java. ستمكنك هذه المعرفة من إدارة وتخصيص التسلسل الهرمي لمهام مشروعك بكفاءة.
## الأسئلة الشائعة
### س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Tasks لـ Java؟
 ج: الوثائق متاحة[هنا](https://reference.aspose.com/tasks/java/).
### س: كيف يمكنني تنزيل Aspose.Tasks لـ Java؟
 ج: يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/java/).
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks لـ Java؟
 ج: قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للدعم.
### س: هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 ج: نعم، احصل على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
