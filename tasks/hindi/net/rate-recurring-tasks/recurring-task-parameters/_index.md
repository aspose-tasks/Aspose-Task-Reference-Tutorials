---
title: Aspose.Tasks में आवर्ती कार्य पैरामीटर सेट करना
linktitle: Aspose.Tasks में आवर्ती कार्य पैरामीटर सेट करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट में आवर्ती कार्य पैरामीटर सेट करना सीखें। चरण-दर-चरण मार्गदर्शिका के साथ व्यापक ट्यूटोरियल।
weight: 14
url: /hi/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में आवर्ती कार्य पैरामीटर सेट करना

## परिचय
इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट आवर्ती कार्य पैरामीटर सेट करने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. C# प्रोग्रामिंग भाषा की बुनियादी समझ।
2. विज़ुअल स्टूडियो या कोई अन्य C# IDE स्थापित किया गया।
3. .NET लाइब्रेरी के लिए Aspose.Tasks आपके प्रोजेक्ट में स्थापित और संदर्भित हैं।

## नामस्थान आयात करें
सबसे पहले, आपको अपने C# कोड में आवश्यक नामस्थान आयात करने की आवश्यकता है:
```csharp
using Aspose.Tasks;
using System;

```
## चरण 1: दस्तावेज़ निर्देशिका को परिभाषित करें
```csharp
String DataDir = "Your Document Directory";
```
 प्रतिस्थापित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के पथ के साथ।
## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 कोड की यह पंक्ति Microsoft प्रोजेक्ट फ़ाइल को इसमें लोड करती है`project` चर।
## चरण 3: आवर्ती कार्य पैरामीटर्स को परिभाषित करें
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
यहां, आप आवर्ती कार्य के लिए मापदंडों को परिभाषित करते हैं जैसे कार्य का नाम, अवधि, पुनरावृत्ति पैटर्न, पुनरावृत्ति सीमा, और संसाधन कैलेंडर को अनदेखा करना है या नहीं।
## चरण 4: आवर्ती कार्य के लिए कैलेंडर सेट करें
```csharp
parameters.SetCalendar(project, "Standard");
```
यह चरण आवर्ती कार्य के लिए कैलेंडर सेट करता है। इस उदाहरण में, यह कैलेंडर को "मानक" पर सेट करता है।
## चरण 5: प्रोजेक्ट में पैरामीटर जोड़ें
```csharp
project.RootTask.Children.Add(parameters);
```
अंत में, प्रोजेक्ट के रूट कार्य में पैरामीटर जोड़ें।

## निष्कर्ष
इस ट्यूटोरियल में, हमने दिखाया है कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट आवर्ती कार्य पैरामीटर कैसे सेट करें। इन चरणों का पालन करके, आप अपनी परियोजनाओं में आवर्ती कार्यों को कुशलतापूर्वक प्रबंधित कर सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या मैं पुनरावृत्ति पैटर्न को और अधिक अनुकूलित कर सकता हूँ?
हां, Aspose.Tasks आपकी परियोजना आवश्यकताओं के अनुसार अनुकूलित करने के लिए विभिन्न पुनरावृत्ति पैटर्न और विकल्प प्रदान करता है।
### क्या खरीदने से पहले कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप Aspose.Tasks से निःशुल्क परीक्षण डाउनलोड कर सकते हैं[वेबसाइट](https://purchase.aspose.com/buy) पुस्तकालय की विशेषताओं का मूल्यांकन करना।
### क्या Aspose.Tasks अन्य प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है?
हाँ, Aspose.Tasks MPP, XML, XLSX और अन्य सहित विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### यदि कार्यान्वयन के दौरान मुझे कोई समस्या आती है तो क्या मुझे सहायता मिल सकती है?
हाँ, आप समुदाय से सहायता के लिए Aspose.Tasks फ़ोरम पर जा सकते हैं या सीधे सहायता के लिए समर्थन से संपर्क कर सकते हैं।
### मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 आप से अस्थायी लाइसेंस प्राप्त कर सकते हैं[वेबसाइट](https://purchase.aspose.com/temporary-license/) परीक्षण प्रयोजनों के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
