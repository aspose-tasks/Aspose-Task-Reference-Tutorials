---
title: Aspose.Tasks में MS प्रोजेक्ट ग्रुप मानदंड का हेरफेर
linktitle: Aspose.Tasks में समूह मानदंड
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks का उपयोग करके .NET में MS प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने का तरीका जानें। कार्य समूह और मानदंड जानकारी चरण-दर-चरण उदाहरण पुनः प्राप्त करें।
weight: 27
url: /hi/net/tasks-project-management/group-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट ग्रुप मानदंड का हेरफेर

## परिचय
.NET के लिए Aspose.Tasks एक शक्तिशाली API है जो आपके .NET अनुप्रयोगों में Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की सुविधा प्रदान करता है। चाहे आप प्रोजेक्ट प्रबंधन सॉफ़्टवेयर विकसित कर रहे हों या प्रोग्रामेटिक रूप से प्रोजेक्ट डेटा में हेरफेर करने की आवश्यकता हो, Aspose.Tasks आपकी आवश्यकताओं को पूरा करने के लिए सुविधाओं का एक व्यापक सेट प्रदान करता है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
### 1. C# और .NET फ्रेमवर्क का ज्ञान
इस ट्यूटोरियल में दिए गए उदाहरणों को समझने और लागू करने के लिए C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क से परिचित होना आवश्यक है।
### 2. .NET के लिए Aspose.Tasks की स्थापना
 सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए Aspose.Tasks स्थापित है। आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/) और दिए गए इंस्टॉलेशन निर्देशों का पालन करें।
### 3. एकीकृत विकास पर्यावरण (आईडीई)
C# कोड लिखने और निष्पादित करने के लिए अपने सिस्टम पर विज़ुअल स्टूडियो जैसी एक आईडीई स्थापित करें।

## नामस्थान आयात करें
आरंभ करने के लिए, अपने C# कोड में आवश्यक नामस्थान आयात करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## चरण 1: एक Microsoft प्रोजेक्ट फ़ाइल लोड करें
सबसे पहले, अपनी Microsoft Project फ़ाइल का पथ निर्दिष्ट करें:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 प्रतिस्थापित करें`"Your Document Directory"` आपकी प्रोजेक्ट फ़ाइल के पथ के साथ।
## चरण 2: कार्य समूहों की जानकारी पुनः प्राप्त करें
इसके बाद, प्रोजेक्ट में कार्य समूहों के बारे में जानकारी पुनः प्राप्त करें:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
यह कोड स्निपेट कार्य समूहों की कुल संख्या को प्रिंट करता है, दूसरे कार्य समूह, उसका नाम और उसके द्वारा रखे गए मानदंडों की संख्या को पुनः प्राप्त करता है।
## चरण 3: कार्य समूह की मानदंड जानकारी पुनः प्राप्त करें
अब, आइए कार्य समूह के भीतर एक विशिष्ट मानदंड के विवरण पर गौर करें:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
यह खंड मानदंड के विभिन्न गुणों को प्रदर्शित करता है जैसे कि इसका सूचकांक, फ़ील्ड, समूहीकरण जानकारी, सेल रंग, फ़ॉन्ट रंग, समूह अंतराल और प्रारंभिक बिंदु।
## चरण 4: मानदंड की फ़ॉन्ट जानकारी पुनः प्राप्त करें
अंत में, मानदंड का फ़ॉन्ट-संबंधित विवरण प्राप्त करें:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
यह चरण फ़ॉन्ट नाम, आकार, शैली और क्या मानदंड को आरोही या अवरोही क्रम में क्रमबद्ध किया गया है, प्रिंट करता है।

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया कि Microsoft प्रोजेक्ट फ़ाइल से कार्य समूहों और मानदंडों के बारे में जानकारी प्राप्त करने के लिए .NET के लिए Aspose.Tasks का उपयोग कैसे करें। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने .NET अनुप्रयोगों में प्रोग्रामेटिक रूप से प्रोजेक्ट डेटा के साथ कुशलतापूर्वक काम कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks बड़ी Microsoft प्रोजेक्ट फ़ाइलों को संभाल सकता है?
Aspose.Tasks को उच्च प्रदर्शन और विश्वसनीयता सुनिश्चित करते हुए बड़ी परियोजना फ़ाइलों को कुशलतापूर्वक संभालने के लिए अनुकूलित किया गया है।
### क्या Aspose.Tasks Microsoft प्रोजेक्ट के सभी संस्करणों के साथ संगत है?
हाँ, Aspose.Tasks Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न फ़ाइल स्वरूपों में अनुकूलता सुनिश्चित करता है।
### क्या मैं Aspose.Tasks का उपयोग करके प्रोजेक्ट डेटा में हेरफेर कर सकता हूँ?
बिल्कुल, Aspose.Tasks प्रोजेक्ट डेटा में हेरफेर करने के लिए व्यापक कार्यक्षमताएँ प्रदान करता है, जिसमें कार्य, संसाधन, कैलेंडर और बहुत कुछ शामिल हैं।
### क्या Aspose.Tasks विभिन्न .NET प्लेटफ़ॉर्म के लिए समर्थन प्रदान करता है?
हां, Aspose.Tasks .NET फ्रेमवर्क, .NET कोर और .NET स्टैंडर्ड सहित कई .NET प्लेटफार्मों का समर्थन करता है।
### क्या Aspose.Tasks के लिए कोई सामुदायिक मंच है जहां मैं सहायता मांग सकता हूं?
 हां, आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) प्रश्न पूछने, ज्ञान साझा करने और अन्य उपयोगकर्ताओं के साथ सहयोग करने के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
