---
title: Aspose.Tasks में ट्री एल्गोरिथम का उपयोग करना
linktitle: Aspose.Tasks में ट्री एल्गोरिथम का उपयोग करना
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks' ट्री एल्गोरिथम का उपयोग करके अपने .NET प्रोजेक्ट्स में कार्य पदानुक्रमों को प्रभावी ढंग से हेरफेर करना सीखें।
type: docs
weight: 13
url: /hi/net/advanced-concepts/tree-algorithm/
---
## परिचय

.NET के लिए Aspose.Tasks परियोजना प्रबंधन कार्यों, संसाधनों और शेड्यूल के साथ काम करने के लिए शक्तिशाली कार्यक्षमता प्रदान करता है। ऐसी ही एक सुविधा ट्री एल्गोरिथम है, जो उपयोगकर्ताओं को कार्य पदानुक्रम में कुशलतापूर्वक हेरफेर करने की अनुमति देती है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि किसी प्रोजेक्ट के भीतर सामान्य कार्य एकत्र करने और कार्य मूल्यों को अपडेट करने के लिए .NET के लिए Aspose.Tasks में ट्री एल्गोरिदम का उपयोग कैसे करें।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. विजुअल स्टूडियो: सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
2.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# की बुनियादी समझ: उदाहरणों के साथ C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।

## नामस्थान आयात करें

अपने C# प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं के साथ काम करने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

अब, आइए प्रत्येक उदाहरण को कई चरणों में तोड़ें:

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 का उपयोग करके प्रोजेक्ट फ़ाइल को मेमोरी में लोड करें`Project` कक्षा।

## चरण 2: कार्य पदानुक्रम को परिभाषित करें

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

माता-पिता और बच्चे के कार्यों को जोड़कर कार्य पदानुक्रम को परिभाषित करें।

## चरण 3: कार्य गुण सेट करें

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

कार्यों के लिए प्रारंभ तिथि, अवधि और समाप्ति तिथि जैसे गुण सेट करें।

## चरण 4: संसाधन जोड़ें

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

प्रोजेक्ट में संसाधन जोड़ें और उन्हें आवश्यकतानुसार कार्य सौंपें।

## चरण 5: ट्री एल्गोरिथम लागू करें

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 को आरंभ करें`WorkAccumulator` क्लास करें और सामान्य कार्य एकत्र करने के लिए ट्री एल्गोरिथम लागू करें।

## चरण 6: कार्य कार्य अद्यतन करें

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

एकत्रित जानकारी के आधार पर कार्यों के लिए कार्य मूल्यों को अद्यतन करें।

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि कार्य पदानुक्रम को प्रभावी ढंग से हेरफेर करने के लिए .NET के लिए Aspose.Tasks में ट्री एल्गोरिदम का उपयोग कैसे करें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपनी परियोजनाओं के भीतर कार्यों और संसाधनों को कुशलतापूर्वक प्रबंधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: .NET के लिए Aspose.Tasks क्या है?

A1: .NET के लिए Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को C# का उपयोग करके प्रोग्रामेटिक रूप से Microsoft प्रोजेक्ट फ़ाइलों में हेरफेर करने की अनुमति देता है।

### Q2: क्या मैं .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण डाउनलोड कर सकता हूँ?

 उ2: हाँ, आप .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).

### Q3: मुझे .NET के लिए Aspose.Tasks के लिए दस्तावेज़ कहाँ मिल सकते हैं?

 A3: आप .NET के लिए Aspose.Tasks के लिए दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/tasks/net/).

### Q4: मैं .NET के लिए Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?

 A4: .NET के लिए Aspose.Tasks से संबंधित सहायता के लिए, आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).

### Q5: क्या परीक्षण उद्देश्यों के लिए कोई अस्थायी लाइसेंस उपलब्ध है?

 A5: हां, आप परीक्षण उद्देश्यों के लिए यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).