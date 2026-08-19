---
date: 2026-02-26
description: تعلم كيفية تقسيم تواريخ انتهاء المهام وإدارة جداول المشروع باستخدام Aspose.Tasks
  للغة Java. يوضح هذا الدليل كيفية تقسيم المهمة بكفاءة.
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إدارة جداول المشروع – تاريخ انتهاء المهمة المقسمة في Aspose.Tasks
url: /ar/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تقسيم تاريخ الانتهاء للمهمة في Aspose.Tasks

## المقدمة
إدارة **manage project timelines** بفعالية هي حجر الأساس لتسليم المشروع بنجاح. عندما يتغير مدة المهمة، يجب إعادة حساب تاريخ الانتهاء للحفاظ على دقة الجدول. في هذا الدرس سنوضح لك **how to split task** تواريخ الانتهاء باستخدام Aspose.Tasks for Java، مما يمنحك تحكمًا دقيقًا في جدول مشروعك.

## إجابات سريعة
- **What does splitting a task finish date achieve?** يتيح لك حساب تاريخ الانتهاء لأي مدة معينة، مما يساعدك على تعديل الجداول بسرعة.  
- **Which library is required?** Aspose.Tasks for Java (downloadable from the official site).  
- **Do I need a license for development?** ترخيص مؤقت يعمل للاختبار؛ ترخيص كامل مطلوب للإنتاج.  
- **Can I use this with any project calendar?** نعم، الـ API يستخدم تقويم المشروع لتطبيق أيام العمل والعطلات.  
- **How many lines of code are needed?** أقل من عشر أسطر للحصول على تاريخ الانتهاء لأي مدة.

## ما هو “manage project timelines” في سياق Aspose.Tasks؟
إدارة جداول المشروع تعني الحفاظ على تواريخ بدء وانتهاء كل مهمة متزامنة مع الجدول العام، مع مراعاة التقويمات والموارد واعتمادات المهام. حساب تواريخ الانتهاء بدقة أمر أساسي لتوقعات واقعية وثقة أصحاب المصلحة.

## لماذا تقسيم تاريخ انتهاء المهمة؟
- **Flexibility:** شاهد بسرعة كيف تؤثر تخصيصات ساعات العمل المختلفة على التسليم.  
- **Risk assessment:** قيم سيناريوهات “ماذا لو” دون تعديل الخطة الأصلية.  
- **Resource planning:** توافق مدد المهام مع قدرة الفريق وقيود التقويم.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:
- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Tasks for Java مثبتة. يمكنك تنزيلها [هنا](https://releases.aspose.com/tasks/java/).  
- إعداد بيئة تطوير Java.

## استيراد الحزم
ابدأ بإضافة الحزم اللازمة إلى مشروع Java الخاص بك:
```java
import com.aspose.tasks.*;
```

## الخطوة 1: العثور على مهمة مقسمة
حدد المهمة التي تريد تقسيمها داخل المشروع:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## الخطوة 2: العثور على تقويم المشروع
استرجع تقويم المشروع لحساب التواريخ بدقة:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## الخطوة 3: حساب تاريخ انتهاء المهمة بمدد مختلفة
الآن، احسب تاريخ انتهاء المهمة لمدد مختلفة.

### الخطوة 3.1: مدة 8 ساعات
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*كرر الكود أعلاه لمدد مختلفة، مع تعديل الساعات وفقًا لذلك، لرؤية كيف يؤثر كل تغيير على تاريخ الانتهاء.*

## المشكلات الشائعة والحلول
- **Incorrect calendar reference:** تأكد من استرجاع تقويم المشروع (`project.get(Prj.CALENDAR)`) بدلاً من إنشاء تقويم جديد.  
- **Wrong task UID:** يجب أن يتطابق الـ UID مع مهمة موجودة فعليًا؛ وإلا سيعيد `getByUid` قيمة `null` ويتسبب في `NullPointerException`.  
- **Time zone mismatches:** الـ API يعمل مع المنطقة الزمنية للتقويم؛ تحقق من المنطقة الافتراضية لنظامك إذا بدت النتائج غير صحيحة.

## الخاتمة
إتقان فن **managing project timelines** عبر تقسيم تواريخ انتهاء المهام أمر حاسم لإدارة مشروع فعّالة. Aspose.Tasks for Java يبسط هذه العملية، مما يتيح لك تنظيم جداولك بسهولة.

## الأسئلة المتكررة
### س1: كيف يمكنني تنزيل Aspose.Tasks for Java؟
A1: يمكنك تنزيله [هنا](https://releases.aspose.com/tasks/java/).

### س2: أين يمكنني العثور على وثائق Aspose.Tasks؟
A2: راجع الوثائق [هنا](https://reference.aspose.com/tasks/java/).

### س3: كيف أحصل على ترخيص مؤقت لـ Aspose.Tasks؟
A3: احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س4: أين يمكنني طلب الدعم لـ Aspose.Tasks؟
A4: زر منتدى الدعم [هنا](https://forum.aspose.com/c/tasks/15).

### س5: هل يمكنني شراء Aspose.Tasks؟
A5: نعم، يمكنك شرائه [هنا](https://purchase.aspose.com/buy).

## أسئلة إضافية متكررة

**س: هل يمكنني استخدام هذه التقنية مع تقويم مخصص؟**  
ج: بالتأكيد. استبدل `project.get(Prj.CALENDAR)` بمثيل `Calendar` المخصص الخاص بك.

**س: هل الطريقة تأخذ أيام غير العمل في الاعتبار؟**  
ج: نعم، يتم تطبيق تعريفات أوقات العمل في التقويم عند حساب تاريخ الانتهاء.

**س: هل هناك طريقة لاسترجاع تاريخ الانتهاء لساعات جزئية (مثلاً 3.5 ساعات)؟**  
ج: مرّر قيمة `double` مثل `3.5d` إلى `getTaskFinishDateFromDuration`؛ الـ API يتعامل مع مدد جزئية.

**س: كيف أقوم بتنسيق تاريخ الإخراج؟**  
ج: استخدم `java.time.format.DateTimeFormatter` على كائن `Date` المسترجع لعرضه بالتنسيق المفضل لديك.

---

**آخر تحديث:** 2026-02-26  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}