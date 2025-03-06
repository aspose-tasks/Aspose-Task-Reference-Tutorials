---
title: Aspose.Tasks में कैलेंडर अपवादों को संभालना
linktitle: Aspose.Tasks में कैलेंडर अपवादों को संभालना
second_title: Aspose.Tasks .NET API
description: चरण-दर-चरण ट्यूटोरियल और उदाहरणों के साथ .NET के लिए Aspose.Tasks में कैलेंडर अपवादों को प्रबंधित करना सीखें।
weight: 12
url: /hi/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कैलेंडर अपवादों को संभालना

## परिचय

इस ट्यूटोरियल में, हम जानेंगे कि .NET फ्रेमवर्क का उपयोग करके Aspose.Tasks में कैलेंडर अपवादों को कैसे प्रबंधित किया जाए। कैलेंडर अपवाद हमें प्रोजेक्ट कैलेंडर में विशेष तिथियों या अवधियों को परिभाषित करने की अनुमति देते हैं जहां नियमित कामकाजी शेड्यूल बदल दिया जाता है, जैसे छुट्टियां या अस्थायी बंद। हम .NET के लिए Aspose.Tasks का उपयोग करके चरण दर चरण कैलेंडर अपवादों को संभालने के विभिन्न तरीकों को कवर करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित है।
- .NET लाइब्रेरी के लिए Aspose.Tasks आपके प्रोजेक्ट में जोड़ा गया।

## नामस्थान आयात करें

सबसे पहले, आइए अपने प्रोजेक्ट के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;


```

## चरण 1: कैलेंडर अपवाद हटाना

कैलेंडर अपवाद को हटाने के लिए, इन चरणों का पालन करें:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // कैलेंडर जानकारी प्रदर्शित करें
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // पहला अपवाद हटाएँ
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## चरण 2: कैलेंडर अपवाद का कार्य समय प्राप्त करना

कैलेंडर अपवाद का कार्य समय पुनः प्राप्त करने के लिए, इन चरणों का पालन करें:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // कैलेंडर और अपवाद जानकारी प्रदर्शित करें
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // कार्य समय प्राप्त करें और विवरण प्रदर्शित करें
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## चरण 3: कैलेंडर अपवादों को परिभाषित करना

कैलेंडर अपवाद जोड़ने या हटाने के लिए, इन चरणों का पालन करें:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // एक नया कैलेंडर अपवाद बनाएं
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // अपवाद विवरण सेट करें
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // जांचें कि क्या कोई तारीख अपवाद है
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // कैलेंडर में अपवाद जोड़ें
    calendar.Exceptions.Add(exception);

    // यदि कोई अपवाद मौजूद है तो उसे हटा दें
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // एक नया अपवाद जोड़ें
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // अपवाद प्रिंट करें
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Tasks में कैलेंडर अपवादों को संभालने के विभिन्न पहलुओं को शामिल किया है। दिए गए चरणों का पालन करके, आप काम के घंटों और विशेष घटनाओं का सटीक प्रतिनिधित्व सुनिश्चित करते हुए, अपने प्रोजेक्ट शेड्यूल में अपवादों को प्रभावी ढंग से प्रबंधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं एक ही कैलेंडर में एकाधिक अपवाद जोड़ सकता हूँ?

उ1: हां, आप विभिन्न विशेष तिथियों या अवधियों को समायोजित करने के लिए कैलेंडर में कई अपवाद जोड़ सकते हैं।

### Q2: मैं कैसे जांच सकता हूं कि कोई विशिष्ट तारीख अपवाद है या नहीं?

 A2: आप इसका उपयोग कर सकते हैं`CheckException()` यह सत्यापित करने की विधि कि कोई विशेष तिथि अपवाद के अंतर्गत आती है या नहीं।

### Q3: क्या किसी कैलेंडर से मौजूदा अपवाद को हटाना संभव है?

 उ3: हां, आप पहुंच कर अपवादों को हटा सकते हैं`Exceptions` कैलेंडर का संग्रह और उसका उपयोग करना`Remove()` तरीका।

### Q4: किस प्रकार के कैलेंडर अपवाद समर्थित हैं?

A4: Aspose.Tasks दैनिक, साप्ताहिक, मासिक और वार्षिक अपवादों सहित विभिन्न प्रकार के अपवादों का समर्थन करता है, जो अपवाद नियमों को परिभाषित करने में लचीलापन प्रदान करता है।

### Q5: क्या मैं विशिष्ट अपवाद तिथियों के लिए कार्य घंटों को अनुकूलित कर सकता हूँ?

A5: हां, आप Aspose.Tasks द्वारा प्रदान की गई उचित विधियों का उपयोग करके व्यक्तिगत अपवाद तिथियों के लिए कस्टम कार्य समय परिभाषित कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
