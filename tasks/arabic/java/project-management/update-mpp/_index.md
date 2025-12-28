---
date: 2025-12-28
description: تعلم كيفية إضافة مهمة وتحديث ملفات MPP باستخدام Aspose.Tasks for Java،
  مكتبة إدارة المشاريع بلغة جافا. اتبع دليلنا خطوة بخطوة لإنشاء مهمة في ملف MPP وحفظ
  المشروع كملف MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إضافة مهمة وتحديث ملف MPP في Aspose.Tasks
url: /ar/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مهمة وتحديث ملف MPP في Aspose.Tasks

## المقدمة
في هذا الدرس سنوضح لك **كيفية إضافة مهمة** وتحديث ملف MPP باستخدام Aspose.Tasks for Java، وهي مكتبة **إدارة مشاريع جافا** رائدة. سواءً كنت تبني جدولة مخصصة أو تحتاج إلى تعديل خطط المشاريع الموجودة برمجياً، فإن هذا الدليل سيرشدك خلال كل خطوة—من تحميل الملف إلى حفظ التغييرات كمستند MPP جديد.

## إجابات سريعة
- **ماذا يعني “كيفية إضافة مهمة” في هذا السياق؟** يشير إلى إنشاء مهمة جديدة داخل ملف Microsoft Project (MPP) موجود برمجياً.  
- **أي مكتبة تتولى العملية؟** Aspose.Tasks for Java، مكتبة إدارة مشاريع جافا قوية.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يكفي للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني حفظ النتيجة كملف MPP؟** نعم—استخدم `project.save(..., SaveFileFormat.Mpp)` **لحفظ المشروع كملف mpp**.  
- **ما نسخة جافا المطلوبة؟** Java 8 أو أحدث.

## ما معنى “كيفية إضافة مهمة” في ملف MPP؟
إضافة مهمة تعني إدراج عنصر عمل جديد في هيكل المشروع، وتحديد تواريخ البدء/الانتهاء له، ثم حفظ التغيير مرة أخرى في ملف MPP. تقوم Aspose.Tasks بتجريد تفاصيل تنسيق الملف منخفض المستوى، مما يتيح لك التركيز على منطق الأعمال.

## لماذا نستخدم Aspose.Tasks for Java؟
- **توافق كامل** مع ملفات Microsoft Project 2007‑2021.  
- **لا حاجة لتثبيت COM أو Office**—API جافا نقي.  
- **مجموعة ميزات غنية**: ربط المهام، تخصيص الموارد، الحقول المخصصة، وأكثر.  
- **أداء عالي** لملفات المشاريع الكبيرة، مما يجعلها مثالية للأتمتة على الخادم.

## المتطلبات المسبقة
1. **بيئة تطوير جافا** – JDK 8+ مثبتة ومُعَدة.  
2. **Aspose.Tasks for Java** – حمّلها من [صفحة التحميل](https://releases.aspose.com/tasks/java/).  
3. **معرفة أساسية بجافا** – الإلمام بالصفوف، الكائنات، ومعالجة التواريخ.  

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. يتيح لك ذلك الوصول إلى تعديل المشروع، خصائص المهمة، ومعالجة التواريخ.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## الخطوة 1: تعريف دليل البيانات
```java
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمسار المطلق حيث يقع ملف MPP المصدر الخاص بك.

## الخطوة 2: قراءة المشروع الموجود
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
يقوم مُنشئ `Project` بتحميل **SampleMSP2010.mpp**، مما يمنحك نموذج كائن قابل للتعديل.

## الخطوة 3: إنشاء مهمة جديدة (كيفية إضافة مهمة)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
هذا السطر **ينشئ مهمة في mpp** بإضافة فرع باسم *Task1* إلى المهمة الجذرية.

## الخطوة 4: تعيين تواريخ البدء والانتهاء
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
هنا نحدد الجدول الزمني للمهمة التي أُضيفت حديثاً. عدّل التواريخ لتتناسب مع مخطط مشروعك.

## الخطوة 5: حفظ المشروع (حفظ المشروع كملف mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
يتم حفظ المشروع المحدث، الذي يحتوي الآن على المهمة الجديدة، كملف **AfterLinking.mpp**.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **الملف غير موجود** | تحقق من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\\`) وأن اسم الملف صحيح. |
| **تواريخ غير صحيحة** | تذكر أن شهور `Calendar` تبدأ من الصفر؛ `Calendar.JULY` هو الصحيح لشهر يوليو. |
| **استثناء الترخيص** | قم بتثبيت ترخيص Aspose.Tasks صالح قبل استدعاء أي API لتجنب علامات التقييم. |

## الأسئلة المتكررة
### س: هل يمكن لـ Aspose.Tasks for Java التعامل مع هياكل مشاريع معقدة؟
ج: نعم، توفر Aspose.Tasks for Java ميزات قوية للتعامل مع هياكل مشاريع معقدة بكفاءة.  
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [الموقع الإلكتروني](https://releases.aspose.com/).  
### س: هل يدعم Aspose.Tasks for Java إصدارات مختلفة من ملفات Microsoft Project؟
ج: بالتأكيد، يدعم Aspose.Tasks for Java إصدارات متعددة من ملفات Microsoft Project، بما في ذلك صيغ MPP و MPT و XML.  
### س: هل يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Tasks for Java؟
ج: نعم، تتوفر تراخيص مؤقتة لأغراض الاختبار. يمكنك الحصول عليها من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).  
### س: أين يمكنني طلب المساعدة أو الدعم بخصوص Aspose.Tasks for Java؟
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) لأي مساعدة أو استفسارات.

## أسئلة شائعة أخرى
**س: كيف يمكنني إضافة عدة مهام مرة واحدة؟**  
ج: كرّر حلقة على مجموعة من أسماء المهام وكرر كتلة “إنشاء مهمة” داخل الحلقة.

**س: هل يمكنني تعيين حقول مخصصة للمهمة الجديدة؟**  
ج: نعم—استخدم `task.set(Tsk.CUSTOM_FIELD_x, value)` حيث *x* هو رقم الحقل.

**س: هل يمكن نسخ مهمة موجودة كقالب؟**  
ج: استنسخ المهمة المصدر (`Task cloned = sourceTask.clone();`) ثم أضفها إلى الوالد المطلوب.

**س: ماذا لو احتجت لتحديث مهمة موجودة بدلاً من إضافة جديدة؟**  
ج: استرجع المهمة بالمعرف (`Task existing = project.getRootTask().getChildren().getById(id);`) وعدل خصائصها.

**س: هل يدعم Aspose.Tasks الحفظ إلى صيغ أخرى مثل PDF أو PNG؟**  
ج: نعم—استخدم `project.save("output.pdf", SaveFileFormat.Pdf);` أو `SaveFileFormat.Png` للحصول على تمثيلات بصرية.

---

**آخر تحديث:** 2025-12-28  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}