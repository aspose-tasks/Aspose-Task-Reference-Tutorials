---
title: Aspose.Tasks में दैनिक कार्य दोहराव
linktitle: Aspose.Tasks में दैनिक कार्य दोहराव
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों में दैनिक आवर्ती कार्य बनाना सीखें। सहजता से उत्पादकता और संगठन को बढ़ावा दें।
weight: 26
url: /hi/net/calendar-scheduling/daily-work-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में दैनिक कार्य दोहराव

## परिचय

.NET के लिए Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों में आसानी से हेरफेर करने में सक्षम बनाती है। इसकी असंख्य विशेषताओं में आवर्ती कार्यों को कुशलतापूर्वक संभालने की क्षमता है। इस ट्यूटोरियल में, हम दैनिक कार्य दोहराव कार्यक्षमता के बारे में विस्तार से जानेंगे, जो एक प्रोजेक्ट के भीतर प्रतिदिन दोहराए जाने वाले कार्यों के निर्माण की अनुमति देता है।

## आवश्यक शर्तें

इस ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- C# और .NET फ्रेमवर्क का बुनियादी ज्ञान।
- आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित है।
-  .NET लाइब्रेरी के लिए Aspose.Tasks। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
- Microsoft प्रोजेक्ट फ़ाइलों (.mpp) से परिचित होना।

## नामस्थान आयात करें

शुरू करने से पहले, सुनिश्चित करें कि आप आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

आइए दिए गए उदाहरण को कई चरणों में तोड़ें:

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

सबसे पहले, का उपयोग करके प्रोजेक्ट फ़ाइल लोड करें`Project` कक्षा:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## चरण 2: आवर्ती कार्य पैरामीटर्स को परिभाषित करें

आवर्ती कार्य के लिए पैरामीटर परिभाषित करें:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## चरण 3: कैलेंडर और कार्य आरंभ तिथि निर्धारित करें

कार्य के लिए कैलेंडर और आरंभ तिथि निर्धारित करें:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया कि दैनिक कार्य पुनरावृत्ति के साथ आवर्ती कार्य बनाने के लिए .NET के लिए Aspose.Tasks का उपयोग कैसे करें। इन चरणों का पालन करके, आप सुचारू वर्कफ़्लो और संगठन सुनिश्चित करते हुए, अपनी परियोजनाओं के भीतर कार्यों को कुशलतापूर्वक प्रबंधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं पुनरावृत्ति पैटर्न को और अधिक अनुकूलित कर सकता हूँ?

A1: हाँ, आप अपनी आवश्यकताओं के अनुसार पुनरावृत्ति पैटर्न को तैयार करने के लिए आरंभ तिथि, घटना संख्या और पुनरावृत्ति अंतराल जैसे मापदंडों को समायोजित कर सकते हैं।

### Q2: क्या Aspose.Tasks Microsoft प्रोजेक्ट के विभिन्न संस्करणों के साथ संगत है?

A2: हां, Aspose.Tasks संगतता और निर्बाध एकीकरण सुनिश्चित करते हुए Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।

### Q3: मैं आवर्ती कार्यों में अपवादों या संशोधनों को कैसे संभाल सकता हूँ?

A3: Aspose.Tasks लचीलेपन और अनुकूलन की अनुमति देते हुए, आवर्ती कार्यों के भीतर अपवादों और संशोधनों को प्रबंधित करने के लिए मजबूत कार्यक्षमता प्रदान करता है।

### Q4: क्या मैं प्रोजेक्ट को विभिन्न प्रारूपों में निर्यात कर सकता हूँ?

A4: बिल्कुल, Aspose.Tasks पीडीएफ, HTML, XML और अधिक सहित विभिन्न प्रारूपों में परियोजनाओं को निर्यात करने के लिए समर्थन प्रदान करता है, जिससे आसान साझाकरण और सहयोग की सुविधा मिलती है।

### Q5: क्या Aspose.Tasks तकनीकी सहायता प्रदान करता है?

A5: हाँ, Aspose.Tasks अपने फ़ोरम के माध्यम से व्यापक तकनीकी सहायता प्रदान करता है, जहाँ आप सहायता प्राप्त कर सकते हैं, अनुभव साझा कर सकते हैं और साथी उपयोगकर्ताओं के साथ जुड़ सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
