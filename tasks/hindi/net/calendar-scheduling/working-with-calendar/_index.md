---
title: Aspose.Tasks में कैलेंडर के साथ कार्य करना
linktitle: Aspose.Tasks में कैलेंडर के साथ कार्य करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके प्रोजेक्ट कैलेंडर प्रबंधित करें, अवधि की गणना करें, अपवादों को आसानी से संभालें।
type: docs
weight: 10
url: /hi/net/calendar-scheduling/working-with-calendar/
---
## परिचय

.NET के लिए Aspose.Tasks कैलेंडर के साथ काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जो डेवलपर्स को प्रोजेक्ट शेड्यूल और संसाधन आवंटन को कुशलतापूर्वक प्रबंधित करने में सक्षम बनाता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि कैलेंडर के साथ इंटरैक्ट करने के लिए Aspose.Tasks का उपयोग कैसे किया जाए, जिसमें आवश्यक कार्यों को शामिल किया जाए जैसे कि कैलेंडर जानकारी प्राप्त करना, कार्य सप्ताहों को परिभाषित करना, काम के घंटों की गणना करना और बहुत कुछ।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ स्थापित हैं:

- C# प्रोग्रामिंग भाषा की बुनियादी समझ।
-  .NET के लिए Aspose.Tasks की स्थापना। यदि इंस्टॉल नहीं है तो इसे यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/tasks/net/).
- विजुअल स्टूडियो या किसी अन्य पसंदीदा .NET विकास परिवेश से परिचित होना।

## नामस्थान आयात करें

कोडिंग शुरू करने से पहले, आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

अब, आइए चरण-दर-चरण मार्गदर्शिका प्रारूप में प्रत्येक उदाहरण को कई चरणों में विभाजित करें:

## चरण 1: कैलेंडर जानकारी पुनः प्राप्त करें

किसी प्रोजेक्ट से कैलेंडर जानकारी पुनर्प्राप्त करने के लिए, इन चरणों का पालन करें:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // कैलेंडर जानकारी पुनः प्राप्त करें
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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- प्रोजेक्ट में प्रत्येक कैलेंडर के माध्यम से पुनरावृति करें।
- प्रत्येक कैलेंडर का यूआईडी और नाम प्रिंट करें।

## चरण 2: कार्य सप्ताह की जानकारी पढ़ें

किसी कैलेंडर से कार्य सप्ताहों की जानकारी पढ़ने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- यूआईडी द्वारा कैलेंडर प्राप्त करें.
- कैलेंडर में प्रत्येक कार्य सप्ताह को दोहराएँ।
- प्रत्येक कार्य सप्ताह का नाम, प्रारंभ तिथि और समाप्ति तिथि प्रिंट करें।
- प्रत्येक सप्ताह के भीतर कार्य दिवसों और कार्य समयों का भ्रमण करें।

## चरण 3: कैलेंडर गुण पढ़ें

प्रोजेक्ट कैलेंडर के गुण पढ़ने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- प्रोजेक्ट में प्रत्येक कैलेंडर के माध्यम से पुनरावृति करें।
- यूआईडी, नाम और क्या यह आधार कैलेंडर है, प्रिंट करें।
- प्रत्येक दिन के प्रकार के लिए कार्य के घंटे प्रिंट करें।

## चरण 4: कार्य घंटों की गणना करें

किसी कार्य के लिए कार्य घंटों की गणना करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- कैलेंडर, प्रारंभ तिथि और समाप्ति तिथि जैसे कार्य विवरण प्राप्त करें।
- प्रत्येक दिन को दोहराते हुए और यह जाँच कर कि क्या यह कार्य दिवस है, कार्य घंटों की गणना करें।
- कुल अवधि को मिनटों में जोड़ें।

## चरण 5: कैलेंडर के लिए सप्ताह के दिनों को परिभाषित करें

किसी कैलेंडर के लिए कार्यदिवस परिभाषित करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- एक नया प्रोजेक्ट और कैलेंडर बनाएं.
- डिफ़ॉल्ट कार्य दिवस (सोमवार से गुरुवार) और शुक्रवार के लिए कस्टम कार्य समय जोड़ें।
- शनिवार और रविवार को गैर-कार्य दिवस के रूप में निर्धारित करें।

## चरण 6: अद्यतन कैलेंडर डेटा को एमपीपी पर लिखें

एमपीपी फ़ाइल में अद्यतन कैलेंडर डेटा लिखने के लिए, इन चरणों का पालन करें:

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/)");
    }
}
```

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें और मानक कैलेंडर पुनर्प्राप्त करें।
- अपवाद और कार्य समय जैसे कैलेंडर डेटा को संशोधित करें।
- संशोधित कैलेंडर डेटा के साथ अद्यतन प्रोजेक्ट को सहेजें।

## चरण 7: विभाजित कार्य समाप्ति तिथि की गणना करें

किसी विभाजित कार्य की समाप्ति तिथि की गणना करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें और विभाजित कार्य पुनः प्राप्त करें।
- प्रोजेक्ट कैलेंडर प्राप्त करें.
- कस्टम अवधि के आधार पर समाप्ति तिथि की गणना करें।

## चरण 8: कैलेंडर अपवाद पुनर्प्राप्त करें

कैलेंडर अपवादों के बारे में जानकारी पुनः प्राप्त करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- प्रत्येक कैलेंडर और उसके अपवादों को दोहराएँ।
- प्रत्येक अपवाद की आरंभ और समाप्ति तिथियां प्रिंट करें।

## चरण 9: आधार संसाधन कैलेंडर प्राप्त करें

किसी संसाधन के कैलेंडर के आधार कैलेंडर के साथ काम करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- एक संसाधन और उसका कैलेंडर जोड़ें.
- सभी संसाधनों के लिए आधार कैलेंडर नाम प्रिंट करें।

## चरण 10: कैलेंडर हटाएँ

किसी प्रोजेक्ट से कैलेंडर हटाने के लिए, इन चरणों का पालन करें:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- नाम से कैलेंडर प्राप्त करें.
- कैलेंडर हटाएँ.

## चरण 11: प्रारंभ और कार्य के आधार पर समाप्ति तिथि प्राप्त करें

आरंभ तिथि और कार्य के आधार पर समाप्ति तिथि की गणना करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- मानक कैलेंडर प्राप्त करें.
- आरंभ तिथि और कार्य अवधि निर्धारित करें.
- आरंभ तिथि और कार्य के आधार पर समाप्ति तिथि की गणना करें।

## चरण 12: अगले कार्य दिवस की शुरुआत करें

कैलेंडर का उपयोग करके अगले कार्य दिवस की शुरुआत करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- यूआईडी द्वारा कैलेंडर प्राप्त करें.
- अगले कार्य दिवस का प्रारंभ समय प्राप्त करें.

## चरण 13: पिछले कार्य दिवस की समाप्ति प्राप्त करें

कैलेंडर का उपयोग करके पिछले कार्य दिवस की समाप्ति जानने के लिए, इन चरणों का पालन करें:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- यूआईडी द्वारा कैलेंडर प्राप्त करें.
- पिछले कार्य दिवस का समाप्ति समय प्राप्त करें।

## चरण 14: समाप्ति और अवधि से आरंभ तिथि प्राप्त करें

समाप्ति तिथि और अवधि के अनुसार आरंभ तिथि प्राप्त करने के लिए, इन चरणों का पालन करें:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- यूआईडी द्वारा कैलेंडर प्राप्त करें.
- समाप्ति तिथि और अवधि से प्रारंभ तिथि की गणना करें।

## चरण 15: कार्य के घंटे प्राप्त करें

किसी विशिष्ट तिथि के लिए कार्य घंटे जानने के लिए, इन चरणों का पालन करें:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- यूआईडी द्वारा कैलेंडर प्राप्त करें.
- निर्दिष्ट तिथि के लिए कार्य के घंटे प्राप्त करें.

## चरण 16: कार्य समय प्राप्त करें

किसी विशिष्ट तिथि के लिए कार्य समय प्राप्त करने के लिए, इन चरणों का पालन करें:

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

स्पष्टीकरण:
- प्रोजेक्ट फ़ाइल लोड करें.
- यूआईडी द्वारा कैलेंडर प्राप्त करें.
- निर्दिष्ट तिथि के लिए कार्य समय प्राप्त करें.

## निष्कर्ष

प्रोजेक्ट शेड्यूल को प्रभावी ढंग से प्रबंधित करने के लिए .NET के लिए Aspose.Tasks में कैलेंडर के साथ काम करना महत्वपूर्ण है। दिए गए उदाहरणों और चरण-दर-चरण मार्गदर्शिकाओं के साथ, आप आसानी से कैलेंडर डेटा में हेरफेर कर सकते हैं, कार्य अवधि की गणना कर सकते हैं और अपवादों को कुशलतापूर्वक संभाल सकते हैं। इन कार्यात्मकताओं को अपने अनुप्रयोगों में एकीकृत करके, आप परियोजना प्रबंधन प्रक्रियाओं को सुव्यवस्थित कर सकते हैं और सटीक शेड्यूलिंग सुनिश्चित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मुझे .NET के लिए Aspose.Tasks का उपयोग करने के लिए लाइसेंस की आवश्यकता है?

 उ1: हाँ, आपको अपने अनुप्रयोगों में .NET के लिए Aspose.Tasks का उपयोग करने के लिए एक वैध लाइसेंस की आवश्यकता है। आप पूर्ण लाइसेंस खरीद सकते हैं या 30-दिवसीय अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### Q2: क्या मैं कैलेंडर अपवादों को प्रोग्रामेटिक रूप से संशोधित कर सकता हूँ?

A2: हां, आप .NET API के लिए Aspose.Tasks का उपयोग करके कैलेंडर अपवादों को प्रोग्रामेटिक रूप से जोड़, अपडेट या हटा सकते हैं।

### Q3: मैं कस्टम अवधि के साथ कार्य समाप्ति तिथियों की गणना कैसे कर सकता हूं?

 A3: .NET के लिए Aspose.Tasks जैसे तरीके प्रदान करता है`GetTaskFinishDateFromDuration()` कस्टम अवधि के आधार पर कार्य समाप्ति तिथियों की गणना करने के लिए।

### Q4: क्या रात की पाली के कैलेंडर जैसे कस्टम कैलेंडर बनाना संभव है?

A4: हां, आप .NET API के लिए Aspose.Tasks का उपयोग करके नाइट शिफ्ट कैलेंडर जैसे कस्टम कैलेंडर बना सकते हैं।

### Q5: क्या मैं प्रोजेक्ट फ़ाइलों से कैलेंडर अपवादों के बारे में जानकारी प्राप्त कर सकता हूँ?

A5: हां, आप .NET के लिए Aspose.Tasks का उपयोग करके प्रोजेक्ट फ़ाइलों से कैलेंडर अपवादों के बारे में आसानी से जानकारी प्राप्त कर सकते हैं।