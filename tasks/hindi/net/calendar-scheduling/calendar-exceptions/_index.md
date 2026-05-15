---
date: 2026-04-13
description: Aspose.Tasks for .NET में कैलेंडर अपवाद को कैसे हटाएँ और ASP.NET कैलेंडर
  शेड्यूलिंग का प्रबंधन करते समय अपवाद तिथि की जाँच करें।
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Aspose.Tasks के साथ कैलेंडर अपवाद हटाएँ
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks के साथ कैलेंडर अपवाद हटाएँ
url: /hi/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ कैलेंडर अपवाद हटाएँ

## परिचय

इस ट्यूटोरियल में, आप Aspose.Tasks का उपयोग करके .NET फ्रेमवर्क में **कैलेंडर अपवाद हटाना** और अन्य कैलेंडर अपवादों का प्रबंधन करना सीखेंगे। कैलेंडर अपवाद आपको छुट्टियों, अस्थायी बंद या किसी भी विशेष अवधि को मॉडल करने की अनुमति देते हैं जहाँ सामान्य कार्य शेड्यूल बदलता है। इन अपवादों को जोड़ना, क्वेरी करना और हटाना समझना सटीक प्रोजेक्ट शेड्यूलिंग के लिए आवश्यक है, विशेष रूप से **ASP.NET कैलेंडर शेड्यूलिंग** परिदृश्यों में काम करते समय।

## त्वरित उत्तर
- **अपवाद हटाने की मुख्य विधि क्या है?** `CalendarException` ऑब्जेक्ट पर `Delete()` मेथड का उपयोग करें।  
- **कौन सा क्लास किसी तिथि को अपवाद के विरुद्ध जांचता है?** `CalendarException.CheckException()`—**अपवाद तिथि जांचने** के लिए उपयोगी।  
- **क्या कोड चलाने के लिए लाइसेंस चाहिए?** हाँ, उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं एक कैलेंडर में कई अपवाद जोड़ सकता हूँ?** बिल्कुल; `Exceptions` कलेक्शन कई एंट्रीज़ का समर्थन करता है।  
- **समर्थित .NET संस्करण?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## कैलेंडर अपवाद क्या है?

**कैलेंडर अपवाद** नियमित कार्य कैलेंडर से विचलन को दर्शाता है—इसे इस तरह समझें कि “इन तिथियों पर कार्य घंटे अलग हैं या बिल्कुल नहीं।” Aspose.Tasks में, प्रत्येक अपवाद के अपने कार्य समय, आवृत्ति पैटर्न, और फ़्लैग हो सकते हैं जो यह संकेत देते हैं कि वह दिन कार्य दिवस है या नहीं।

## ASP.NET कैलेंडर शेड्यूलिंग में कैलेंडर अपवादों का प्रबंधन क्यों करें?

- **सटीक समयरेखा:** प्रोजेक्ट स्वचालित रूप से छुट्टियों और विशेष बंदों का सम्मान करते हैं, जिससे अवास्तविक डेडलाइन से बचा जा सके।  
- **लचीलापन:** आप दैनिक, साप्ताहिक, मासिक, या वार्षिक पैटर्न परिभाषित कर सकते हैं, जो वास्तविक व्यवसाय कैलेंडरों से मेल खाते हैं।  
- **स्वचालन:** प्रोग्रामेटिक रूप से अपवाद तिथि की जांच करने से आप ASP.NET एप्लिकेशन में डायनेमिक शेड्यूलिंग लॉजिक बना सकते हैं।

## आवश्यकताएँ

- C# प्रोग्रामिंग का बुनियादी ज्ञान।  
- Visual Studio (कोई भी नवीनतम संस्करण)।  
- आपके प्रोजेक्ट में Aspose.Tasks for .NET लाइब्रेरी जोड़ें (NuGet या मैन्युअल रेफ़रेंस के माध्यम से)।  

## नेमस्पेस आयात करें

सबसे पहले, उन नेमस्पेस को आयात करें जिनकी आपको आवश्यकता होगी:

```csharp
using Aspose.Tasks;
using System;
```

## चरण 1: कैलेंडर अपवाद हटाएँ

अनचाहे अपवाद को हटाना सरल है। निम्नलिखित कोड एक प्रोजेक्ट लोड करता है, पहला कैलेंडर चुनता है, बुनियादी जानकारी दिखाता है, पहला अपवाद हटाता है, और फिर अपडेटेड काउंट दिखाता है।

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Pro tip:** `Delete()` कॉल करने से पहले हमेशा यह सत्यापित करें कि अपवाद इंडेक्स मौजूद है, ताकि `IndexOutOfRangeException` से बचा जा सके।

## चरण 2: कैलेंडर अपवाद का कार्य समय प्राप्त करें

यदि आपको किसी अपवाद के लिए परिभाषित कार्य घंटों की जाँच करनी है, तो `GetWorkingTime()` का उपयोग करें। यह उदाहरण यह भी दर्शाता है कि `CheckException` के साथ **अपवाद तिथि जांचना** कैसे किया जाता है।

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## चरण 3: कैलेंडर अपवाद निर्धारित करें

नीचे एक पूर्ण walkthrough दिया गया है जो दिखाता है कि कैलेंडर अपवादों को **जोड़ना**, **जांचना**, और **हटाना** कैसे किया जाता है। विशेष क्षण के लिए **अपवाद तिथि जांचने** हेतु `CheckException` के उपयोग पर ध्यान दें।

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## सामान्य समस्याएँ और सुझाव

| समस्या | कारण | समाधान |
|-------|--------|----------|
| **`IndexOutOfRangeException` हटाते समय** | ऐसे अपवाद को हटाने की कोशिश करना जो मौजूद नहीं है। | `Delete()` कॉल करने से पहले `calendar.Exceptions.Count` > इंडेक्स है यह सत्यापित करें। |
| **गलत कार्य समय** | `DayWorking` या `WorkingTimes` को सही ढंग से सेट न करना। | स्पष्ट अवधि निर्धारित करने के लिए `exception.WorkingTimes.Add(new WorkingTime(...))` का उपयोग करें। |
| **अपवाद पहचाना नहीं गया** | `CheckException` `false` लौटाता है क्योंकि तिथि परिभाषित रेंज के बाहर है। | `FromDate`/`ToDate` और `Type` (Daily, Weekly, आदि) को दोबारा जांचें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही कैलेंडर में कई अपवाद जोड़ सकता हूँ?**  
**A:** हाँ, आप आवश्यकतानुसार कई अपवाद जोड़ सकते हैं जो छुट्टियों, रखरखाव विंडो या किसी भी विशेष शेड्यूलिंग नियम को दर्शाते हैं।

**Q: मैं किसी विशिष्ट दिन के लिए **check exception date** कैसे करूँ?**  
**A:** `CalendarException` इंस्टेंस पर `CheckException(DateTime date)` मेथड का उपयोग करें। यह `true` लौटाता है यदि प्रदान की गई तिथि अपवाद रेंज के भीतर आती है।

**Q: क्या कैलेंडर से मौजूदा अपवाद को हटाना संभव है?**  
**A:** बिल्कुल। `Exceptions` कलेक्शन तक पहुँचें और `Remove()` कॉल करें या विशिष्ट `CalendarException` ऑब्जेक्ट पर `Delete()` को इनवोक करें।

**Q: कौन से प्रकार के कैलेंडर अपवाद समर्थित हैं?**  
**A:** Aspose.Tasks Daily, Weekly, Monthly, और Yearly अपवाद प्रकारों को समर्थन देता है, जिससे आप लगभग किसी भी आवृत्ति पैटर्न को मॉडल कर सकते हैं।

**Q: क्या मैं विशिष्ट अपवाद तिथियों के लिए कार्य घंटे कस्टमाइज़ कर सकता हूँ?**  
**A:** हाँ। अपवाद बनाने के बाद, उसकी `WorkingTimes` कलेक्शन को `WorkingTime` ऑब्जेक्ट्स से भरें जो उस दिन के प्रारम्भ और समाप्ति समय को परिभाषित करते हैं।

## निष्कर्ष

हमने **कैलेंडर अपवाद हटाने** ऑपरेशनों के पूरे जीवनचक्र को देखा, मौजूदा अपवादों की जाँच से लेकर नए जोड़ने और तिथियों की जांच तक। इन तकनीकों में निपुणता यह सुनिश्चित करती है कि आपके प्रोजेक्ट शेड्यूल वास्तविक कैलेंडरों का सम्मान करें, जिससे आपका ASP.NET कैलेंडर शेड्यूलिंग कार्यान्वयन मजबूत और विश्वसनीय बनता है।

---

**अंतिम अद्यतन:** 2026-04-13  
**परीक्षित संस्करण:** Aspose.Tasks for .NET (latest release)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}