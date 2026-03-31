---
date: 2026-03-19
description: Aspose.Tasks के ट्री एल्गोरिदम का उपयोग करके प्रोजेक्ट में संसाधन जोड़ना
  और कार्य की अवधि की गणना करना सीखें, और .NET में कार्यों को संसाधन सौंपें।
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में ट्री एल्गोरिद्म का उपयोग करके प्रोजेक्ट में संसाधन जोड़ें
url: /hi/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में ट्री एल्गोरिदम के साथ प्रोजेक्ट में रिसोर्स जोड़ें

## परिचय

इस ट्यूटोरियल में आप **प्रोजेक्ट में रिसोर्स कैसे जोड़ें** यह सीखेंगे, Aspose.Tasks for .NET द्वारा प्रदान किए गए शक्तिशाली ट्री एल्गोरिदम का उपयोग करके। हम टास्क हायरार्की बनाने, टास्क की अवधि की गणना करने, और टास्क को रिसोर्स असाइन करने की प्रक्रिया को स्पष्ट, चरण‑दर‑चरण तरीके से दिखाएंगे, जिसे आप अपने समाधान में कॉपी कर सकते हैं।

## त्वरित उत्तर
- **ट्री एल्गोरिदम क्या करता है?** यह टास्क हायरार्की को पार करके कार्य मानों को कुशलतापूर्वक एकत्र करता है।  
- **यह गाइड कौन सी मुख्य क्रिया को कवर करता है?** प्रोजेक्ट में रिसोर्स जोड़ना और कार्य कुल को अपडेट करना।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक अस्थायी या पूर्ण लाइसेंस आवश्यक है।  
- **क्या मैं इसे .NET Core के साथ उपयोग कर सकता हूँ?** हाँ, Aspose.Tasks .NET Framework और .NET Core दोनों को सपोर्ट करता है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** एक बेसिक प्रोजेक्ट फ़ाइल के लिए लगभग 10‑15 मिनट।

## Aspose.Tasks में “प्रोजेक्ट में रिसोर्स जोड़ना” क्या है?

प्रोजेक्ट में रिसोर्स जोड़ना मतलब एक `Resource` ऑब्जेक्ट बनाना, उसका प्रकार (जैसे, work) निर्धारित करना, और उसे `ResourceAssignments` के माध्यम से एक या अधिक टास्क से लिंक करना है। इससे शेड्यूलर प्रयास, लागत, और कुल प्रोजेक्ट अवधि की गणना कर सकता है।

## रिसोर्स कार्य गणनाओं के लिए ट्री एल्गोरिदम का उपयोग क्यों करें?

ट्री एल्गोरिदम टास्क ट्री को एक बार चलाता है, पत्ती टास्क से लेकर उनके समरी टास्क तक कार्य को संचित करता है। यह तरीका प्रत्येक टास्क को अलग‑अलग इटररेट करने की तुलना में बहुत अधिक कुशल है, विशेषकर बड़े प्रोजेक्ट्स में जहाँ हायरार्की गहरी होती है। यह यह भी सुनिश्चित करता है कि समरी कार्य मान उनके चाइल्ड टास्क के साथ सिंक में रहें।

## पूर्वापेक्षाएँ

1. **Visual Studio** – कोई भी नवीनतम संस्करण (2019, 2022, या बाद का)।  
2. **Aspose.Tasks for .NET** – इसे [here](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।  
3. **Basic C# knowledge** – आपको क्लासेज़, ऑब्जेक्ट्स, और सरल LINQ में सहज होना चाहिए।

## नेमस्पेस इम्पोर्ट करें

अपने C# प्रोजेक्ट में, Aspose.Tasks की कार्यक्षमताओं के साथ काम करने के लिए आवश्यक नेमस्पेस इम्पोर्ट करें:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

अब प्रत्येक उदाहरण को कई चरणों में विभाजित करते हैं:

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

`Project` क्लास का उपयोग करके प्रोजेक्ट फ़ाइल को मेमोरी में लोड करें।

## चरण 2: टास्क हायरार्की परिभाषित करें

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

पैरेंट और चाइल्ड टास्क जोड़कर टास्क हायरार्की को परिभाषित करें।

## चरण 3: टास्क प्रॉपर्टीज़ सेट करें (जिसमें **calculate task duration** शामिल है)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

यहाँ हम कार्य घंटे को `Duration` ऑब्जेक्ट में बदलकर और फिर समाप्ति तिथि निकालकर **टास्क की अवधि की गणना** करते हैं।

## चरण 4: रिसोर्स जोड़ें (**assign resources to tasks**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

यह स्निपेट **प्रोजेक्ट में एक रिसोर्स जोड़ता है** और **टास्क को रिसोर्स असाइन करता है** ताकि शेड्यूलर को पता हो कि कार्य किसके द्वारा किया जाएगा।

## चरण 5: ट्री एल्गोरिदम लागू करें

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

`WorkAccumulator` क्लास को इनिशियलाइज़ करें और हायरार्की में सामान्य कार्य को इकट्ठा करने के लिए ट्री एल्गोरिदम लागू करें।

## चरण 6: टास्क कार्य अपडेट करें

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

इकट्ठा की गई जानकारी के आधार पर टास्क के कार्य मानों को अपडेट करें।

## सामान्य समस्याएँ और टिप्स

- **कैलेंडर सेटिंग्स गायब:** यदि समाप्ति तिथि गलत दिख रही है, तो `GetFinishDateByStartAndWork` कॉल करने से पहले सुनिश्चित करें कि प्रोजेक्ट कैलेंडर सही ढंग से कॉन्फ़िगर किया गया है।  
- **रिसोर्स प्रकार का असंगत होना:** हमेशा `Rsc.Type` को `ResourceType.Work` सेट करें यदि रिसोर्स प्रयास‑आधारित है; अन्यथा, कार्य संकलन शून्य हो सकता है।  
- **प्रो टिप:** कार्य अपडेट करने के बाद, बदलावों को सहेजने के लिए `project.Save("UpdatedProject.mpp")` कॉल करें।

## निष्कर्ष

इन चरणों का पालन करके अब आप जानते हैं कि Aspose.Tasks के ट्री एल्गोरिदम का उपयोग करके **प्रोजेक्ट में रिसोर्स कैसे जोड़ें**, **टास्क की अवधि कैसे गणना करें**, और **टास्क को रिसोर्स कैसे असाइन करें**। यह विधि हायरार्की प्रबंधन को सरल बनाती है और न्यूनतम कोड के साथ समरी कार्य मानों को सटीक रखती है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: Aspose.Tasks for .NET क्या है?

Aspose.Tasks for .NET एक शक्तिशाली API है जो डेवलपर्स को C# का उपयोग करके प्रोग्रामेटिकली Microsoft Project फ़ाइलों को मैनीपुलेट करने की अनुमति देता है।

### Q2: क्या मैं Aspose.Tasks for .NET का फ्री ट्रायल डाउनलोड कर सकता हूँ?

हाँ, आप Aspose.Tasks for .NET का फ्री ट्रायल [here](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

### Q3: Aspose.Tasks for .NET की डॉक्यूमेंटेशन कहाँ मिल सकती है?

आप Aspose.Tasks for .NET की डॉक्यूमेंटेशन [here](https://reference.aspose.com/tasks/net/) पर पा सकते हैं।

### Q4: Aspose.Tasks for .NET के लिए सपोर्ट कैसे प्राप्त करूँ?

Aspose.Tasks for .NET से संबंधित सपोर्ट के लिए, आप [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

### Q5: क्या परीक्षण के लिए अस्थायी लाइसेंस उपलब्ध है?

हाँ, आप परीक्षण उद्देश्यों के लिए एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इस दृष्टिकोण को मौजूदा बड़े प्रोजेक्ट फ़ाइल के साथ उपयोग कर सकता हूँ?**  
A: बिल्कुल। ट्री एल्गोरिदम किसी भी `Project` इंस्टेंस पर काम करता है, चाहे उसका आकार कुछ भी हो।

**Q: क्या एल्गोरिदम लागत मानों को भी अपडेट करता है?**  
A: उदाहरण कार्य पर केंद्रित है, लेकिन आप समान तरीके से `Tsk.Cost` को संचित करके इसे लागत तक विस्तारित कर सकते हैं।

**Q: कौन से .NET संस्करण समर्थित हैं?**  
A: Aspose.Tasks .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, और .NET 6+ को सपोर्ट करता है।

**Q: मैं एक टास्क में कई रिसोर्स कैसे संभालूँ?**  
A: प्रत्येक रिसोर्स को `project.ResourceAssignments.Add(task, resource)` से जोड़ें; एग्रीगेटर स्वचालित रूप से उनके कार्य को जोड़ देगा।

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}