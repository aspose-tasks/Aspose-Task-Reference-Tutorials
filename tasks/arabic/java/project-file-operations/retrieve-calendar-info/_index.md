---
date: 2025-12-20
description: تعلم كيفية استخدام Aspose.Tasks لاستخراج تفاصيل تقويم المشروع من ملفات
  Microsoft Project باستخدام Java. دليل خطوة بخطوة مع أمثلة على الشيفرة.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية استخدام Aspose.Tasks لاسترجاع معلومات تقويم MS Project
url: /ar/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخدام Aspose.Tasks لاسترجاع معلومات تقويم MS Project

## المقدمة
في هذا البرنامج التعليمي، **ستكتشف كيفية استخدام Aspose.Tasks** لاسترجاع معلومات التقويم برمجيًا من ملفات Microsoft Project. الوصول إلى بيانات التقويم مثل أيام العمل والساعات والاستثناءات أمر أساسي عندما تحتاج إلى **استخراج تقويم المشروع** للتقارير أو التكامل أو منطق الجدولة المخصص. دعنا نتبع العملية خطوة بخطوة.

## إجابات سريعة
- **ما المكتبة التي يستخدمها هذا البرنامج التعليمي؟** Aspose.Tasks for Java.  
- **ما الكلمة المفتاحية الأساسية التي تم تغطيتها؟** *how to use aspose.tasks*.  
- **ماذا يمكنك استخراج؟** تقاويم المشروع، بما في ذلك أيام العمل والساعات.  
- **هل أحتاج إلى ترخيص؟** تتوفر نسخة تجريبية مجانية؛ يلزم وجود ترخيص للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.

## لماذا استخراج معلومات تقويم المشروع؟
تحدد تقاويم المشروع تواريخ المهام وتخصيص الموارد وحسابات الجدول الزمني الكلية. من خلال استخراج هذه البيانات يمكنك:
- إنشاء تقارير مخصصة تعكس جداول العمل الفعلية.  
- مزامنة جداول Microsoft Project مع الأنظمة الخارجية (ERP، BI، إلخ).  
- إجراء تحليل ماذا‑لو عن طريق تعديل إعدادات التقويم برمجيًا.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أنك تمتلك:

- معرفة أساسية ببرمجة Java.  
- مجموعة تطوير Java (JDK) مثبتة على نظامك.  
- مكتبة Aspose.Tasks for Java. يمكنك تنزيلها من [here](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، استورد الفئات اللازمة من Aspose.Tasks إلى مشروع Java الخاص بك.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## الخطوة 1: تعيين دليل البيانات
حدد المجلد الذي يحتوي على ملف *.mpp* الخاص بك.

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق للمجلد الذي يحتوي على **project.mpp**.

## الخطوة 2: تعريف وحدات الوقت
أنشئ ثوابت تساعد على تحويل تمثيل الوقت الداخلي إلى ساعات قابلة للقراءة البشرية.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

هذه القيم معبر عنها بالميكروثانية، وهي الطريقة التي يخزن بها Aspose.Tasks الوقت داخليًا.

## الخطوة 3: إنشاء كائن المشروع
حمّل ملف Microsoft Project إلى كائن `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

يقوم مُنشئ `Project` بتحليل ملف *.mpp* ويجعل جميع بيانات المشروع، بما في ذلك التقويمات، متاحة عبر API.

## الخطوة 4: استرجاع معلومات التقويمات
احصل على مجموعة التقويمات المعرفة في المشروع.

```java
CalendarCollection alCals = project.getCalendars();
```

يمكن للمشروع أن يحتوي على عدة تقاويم (تقويم قياسي، تقويم موارد، وتقويمات مخصصة). تتيح لك هذه المجموعة الوصول إلى كل منها.

## الخطوة 5: التكرار عبر التقويمات
قم بالتكرار عبر كل تقويم، واعرض معرفه الفريد (UID)، اسمه، وأيام العمل مع الساعات المقابلة.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

يتحقق الحلقة الداخلية من كل كائن `WeekDay`. إذا تم وضع علامة على اليوم كعمل، فإنه يطبع نوع اليوم (Monday، Tuesday، …) مع الساعات العملية المحسوبة.

## الخطوة 6: عرض رسالة الانتهاء
أظهر أن عملية الاستخراج قد انتهت.

```java
System.out.println("Process completed Successfully");
```

## الخلاصة
باتباع هذه الخطوات، **أنت الآن تعرف كيفية استخدام Aspose.Tasks لاستخراج معلومات تقويم المشروع** من ملف MS Project باستخدام Java. يمكنك دمج هذه المنطق في تطبيقات أكبر، أتمتة التقارير، أو مزامنة الجداول مع أنظمة المؤسسة الأخرى.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، يدعم Aspose.Tasks منصات ولغات برمجة متعددة، بما في ذلك .NET، C++، Python، و Java.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Tasks؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [here](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟**  
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: نعم، تتوفر تراخيص مؤقتة للشراء [here](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks؟**  
ج: يمكنك الرجوع إلى الوثائق [here](https://reference.aspose.com/tasks/java/).

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}