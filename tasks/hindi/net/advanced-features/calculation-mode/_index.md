---
title: Aspose.Tasks में गणना मोड
linktitle: Aspose.Tasks में गणना मोड
second_title: Aspose.Tasks .NET API
description: प्रोजेक्ट शेड्यूलिंग और कार्य निर्भरता को सुव्यवस्थित करने के लिए .NET के लिए Aspose.Tasks में गणना मोड को प्रभावी ढंग से प्रबंधित करना सीखें।
weight: 29
url: /hi/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में गणना मोड

## परिचय

.NET के लिए Aspose.Tasks एक शक्तिशाली API है जो डेवलपर्स को उनके .NET अनुप्रयोगों में Microsoft प्रोजेक्ट फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। प्रोजेक्ट फ़ाइलों के साथ काम करने का एक महत्वपूर्ण पहलू गणना मोड का प्रबंधन करना है, जो यह तय करता है कि कार्यों और प्रोजेक्ट शेड्यूल की गणना और अद्यतन कैसे किया जाता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks द्वारा समर्थित विभिन्न गणना मोड के बारे में विस्तार से जानेंगे और प्रदर्शित करेंगे कि उनका प्रभावी ढंग से उपयोग कैसे किया जाए।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. विजुअल स्टूडियो: सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
2.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# प्रोग्रामिंग की बुनियादी समझ: C# प्रोग्रामिंग अवधारणाओं से खुद को परिचित करें।

## नामस्थान आयात करें

इससे पहले कि हम .NET के लिए Aspose.Tasks के साथ काम करना शुरू करें, आइए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;


```

## स्वचालित गणना मोड लागू करना

### चरण 1: एक नया प्रोजेक्ट इंस्टेंस बनाएं

 एक नया प्रारंभ करें`Project` ऑब्जेक्ट करें और उसे सेट करें`CalculationMode` संपत्ति को`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### चरण 2: प्रोजेक्ट प्रारंभ तिथि निर्धारित करें और कार्य जोड़ें

प्रोजेक्ट की प्रारंभ तिथि निर्धारित करें और उसमें कार्य जोड़ें।

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### चरण 3: कार्यों को लिंक करें

कार्यों के बीच निर्भरता स्थापित करें।

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### चरण 4: पुनर्गणना की गई तिथियों को सत्यापित करें

जांचें कि क्या तिथियां स्वचालित रूप से पुनर्गणना की गई हैं।

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// आवश्यकतानुसार अधिक सत्यापन जोड़ें
```

## मैन्युअल गणना मोड लागू करना

### चरण 1: एक नया प्रोजेक्ट इंस्टेंस बनाएं

 एक नया प्रारंभ करें`Project` ऑब्जेक्ट करें और उसे सेट करें`CalculationMode` संपत्ति को`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### चरण 2: प्रोजेक्ट प्रारंभ तिथि निर्धारित करें और कार्य जोड़ें

प्रोजेक्ट की प्रारंभ तिथि निर्धारित करें और उसमें कार्य जोड़ें।

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### चरण 3: कार्य गुणों को सत्यापित करें

जांचें कि कार्य गुण मैन्युअल मोड में सही ढंग से सेट हैं या नहीं।

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// आवश्यकतानुसार अधिक सत्यापन जोड़ें
```

### चरण 4: कार्यों को लिंक करें और तिथियां सत्यापित करें

कार्यों को एक साथ लिंक करें और जांचें कि क्या उनकी तिथियों की पुनर्गणना नहीं की गई है।

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## कोई नहीं गणना मोड लागू करना

### चरण 1: एक नया प्रोजेक्ट इंस्टेंस बनाएं

 एक नया प्रारंभ करें`Project` ऑब्जेक्ट करें और उसे सेट करें`CalculationMode` संपत्ति को`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### चरण 2: एक नया कार्य जोड़ें

प्रोजेक्ट में एक नया कार्य जोड़ें.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### चरण 3: कार्य गुणों को सत्यापित करें

जांचें कि क्या कार्य गुणों की गणना स्वचालित रूप से नहीं की जाती है।

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// आवश्यकतानुसार अधिक सत्यापन जोड़ें
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Tasks में उपलब्ध गणना मोड का पता लगाया है और सीखा है कि उन्हें व्यावहारिक परिदृश्यों में कैसे लागू किया जाए। चाहे आपको स्वचालित, मैन्युअल या बिना गणना मोड की आवश्यकता हो, Aspose.Tasks आपके प्रोजेक्ट की आवश्यकताओं के अनुरूप लचीलापन प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं रनटाइम के दौरान गणना मोड को गतिशील रूप से बदल सकता हूँ?

A1: हां, आप रनटाइम के दौरान किसी भी समय किसी प्रोजेक्ट के गणना मोड को संशोधित करके बदल सकते हैं`CalculationMode` संपत्ति।

### Q2: क्या Aspose.Tasks Microsoft प्रोजेक्ट के अलावा अन्य प्रोजेक्ट प्रबंधन फ़ाइल स्वरूपों का समर्थन करता है?

A2: Aspose.Tasks मुख्य रूप से Microsoft प्रोजेक्ट फ़ाइल स्वरूपों पर केंद्रित है, लेकिन यह प्रिमावेरा P6 XML, प्रिमावेरा DB और एस्टा पॉवरप्रोजेक्ट XML जैसे अन्य स्वरूपों का भी समर्थन करता है।

### Q3: क्या Aspose.Tasks छोटे पैमाने और उद्यम स्तर की परियोजनाओं दोनों के लिए उपयुक्त है?

उ3: बिल्कुल! Aspose.Tasks को इसकी व्यापक सुविधाओं और मजबूत एपीआई के साथ छोटे पैमाने और उद्यम स्तर की परियोजनाओं की जरूरतों को पूरा करने के लिए डिज़ाइन किया गया है।

### Q4: क्या मैं Aspose.Tasks को अन्य .NET लाइब्रेरीज़ और फ्रेमवर्क के साथ एकीकृत कर सकता हूँ?

A4: हां, आप अपने एप्लिकेशन की कार्यक्षमता को बढ़ाने के लिए Aspose.Tasks को अन्य .NET लाइब्रेरी और फ्रेमवर्क के साथ सहजता से एकीकृत कर सकते हैं।

### Q5: क्या Aspose.Tasks उपयोगकर्ताओं के लिए कोई सामुदायिक मंच या सहायता चैनल उपलब्ध है?

 A5: हाँ, आप यहाँ जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
