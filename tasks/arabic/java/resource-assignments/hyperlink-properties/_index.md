---
date: 2026-01-07
description: تعلم كيفية تعيين خصائص الروابط التشعبية لتخصيصات الموارد في Aspose.Tasks
  للغة Java، مما يتيح تحسين التعاون وإمكانية الوصول.
linktitle: Manage Hyperlink Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تعيين خصائص الارتباط التشعبي للتكليفات في Aspose.Tasks
url: /ar/java/resource-assignments/hyperlink-properties/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين خصائص الارتباط التشعبي للتعيينات في Aspose.Tasks

## المقدمة
يقدم Aspose.Tasks for Java ميزات قوية لإدارة مهام المشروع والموارد. في هذا البرنامج التعليمي، سنوضح لك **كيفية تعيين الارتباط التشعبي** للتعيينات الخاصة بالموارد باستخدام Aspose.Tasks for Java. باتباع هذه التعليمات خطوة بخطوة، ستتمكن من التعامل بفعالية مع الارتباطات التشعبية المرتبطة بتعيينات موارد مشروعك.

## إجابات سريعة
- **ماذا يفعل “set hyperlink”؟** يضيف عنوان URL قابل للنقر (وعنوان فرعي اختياري) إلى تعيين المورد.  
- **أي فئة تخزن بيانات الارتباط التشعبي؟** فئة `Asn` توفر الحقول `HYPERLINK`، `HYPERLINK_ADDRESS`، و `HYPERLINK_SUB_ADDRESS`.  
- **هل أحتاج إلى ترخيص لاستخدام هذه الميزة؟** يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام في بيئة الإنتاج؛ نسخة تجريبية مجانية تكفي للاختبار.  
- **هل يمكنني التحقق من صحة الارتباط التشعبي في Java؟** نعم—استخدم التحقق القياسي من URL (مثل `java.net.URL`) قبل تعيينه.  
- **هل هذا النهج متوافق مع أي مشروع Java؟** بالتأكيد؛ يعمل مع أي مشروع Java يتضمن مكتبة Aspose.Tasks.

## ما هو “how to set hyperlink” في Aspose.Tasks؟
يعني تعيين الارتباط التشعبي ربط عنوان URL (وبشكل اختياري عنوان فرعي) بتعيين مورد بحيث يتمكن أصحاب المصلحة في المشروع من الانتقال بسرعة إلى صفحات الويب أو المستندات أو أقسام المشروع الداخلية مباشرةً من عرض التعيين.

## لماذا نضيف ارتباطًا تشعبيًا إلى تعيينات المهام؟
- **تحسين التعاون:** يمكن لأعضاء الفريق النقر على الرابط للوصول إلى المواصفات أو التصاميم أو الموارد الخارجية دون مغادرة ملف المشروع.  
- **مركزية المعلومات:** تُخزن جميع عناوين URL ذات الصلة داخل المشروع، مما يقلل من خطر فقدان أو تقادم المراجع.  
- **تحسين التتبع:** يمكن للارتباطات التشعبية الإشارة إلى طلبات التغيير أو متتبعات المشكلات أو الوثائق، مما يخلق مسار تدقيق واضح.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر المتطلبات التالية:
- معرفة أساسية بلغة برمجة Java.  
- تثبيت مجموعة تطوير Java (JDK).  
- الوصول إلى مكتبة Aspose.Tasks for Java.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
أولاً، تأكد من استيراد الحزم اللازمة لاستخدام وظائف Aspose.Tasks في مشروع Java الخاص بك.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## الخطوة 1: إنشاء كائن Project
ابدأ بإنشاء كائن مشروع جديد باستخدام Aspose.Tasks.

```java
Project prj = new Project();
```

## الخطوة 2: إضافة مهمة إلى المشروع
الآن، أضف مهمة إلى المشروع التي سيتم ربطها بالارتباط التشعبي.

```java
Task task = prj.getRootTask().getChildren().add("Task 1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## الخطوة 3: إضافة مورد
بعد ذلك، أضف موردًا إلى المشروع.

```java
Resource resource = prj.getResources().add("Resource 1");
```

## الخطوة 4: إنشاء تعيين مورد
أنشئ **تعيين مورد** واربطه بالمهمة والموارد.

```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## الخطوة 5: تعيين خصائص الارتباط التشعبي
قم بتعيين خصائص الارتباط التشعبي لتعيين المورد. هنا نقوم **بتعيين عنوان الارتباط التشعبي** و **العنوان الفرعي للارتباط التشعبي** كجزء من عملية “how to set hyperlink”.

```java
assignment.set(Asn.HYPERLINK, "Click to visit our site");
assignment.set(Asn.HYPERLINK_ADDRESS, "https://products.aspose.com");
assignment.set(Asn.HYPERLINK_SUB_ADDRESS, "/total/net");
```

## الخطوة 6: طباعة خصائص الارتباط التشعبي
اطبع خصائص الارتباط التشعبي للتحقق من الإعداد.

```java
System.out.println("Hyperlink: " + assignment.get(Asn.HYPERLINK));
System.out.println("Hyperlink Address: " + assignment.get(Asn.HYPERLINK_ADDRESS));
System.out.println("Hyperlink Sub Address: " + assignment.get(Asn.HYPERLINK_SUB_ADDRESS));
```

## الخطوة 7: إكمال العملية
أخيرًا، اعرض رسالة تشير إلى إكمال العملية بنجاح.

```java
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والحلول
- **تنسيق URL غير صالح:** تحقق من صحة URL باستخدام `java.net.URL` قبل تعيينه لتجنب أخطاء وقت التشغيل.  
- **قيمة الارتباط التشعبي فارغة (null):** تأكد من تعيين جميع الخصائص الثلاث (`HYPERLINK`، `HYPERLINK_ADDRESS`، `HYPERLINK_SUB_ADDRESS`) إذا كنت تحتاجها؛ وإلا، عيّن القيم غير المستخدمة إلى `null` أو سلسلة فارغة.  
- **عدم العثور على الترخيص:** إذا ظهرت أخطاء الترخيص، تحقق من تحميل ملف ترخيص Aspose.Tasks بشكل صحيح قبل إنشاء كائن `Project`.

## الأسئلة المتكررة

**س: هل يمكنني إضافة روابط تشعبية متعددة إلى تعيين مورد واحد؟**  
ج: نعم، يمكنك إضافة روابط تشعبية متعددة بتكرار العملية الموضحة في هذا البرنامج التعليمي لكل رابط، وتعيين قيم مختلفة لـ `HYPERLINK_ADDRESS`.

**س: هل يمكن تخصيص مظهر الروابط التشعبية في Aspose.Tasks؟**  
ج: يركز Aspose.Tasks أساسًا على إدارة بيانات المشروع والخصائص، بما في ذلك الروابط التشعبية. للتخصيص البصري المتقدم، قد تحتاج إلى استخدام مكتبات واجهة مستخدم إضافية.

**س: هل هناك حدود لطول الروابط التشعبية في Aspose.Tasks؟**  
ج: لا يفرض Aspose.Tasks حدودًا صارمة للطول، لكن الحفاظ على URLs مختصرة يحسن القابلية للقراءة.

**س: هل يمكنني إزالة الروابط التشعبية من تعيينات الموارد برمجيًا؟**  
ج: نعم، عيّن خصائص الارتباط التشعبي إلى `null` أو سلسلة فارغة لإزالتها.

**س: هل يدعم Aspose.Tasks التحقق من صحة الروابط التشعبية؟**  
ج: تقوم المكتبة بتخزين بيانات الروابط التشعبية لكنها لا تتحقق من صحة URLs تلقائيًا. يمكنك تنفيذ منطق تحقق مخصص في كود Java إذا لزم الأمر.

**س: كيف يتناسب هذا مع استراتيجية الروابط التشعبية في مشروع Java أكبر؟**  
ج: من خلال مركزية URLs داخل ملف المشروع، تنشئ **خريطة روابط تشعبية لمشروع Java** يمكن الاستعلام عنها برمجيًا، أو تصديرها، أو تدقيقها.

## الخلاصة
في الختام، إدارة خصائص الارتباط التشعبي لتعيينات الموارد في Aspose.Tasks for Java أمر بسيط وفعّال. باتباع الخطوات المذكورة أعلاه، يمكنك بسهولة **إضافة ارتباط تشعبي إلى تعيينات المهام**، **تعيين عنوان الارتباط التشعبي**، وحتى **التحقق من صحة كود الارتباط التشعبي في Java**، مما يعزز التعاون وإتاحة المعلومات عبر فرق مشروعك.

---

** تحديث:** 2026-01-07  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}