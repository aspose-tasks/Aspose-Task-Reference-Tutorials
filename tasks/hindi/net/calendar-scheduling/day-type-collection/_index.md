---
title: Aspose.Tasks में दिवस प्रकार संग्रह का प्रबंधन
linktitle: Aspose.Tasks में दिवस प्रकार संग्रह का प्रबंधन
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks में दिन-प्रकार के संग्रहों को कुशलतापूर्वक प्रबंधित करना सीखें। आसानी से कैलेंडर अपवाद बनाएं, संशोधित करें और हेरफेर करें।
type: docs
weight: 28
url: /hi/net/calendar-scheduling/day-type-collection/
---
## परिचय

 .NET के लिए Aspose.Tasks दिन प्रकार के संग्रह के प्रबंधन के लिए मजबूत कार्यक्षमता प्रदान करता है, जो परियोजना प्रबंधन अनुप्रयोगों में साप्ताहिक कैलेंडर अपवादों को परिभाषित करने के लिए महत्वपूर्ण है। इस ट्यूटोरियल में, हम जानेंगे कि इसका उपयोग कैसे करें`DayTypeCollection` कक्षा कुशलतापूर्वक. 

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल के साथ आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1. विजुअल स्टूडियो: सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
2.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क अवधारणाओं से परिचित।

## नामस्थान आयात करें

आरंभ करने के लिए, आपको अपने C# प्रोजेक्ट में आवश्यक नामस्थान आयात करने होंगे:

```csharp
using Aspose.Tasks;
using System;


```

अब, आइए दिए गए उदाहरण को कई चरणों में तोड़ें:

## चरण 1: प्रोजेक्ट लोड करें और कैलेंडर एक्सेस करें

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

यह चरण एक नए प्रोजेक्ट इंस्टेंस को आरंभ करता है और उसके यूआईडी द्वारा कैलेंडर को पुनः प्राप्त करता है।

## चरण 2: कैलेंडर अपवादों के माध्यम से पुनरावृति करें

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

यहां, हम प्रत्येक कैलेंडर अपवाद को दोहराते हैं और उसका नाम और संबंधित दिन प्रकार प्रिंट करते हैं।

## चरण 3: कैलेंडर अपवाद संशोधित करें

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

यह चरण दर्शाता है कि दिन के प्रकारों को जोड़कर, हटाकर या अपडेट करके कैलेंडर अपवादों को कैसे संशोधित किया जाए।

## चरण 4: नए कैलेंडर अपवाद बनाएं और उनमें हेरफेर करें

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

इस अंतिम चरण में, हम नए कैलेंडर अपवाद बनाते हैं और दिन के प्रकारों को जोड़कर और कॉपी करके उनमें हेरफेर करते हैं।

## निष्कर्ष

 निष्कर्ष में, परियोजना प्रबंधन अनुप्रयोगों में साप्ताहिक कैलेंडर अपवादों को परिभाषित करने और संशोधित करने के लिए .NET के लिए Aspose.Tasks में दिन प्रकार के संग्रह का प्रबंधन करना आवश्यक है। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप इसका प्रभावी ढंग से उपयोग कर सकते हैं`DayTypeCollection` विभिन्न कैलेंडर परिचालनों को संभालने के लिए कक्षा।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या .NET के लिए Aspose.Tasks का उपयोग प्रोग्रामेटिक रूप से गैंट चार्ट बनाने के लिए किया जा सकता है?

A1: हां, .NET के लिए Aspose.Tasks .NET अनुप्रयोगों में गैंट चार्ट बनाने और उनमें हेरफेर करने के लिए एपीआई प्रदान करता है।

### Q2: क्या .NET के लिए Aspose.Tasks .NET कोर और .NET फ्रेमवर्क दोनों के साथ संगत है?

A2: हाँ, .NET के लिए Aspose.Tasks .NET कोर और .NET फ्रेमवर्क दोनों का समर्थन करता है।

### Q3: मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 उ3: आप पर जाकर समर्थन प्राप्त कर सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) जहां आप प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं के साथ बातचीत कर सकते हैं।

### Q4: क्या .NET के लिए Aspose.Tasks निःशुल्क परीक्षण की पेशकश करता है?

 उ4: हाँ, आप .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q5: क्या मैं .NET के लिए Aspose.Tasks के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?

 A5: हाँ, अस्थायी लाइसेंस खरीद के लिए उपलब्ध हैं[Aspose वेबसाइट](https://purchase.aspose.com/temporary-license/).