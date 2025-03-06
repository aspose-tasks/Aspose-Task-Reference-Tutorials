---
title: Aspose.Tasks में MS प्रोजेक्ट संसाधन उपयोग दृश्य कॉन्फ़िगर करना
linktitle: Aspose.Tasks में संसाधन उपयोग दृश्य कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधन उपयोग दृश्यों को कॉन्फ़िगर करने का तरीका जानें। कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका शामिल है।
weight: 15
url: /hi/net/resource-risk-analysis/resource-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट संसाधन उपयोग दृश्य कॉन्फ़िगर करना

## परिचय
माइक्रोसॉफ्ट प्रोजेक्ट (एमएस प्रोजेक्ट) परियोजना प्रबंधन के लिए एक शक्तिशाली उपकरण है, जो उपयोगकर्ताओं को अपनी परियोजनाओं की कुशलतापूर्वक योजना बनाने, निष्पादित करने और ट्रैक करने की अनुमति देता है। .NET के लिए Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के साथ सहज एकीकरण प्रदान करता है, जिससे डेवलपर्स प्रोजेक्ट डेटा को प्रोग्रामेटिक रूप से हेरफेर करने में सक्षम होते हैं। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधन उपयोग दृश्यों को कैसे कॉन्फ़िगर किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/).
2. Microsoft प्रोजेक्ट फ़ाइल: एक Microsoft प्रोजेक्ट फ़ाइल रखें (`.mpp`) जिसमें वह प्रोजेक्ट डेटा शामिल है जिसके साथ आप काम करना चाहते हैं।

## नामस्थान आयात करें
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
सबसे पहले, Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइल लोड करें:
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## चरण 2: सहेजें विकल्प परिभाषित करें
आवश्यक टाइमस्केल सेटिंग्स और प्रस्तुति प्रारूप को निर्दिष्ट करते हुए सेव विकल्पों को परिभाषित करें:
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## चरण 3: प्रोजेक्ट को संसाधन उपयोग दृश्यों के साथ सहेजें
कॉन्फ़िगर किए गए संसाधन उपयोग दृश्यों के साथ प्रोजेक्ट को एक पीडीएफ फ़ाइल में सहेजें:
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधन उपयोग दृश्यों को कैसे कॉन्फ़िगर किया जाए। दिए गए चरणों का पालन करके, डेवलपर्स प्रोजेक्ट डेटा में कुशलतापूर्वक हेरफेर करने के लिए Aspose.Tasks को अपने .NET अनुप्रयोगों में एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
उत्तर: हाँ, Aspose.Tasks .mpp, .mpt, .xml, और .mpx सहित Microsoft Project फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### प्रश्न: क्या मैं टाइमस्केल सेटिंग्स और प्रस्तुति प्रारूप को और अधिक अनुकूलित कर सकता हूं?
उत्तर: बिल्कुल, Aspose.Tasks आपकी आवश्यकताओं के अनुसार टाइमस्केल सेटिंग्स और प्रस्तुति प्रारूपों को अनुकूलित करने के लिए लचीलापन प्रदान करता है।
### प्रश्न: क्या Aspose.Tasks पीडीएफ के अलावा अन्य आउटपुट स्वरूपों का समर्थन करता है?
उत्तर: हाँ, Aspose.Tasks XLSX, MPP, XML, HTML और अन्य सहित विभिन्न प्रकार के आउटपुट स्वरूपों का समर्थन करता है।
### प्रश्न: क्या Aspose.Tasks समर्थन के लिए कोई समुदाय या मंच है?
 उत्तर: हां, आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) किसी भी प्रश्न, चर्चा या समर्थन आवश्यकता के लिए।
### प्रश्न: क्या मैं खरीदने से पहले Aspose.Tasks आज़मा सकता हूँ?
 उ: बेशक, आप नि:शुल्क परीक्षण के साथ Aspose.Tasks का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
