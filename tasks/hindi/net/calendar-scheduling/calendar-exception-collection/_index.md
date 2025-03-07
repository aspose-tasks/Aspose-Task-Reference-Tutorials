---
title: Aspose.Tasks में कैलेंडर अपवादों का संग्रह
linktitle: Aspose.Tasks में कैलेंडर अपवादों का संग्रह
second_title: Aspose.Tasks .NET API
description: सटीक शेड्यूलिंग और संसाधन प्रबंधन सुनिश्चित करते हुए, Aspose.Tasks का उपयोग करके अपने .NET प्रोजेक्ट्स में कैलेंडर अपवादों को कुशलतापूर्वक संभालने का तरीका जानें।
weight: 13
url: /hi/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कैलेंडर अपवादों का संग्रह

## परिचय

परियोजना प्रबंधन में, सफलता के लिए सटीक शेड्यूलिंग महत्वपूर्ण है। हालाँकि, वास्तविक दुनिया के परिदृश्यों में अक्सर छुट्टियों, विशेष आयोजनों या अन्य कारकों के कारण मानक कार्यक्रम से विचलन की आवश्यकता होती है। .NET के लिए Aspose.Tasks अपने कैलेंडर अपवाद संग्रह सुविधा के माध्यम से ऐसे अपवादों को प्रबंधित करने के लिए एक मजबूत समाधान प्रदान करता है। यह ट्यूटोरियल चरण दर चरण इस कार्यक्षमता का उपयोग करने की प्रक्रिया में आपका मार्गदर्शन करेगा।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1.  .NET के लिए Aspose.Tasks: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना उदाहरणों को समझने में सहायक होगा।
3. विकास परिवेश: अपना पसंदीदा विकास परिवेश सेट करें, जैसे विज़ुअल स्टूडियो या जेटब्रेन राइडर।

## नामस्थान आयात करें

इससे पहले कि आप .NET के लिए Aspose.Tasks के साथ काम करना शुरू करें, आपको अपने प्रोजेक्ट में आवश्यक नेमस्पेस आयात करना होगा। यह चरण आपको कैलेंडर अपवादों को प्रबंधित करने के लिए आवश्यक कक्षाओं और विधियों तक पहुंचने में सक्षम बनाता है।

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

अब, आइए दिए गए उदाहरण को कई चरणों में तोड़ें:

## चरण 1: प्रोजेक्ट लोड करें और कैलेंडर पुनर्प्राप्त करें

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

इस चरण में, हम एक प्रोजेक्ट फ़ाइल लोड करते हैं और उसके यूआईडी द्वारा वांछित कैलेंडर पुनर्प्राप्त करते हैं।

## चरण 2: मौजूदा अपवाद साफ़ करें और मानक कैलेंडर सेट करें

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

यह चरण कैलेंडर से किसी भी मौजूदा अपवाद को साफ़ करता है और इसे एक मानक कॉन्फ़िगरेशन पर सेट करता है।

## चरण 3: कार्य समय अपवाद को परिभाषित करें और जोड़ें

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

यह चरण विशिष्ट प्रारंभ और समाप्ति तिथियों के साथ-साथ उन तिथियों के भीतर कार्य समय के साथ कार्य समय अपवाद को परिभाषित करता है, और इसे कैलेंडर में जोड़ता है।

## चरण 4: गैर-कार्य समय अपवादों को परिभाषित करें और जोड़ें

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// यदि आवश्यक हो तो और अपवाद जोड़ें

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

यह चरण छुट्टियों जैसे गैर-कार्य समय अपवादों को परिभाषित करता है, और उन्हें कैलेंडर में जोड़ता है।

## चरण 5: कैलेंडर अपवाद प्रदर्शित करें

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

यह चरण जोड़े गए कैलेंडर अपवादों को उनके विवरण के साथ प्रदर्शित करता है।

## चरण 6: सभी अपवाद हटाएँ

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

अंत में, यह चरण कैलेंडर से सभी अपवादों को हटा देता है।

## निष्कर्ष

सटीक प्रोजेक्ट शेड्यूलिंग के लिए कैलेंडर अपवादों को प्रबंधित करना महत्वपूर्ण है। .NET के लिए Aspose.Tasks कैलेंडर अपवाद संग्रह सहित सुविधाओं का एक व्यापक सेट प्रदान करके इस कार्य को सरल बनाता है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप अपनी परियोजनाओं के भीतर विभिन्न शेड्यूलिंग परिदृश्यों को कुशलतापूर्वक संभाल सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं एक ही कैलेंडर में एकाधिक अपवाद जोड़ सकता हूँ?

 A1: हां, आप इसका उपयोग करके कैलेंडर में एकाधिक अपवाद जोड़ सकते हैं`AddRange` तरीका।

### Q2: मैं साप्ताहिक छुट्टियों जैसे आवर्ती अपवादों को कैसे संभाल सकता हूँ?

A2: आप प्रोग्रामेटिक रूप से आवर्ती अपवादों की गणना कर सकते हैं और कस्टम तर्क का उपयोग करके उन्हें कैलेंडर में जोड़ सकते हैं।

### Q3: क्या बाहरी स्रोतों से कैलेंडर अपवाद आयात करना संभव है?

उ3: हाँ, आप डेटाबेस या सीएसवी फ़ाइलों जैसे बाहरी स्रोतों से कैलेंडर अपवाद पढ़ सकते हैं और उन्हें अपने प्रोजेक्ट में एकीकृत कर सकते हैं।

### Q4: यदि कैलेंडर में ओवरलैपिंग अपवाद हों तो क्या होगा?

A4: .NET के लिए Aspose.Tasks आपको अपनी परियोजना आवश्यकताओं के आधार पर प्राथमिकताओं को परिभाषित करने या संघर्षों को हल करके ओवरलैपिंग अपवादों को संभालने की अनुमति देता है।

### Q5: क्या मैं अपवाद के रूप में प्रत्येक दिन के लिए कार्य समय को अनुकूलित कर सकता हूँ?

A5: हां, आप विशिष्ट शेड्यूलिंग आवश्यकताओं को समायोजित करने के लिए अपवाद के भीतर अलग-अलग दिनों के लिए कस्टम कार्य समय निर्दिष्ट कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
