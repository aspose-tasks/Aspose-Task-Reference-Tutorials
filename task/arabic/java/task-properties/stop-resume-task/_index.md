---
title: إيقاف واستئناف المهمة في Aspose.Tasks
linktitle: إيقاف واستئناف المهمة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: اكتشف قوة Aspose.Tasks لـ Java من خلال دليلنا المفصّل خطوة بخطوة حول إيقاف المهام واستئنافها. تعزيز إدارة المشروع بسلاسة!
type: docs
weight: 30
url: /ar/java/task-properties/stop-resume-task/
---
## مقدمة
في مجال تطوير Java، تعد إدارة المهام بكفاءة جانبًا حاسمًا في تنفيذ المشروع. يوفر Aspose.Tasks for Java حلاً قويًا للتعامل مع المهام بميزاته القوية. في هذا البرنامج التعليمي، سوف نتعمق في وظيفة واحدة محددة - إيقاف المهام واستئنافها. باتباع هذا الدليل التفصيلي، ستتمكن من دمج هذه الميزة بسلاسة في مشاريع Java الخاصة بك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي لبرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل Aspose.Tasks لمكتبة Java وإضافتها إلى مشروعك. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
لبدء العملية، تأكد من استيراد الحزم الضرورية إلى مشروع Java الخاص بك:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## الخطوة 1: التهيئة
 ابدأ بتهيئة مشروعك وإنشاء ملف`ChildTasksCollector` المثال لجمع كافة المهام.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## الخطوة 2: تعيين الحد الأدنى للتاريخ
حدد الحد الأدنى للتاريخ لتصفية المهام التي تحتاج إلى إيقافها أو استئنافها.
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## الخطوة 3: إيقاف واستئناف المهام
قم بالتكرار خلال المهام، والتحقق من تواريخ التوقف والاستئناف وطباعتها.
```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```
كرر هذه الخطوات في مشروع Java الخاص بك لدمج وظائف الإيقاف والاستئناف بسلاسة باستخدام Aspose.Tasks for Java.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية إيقاف المهام واستئنافها باستخدام Aspose.Tasks لـ Java. باتباع الخطوات الموضحة أعلاه، يمكنك تحسين قدرات إدارة المشروع لديك وتبسيط تنفيذ المهام.
## أسئلة مكررة
### هل Aspose.Tasks for Java مناسب للمشاريع واسعة النطاق؟
قطعاً! تم تصميم Aspose.Tasks for Java للتعامل مع المشاريع ذات الأحجام المختلفة، مما يضمن الكفاءة والموثوقية.
### هل يمكنني تخصيص تاريخ إيقاف المهام واستئنافها؟
نعم، يتيح المثال المقدم المرونة في تحديد الحد الأدنى للتاريخ وفقًا لمتطلبات مشروعك.
### أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks لـ Java؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع والمناقشات.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks لـ Java؟
 نعم يمكنك الوصول إلى[تجربة مجانية](https://releases.aspose.com/) لاستكشاف الميزات قبل إجراء عملية الشراء.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) لأغراض تجريبية.