---
title: إدارة المهام الحرجة والموجهة بالجهد في Aspose.Tasks
linktitle: إدارة المهام الحرجة والموجهة بالجهد في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: قم بإدارة المهام الحرجة والموجهة نحو الجهد بسهولة في مشاريع Java الخاصة بك باستخدام Aspose.Tasks. قم بتنزيل المكتبة وعزز قدرات إدارة مشروعك.
weight: 14
url: /ar/java/task-properties/critical-effort-driven-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة المهام الحرجة والموجهة بالجهد في Aspose.Tasks

في عالم إدارة المشاريع سريع الخطى، يعد التعامل بكفاءة مع المهام الحرجة والموجهة بالجهد أمرًا ضروريًا لإنجاز المشروع بنجاح. يوفر Aspose.Tasks for Java حلاً قويًا لإدارة هذه المهام بسلاسة. في هذا البرنامج التعليمي، سنرشدك خلال عملية استخدام Aspose.Tasks لـ Java للتعامل مع المهام الحرجة والمبنية على الجهد في مشاريعك.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Tasks لمكتبة Java: قم بتنزيل المكتبة وتثبيتها من ملف[Aspose.Tasks لوثائق جافا](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
- بيئة التطوير المتكاملة (IDE): استخدم IDE المفضل لديك لتطوير Java.
- ملف المشروع: قم بإعداد ملف المشروع بتنسيق XML الذي ستستخدمه للعرض التوضيحي.
## حزم الاستيراد
في مشروع Java الخاص بك، قم باستيراد الحزم اللازمة للاستفادة من وظائف Aspose.Tasks لـ Java:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```
الآن، دعونا نقسم كل خطوة إلى دليل شامل:
## الخطوة 1: جمع المهام باستخدام ChildTaskCollector
 إنشاء`ChildTasksCollector` مثيل لجمع كافة المهام من المهمة الجذرية باستخدام`TaskUtils.apply`. وهذا يضمن لك الوصول إلى جميع المهام داخل المشروع.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// قم بإنشاء مثيل ChildTasksCollector
ChildTasksCollector collector = new ChildTasksCollector();
// اجمع كل المهام من RootTask باستخدام TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## الخطوة 2: التكرار من خلال المهام المجمعة
 تحليل جميع المهام التي تم جمعها باستخدام`for` حلقة. بالنسبة لكل مهمة، حدد ما إذا كانت تعتمد على الجهد والأهمية، ثم قم بطباعة الحالة المعنية.
```java
// تحليل جميع المهام التي تم جمعها
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
باتباع هذه الخطوات، يمكنك إدارة المهام المهمة والمعتمدة على الجهد بشكل فعال في مشاريعك باستخدام Aspose.Tasks for Java.
## خاتمة
في الختام، يعمل Aspose.Tasks for Java على تمكين مطوري Java من إدارة المهام الحرجة والموجهة نحو الجهد بكفاءة في إدارة المشاريع. بفضل ميزاته سهلة الاستخدام ووظائفه القوية، يصبح التعامل مع سيناريوهات المشروع المعقدة أمرًا سهلاً.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java في بيئات Windows وLinux؟
نعم، Aspose.Tasks for Java مستقل عن النظام الأساسي ويمكن استخدامه في بيئات Windows وLinux.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Tasks لـ Java[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks لـ Java؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع والمناقشات.
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني شراء Aspose.Tasks لـ Java؟
 يمكنك شراء Aspose.Tasks لـ Java من[صفحة الشراء](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
