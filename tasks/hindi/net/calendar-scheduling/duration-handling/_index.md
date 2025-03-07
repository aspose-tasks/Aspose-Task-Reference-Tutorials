---
title: Aspose.Tasks में अवधि प्रबंधन
linktitle: Aspose.Tasks में अवधि प्रबंधन
second_title: Aspose.Tasks .NET API
description: चरण-दर-चरण ट्यूटोरियल के साथ .NET के लिए Aspose.Tasks में अवधियों को प्रभावी ढंग से प्रबंधित करना सीखें।
weight: 30
url: /hi/net/calendar-scheduling/duration-handling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में अवधि प्रबंधन

## परिचय

परियोजना प्रबंधन अनुप्रयोगों में अवधियों को प्रभावी ढंग से संभालना महत्वपूर्ण है। .NET के लिए Aspose.Tasks अवधियों को कुशलतापूर्वक प्रबंधित करने के लिए मजबूत कार्यक्षमता प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks का उपयोग करके अवधि प्रबंधन के विभिन्न पहलुओं का पता लगाएंगे।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1. C# का बुनियादी ज्ञान: उदाहरणों को समझने और लागू करने के लिए C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।
2. विजुअल स्टूडियो: .NET एप्लिकेशन बनाने और चलाने के लिए विजुअल स्टूडियो आईडीई स्थापित करें।
3.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).

## नामस्थान आयात करें

सबसे पहले, आइए Aspose.Tasks कार्यात्मकताओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

आइए चरण-दर-चरण मार्गदर्शिका प्रारूप में प्रत्येक उदाहरण को कई चरणों में विभाजित करें:

## कार्यों की अवधि अद्यतन करना

### चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### चरण 2: कार्य और अवधि प्राप्त करें

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### चरण 3: अद्यतन अवधि

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### चरण 4: अद्यतन अवधि प्रदर्शित करें

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## कार्यों की अवधि घटाना

### चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### चरण 2: कार्य और अवधि प्राप्त करें

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### चरण 3: अवधि घटाएं

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### चरण 4: अद्यतन अवधि प्रदर्शित करें

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## अवधि को टाइमस्पेन में परिवर्तित करना

### चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### चरण 2: कार्य और अवधि प्राप्त करें

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### चरण 3: अवधि को टाइमस्पेन में बदलें

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## अवधि को स्ट्रिंग में परिवर्तित करना

### चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### चरण 2: कार्य और अवधि प्राप्त करें

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### चरण 3: अवधि को स्ट्रिंग में बदलें

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Tasks में अवधि प्रबंधन के विभिन्न पहलुओं को कवर किया। सफल परियोजना प्रबंधन के लिए अवधियों को समझना और प्रभावी ढंग से प्रबंधित करना महत्वपूर्ण है। Aspose.Tasks आपके .NET अनुप्रयोगों में अवधि प्रबंधन कार्यों को सरल बनाने के लिए व्यापक कार्यक्षमताएँ प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: .NET के लिए Aspose.Tasks क्या है?

A1: .NET के लिए Aspose.Tasks .NET अनुप्रयोगों में Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है।

### Q2: क्या Aspose.Tasks जटिल परियोजना संरचनाओं को संभाल सकता है?

A2: हां, Aspose.Tasks जटिल परियोजना संरचनाओं को आसानी से संभाल सकता है, हेरफेर के लिए व्यापक एपीआई प्रदान करता है।

### Q3: क्या .NET के लिए Aspose.Tasks .NET कोर के साथ संगत है?

A3: हाँ, .NET के लिए Aspose.Tasks .NET कोर के साथ संगत है, जिससे आप इसे क्रॉस-प्लेटफ़ॉर्म अनुप्रयोगों में उपयोग कर सकते हैं।

### Q4: क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों को पढ़ने और लिखने का समर्थन करता है?

A4: हाँ, Aspose.Tasks MPP, XML और MPX सहित विभिन्न स्वरूपों में Microsoft प्रोजेक्ट फ़ाइलों को पढ़ने और लिखने का समर्थन करता है।

### Q5: क्या .NET के लिए Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?

A5: हाँ, आप .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
