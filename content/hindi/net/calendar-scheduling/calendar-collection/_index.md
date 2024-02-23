---
title: Aspose में कैलेंडर संग्रह का प्रबंधन। कार्य
linktitle: Aspose में कैलेंडर संग्रह का प्रबंधन। कार्य
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks में कैलेंडर संग्रहों को कुशलतापूर्वक कैसे प्रबंधित किया जाए। आसानी से कैलेंडर बनाएं, संशोधित करें और उनमें हेरफेर करें।
type: docs
weight: 11
url: /hi/net/calendar-scheduling/calendar-collection/
---
## परिचय

इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks में कैलेंडर संग्रह कैसे प्रबंधित करें। कार्यदिवसों, छुट्टियों और अपवादों को परिभाषित करने में कैलेंडर परियोजना प्रबंधन में महत्वपूर्ण भूमिका निभाते हैं। Aspose.Tasks आपकी परियोजनाओं के भीतर कैलेंडर में हेरफेर करने के लिए मजबूत कार्यक्षमता प्रदान करता है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. विजुअल स्टूडियो: .NET विकास के लिए विजुअल स्टूडियो या कोई अन्य संगत आईडीई स्थापित करें।
2.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा।

## नामस्थान आयात करें

सबसे पहले, आइए Aspose.Tasks के साथ काम करने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## एक नया कैलेंडर बनाना

###  चरण 1: एक नया प्रारंभ करें`Project` object.
```csharp
var project = new Project();
```

### चरण 2: प्रोजेक्ट के कैलेंडर संग्रह में कैलेंडर जोड़ें।
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### चरण 3: कैलेंडरों को दोबारा दोहराएं और उनके नाम प्रदर्शित करें।
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## कैलेंडर को नये कैलेंडर से बदलना

### चरण 1: किसी मौजूदा प्रोजेक्ट को लोड करें।
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### चरण 2: मौजूदा कैलेंडर हटाएं (यदि मौजूद है)।
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### चरण 3: एक नया कैलेंडर जोड़ें.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## नाम या आईडी के आधार पर कैलेंडर प्राप्त करना

### चरण 1: प्रोजेक्ट लोड करें.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### चरण 2: नाम या यूआईडी द्वारा कैलेंडर पुनर्प्राप्त करें।
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### चरण 3: कैलेंडर विवरण प्रदर्शित करें।
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## कैलेंडरों पर पुनरावृत्ति

### चरण 1: प्रोजेक्ट लोड करें.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### चरण 2: कैलेंडरों की गिनती पुनः प्राप्त करें।
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### चरण 3: कैलेंडर संग्रह और प्रदर्शन नामों पर पुनरावृति करें।
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## एक मानक कैलेंडर बनाना

### चरण 1: एक नया प्रोजेक्ट प्रारंभ करें।
```csharp
var project = new Project();
```

### चरण 2: एक नया कैलेंडर परिभाषित करें और इसे मानक बनाएं।
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### चरण 3: प्रोजेक्ट सहेजें.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## निष्कर्ष

प्रभावी परियोजना प्रबंधन के लिए .NET के लिए Aspose.Tasks में कैलेंडर संग्रह प्रबंधित करना आवश्यक है। प्रदान की गई कार्यक्षमताओं के साथ, आप अपनी परियोजना आवश्यकताओं के अनुसार कुशलतापूर्वक कैलेंडर बना सकते हैं, संशोधित कर सकते हैं और उनमें हेरफेर कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.Tasks में कस्टम कार्यदिवस बना सकता हूँ?

A1: हाँ, आप कैलेंडर में अपवाद जोड़कर कस्टम कार्यदिवस बना सकते हैं।

### Q2: क्या Microsoft प्रोजेक्ट फ़ाइलों से कैलेंडर आयात करना संभव है?

A2: बिल्कुल, Aspose। कार्य Microsoft प्रोजेक्ट फ़ाइलों से कैलेंडर आयात करने का समर्थन करता है।

### Q3: मैं किसी प्रोजेक्ट से एक विशिष्ट कैलेंडर कैसे हटा सकता हूँ?

उ3: आप किसी कैलेंडर को संग्रह से प्राप्त करके और फिर कॉल करके हटा सकते हैं`Remove` तरीका।

### Q4: क्या Aspose.Tasks विभिन्न प्रारूपों में कैलेंडर निर्यात करने का समर्थन करता है?

A4: हां, Aspose.Tasks XML, MPP आदि जैसे विभिन्न प्रारूपों में कैलेंडर निर्यात करने की अनुमति देता है।

### Q5: क्या मैं कैलेंडर में विशिष्ट दिनों के लिए कार्य घंटों को अनुकूलित कर सकता हूँ?

A5: निश्चित रूप से, आप कैलेंडर में अपवादों का उपयोग करके अलग-अलग दिनों के लिए कार्य घंटे परिभाषित कर सकते हैं।