---
date: 2026-03-08
description: تعلم كيفية استيراد ملف المشروع باستخدام Aspose.Tasks لـ .NET، بما في
  ذلك كيفية تحديد ترميز الملف وتحميل ملف Microsoft Project بكفاءة.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: استيراد ملف المشروع – خيارات التحميل في Aspose.Tasks
url: /ar/net/advanced-concepts/loading-options/
weight: 16
---

 each step heading.

Step 1: Load a Password‑Protected Project

Translate.

Then placeholder.

Similarly others.

Now "By following these steps you can precisely **import project file** data, tailor the loading process to your needs, and keep your application robust." translate.

Now "Common Issues & Tips" heading.

List items translate.

Now "Frequently Asked Questions" heading.

Each Q/A translate, keep bold Q: etc. Keep code formatting.

Translate link texts.

Now "Last Updated:" etc. Keep dates.

Now shortcodes closing.

Now final backtop button shortcode.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استيراد ملف المشروع – خيارات التحميل في Aspose.Tasks

## المقدمة

تجعل Aspose.Tasks for .NET عملية **استيراد ملف المشروع** من Microsoft Project وPrimavera وغيرها من الصيغ سهلة. سواء كنت بحاجة إلى قراءة ملف محمي بكلمة مرور، أو تعيين ترميز مخصص، أو التعامل مع أخطاء التحليل، توفر المكتبة تحكمًا دقيقًا عبر خيارات التحميل. في هذا الدرس سنستعرض أكثر السيناريوهات شيوعًا حتى تتمكن من **تحميل ملف Microsoft Project** بثقة في تطبيقات .NET الخاصة بك.

## إجابات سريعة
- **ما هي الطريقة الأساسية لاستيراد ملف مشروع؟** استخدم مُنشئ `Project` مع كائن `LoadOptions`.  
- **هل يمكنني فتح ملفات محمية بكلمة مرور؟** نعم—قم بتعيين خاصية `Password` في `LoadOptions`.  
- **كيف أحدد ترميز الملف؟** عيّن كائن `Encoding` إلى `LoadOptions.Encoding`.  
- **هل يمكن تخصيص معالجة الأخطاء؟** بالتأكيد—قدّم دالة إلى `LoadOptions.ErrorHandler`.  
- **هل تعمل هذه الخيارات مع ملفات Primavera؟** نعم، عبر `PrimaveraReadOptions` داخل `LoadOptions`.

## المتطلبات المسبقة

قبل المتابعة، تأكد من وجود ما يلي:

1. **Visual Studio** (أو أي بيئة تطوير .NET مفضلة).  
2. **Aspose.Tasks for .NET** – قم بتنزيله من الـ[موقع الإلكتروني](https://releases.aspose.com/tasks/net/).  
3. فهم أساسي لصياغة **C#** وبنية المشروع.

الآن بعد أن أصبح كل شيء جاهزًا، لنستورد المساحات الاسم المطلوبة.

## استيراد المساحات الاسم

في مشروع C# الخاص بك، أضف عبارات `using` التالية لتصبح فئات الـ API متاحة:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## كيفية استيراد ملف المشروع مع خيارات التحميل

فيما يلي أربعة أمثلة عملية تغطي أكثر سيناريوهات التحميل شيوعًا.

### الخطوة 1: تحميل مشروع محمي بكلمة مرور

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### الخطوة 2: تحميل مشروع Primavera مع خيارات مخصصة

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### الخطوة 3: **تحديد ترميز الملف** عند استيراد ملف XER

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### الخطوة 4: تحميل مشروع Primavera مع معالجة أخطاء مخصصة

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

باتباع هذه الخطوات يمكنك بدقة **استيراد ملف المشروع**، وتخصيص عملية التحميل وفقًا لاحتياجاتك، والحفاظ على استقرار تطبيقك.

## المشكلات الشائعة والنصائح

- **كلمة مرور غير صحيحة** – خاصية `Password` ستطرح استثناء؛ تحقق من صحة الاعتماد قبل التحميل.  
- **ترميز غير مدعوم** – تأكد من وجود صفحة الترميز التي تحددها على الجهاز الهدف (`Encoding.GetEncoding(1251)` تعمل للغة السيريالية).  
- **غياب خيارات Primavera** – إذا كنت بحاجة للحفاظ على معرفات المهام (UIDs)، عيّن `PreserveUids = true`؛ وإلا قد تظهر معرفات مكررة.  
- **معالج الأخطاء يُعيد null** – إرجاع `null` يُشير إلى أن المحلل يتخطى العنصر المسبب للمشكلة؛ خصص السلوك حسب الحاجة.

## الأسئلة المتكررة

**س: هل Aspose.Tasks for .NET متوافق مع جميع إصدارات Microsoft Project؟**  
ج: نعم، يدعم مجموعة واسعة من إصدارات Microsoft Project، لذا يمكنك **تحميل ملفات Microsoft Project** من ملفات MPP القديمة إلى أحدث الصيغ.

**س: هل يمكنني دمج Aspose.Tasks for .NET مع مكتبات طرف ثالث أخرى؟**  
ج: بالتأكيد. تعمل المكتبة بسلاسة مع حزم .NET الأخرى، مما يتيح لك دمجها مع أطر التقارير، واجهات المستخدم، أو أطر الوصول إلى البيانات.

**س: هل توفر Aspose.Tasks for .NET وثائق وموارد دعم؟**  
ج: نعم، يمكنك الرجوع إلى الـ[وثائق الشاملة](https://reference.aspose.com/tasks/net/) والوصول إلى الدعم عبر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**س: هل توجد خيارات ترخيص متاحة لـ Aspose.Tasks for .NET؟**  
ج: نعم، يمكنك استكشاف خيارات الترخيص المختلفة، بما في ذلك التجارب المجانية والتراخيص المؤقتة، على موقع [Aspose.Tasks](https://purchase.aspose.com/buy).

**س: ما مدى تكرار إصدار التحديثات والميزات الجديدة لـ Aspose.Tasks for .NET؟**  
ج: تصدر Aspose.Tasks تحديثات منتظمة تضيف ميزات، وتحسن الأداء، وتحافظ على التوافق مع أحدث إصدارات Microsoft Project.

---

**آخر تحديث:** 2026-03-08  
**تم الاختبار مع:** Aspose.Tasks 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}