---
date: 2026-01-25
description: تعلم كيفية استخدام Aspose Tasks Java لإدارة المهام في جافا، ومعالجة المهام
  الحرجة والمهام المدفوعة بالجهد في مشاريعك. حسّن سير عمل المشروع باستخدام هذا الدليل.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – إدارة المهام الحرجة والمهام المدفوعة بالجهد
url: /ar/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java: إدارة المهام الحرجة والمهام المدفوعة بالجهد

في إدارة المشاريع الحديثة، يمنحك **aspose tasks java** القدرة على تحديد والتحكم في المهام الحرجة والمهام المدفوعة بالجهد مباشرةً من خلال شفرة Java الخاصة بك. سواء كنت تبني أداة جدولة، أو أداة تقارير، أو لوحة تحكم مخصصة، فإن التعامل الصحيح مع خصائص هذه المهام يمكن أن يكون الفارق بين مشروع يبقى على المسار الصحيح وآخر يخرج عن السيطرة. في هذا الدرس سنستعرض كل ما تحتاج معرفته للعمل مع المهام الحرجة والمهام المدفوعة بالجهد باستخدام Aspose Tasks Java.

## إجابات سريعة
- **ما معنى “critical”؟** مهمة إذا تأخرت ستمدد تاريخ انتهاء المشروع.  
- **ما هو “effort‑driven”؟** مهمة تقوم تلقائيًا بتعديل مدتها عندما تغير مقدار الجهد العملي.  
- **أي مكتبة توفر هذه الميزات؟** Aspose Tasks Java.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.  
- **هل يمكن تشغيله على أي نظام تشغيل؟** نعم – المكتبة مستقلة عن النظام (Windows، Linux، macOS).

## ما هي المهام الحرجة والمهام المدفوعة بالجهد؟
المهام الحرجة هي تلك الموجودة على المسار الحرج للمشروع؛ أي تأخير يؤثر مباشرةً على الجدول الزمني العام. أما المهام المدفوعة بالجهد، فتعيد حساب مدتها بناءً على كمية العمل المخصصة، مما يجعلها مثالية للموارد التي يمكنها العمل لساعات إضافية أو مشاركة الجهد عبر تعيينات متعددة.

## لماذا نستخدم Aspose Tasks Java لهذا؟
- **واجهة برمجة تطبيقات Full .NET‑style في Java** – لا حاجة لتغيير اللغة.  
- **أداء عالي** – يعمل مع ملفات مشروع XML الكبيرة دون الحاجة لتحميل الملف بالكاملمجموعة خصائص غنية** – إمكانية الوصول إلى `IS_CRITICAL`، `IS_EFFORT_DRIVEN`، والعديد من سمات المهمة الأخرى.  
- **متعدد المنصات** – تشغيل على أي بيئة متوافقة مع JVM.

## المتطلبات المسبقة
- مكتبة Aspose.Tasks for Java: قم بتحميل وتثبيت المكتبة من [توثيق Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).
- مجموعة تطوير جافا (JDK): تأكد من تثبيت Java على نظامك.
- بيئة تطوير متكاملة (IDE): استخدم بيئة التطوير التي تفضلها لتطوير Java.
- ملف المشروع: جهّز ملف مشروع بصيغة XML لاستخدامه في العرض.

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم اللازمة للاستفادة من وظائف Aspose.Tasks for Java:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### الخطوة 1: جمع المهام باستخدام `ChildTasksCollector`
أنشئ كائن `ChildTasksCollector` لجمع جميع المهام من المهمة الجذرية باستخدام `TaskUtils.apply`. يضمن ذلك حصولك على إمكانية الوصول إلى كل مهمة داخل المشروع.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### الخطوة 2: التكرار عبر المهام المجمعة
استعرض جميع المهام المجمعة باستخدام حلقة `for`. لكل مهمة، حدد ما إذا كانت مدفوعة بالجهد وحرجة، ثم اطبع الحالة المناسبة.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

باتباع هذهaspose tasks java**| المشكلة | موجود | مسار `dataDir` غير صحيح أو امتداد الملف مفق(dataDir, "قييم، مما يحد من الميزات. | حمّل ملف الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` قبل إنشاء كائن `Project`. |

## الأسئلة المتكررة
### س: هل يمكنني استخدام Aspose.Tasks for Java في بيئات Windows و Linux؟
ج: نعم، Aspose.Tasks for Java مستقلة عن المنصة ويمكن استخدامها في كل من بيئات Windows و Linux.

### س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Tasks for Java؟
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks for Java [هنا](https://releases.aspose.com/).

### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks for Java؟
ج: قم بزيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على دعم المجتمع والنقاشات.

### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟
ج: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س: أين يمكنني شراء Aspose.Tasks for Java؟
ج: يمكنك شراء Aspose.Tasks for Java من [صفحة الشراء](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-01-25  
**تم الاختبار مع:** Aspose.Tasks Java 24.11 (أحدث نسخة عند كتابة هذا المقال)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}