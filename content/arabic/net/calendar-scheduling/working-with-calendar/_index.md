---
title: العمل مع التقويم في Aspose.Tasks
linktitle: العمل مع التقويم في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: إدارة تقويمات المشروع، وحساب المدد، والتعامل مع الاستثناءات بسهولة باستخدام Aspose.Tasks لـ .NET.
type: docs
weight: 10
url: /ar/net/calendar-scheduling/working-with-calendar/
---
## مقدمة

يوفر Aspose.Tasks for .NET ميزات قوية للعمل مع التقويمات، مما يتيح للمطورين إدارة جداول المشروع وتخصيص الموارد بكفاءة. في هذا البرنامج التعليمي، سنستكشف كيفية استخدام Aspose.Tasks للتفاعل مع التقويمات، وتغطية العمليات الأساسية مثل استرداد معلومات التقويم، وتحديد أسابيع العمل، وحساب ساعات العمل، والمزيد.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من إعداد المتطلبات الأساسية التالية:

- الفهم الأساسي للغة البرمجة C#.
-  تثبيت Aspose.Tasks لـ .NET. إذا لم يتم تثبيته، قم بتنزيله من[هنا](https://releases.aspose.com/tasks/net/).
- الإلمام بـ Visual Studio أو أي بيئة تطوير NET مفضلة أخرى.

## استيراد مساحات الأسماء

قبل البدء في البرمجة، تأكد من استيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

الآن، دعونا نقسم كل مثال إلى خطوات متعددة بتنسيق دليل خطوة بخطوة:

## الخطوة 1: استرداد معلومات التقويم

لاسترداد معلومات التقويم من مشروع، اتبع الخطوات التالية:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // استرداد معلومات التقويمات
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

توضيح:
- قم بتحميل ملف المشروع.
- التكرار من خلال كل تقويم في المشروع.
- طباعة UID واسم كل تقويم.

## الخطوة 2: اقرأ معلومات أسابيع العمل

لقراءة معلومات أسابيع العمل من التقويم، اتبع الخطوات التالية:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

توضيح:
- قم بتحميل ملف المشروع.
- الحصول على التقويم عن طريق UID.
- كرر خلال كل أسبوع عمل في التقويم.
- طباعة الاسم وتاريخ البدء وتاريخ الانتهاء لكل أسبوع عمل.
- التنقل خلال أيام العمل وأوقات العمل خلال كل أسبوع.

## الخطوة 3: قراءة خصائص التقويم

لقراءة خصائص تقويمات المشروع، اتبع الخطوات التالية:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

توضيح:
- قم بتحميل ملف المشروع.
- التكرار من خلال كل تقويم في المشروع.
- اطبع UID والاسم وما إذا كان تقويمًا أساسيًا.
- طباعة ساعات العمل لكل نوع يوم.

## الخطوة 4: حساب ساعات العمل

لحساب ساعات العمل لمهمة ما، اتبع الخطوات التالية:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

توضيح:
- قم بتحميل ملف المشروع.
- احصل على تفاصيل المهمة مثل التقويم وتاريخ البدء وتاريخ الانتهاء.
- احسب ساعات العمل من خلال تكرار كل يوم والتحقق مما إذا كان يوم عمل.
- لخص المدة الإجمالية في دقائق.

## الخطوة 5: تحديد أيام الأسبوع للتقويم

لتحديد أيام الأسبوع للتقويم، اتبع الخطوات التالية:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

توضيح:
- إنشاء مشروع جديد والتقويم.
- أضف أيام العمل الافتراضية (من الاثنين إلى الخميس) وأوقات العمل المخصصة ليوم الجمعة.
- تعيين السبت والأحد كأيام غير عمل.

## الخطوة 6: كتابة بيانات التقويم المحدثة إلى MPP

لكتابة بيانات التقويم المحدثة إلى ملف MPP، اتبع الخطوات التالية:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/.");
    }
}
```

توضيح:
- قم بتحميل ملف المشروع واسترجاع التقويم القياسي.
- تعديل بيانات التقويم مثل الاستثناءات وأوقات العمل.
- احفظ المشروع المحدث ببيانات التقويم المعدلة.

## الخطوة 7: حساب تاريخ انتهاء المهمة المقسمة

لحساب تاريخ انتهاء مهمة مقسمة، اتبع الخطوات التالية:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

توضيح:
- قم بتحميل ملف المشروع واسترجاع المهمة المقسمة.
- الحصول على تقويم المشروع.
- احسب تاريخ الانتهاء بناءً على مدة مخصصة.

## الخطوة 8: استرداد استثناءات التقويم

لاسترداد معلومات حول استثناءات التقويم، اتبع الخطوات التالية:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

توضيح:
- قم بتحميل ملف المشروع.
- قم بالتكرار خلال كل تقويم واستثناءاته.
- طباعة تاريخي البدء والانتهاء لكل استثناء.

## الخطوة 9: احصل على تقويم الموارد الأساسية

للعمل مع التقويم الأساسي لتقويم المورد، اتبع الخطوات التالية:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

توضيح:
- قم بتحميل ملف المشروع.
- إضافة مورد والتقويم الخاص به.
- طباعة اسم التقويم الأساسي لكافة الموارد.

## الخطوة 10: حذف التقويم

لحذف تقويم من مشروع، اتبع الخطوات التالية:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

توضيح:
- قم بتحميل ملف المشروع.
- احصل على التقويم بالاسم.
- حذف التقويم.

## الخطوة 11: احصل على تاريخ الانتهاء حسب البدء والعمل

لحساب تاريخ الانتهاء حسب تاريخ البدء والعمل، اتبع الخطوات التالية:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

توضيح:
- قم بتحميل ملف المشروع.
- احصل على التقويم القياسي.
- تحديد تاريخ البدء ومدة العمل.
- احسب تاريخ الانتهاء بناءً على تاريخ البدء والعمل.

## الخطوة 12: ابدأ يوم العمل التالي

لبدء يوم العمل التالي باستخدام التقويم، اتبع الخطوات التالية:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

توضيح:
- قم بتحميل ملف المشروع.
- الحصول على التقويم عن طريق UID.
- احصل على وقت بدء يوم العمل التالي.

## الخطوة 13: احصل على نهاية يوم العمل السابق

للحصول على نهاية يوم العمل السابق باستخدام التقويم، اتبع الخطوات التالية:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

توضيح:
- قم بتحميل ملف المشروع.
- الحصول على التقويم عن طريق UID.
- احصل على وقت نهاية يوم العمل السابق.

## الخطوة 14: احصل على تاريخ البدء من النهاية والمدة

للحصول على تاريخ البدء حسب تاريخ الانتهاء والمدة، اتبع الخطوات التالية:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

توضيح:
- قم بتحميل ملف المشروع.
- الحصول على التقويم عن طريق UID.
- احسب تاريخ البدء من تاريخ الانتهاء والمدة.

## الخطوة 15: احصل على ساعات العمل

للحصول على ساعات العمل لتاريخ محدد، اتبع الخطوات التالية:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

توضيح:
- قم بتحميل ملف المشروع.
- الحصول على التقويم عن طريق UID.
- الحصول على ساعات العمل للتاريخ المحدد.

## الخطوة 16: احصل على أوقات العمل

للحصول على أوقات العمل لتاريخ محدد، اتبع الخطوات التالية:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

توضيح:
- قم بتحميل ملف المشروع.
- الحصول على التقويم عن طريق UID.
- الحصول على أوقات العمل للتاريخ المحدد.

## خاتمة

يعد العمل مع التقويمات في Aspose.Tasks لـ .NET أمرًا ضروريًا لإدارة جداول المشروع بفعالية. باستخدام الأمثلة المقدمة والأدلة خطوة بخطوة، يمكنك بسهولة التعامل مع بيانات التقويم وحساب فترات المهام والتعامل مع الاستثناءات بكفاءة. ومن خلال دمج هذه الوظائف في تطبيقاتك، يمكنك تبسيط عمليات إدارة المشروع وضمان جدولة دقيقة.

## الأسئلة الشائعة

### س1: هل أحتاج إلى ترخيص لاستخدام Aspose.Tasks لـ .NET؟

 ج1: نعم، أنت بحاجة إلى ترخيص صالح لاستخدام Aspose.Tasks لـ .NET في تطبيقاتك. يمكنك شراء ترخيص كامل أو الحصول على ترخيص مؤقت لمدة 30 يومًا من[هنا](https://purchase.aspose.com/temporary-license/).

### س٢: هل يمكنني تعديل استثناءات التقويم برمجياً؟

ج2: نعم، يمكنك إضافة استثناءات التقويم أو تحديثها أو حذفها برمجيًا باستخدام Aspose.Tasks لـ .NET APIs.

### س3: كيف يمكنني حساب تواريخ انتهاء المهمة بمدد مخصصة؟

 A3: يوفر Aspose.Tasks لـ .NET أساليب مثل`GetTaskFinishDateFromDuration()` لحساب تواريخ انتهاء المهمة استناداً إلى فترات مخصصة.

### س4: هل من الممكن إنشاء تقويمات مخصصة، مثل تقويمات المناوبة الليلية؟

ج4: نعم، يمكنك إنشاء تقويمات مخصصة مثل تقويمات الورديات الليلية باستخدام Aspose.Tasks لـ .NET APIs.

### س5: هل يمكنني استرداد معلومات حول استثناءات التقويم من ملفات المشروع؟

ج5: نعم، يمكنك بسهولة استرداد معلومات حول استثناءات التقويم من ملفات المشروع باستخدام Aspose.Tasks لـ .NET.