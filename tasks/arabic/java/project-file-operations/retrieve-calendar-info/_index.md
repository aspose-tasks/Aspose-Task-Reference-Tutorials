---
date: 2026-03-27
description: تعلم كيفية استخدام Aspose و Aspose.Tasks لاستخراج تفاصيل تقويم المشروع
  من ملفات Microsoft Project باستخدام Java. دليل خطوة بخطوة مع أمثلة على الشيفرة.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية استخدام Aspose.Tasks لاسترجاع معلومات تقويم MS Project
url: /ar/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيف تستخدم Aspose.Tasks لاسترجاع معلومات تقويم MS Project

## المقدمة
في هذا الدرس، **ستكتشف كيفية استخدام Aspose.Tasks** لاسترجاع معلومات التقويم برمجياً من ملفات Microsoft Project. الوصول إلى بيانات التقويم مثل أيام العمل، الساعات، والاستثناءات أمر أساسي عندما تحتاج إلى **استخراج تقويم المشروع** للتقارير، التكامل، أو منطق الجدولة المخصص. دعنا نتبع العملية خطوة بخطوة، وسترى بالضبط **كيف تستخدم Aspose** لسحب هذه البيانات من ملف *.mpp*.

## إجابات سريعة
- **ما المكتبة التي يستخدمها هذا الدرس؟** Aspose.Tasks for Java.  
- **ما الكلمة المفتاحية الأساسية التي يتم تغطيتها؟** *how to use aspose*.  
- **ماذا يمكنك استخراج؟** تقاويم المشروع، بما في ذلك أيام العمل والساعات.  
- **هل أحتاج إلى ترخيص؟** تتوفر نسخة تجريبية مجانية؛ الترخيص مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى.

## ما هو Aspose.Tasks ولماذا نستخدمه؟
Aspose.Tasks هو API قوي للـ Java يتيح للمطورين قراءة، كتابة، وتعديل ملفات Microsoft Project دون الحاجة إلى Microsoft Project نفسه. باستخدام Aspose.Tasks يمكنك **how to extract calendar**، أتمتة حسابات الجدول، وتكامل بيانات المشروع مع أنظمة المؤسسة الأخرى—كل ذلك من خلال كود Java نقي.

## لماذا نستخرج معلومات تقويم المشروع؟
تقويمات المشروع تحدد تواريخ المهام، تخصيص الموارد، وحسابات الخط الزمني العامة. باستخراج هذه البيانات يمكنك:
- إنشاء تقارير مخصصة تعكس جداول العمل الفعلية.  
- مزامنة جداول Microsoft Project مع الأنظمة الخارجية (ERP، BI، إلخ).  
- إجراء تحليلات “ماذا لو” بتعديل إعدادات التقويم برمجياً.  
- **استخراج بيانات تقويم MS Project** للترحيل إلى أدوات تخطيط أخرى.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك:

- معرفة أساسية ببرمجة Java.  
- مجموعة تطوير Java (JDK) مثبتة على نظامك.  
- مكتبة Aspose.Tasks for Java. يمكنك تحميلها من [هنا](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، استورد الفئات الضرورية من Aspose.Tasks إلى مشروع Java الخاص بك.

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

استبدل `"Your Data Directory"` بالمسار المطلق للمجلد الذي يقع فيه **project.mpp**.

## الخطوة 2: تعريف وحدات الوقت
أنشئ ثوابت تساعد على تحويل تمثيل الوقت الداخلي إلى ساعات قابلة للقراءة البشرية.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

هذه القيم معبر عنها بالميكروثانية، وهي الطريقة التي يخزن بها Aspose.Tasks الوقت داخلياً.

## الخطوة 3: إنشاء كائن المشروع
حمّل ملف Microsoft Project إلى كائن `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

منشئ `Project` يقرأ ملف *.mpp* ويجعل جميع بيانات المشروع، بما في ذلك التقويمات، متاحة عبر الـ API.

## الخطوة 4: استرجاع معلومات التقويمات
احصل على مجموعة التقويمات المعرفة في المشروع.

```java
CalendarCollection alCals = project.getCalendars();
```

يمكن أن يحتوي المشروع على تقويمات متعددة (تقويم قياسي، موارد، وتقويمات مخصصة). هذه المجموعة تمنحك الوصول إلى كل منها.

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

الحلقة الداخلية تتحقق من كل كائن `WeekDay`. إذا كان اليوم مُعرّفاً كعمل، يتم طباعة نوع اليوم (Monday, Tuesday, …) مع عدد الساعات المحسوبة.

## الخطوة 6: عرض رسالة الانتهاء
أظهر أن عملية الاستخراج قد انتهت.

```java
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والحلول
| المشكلة | لماذا يحدث | الحل |
|-------|----------------|-----|
| **عدم إرجاع أي تقويمات** | قد لا يحتوي ملف المشروع على أي تقويمات مخصصة. | تأكد من أن ملف *.mpp* فعلاً يعرّف تقويمات أو افتحه في Microsoft Project للتأكد. |
| **ساعات عمل غير صحيحة** | ثوابت تحويل الوقت غير مناسبة لإصدار Project مختلف. | عدّل `OneSec`، `OneMin`، `OneHour` إذا كنت تستخدم نسخة أحدث من Aspose.Tasks تغير وحدة الوقت الداخلية. |
| **`NullPointerException` على `cal.getName()`** | قد تكون بعض كائنات التقويم فارغة (null). | أضف فحصاً للـ null قبل الوصول إلى الخصائص (كما هو موضح). |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، يدعم Aspose.Tasks منصات ولغات برمجة متعددة، بما في ذلك .NET، C++، Python، و Java.

**س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Tasks؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks؟**  
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

**س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: نعم، تتوفر تراخيص مؤقتة للشراء [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.Tasks؟**  
ج: يمكنك الرجوع إلى الوثائق [هنا](https://reference.aspose.com/tasks/java/).

## الخلاصة
باتباعك لهذه الخطوات، **أنت الآن تعرف كيف تستخدم Aspose.Tasks لاستخراج معلومات تقويم المشروع** من ملف MS Project باستخدام Java. يمكنك دمج هذه المنطق في تطبيقات أكبر، أتمتة التقارير، أو مزامنة الجداول مع أنظمة المؤسسة الأخرى. تذكر أن إتقان **how to use aspose** يفتح الباب أمام العديد من سيناريوهات أتمتة إدارة المشاريع المتقدمة.

---

**آخر تحديث:** 2026-03-27  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}