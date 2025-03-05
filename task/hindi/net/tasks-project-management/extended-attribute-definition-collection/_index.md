---
title: Aspose.Tasks में मास्टर विस्तारित विशेषता परिभाषाएँ MS प्रोजेक्ट
linktitle: Aspose.Tasks में विस्तारित विशेषता परिभाषाओं का संग्रह
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट में विस्तारित विशेषता परिभाषाओं को प्रबंधित करना सीखें। अपने प्रोजेक्ट डेटा को सहजता से अनुकूलित और बढ़ाएं।
type: docs
weight: 14
url: /hi/net/tasks-project-management/extended-attribute-definition-collection/
---
## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट में विस्तारित विशेषता परिभाषाओं के साथ कैसे काम किया जाए। विस्तारित विशेषताएँ प्रोजेक्ट डेटा को अनुकूलित और बढ़ाने का एक लचीला तरीका प्रदान करती हैं, जिससे उपयोगकर्ताओं को डिफ़ॉल्ट रूप से प्रदान किए गए मानक फ़ील्ड से परे अतिरिक्त फ़ील्ड जोड़ने की अनुमति मिलती है। Aspose.Tasks के साथ, आप अपनी परियोजना प्रबंधन आवश्यकताओं को पूरा करने के लिए इन विस्तारित विशेषताओं को आसानी से प्रबंधित कर सकते हैं।
## आवश्यक शर्तें
आगे बढ़ने से पहले, सुनिश्चित करें कि आपने निम्नलिखित शर्तें स्थापित कर ली हैं:
- [।शुद्ध रूपरेखा](https://dotnet.microsoft.com/download)
-  .NET लाइब्रेरी के लिए Aspose.Tasks। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).

## नामस्थान आयात करें
सबसे पहले, आपको अपने .NET प्रोजेक्ट में Aspose.Tasks कक्षाओं और विधियों तक पहुंचने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। इन चरणों का पालन करें:
## चरण 1: अपना .NET प्रोजेक्ट खोलें
अपने .NET प्रोजेक्ट को अपने पसंदीदा IDE, जैसे विज़ुअल स्टूडियो, में खोलें।
## चरण 2: Aspose.Tasks नेमस्पेस जोड़ें
Aspose.Tasks नेमस्पेस को आयात करने के लिए अपनी कोड फ़ाइल की शुरुआत में निम्नलिखित पंक्ति जोड़ें:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

अब, आइए व्यापक समझ के लिए दिए गए कोड उदाहरणों को कई चरणों में तोड़ें:
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## चरण 2: मौजूदा विस्तारित विशेषता परिभाषाएँ साफ़ करें (वैकल्पिक)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## चरण 3: किसी कार्य के लिए विस्तारित विशेषता परिभाषा बनाएं और जोड़ें
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## चरण 4: कार्य विस्तारित विशेषताओं पर पुनरावृति करें
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## चरण 5: किसी संसाधन के लिए विस्तारित विशेषता परिभाषा बनाएं और जोड़ें
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## चरण 6: संसाधन विस्तारित विशेषता परिभाषा सम्मिलित करें
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## चरण 7: अनुक्रमणिका द्वारा विस्तारित विशेषता को हटाएँ
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट में विस्तारित विशेषता परिभाषाओं के साथ काम करने की मूल बातें शामिल की हैं। इन चरणों का पालन करके, आप अपनी परियोजना प्रबंधन आवश्यकताओं के अनुरूप विस्तारित विशेषताओं को कुशलतापूर्वक प्रबंधित और अनुकूलित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं मौजूदा विस्तारित विशेषता परिभाषाओं को संशोधित कर सकता हूँ?
उत्तर: हां, आप अपनी आवश्यकताओं के अनुसार मौजूदा विस्तारित विशेषता परिभाषाओं को संशोधित कर सकते हैं या नई बना सकते हैं।
### प्रश्न: क्या विस्तारित विशेषताएँ Microsoft प्रोजेक्ट के सभी संस्करणों में समर्थित हैं?
उ: हाँ, विस्तारित विशेषताएँ Microsoft प्रोजेक्ट के अधिकांश संस्करणों में समर्थित हैं, जिनमें हाल के संस्करण भी शामिल हैं।
### प्रश्न: क्या मैं कस्टम फ़ील्ड की गणना के लिए विस्तारित विशेषताओं का उपयोग कर सकता हूँ?
उत्तर: बिल्कुल, विस्तारित विशेषताओं का उपयोग आपके द्वारा परिभाषित विशिष्ट मानदंडों के आधार पर कस्टम फ़ील्ड की गणना करने के लिए किया जा सकता है।
### प्रश्न: क्या Aspose.Tasks अन्य .NET फ्रेमवर्क के साथ संगत है?
उत्तर: Aspose.Tasks विभिन्न .NET फ्रेमवर्क के साथ संगत है, जो लचीलापन और एकीकरण में आसानी सुनिश्चित करता है।
### प्रश्न: Aspose.Tasks के लिए मुझे अधिक संसाधन और समर्थन कहां मिल सकता है?
 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समर्थन के लिए और दस्तावेज़ीकरण का अन्वेषण करें[यहाँ](https://reference.aspose.com/tasks/net/).