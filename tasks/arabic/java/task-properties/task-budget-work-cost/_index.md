---
title: إدارة الميزانية والعمل والتكلفة للمهام الموجودة في Aspose.Tasks
linktitle: إدارة الميزانية والعمل والتكلفة للمهام الموجودة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: احصل على إدارة فعالة للميزانية والتكلفة في مشاريع Java باستخدام Aspose.Tasks. استكشف الإرشادات خطوة بخطوة لتحقيق التكامل السلس.
weight: 31
url: /ar/java/task-properties/task-budget-work-cost/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة الميزانية والعمل والتكلفة للمهام الموجودة في Aspose.Tasks

## مقدمة
تعد إدارة الميزانيات والعمل والتكاليف بكفاءة أمرًا بالغ الأهمية لنجاح تنفيذ المشروع. يوفر Aspose.Tasks for Java حلاً قويًا للتعامل مع المهام المتعلقة بالمشروع، بما في ذلك إعداد الميزانية وإدارة التكاليف. في هذا البرنامج التعليمي، سنستكشف كيفية استخدام Aspose.Tasks لـ Java لتحقيق إدارة فعالة للميزانية والعمل والتكلفة في مشاريعك.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- بيئة تطوير Java: تأكد من إعداد بيئة تطوير Java على نظامك.
-  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java. يمكنك العثور على المكتبة[هنا](https://releases.aspose.com/tasks/java/).
## حزم الاستيراد
في مشروع Java الخاص بك، ابدأ باستيراد الحزم الضرورية. وهذا يضمن أن لديك حق الوصول إلى وظيفة Aspose.Tasks. قم بتضمين الأسطر التالية في بداية ملف Java الخاص بك:
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
## 1. قم بتعيين دليل المستندات
ابدأ بتعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يتم فيه تخزين ملفات مشروعك. استخدم مقتطف الكود التالي:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
```
## 2. قم بتحميل المشروع
قم بتحميل ملف المشروع باستخدام مكتبة Aspose.Tasks. استبدل "BudgetWorkAndCost.mpp" باسم ملف المشروع الخاص بك.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```
## 3. استرداد ميزانيات المشروع والموارد
جلب وعرض ميزانيات المشروع والموارد باستخدام الكود التالي:
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```
## 4. عرض ميزانيات المهام
التكرار من خلال تعيينات المشروع وعرض معلومات الميزانية:
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```
كرر هذه الخطوات حسب الحاجة لدمج وظائف إدارة الميزانية والعمل والتكلفة في مشروع Aspose.Tasks for Java.
## خاتمة
تعد إدارة الميزانيات والعمل والتكاليف بشكل فعال أمرًا محوريًا لنجاح المشروع. يعمل Aspose.Tasks for Java على تبسيط هذه العملية، مما يوفر حلاً شاملاً لاحتياجات إدارة مشروعك. باتباع هذا الدليل التفصيلي خطوة بخطوة، يمكنك دمج إدارة الميزانية والتكلفة بسلاسة في مشاريع Java الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Tasks لـ Java مع أطر عمل Java الأخرى؟
نعم، Aspose.Tasks for Java متوافق مع أطر عمل Java المختلفة، مما يضمن المرونة في التكامل.
### هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Tasks لـ Java[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على دعم إضافي لـ Aspose.Tasks لـ Java؟
 استكشف منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15) للدعم والمناقشات.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتقييم.
### هل هناك أي موارد إضافية لـ Aspose.Tasks لـ Java؟
 الرجوع إلى الوثائق[هنا](https://reference.aspose.com/tasks/java/) للحصول على معلومات وأمثلة متعمقة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
