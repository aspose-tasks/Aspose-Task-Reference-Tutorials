---
date: 2026-02-28
description: تعلم كيفية إدارة الميزانية والعمل والتكلفة للمهام في مشاريع جافا باستخدام
  Aspose.Tasks. يوضح هذا الدليل أيضًا كيفية حساب تكلفة المهمة بكفاءة.
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إدارة الميزانية والعمل والتكلفة في Aspose.Tasks Java
url: /ar/java/task-properties/task-budget-work-cost/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إدارة الميزانية والعمل والتكلفة في Aspose.Tasks Java

إدارة مالية المشروع هي مسؤولية أساسية لأي مدير مشروع. في هذا البرنامج التعليمي ستكتشف **كيفية إدارة الميزانية** للمهام والعمل والموارد باستخدام Aspose.Tasks Java API، وسترى أيضًا **كيفية حساب تكلفة المهمة** عندما تحتاج إلى تقارير مالية دقيقة. في نهاية الدليل ستكون قادرًا على قراءة وعرض وتعديل الحقول المتعلقة بالميزانية مباشرةً من ملفات Microsoft Project الخاصة بك.

## إجابات سريعة
- **ما الذي تمثله “budget work”?** مقدار العمل (بالساعات) المخصص لمهمة أو مورد.  
- **هل يمكنني استرجاع تكلفة الميزانية برمجياً؟** نعم، باستخدام الحقل `BUDGET_COST` على المهام أو الموارد أو التخصيصات.  
- **هل أحتاج إلى ترخيص لـ Aspose.Tasks؟** الترخيص مطلوب للإنتاج؛ يتوفر إصدار تجريبي مجاني.  
- **ما نسخة Java المدعومة؟** Aspose.Tasks يعمل مع Java 8 وما فوق.  
- **هل يمكن حساب تكلفة المهمة من التخصيصات؟** بالتأكيد – اجمع قيم `BUDGET_COST` للتخصيصات.

## ما هو إدارة الميزانية في Aspose.Tasks؟
يخزن Aspose.Tasks معلومات الميزانية في حقول مخصصة (`BUDGET_WORK`، `BUDGET_COST`) للمهام والموارد والتخصيصات. تتيح لك هذه الحقول تخطيط الجهد المتوقع والنفقات المالية قبل تنفيذ أي عمل، مما يتيح توقعات دقيقة وتحليل الفروقات.

## لماذا حساب تكلفة المهمة؟
- متابعة الأداء المالي مقارنةً بالتقدير الأصلي.  
- إنشاء تقارير مبنية على التكلفة لأصحاب المصلحة.  
- تحديد المهام التي تتجاوز ميزانيتها مبكراً.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من وجود ما يلي:

- بيئة تطوير Java (JDK 8+).  
- مكتبة Aspose.Tasks for Java – قم بتنزيلها **[here](https://releases.aspose.com/tasks/java/)**.  
- ملف Microsoft Project تجريبي (مثال: `BudgetWorkAndCost.mpp`) موجود في دليل معروف.

## استيراد الحزم
في مشروع Java الخاص بك، ابدأ باستيراد الحزم اللازمة. يضمن ذلك وصولك إلى وظائف Aspose.Tasks. أدرج السطور التالية في بداية ملف Java الخاص بك:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## الخطوة 1: تعيين دليل المستندات
ابدأ بتعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تُخزن فيه ملفات المشروع.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## الخطوة 2: تحميل المشروع
حمّل ملف المشروع باستخدام مكتبة Aspose.Tasks. استبدل `"BudgetWorkAndCost.mpp"` باسم ملف مشروعك.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```

## الخطوة 3: استرجاع ميزانيات المشروع والموارد
احصل على ميزانيات مستوى المشروع ومستوى الموارد وعرضها. تُظهر لك هذه الخطوة كيفية **حساب تكلفة المهمة** بقراءة القيم المخزنة.
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```

## الخطوة 4: عرض ميزانيات التخصيص
تجول عبر تخصيصات مهمة الملخص (أو أي مهمة) وعرض معلومات ميزانية كل تخصيص. يتيح لك ذلك رؤية التكلفة المخصصة لكل مورد.
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```

## المشكلات الشائعة ونصائح الخبراء
- **القيم الفارغة:** إذا أعاد حقل الميزانية `null`، قد لا يحتوي ملف المشروع على تلك البيانات. استخدم فحوصات `project.getRootTask().get(Tsk.BUDGET_WORK) != null` قبل الطباعة.  
- **معرف UID غير صحيح:** تأكد من وجود معرف UID للمورد الذي تستعلم عنه (`getByUid(2)`)؛ وإلا ستحصل على استثناء `NullPointerException`.  
- **تنسيق العملة:** يُعيد `BUDGET_COST` قيمة double خام. قم بتنسيقها باستخدام `NumberFormat.getCurrencyInstance()` للحصول على مخرجات صديقة للمستخدم.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java مع أطر Java الأخرى؟**  
ج: نعم، Aspose.Tasks for Java متوافق مع أطر Java المختلفة، مما يضمن مرونة في التكامل.

**س: هل يتوفر إصدار تجريبي لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks for Java **[here](https://releases.aspose.com/)**.

**س: أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks for Java؟**  
ج: استكشف منتدى مجتمع Aspose.Tasks **[here](https://forum.aspose.com/c/tasks/15)** للحصول على الدعم والنقاشات.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟**  
ج: احصل على ترخيص مؤقت **[here](https://purchase.aspose.com/temporary-license/)** لأغراض الاختبار والتقييم.

**س: هل هناك موارد إضافية لـ Aspose.Tasks for Java؟**  
ج: راجع الوثائق **[here](https://reference.aspose.com/tasks/java/)** للحصول على معلومات وأمثلة متعمقة.

---

**آخر تحديث:** 2026-02-28  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}