---
title: إتقان خصائص المهمة في Aspose.Tasks
linktitle: قراءة وكتابة الخصائص العامة للمهام في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: اكتشف قوة Aspose.Tasks لـ Java في إدارة خصائص المهام دون عناء. اقرأ واكتب بسهولة باستخدام دليلنا خطوة بخطوة.
weight: 26
url: /ar/java/task-properties/read-write-general-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان خصائص المهمة في Aspose.Tasks

## مقدمة
أطلق العنان للإمكانات الكاملة لإدارة المهام في Java باستخدام Aspose.Tasks. في هذا الدليل الشامل، سنتعمق في قراءة وكتابة الخصائص العامة للمهام باستخدام Aspose.Tasks for Java. سواء كنت مطورًا متمرسًا أو مبتدئًا، سيزودك هذا البرنامج التعليمي بالمهارات اللازمة للتعامل مع خصائص المهمة دون عناء.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تم تنزيل Aspose.Tasks لمكتبة Java وإعدادها. يمكنك العثور على رابط التحميل[هنا](https://releases.aspose.com/tasks/java/).
- محرر أكواد برمجية مثل IntelliJ IDEA أو Eclipse.
## حزم الاستيراد
لبدء الأمور، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك. تضمن هذه الخطوة أن يكون لديك حق الوصول إلى وظائف Aspose.Tasks. إليك مقتطف لإرشادك:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## قراءة الخصائص العامة للمهام
## الخطوة 1: إنشاء مهمة
ابدأ بإنشاء مهمة في مشروعك. يتضمن ذلك إعداد اسم المهمة وتاريخ البدء والتفاصيل الأخرى ذات الصلة. هنا مثال:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## الخطوة 2: قراءة خصائص المهمة
الآن بعد أن قمت بإنشاء مهمة، فلنسترد ونعرض خصائصها العامة. مقتطف التعليمات البرمجية التالي ينجز هذا:
```java
// قراءة الخصائص العامة للمهام
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## كتابة الخصائص العامة للمهام
## الخطوة 3: تحميل المشروع وإنشاء المجمع
 لكتابة خصائص عامة، قم بتحميل مشروع موجود وقم بإعداد ملف`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## الخطوة 4: تحليل وعرض الخصائص
أخيرًا، قم بتحليل المهام المجمعة وعرض خصائصها:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
تهانينا! لقد نجحت في قراءة وكتابة الخصائص العامة للمهام باستخدام Aspose.Tasks لـ Java.
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا الخطوات الأساسية للتعامل مع خصائص المهمة بسلاسة باستخدام Aspose.Tasks لـ Java. من خلال إتقان هذه التقنيات، يمكنك رفع مهاراتك في تطوير Java وتبسيط إدارة المهام في مشاريعك.
## الأسئلة الشائعة
### هل Aspose.Tasks متوافق مع Java 11؟
نعم، Aspose.Tasks متوافق مع Java 11 والإصدارات الأحدث.
### هل يمكنني استخدام Aspose.Tasks للمشاريع التجارية؟
 قطعاً! Aspose.Tasks هي أداة قوية لكل من المشاريع الشخصية والتجارية. يزور[هنا](https://purchase.aspose.com/buy) لاستكشاف خيارات الترخيص.
### كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟
 الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.
### أين يمكنني العثور على دعم المجتمع لـ Aspose.Tasks؟
 انضم إلى مناقشة المجتمع في[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) للمساعدة والتعاون.
### هل هناك أي مشاريع عينة متاحة للرجوع إليها؟
 استكشف قسم أمثلة الوثائق[هنا](https://reference.aspose.com/tasks/java/) لنماذج المشاريع ومقتطفات التعليمات البرمجية.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
