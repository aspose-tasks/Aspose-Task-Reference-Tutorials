---
title: Aspose.Tasks के साथ MS प्रोजेक्ट कार्यों को हटाना
linktitle: Aspose.Tasks में कार्य हटाना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट कार्यों को प्रोग्रामेटिक रूप से हटाने का तरीका जानें। कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका शामिल है।
weight: 15
url: /hi/net/rate-recurring-tasks/removing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ MS प्रोजेक्ट कार्यों को हटाना

## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइल से कार्यों को कैसे हटाया जाए। Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देता है। प्रोजेक्ट फ़ाइल से कार्यों को हटाना प्रोजेक्ट प्रबंधन परिदृश्यों में एक सामान्य आवश्यकता हो सकती है, और Aspose.Tasks इसे प्राप्त करने का एक सीधा तरीका प्रदान करता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET के लिए Aspose.Tasks की स्थापना: आपको अपने विकास परिवेश में .NET के लिए Aspose.Tasks को स्थापित करना होगा। यदि आपने इसे अभी तक इंस्टॉल नहीं किया है, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल: एक माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल तैयार करें (`Project1.mpp` इस उदाहरण में) जिसमें से आप कार्यों को हटाना चाहते हैं।

## नामस्थान आयात करें
अपने C# कोड में आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
    using Aspose.Tasks.Util;
Console.WriteLine("Number of tasks before using the algorithm: " + tasks.Count);
Console.WriteLine("Number of tasks after using the algorithm: " + tasks.Count);
```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 इस चरण में, हम Microsoft प्रोजेक्ट फ़ाइल को एक उदाहरण में लोड करते हैं`Project` Aspose.Tasks द्वारा प्रदान की गई कक्षा।
## चरण 2: हटाए जाने वाले कार्यों की पहचान करें
```csharp
var task1 = project.RootTask.Children.Add("1");
var task2 = project.RootTask.Children.Add("2");
var task3 = project.RootTask.Children.Add("3");
var task4 = project.RootTask.Children.Add("4");
```
यहां, हम प्रोजेक्ट के मूल कार्य में कार्य जोड़ रहे हैं। जिन कार्यों को आप हटाना चाहते हैं, उनकी पहचान करने के लिए आप इसे अपने तर्क से बदल देंगे।
## चरण 3: कार्य हटाएँ
```csharp
// ट्री से कार्य1 को हटाने के लिए ट्री आधारित एल्गोरिदम का उपयोग करें
var algorithm = new RemoveTask(task1);
// कार्य वृक्ष पर एल्गोरिदम लागू करें
TaskUtils.Apply(project.RootTask, algorithm, 0);
```
इस चरण में निर्दिष्ट कार्य को हटाने के लिए ट्री-आधारित एल्गोरिदम का उपयोग करना शामिल है (`task1` इस उदाहरण में) प्रोजेक्ट फ़ाइल से।
## चरण 4: परिणाम जांचें
```csharp
// परिणाम जांचें
List<Task> tasks = new List<Task>(project.RootTask.SelectAllChildTasks());
Console.WriteLine("Number of tasks after using the algorithm: " + tasks.Count);
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    Console.WriteLine("Task Name: " + task.Get(Tsk.Name));
}
```
अंत में, हम यह सुनिश्चित करने के लिए परिणामों की जांच करते हैं कि निर्दिष्ट कार्य को प्रोजेक्ट फ़ाइल से सफलतापूर्वक हटा दिया गया है।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइल से कार्यों को कैसे हटाया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाते हुए, इस कार्यक्षमता को अपने .NET अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं Aspose.Tasks का उपयोग करके एक साथ कई कार्य हटा सकता हूँ?
उत्तर: हां, आप जिन कार्यों को हटाना चाहते हैं, उन्हें दोहराकर और प्रत्येक कार्य में निष्कासन एल्गोरिदम को लागू करके आप कई कार्यों को हटा सकते हैं।
### प्रश्न: क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
उत्तर: हाँ, Aspose.Tasks MPP और XML प्रारूपों सहित Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### प्रश्न: यदि आवश्यक हो तो क्या मैं कार्य हटाने की कार्रवाई को पूर्ववत कर सकता हूँ?
उत्तर: Aspose.Tasks पूर्ववत कार्यों के लिए मजबूत कार्यक्षमता प्रदान करता है। यदि आवश्यक हो तो पूर्ववत परिदृश्यों को संभालने के लिए आप कस्टम तर्क लागू कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks जटिल परियोजना संरचनाओं के लिए सहायता प्रदान करता है?
उत्तर: बिल्कुल, Aspose.Tasks जटिल परियोजना संरचनाओं के लिए व्यापक समर्थन प्रदान करता है, जिससे आप कार्यों, संसाधनों और अन्य परियोजना तत्वों में आसानी से हेरफेर कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हां, आप Aspose.Tasks का निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/) खरीदारी करने से पहले इसकी विशेषताओं का पता लगाएं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
