---
title: Aspose.Tasks के साथ शीर्ष लेख और पाद लेख जानकारी निकालें
linktitle: Aspose.Tasks में शीर्ष लेख और पाद लेख की जानकारी
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से हेडर और फ़ुटर जानकारी निकालना सीखें। आसान, कुशल और डेवलपर-अनुकूल समाधान।
type: docs
weight: 29
url: /hi/net/tasks-project-management/header-footer-information/
---
## परिचय
.NET के लिए Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों में आसानी से हेरफेर करने की अनुमति देती है। इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से हेडर और फ़ुटर जानकारी कैसे प्राप्त करें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. विजुअल स्टूडियो: अपने सिस्टम पर विजुअल स्टूडियो इंस्टॉल करें।
2.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना।

## नामस्थान आयात करें
सबसे पहले, आपको अपने C# प्रोजेक्ट में आवश्यक नेमस्पेस आयात करना होगा। यह आपको Aspose.Tasks लाइब्रेरी द्वारा प्रदान की गई कक्षाओं और विधियों तक पहुंचने की अनुमति देगा।
```csharp
    using Aspose.Tasks;
    using System;
    
```
## चरण 1: प्रोजेक्ट ऑब्जेक्ट को आरंभ करें
 आरंभ करने के लिए, आपको a प्रारंभ करना होगा`Project` मौजूदा एमएस प्रोजेक्ट फ़ाइल को लोड करके ऑब्जेक्ट करें।
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## चरण 2: शीर्ष लेख और पाद लेख जानकारी पुनः प्राप्त करें
 एक बार जब आप प्रोजेक्ट फ़ाइल लोड कर लेते हैं, तो आप इसका उपयोग करके हेडर और फ़ुटर जानकारी पुनः प्राप्त कर सकते हैं`PageInfo` संपत्ति।
```csharp
var info = project.DefaultView.PageInfo;
// शीर्षलेख सूचना
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// पादलेख सूचना
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
इन सरल चरणों का पालन करके, आप .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से हेडर और फ़ुटर जानकारी आसानी से प्राप्त कर सकते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से हेडर और फ़ुटर जानकारी कैसे निकाली जाए। यह शक्तिशाली लाइब्रेरी C# अनुप्रयोगों में प्रोजेक्ट फ़ाइलों के साथ काम करने के कार्य को सरल बनाती है, डेवलपर्स को हेरफेर के लिए मजबूत उपकरण प्रदान करती है।
### पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Tasks का उपयोग करके शीर्ष लेख और पाद लेख जानकारी को संशोधित कर सकता हूँ?
हां, आप .NET के लिए Aspose.Tasks का उपयोग करके हेडर और फ़ूटर जानकारी को प्रोग्रामेटिक रूप से संशोधित कर सकते हैं।
### क्या Aspose.Tasks MS प्रोजेक्ट के अलावा अन्य प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है?
हाँ, Aspose.Tasks MPP, XML और MPX सहित विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों का समर्थन करता है।
### क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप Aspose. Tasks का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे Aspose.Tasks के लिए दस्तावेज़ कहाँ मिल सकते हैं?
 आप Aspose.Tasks के लिए दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/tasks/net/).
### मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप पर जाकर Aspose.कार्यों के लिए समर्थन प्राप्त कर सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).