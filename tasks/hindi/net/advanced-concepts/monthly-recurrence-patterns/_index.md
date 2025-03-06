---
title: Aspose.Tasks में मासिक पुनरावृत्ति पैटर्न को संभालना
linktitle: Aspose.Tasks में मासिक पुनरावृत्ति पैटर्न को संभालना
second_title: Aspose.Tasks .NET API
description: इस चरण-दर-चरण ट्यूटोरियल के साथ सीखें कि .NET के लिए Aspose.Tasks में मासिक पुनरावृत्ति पैटर्न को कैसे संभालें।
type: docs
weight: 18
url: /hi/net/advanced-concepts/monthly-recurrence-patterns/
---
## परिचय

.NET के लिए Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देता है। इसके द्वारा प्रदान की जाने वाली आवश्यक कार्यक्षमताओं में से एक आवर्ती कार्यों को कुशलतापूर्वक संभालने की क्षमता है। इस ट्यूटोरियल में, हम चरण दर चरण Aspose.Tasks का उपयोग करके मासिक पुनरावृत्ति पैटर्न के साथ कैसे काम करें, इस पर विस्तार से चर्चा करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपने निम्नलिखित शर्तें स्थापित कर ली हैं:

## नामस्थान आयात करें

सबसे पहले, सुनिश्चित करें कि आपने अपने .NET प्रोजेक्ट में आवश्यक नेमस्पेस आयात कर लिया है:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

अब, आइए मासिक पुनरावृत्ति पैटर्न को संभालने की प्रक्रिया को कई चरणों में विभाजित करें:

## चरण 1: प्रोजेक्ट प्रारंभ करें

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## चरण 2: आवर्ती कार्य पैरामीटर सेट करें

कार्य नाम, अवधि और पुनरावृत्ति पैटर्न सहित आवर्ती कार्य के लिए पैरामीटर परिभाषित करें:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## चरण 3: प्रोजेक्ट में पैरामीटर जोड़ें

```csharp
project.RootTask.Children.Add(parameters);
```

## चरण 4: प्रोजेक्ट सहेजें

संशोधित प्रोजेक्ट को आवर्ती कार्य के साथ सहेजें:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## निष्कर्ष

.NET के लिए Aspose.Tasks में मासिक पुनरावृत्ति पैटर्न को संभालना सीधा और कुशल है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप विशिष्ट मासिक अंतराल और पुनरावृत्ति श्रेणियों के साथ आसानी से आवर्ती कार्य बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के सभी संस्करणों के साथ संगत है?

A1: Aspose.Tasks MPP, MPT, XML और MPX सहित Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।

### Q2: क्या मैं पुनरावृत्ति पैटर्न को और अधिक अनुकूलित कर सकता हूँ?

A2: हां, Aspose.Tasks दैनिक, साप्ताहिक, मासिक और वार्षिक सहित पुनरावृत्ति पैटर्न को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।

### Q3: क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 उ3: हाँ, आप वेबसाइट से Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q4: मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 A4: आप सहायता मांग सकते हैं और चर्चा में भाग ले सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).

### Q5: मैं Aspose.Tasks के लिए लाइसेंस कहां से खरीद सकता हूं?

 A5: आप वेबसाइट से Aspose.Tasks के लिए लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy)