---
title: قراءة بيانات مخطط جانت المحددة في Aspose.Tasks
linktitle: قراءة بيانات مخطط جانت المحددة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية استخراج بيانات مخطط جانت محددة باستخدام Aspose.Tasks لـ Java. برنامج تعليمي خطوة بخطوة للتكامل السلس في تطبيقات Java الخاصة بك.
type: docs
weight: 16
url: /ar/java/project-data-reading/read-specific-gantt-chart-data/
---
## مقدمة
تعد مخططات جانت أدوات لا تقدر بثمن لإدارة المشاريع، مما يسمح للمستخدمين بتصور المهام والجداول الزمنية والتبعيات. باستخدام Aspose.Tasks for Java، يمكن للمطورين استخراج بيانات محددة بكفاءة من مخططات جانت لدمجها في تطبيقاتهم. في هذا البرنامج التعليمي، سنرشدك خلال عملية قراءة بيانات مخطط جانت المحددة خطوة بخطوة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت Java على نظامك. يمكنك تنزيله[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة التي تفضلها. تشمل الاختيارات الشائعة IntelliJ IDEA أو Eclipse أو NetBeans.

## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك للوصول إلى وظائف Aspose.Tasks:
```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```
## الخطوة 1: تحميل ملف المشروع
ابدأ بتحميل ملف المشروع الذي يحتوي على بيانات مخطط جانت. قم بتوفير المسار إلى دليل البيانات الخاص بك وحدد اسم الملف.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```
## الخطوة 2: الوصول إلى عرض مخطط جانت
استرداد طريقة عرض مخطط جانت من المشروع. سنفترض أن هذا هو العرض الأول في القائمة.
```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```
## الخطوة 3: استخراج خصائص العرض
الآن، دعونا نستخرج الخصائص المختلفة لعرض مخطط جانت ونطبعها للفحص.
```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// تابع للعقارات الأخرى...
```
## الخطوة 4: استخراج أنماط الشريط
قم بالتكرار عبر أنماط الشريط في طريقة عرض مخطط جانت وطباعة تفاصيلها.
```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // طباعة تفاصيل نمط الشريط...
}
```
## الخطوة 5: استخراج خطوط الشبكة
استرداد وطباعة المعلومات حول خطوط الشبكة في طريقة عرض مخطط جانت.
```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// طباعة تفاصيل خطوط الشبكة...
```
## الخطوة 6: استخراج أنماط النص
استرداد وطباعة أنماط النص المستخدمة في طريقة عرض مخطط جانت.
```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // طباعة تفاصيل نمط النص...
}
```
## الخطوة 7: استخراج خطوط التقدم
الوصول إلى خصائص خطوط التقدم وطباعتها في عرض مخطط جانت.
```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// طباعة تفاصيل خط التقدم الأخرى...
```
## الخطوة 8: استخراج طبقات الجدول الزمني
قم باسترجاع وطباعة المعلومات حول طبقات الجدول الزمني في طريقة عرض مخطط جانت.
```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// طباعة تفاصيل مستويات النطاق الزمني الأخرى...
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية قراءة بيانات مخطط جانت محددة باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات، يمكنك استخراج معلومات مخطط جانت ومعالجتها بكفاءة داخل تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks لـ Java مع مكتبات Java الأخرى؟
ج: نعم، تم تصميم Aspose.Tasks for Java للتكامل بسلاسة مع مكتبات وأطر عمل Java الأخرى.
### س: هل Aspose.Tasks مناسب لمشاريع المؤسسات واسعة النطاق؟
ج: بالتأكيد. يوفر Aspose.Tasks ميزات قوية وأداءً ممتازًا، مما يجعله مناسبًا للمشاريع على أي نطاق.
### س: هل يدعم Aspose.Tasks تنسيقات ملفات المشروع المتعددة؟
ج: نعم، يدعم Aspose.Tasks العديد من تنسيقات ملفات المشروع، بما في ذلك MPP وXML وMPX.
### س: هل يمكنني تخصيص مظهر مخططات جانت باستخدام Aspose.Tasks؟
ج: بالتأكيد. يوفر Aspose.Tasks واجهات برمجة تطبيقات واسعة النطاق لتخصيص مظهر مخطط جانت وفقًا لمتطلباتك.
### س: هل يتوفر الدعم الفني لمستخدمي Aspose.Tasks؟
ج: نعم، تقدم Aspose.Tasks دعمًا فنيًا شاملاً من خلال المنتدى الخاص بها وقنوات الدعم المخصصة.