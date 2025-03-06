---
title: Aspose.Tasks में माह दिवस के अनुसार पुनरावृत्ति
linktitle: Aspose.Tasks में माह दिवस के अनुसार पुनरावृत्ति
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks के साथ .NET परियोजनाओं में आवर्ती कार्यों को प्रबंधित करना सीखें। महीने के दिन के अनुसार पुनरावृत्ति से निपटने के लिए चरण-दर-चरण मार्गदर्शिका।
weight: 25
url: /hi/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में माह दिवस के अनुसार पुनरावृत्ति

## परिचय

.NET विकास के क्षेत्र में, Aspose.Tasks परियोजना कार्यों और शेड्यूल के प्रबंधन के लिए एक शक्तिशाली उपकरण के रूप में खड़ा है। यह आवर्ती कार्यों को संभालने सहित परियोजना प्रबंधन वर्कफ़्लो को सुव्यवस्थित करने के लिए ढेर सारी कार्यक्षमताएँ प्रदान करता है। प्रोजेक्ट शेड्यूलिंग में महीने के दिन के अनुसार दोहराव एक सामान्य आवश्यकता है, और Aspose.Tasks इस परिदृश्य के लिए मजबूत समर्थन प्रदान करता है।

## आवश्यक शर्तें

ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1. C# की बुनियादी समझ: इस ट्यूटोरियल में चर्चा की गई अवधारणाओं को समझने के लिए C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।
2. .NET के लिए Aspose.Tasks की स्थापना: सुनिश्चित करें कि आपने .NET के लिए Aspose.Tasks स्थापित कर लिया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
3. एकीकृत विकास पर्यावरण (आईडीई): कोडिंग सुविधा के लिए अपने सिस्टम पर विजुअल स्टूडियो जैसा एक आईडीई स्थापित करें।

## नामस्थान आयात करें

अपने C# प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

आइए दिए गए कोड उदाहरण को चरण-दर-चरण मार्गदर्शिका प्रारूप में विभाजित करें:

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
// वें दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 कोड की यह पंक्ति एक नए उदाहरण को प्रारंभ करती है`Project` क्लास, "Project1.mpp" नामक प्रोजेक्ट फ़ाइल लोड कर रहा है।

## चरण 2: आवर्ती कार्य पैरामीटर्स को परिभाषित करें

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

यह अनुभाग आवर्ती कार्य के लिए पैरामीटर को परिभाषित करता है, जिसमें उसका नाम, अवधि, दोहराव पैटर्न और पुनरावृत्ति सीमा शामिल है।

## चरण 3: प्रोजेक्ट में कार्य जोड़ें

```csharp
project.RootTask.Children.Add(parameters);
```

यहां, हम प्रोजेक्ट में आवर्ती कार्य पैरामीटर जोड़ते हैं।

## चरण 4: प्रोजेक्ट फ़ाइल सहेजें

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

अंत में, संशोधित प्रोजेक्ट अतिरिक्त आवर्ती कार्य के साथ सहेजा जाता है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि .NET के लिए Aspose.Tasks में महीने के दिन के अनुसार पुनरावृत्ति को कैसे संभालना है। दिए गए चरणों का पालन करके, आप अपने प्रोजेक्ट शेड्यूल के भीतर आवर्ती कार्यों को कुशलतापूर्वक प्रबंधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या Aspose.Tasks .NET के सभी संस्करणों के साथ संगत है?

A1: Aspose.Tasks .NET फ्रेमवर्क के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न वातावरणों में अनुकूलता सुनिश्चित करता है।

### Q2: क्या मैं पुनरावृत्ति पैटर्न को और अधिक अनुकूलित कर सकता हूँ?

A2: हाँ, Aspose.Tasks विशिष्ट परियोजना आवश्यकताओं के अनुसार पुनरावृत्ति पैटर्न को परिभाषित करने के लिए व्यापक अनुकूलन विकल्प प्रदान करता है।

### Q3: क्या Aspose.Tasks अन्य परियोजना प्रबंधन कार्यात्मकताओं के लिए सहायता प्रदान करता है?

A3: बिल्कुल, Aspose.Tasks प्रोजेक्ट प्रबंधन के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें कार्य ट्रैकिंग, संसाधन आवंटन और गैंट चार्ट निर्माण शामिल हैं।

### Q4: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?

 उ4: हाँ, आप नि:शुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/) खरीदारी का निर्णय लेने से पहले Aspose.Tasks की क्षमताओं का पता लगाना।

### Q5: यदि मुझे कोई समस्या आती है या मेरे कोई प्रश्न हैं तो मैं कहां सहायता मांग सकता हूं?

 A5: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समुदाय या Aspose टीम से समर्थन प्राप्त करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
