---
date: 2026-02-28
description: تعلم كيفية استخدام Aspose.Tasks للـ Java لإدارة بيانات المهام الزمنية،
  حمّل المكتبة، جرّبها مجانًا، وسهّل تتبع المشروع.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية استخدام Aspose.Tasks لإدارة بيانات المهام المتدرجة زمنياً (Java)
url: /ar/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام Aspose.Tasks لبيانات المهام الزمنية المرحلية

## Introduction
إذا كنت تبحث عن **كيفية استخدام Aspose** للسيطرة القوية على جدول مشروعك، فأنت في المكان الصحيح. إن تتبع بيانات المهام الزمنية المرحلية بدقة هو حجر الزاوية لإدارة المشاريع الناجحة، وتوفر لك Aspose.Tasks for Java الأدوات اللازمة لأتمتة هذه العملية. في هذا البرنامج التعليمي سنستعرض مثالًا كاملاً من البداية إلى النهاية يوضح لك كيفية استخدام Aspose.Tasks لإنشاء مشروع، وتعيين الموارد، وتحديد الخطوط الأساسية، وأخيرًا استرجاع وعرض البيانات الزمنية المرحلية.

## Quick Answers
- **ما معنى “البيانات الزمنية المرحلية”?** هي بيانات مقسمة حسب فترات زمنية (أيام، أسابيع، شهور) تُظهر العمل أو التكلفة أو العمل المتبقي على مدار جدول المشروع.  
- **أي مكتبة توفر هذه القدرة؟** Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص للإنتاج.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى.  
- **هل يمكنني تصدير النتائج إلى Excel؟** نعم – يمكنك تكرار مجموعة `TimephasedData` وكتابة القيم إلى أي تنسيق تحتاجه.

## What is Task Timephased Data?
تمثل بيانات المهام الزمنية المرحلية مقدار العمل (أو التكلفة) المجدول لمهمة خلال كل شريحة زمنية من تقويم المشروع. تمكنك من رؤية كيفية توزيع العمل، واكتشاف الإفراط في التخصيص، ومقارنة التقدم المخطط به مقابل الفعلي.

## Why Use Aspose.Tasks to Manage Timephased Data?
- **تحكم كامل** – إنشاء وتعديل واستعلام المعلومات الزمنية المرحلية برمجياً دون الحاجة لفتح Microsoft Project.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **بدون تبعيات COM** – مثالي لأتمتة الخادم.  
- **API غني** – يدعم الخطوط الأساسية، وتوزيعات العمل، والحقول المخصصة مباشرةً.

## Prerequisites
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

- **بيئة تطوير Java** – تثبيت JDK 8+ وتكوين `JAVA_HOME`.  
- **مكتبة Aspose.Tasks for Java** – قم بتحميل وإدراج مكتبة Aspose.Tasks في مشروعك. يمكنك العثور على المكتبة [هنا](https://releases.aspose.com/tasks/java/).  
- **دليل المستندات** – مجلد على جهازك حيث سيتم قراءة ملف المشروع العيني (`project.xml`) وكتابته.

## Import Packages
في مشروع Java الخاص بك، استورد الفئات الضرورية من Aspose.Tasks:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*شرح:* نقوم بإنشاء كائن `Project`، ونُهيئ `Calendar` إلى تاريخ البدء المطلوب، ثم نُعيّنها إلى خاصية المشروع `START_DATE`.

## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*شرح:* يتم إضافة مهمة جديدة باسم **Task** تحت المهمة الجذرية. كما نقوم بإنشاء مورد يُدعى **Rsc** وتعيين معدلاته القياسية ومعدلات العمل الإضافي.

## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*شرح:* تم جدولة المهمة لمدة **6 أيام**.

## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*شرح:* يتم ربط المورد المُعرّف مسبقًا بالمهمة عبر `ResourceAssignment`.

## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*شرح:* نحدد تواريخ الإيقاف والاستئناف للتعيين (باستخدام قيمة نائب) ونطبق توزيع عمل **Back‑Loaded**، الذي يركز المزيد من العمل نحو نهاية التعيين.

## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*شرح:* التقاط خط أساسي يتيح لك مقارنة القيم المخططة مقابل الفعلية لاحقًا.

## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*شرح:* تم وضع علامة على المهمة بأنها **مكتملة بنسبة 50 %**، مما سيؤثر على حسابات العمل المتبقي.

## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*شرح:* هذه الاستدعاء يجلب **العمل المتبقي** للتعيين، مقسماً حسب فترات زمنية المشروع.

## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*شرح:* نقوم ببساطة بطباعة عدد الإدخالات الزمنية والقيمة للإدخال الأول. في سيناريو واقعي، ستقوم بتكرار القائمة وتصدير البيانات إلى تقرير أو واجهة مستخدم.

## Common Issues and Solutions
- **NullPointerException عند `getTimephasedData`** – تأكد من ضبط تواريخ `START` و `FINISH` للتعيين قبل استدعاء الطريقة.  
- **توزيع عمل غير صحيح** – تحقق من أن `WorkContourType` المختار يتطابق مع استراتيجية الجدولة الخاصة بك؛ `BackLoaded` هو أحد الخيارات المتعددة.  
- **الخط الأساسي لا يعكس التغييرات** – تذكر استدعاء `project.setBaseline` *بعد* تعريف المهام والموارد والتعيينات.

## Frequently Asked Questions
### س: هل يمكنني استخدام Aspose.Tasks for Java في أي مشروع Java؟
A: نعم، Aspose.Tasks for Java متوافق مع أي مشروع مبني على Java.

### س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks for Java؟
A: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على الدعم والنقاشات.

### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟
A: نعم، يمكنك تجربة النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟
A: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### س: أين يمكنني شراء Aspose.Tasks for Java؟
A: يمكنك شراء Aspose.Tasks for Java [هنا](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-02-28  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}