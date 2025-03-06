---
title: .NET के लिए Aspose.Tasks में कार्य उपयोग दृश्यों में महारत हासिल करना
linktitle: Aspose.Tasks में कार्य उपयोग दृश्य कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का अन्वेषण करें और जानें कि कार्य उपयोग दृश्यों को कैसे कॉन्फ़िगर करें। टाइमस्केल सेटिंग्स को अनुकूलित करें और अपने प्रोजेक्ट प्रबंधन दृश्यों को बढ़ाएं।
weight: 24
url: /hi/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Tasks में कार्य उपयोग दृश्यों में महारत हासिल करना

## परिचय
परियोजना प्रबंधन के क्षेत्र में, प्रभावी योजना और निष्पादन के लिए कार्य उपयोग की कल्पना करना महत्वपूर्ण है। .NET के लिए Aspose.Tasks कार्य उपयोग दृश्यों को प्रस्तुत करने के लिए एक मजबूत समाधान प्रदान करता है, जिससे आप टाइमस्केल सेटिंग्स और प्रस्तुति प्रारूपों को अनुकूलित कर सकते हैं। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके कार्य उपयोग दृश्यों को कॉन्फ़िगर करने के चरणों के बारे में जानेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET के लिए Aspose.Tasks: सुनिश्चित करें कि आपके पास Aspose.Tasks लाइब्रेरी आपके .NET प्रोजेक्ट में एकीकृत है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. .NET वातावरण: अपनी मशीन पर एक कार्यशील .NET वातावरण स्थापित करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करें। अपने कोड में निम्नलिखित पंक्तियाँ जोड़ें:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें
 Aspose.Tasks कार्यात्मकताओं के साथ काम करने से पहले, अपने दस्तावेज़ निर्देशिका के लिए पथ सेट करें। प्रतिस्थापित करें`"Your Document Directory"` वास्तविक पथ के साथ.
```csharp
String DataDir = "Your Document Directory";
```
## चरण 2: प्रोजेक्ट लोड करें
 Aspose.Tasks को प्रारंभ करें`Project` अपनी प्रोजेक्ट फ़ाइल लोड करके ऑब्जेक्ट करें (उदाहरण के लिए, TaskUsageView.mpp)।
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## चरण 3: सेवऑप्शंस को परिभाषित करें
 एक बनाने के`SaveOptions`रेंडरिंग विकल्प निर्दिष्ट करने के लिए ऑब्जेक्ट। समयमान को 'दिन' और प्रस्तुति प्रारूप को 'टास्कयूजेज' पर सेट करें।
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## चरण 4: डेज़ टाइमस्केल के साथ बचत करें
प्रोजेक्ट को 'डेज़' की पूर्वनिर्धारित टाइमस्केल सेटिंग्स के साथ सहेजें।
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## चरण 5: थर्डऑफ़मंथ टाइमस्केल के साथ सहेजें
टाइमस्केल सेटिंग्स को 'थर्ड्सऑफमंथ्स' में बदलें और प्रोजेक्ट को सेव करें।
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## चरण 6: महीनों के टाइमस्केल के साथ बचत करें
समयमान को 'महीने' पर सेट करें और अद्यतन सेटिंग्स के साथ प्रोजेक्ट को सहेजें।
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## निष्कर्ष
.NET के लिए Aspose.Tasks के साथ कार्य उपयोग दृश्यों को कॉन्फ़िगर करना एक सीधी प्रक्रिया है। टाइमस्केल सेटिंग्स को अनुकूलित करके, आप अपनी विशिष्ट आवश्यकताओं के अनुसार अपने प्रोजेक्ट कार्यों के विज़ुअलाइज़ेशन को तैयार कर सकते हैं।
 इसमें अधिक सुविधाओं और कार्यात्मकताओं का पता लगाने के लिए स्वतंत्र महसूस करें[प्रलेखन](https://reference.aspose.com/tasks/net/).
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं समय-सीमा को पूर्वनिर्धारित सेटिंग्स से परे अनुकूलित कर सकता हूँ?
हां, आप अंतराल और इकाइयों को निर्दिष्ट करके एक कस्टम टाइमस्केल सेट कर सकते हैं।
### क्या अन्य प्रस्तुति प्रारूप उपलब्ध हैं?
Aspose.Tasks विभिन्न प्रस्तुति प्रारूपों का समर्थन करता है, जिनमें गैंटचार्ट, रिसोर्सयूजेज और बहुत कुछ शामिल हैं।
### क्या Aspose.Tasks विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों के साथ संगत है?
हाँ, Aspose.Tasks MPP, XML और CSV जैसे लोकप्रिय प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### क्या मैं विशिष्ट कार्यों के लिए अलग-अलग समय-सीमा सेटिंग्स लागू कर सकता हूँ?
बिल्कुल, आप अपने प्रोजेक्ट के भीतर अलग-अलग कार्यों के लिए टाइमस्केल सेटिंग्स को कस्टमाइज़ कर सकते हैं।
### मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ या सहायता कैसे प्राप्त कर सकता हूँ?
 दौरा करना[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन और मार्गदर्शन के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
