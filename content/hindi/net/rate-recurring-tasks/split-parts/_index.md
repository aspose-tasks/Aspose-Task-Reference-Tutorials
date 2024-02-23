---
title: Aspose.Tasks में MS प्रोजेक्ट स्प्लिट पार्ट्स को संभालना
linktitle: Aspose.Tasks में विभाजित भागों को संभालना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks के साथ MS प्रोजेक्ट स्प्लिट पार्ट्स को कुशलतापूर्वक संभालना सीखें। अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो को बढ़ाएँ।
type: docs
weight: 18
url: /hi/net/rate-recurring-tasks/split-parts/
---

## परिचय
.NET के लिए Aspose.Tasks का उपयोग करते समय MS प्रोजेक्ट स्प्लिट पार्ट्स को प्रबंधित करना प्रोजेक्ट प्रबंधन का एक महत्वपूर्ण पहलू हो सकता है। इस ट्यूटोरियल में, हम चरण-दर-चरण मार्गदर्शन का उपयोग करके विभाजित भागों को प्रभावी ढंग से संभालने का तरीका जानेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  .NET के लिए Aspose.Tasks की स्थापना: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[वेबसाइट](https://releases.aspose.com/tasks/net/).
   
2. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा।

## नामस्थान आयात करें
अपने C# कोड में, आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## चरण 1: एक प्रोजेक्ट इंस्टेंस बनाएं
```csharp
var project = new Project();
```
 का एक नया उदाहरण बनाएं`Project` कक्षा. कक्षा.
## चरण 2: परियोजना प्रारंभ और समाप्ति तिथियां निर्धारित करना
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
परियोजना के लिए प्रारंभ और समाप्ति तिथियां निर्धारित करें।
## चरण 3: कार्य जोड़ना
```csharp
var task = project.RootTask.Children.Add("Task1");
```
प्रोजेक्ट में एक नया कार्य जोड़ें.
## चरण 4: कार्य गुण सेट करना
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
कार्य के लिए मैन्युअल स्थिति, प्रारंभ तिथि और अवधि जैसे गुण सेट करें।
## चरण 5: संसाधन असाइनमेंट जोड़ना
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
कार्य में संसाधन असाइनमेंट जोड़ें.
## चरण 6: असाइनमेंट गुण सेट करना
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
असाइनमेंट के लिए आरंभ तिथि, कार्य और समाप्ति तिथि जैसे गुण सेट करें।
## चरण 7: समय चरणबद्ध डेटा तैयार करना
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
प्रोजेक्ट कैलेंडर के आधार पर असाइनमेंट के लिए समय चरणबद्ध डेटा तैयार करें।
## चरण 8: कार्य को विभाजित करना
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
निर्दिष्ट समय सीमा के भीतर कार्य को कई भागों में विभाजित करें।
## चरण 9: विभाजित भागों पर पुनरावृत्ति
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
कार्य के विभाजित हिस्सों पर पुनरावृति करें और उनकी आरंभ और समाप्ति तिथियां प्रिंट करें।

## निष्कर्ष
.NET के लिए Aspose.Tasks में MS प्रोजेक्ट स्प्लिट भागों को प्रभावी ढंग से संभालना परियोजना प्रबंधन दक्षता के लिए महत्वपूर्ण है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप विभाजित कार्यों को सहजता से प्रबंधित कर सकते हैं और अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य .NET फ्रेमवर्क के साथ .NET के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, .NET के लिए Aspose.Tasks .NET कोर और .NET मानक सहित विभिन्न .NET फ्रेमवर्क के साथ संगत है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks का निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: क्या .NET के लिए Aspose.Tasks संसाधन प्रबंधन का समर्थन करता है?
उत्तर: हां, .NET के लिए Aspose.Tasks आपको प्रोजेक्ट संसाधनों को कुशलतापूर्वक प्रबंधित करने की अनुमति देता है।
### प्रश्न: क्या मैं .NET के लिए Aspose.Tasks का उपयोग करके प्रोजेक्ट कैलेंडर को अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल, आप अपनी परियोजना आवश्यकताओं के अनुसार परियोजना कैलेंडर को अनुकूलित कर सकते हैं।
### प्रश्न: मुझे .NET के लिए Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
 उत्तर: आप इस पर समर्थन और सहायता पा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).