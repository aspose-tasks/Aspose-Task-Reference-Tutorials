---
date: 2026-04-01
description: Aspose.Tasks for .NET में पुनरावृत्ति सेट करना सीखें, आवर्ती कार्य जोड़ें
  और महीने, सप्ताह और दिन के अनुसार आवर्ती कार्यों को स्वचालित करें।
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Aspose.Tasks में माह, सप्ताह, दिन के अनुसार पुनरावृत्ति
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में पुनरावृत्ति कैसे सेट करें (महीना, सप्ताह, दिन)
url: /hi/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में आवृत्ति सेट करने का तरीका (माह, सप्ताह, दिन)

## परिचय

यदि आपको प्रोजेक्ट में कार्यों के लिए **how to set recurrence** की आवश्यकता है, तो Aspose.Tasks for .NET आपको एक साफ़, प्रोग्रामेटिक तरीका देता है जिससे आप मासिक, साप्ताहिक या दैनिक चलने वाली आवर्ती कार्य परिभाषाएँ जोड़ सकते हैं। इस ट्यूटोरियल में हम एक वास्तविक उदाहरण के माध्यम से दिखाएंगे कि कैसे **add recurring task** प्रविष्टियाँ **automate recurring tasks** जोड़ें और उन्हें सीधे C# कोड से प्रबंधित करें। अंत तक, आप इस क्षमता को किसी भी शेड्यूलिंग या प्रोजेक्ट‑मैनेजमेंट समाधान में एकीकृत करने के लिए तैयार होंगे।

## त्वरित उत्तर
- **Aspose.Tasks में “recurrence” का क्या अर्थ है?** यह एक पैटर्न (दैनिक, साप्ताहिक, मासिक) को परिभाषित करता है जो तिथि सीमा पर स्वचालित रूप से कार्य उदाहरण बनाता है।  
- **कौन सा मुख्य मेथड आवृत्ति बनाता है?** `RecurringTaskParameters` को एक विशिष्ट `RecurrencePattern` के साथ मिलाकर।  
- **क्या इस कोड को चलाने के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं मासिक के बजाय साप्ताहिक कार्य शेड्यूल कर सकता हूँ?** हाँ – `MonthlyRecurrencePattern` को `WeeklyRecurrencePattern` से बदलें।  
- **कौन से .NET संस्करण समर्थित हैं?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 और बाद के संस्करण।

## Aspose.Tasks में आवृत्ति क्या है?

आवृत्ति नियमों का एक सेट है जो Aspose.Tasks को नियमित अंतराल—दैनिक, साप्ताहिक या मासिक—पर कार्य उदाहरण उत्पन्न करने के लिए कहता है, बिना उन्हें मैन्युअल रूप से डुप्लिकेट किए। यह सुविधा उन प्रोजेक्ट्स के लिए आवश्यक है जिनमें नियमित गतिविधियाँ जैसे स्थिति मीटिंग, निरीक्षण या रखरखाव कार्य शामिल होते हैं।

## आवृत्ति सुविधाओं का उपयोग क्यों करें?

- **समय बचाएँ:** कार्यों को मैन्युअल रूप से कॉपी‑पेस्ट करने की आवश्यकता नहीं।  
- **त्रुटियों को कम करें:** लाइब्रेरी लगातार तिथियों और अवधि को सुनिश्चित करती है।  
- **लचीलापन:** पैटर्न को मिलाएँ (जैसे, “हर 2 महीने का पहला रविवार”)।  
- **स्वचालन:** CI पाइपलाइन या रिपोर्टिंग टूल में शेड्यूल बनाने के लिए उत्तम।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **C# की बुनियादी समझ** – आप कुछ पंक्तियों का C# कोड लिखेंगे।  
2. **Aspose.Tasks for .NET स्थापित** – इसे [download page](https://releases.aspose.com/tasks/net/) से प्राप्त करें।  
3. **एक .mpp प्रोजेक्ट फ़ाइल** – हम स्रोत फ़ाइल के रूप में `Project1.mpp` का उपयोग करेंगे।

## नेमस्पेस आयात करें

शुरू करने के लिए, आवश्यक Aspose.Tasks नेमस्पेस आयात करें:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

हम एक `Project` इंस्टेंस बनाते हैं जो मौजूदा Microsoft Project फ़ाइल की ओर संकेत करता है।

### चरण 2: आवर्ती कार्य पैरामीटर परिभाषित करें

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

यहाँ हम **आवर्ती कार्य** पैरामीटर बनाते हैं:

- **TaskName** – उत्पन्न कार्य का नाम।  
- **Duration** – प्रत्येक घटना की अवधि।  
- **RecurrencePattern** – एक मासिक पैटर्न जो हर 2 महीने में पहले रविवार को दोहराता है।  
- **RecurrenceRange** – शेड्यूल को सीमित करने की प्रारंभ और समाप्ति तिथियाँ।

### चरण 3: प्रोजेक्ट में आवर्ती कार्य जोड़ें

```csharp
project.RootTask.Children.Add(parameters);
```

यह पंक्ति **आवर्ती कार्य** को प्रोजेक्ट पदानुक्रम के मूल में जोड़ती है।

### चरण 4: अपडेटेड प्रोजेक्ट सहेजें

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

प्रोजेक्ट को एक नई `.mpp` फ़ाइल के रूप में सहेजा जाता है जिसमें अब स्वचालित शेड्यूल शामिल है।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|--------|-----|
| **कार्य नहीं दिख रहा है** | आवृत्ति सीमा प्रोजेक्ट तिथियों के बाहर है। | सत्यापित करें कि `Start` और `Finish` मान प्रोजेक्ट कैलेंडर के भीतर हैं। |
| **गलत सप्ताह का दिन** | `WeekDay` एन्‍युम मेल नहीं खाता। | आवश्यकतानुसार `DayOfWeek.Monday` … `DayOfWeek.Sunday` का उपयोग करें। |
| **लाइसेंस अपवाद** | उत्पादन में वैध लाइसेंस के बिना चल रहा है। | सहेजने से पहले एक अस्थायी या पूर्ण लाइसेंस लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: क्या मैं प्रदान किए गए उदाहरणों से आगे आवृत्ति पैटर्न को अनुकूलित कर सकता हूँ?

A1: हाँ, Aspose.Tasks for .NET आवृत्ति पैटर्न के लिए व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे आप उन्हें अपनी विशिष्ट आवश्यकताओं के अनुसार ढाल सकते हैं।

### प्रश्न 2: क्या Aspose.Tasks for .NET के लिए ट्रायल संस्करण उपलब्ध है?

A2: हाँ, आप [releases page](https://releases.aspose.com/) से Aspose.Tasks for .NET का मुफ्त ट्रायल प्राप्त कर सकते हैं।

### प्रश्न 3: मैं Aspose.Tasks for .NET के लिए समर्थन कैसे प्राप्त कर सकता हूँ?

A3: आप [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर सहायता ले सकते हैं और समुदाय के साथ जुड़ सकते हैं।

### प्रश्न 4: क्या Aspose.Tasks for .NET के लिए अस्थायी लाइसेंस उपलब्ध हैं?

A4: हाँ, आप परीक्षण और मूल्यांकन के लिए [purchase page](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस प्राप्त कर सकते हैं।

### प्रश्न 5: मैं Aspose.Tasks for .NET के लिए व्यापक दस्तावेज़ीकरण कहाँ पा सकता हूँ?

A5: आप लाइब्रेरी के उपयोग पर विस्तृत मार्गदर्शन के लिए Aspose वेबसाइट पर उपलब्ध विस्तृत [documentation](https://reference.aspose.com/tasks/net/) को देख सकते हैं।

---

**अंतिम अपडेट:** 2026-04-01  
**परीक्षित संस्करण:** Aspose.Tasks 24.11 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}