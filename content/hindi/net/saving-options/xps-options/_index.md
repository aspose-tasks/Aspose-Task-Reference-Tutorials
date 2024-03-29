---
title: Aspose.Tasks के साथ एमएसपी को एक्सपीएस विकल्पों में बदलें
linktitle: Aspose.Tasks के लिए XPS विकल्प
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों को XPS प्रारूप में परिवर्तित करना सीखें। आसान एकीकरण, मजबूत कार्यक्षमता।
type: docs
weight: 21
url: /hi/net/saving-options/xps-options/
---
## परिचय
माइक्रोसॉफ्ट प्रोजेक्ट (एमएसपी) परियोजना प्रबंधन के लिए व्यापक रूप से उपयोग किया जाने वाला उपकरण है, जो परियोजना गतिविधियों की योजना, ट्रैकिंग और रिपोर्टिंग की सुविधा प्रदान करता है। .NET के लिए Aspose.Tasks एमएसपी फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए मजबूत कार्यक्षमता प्रदान करता है, जिससे डेवलपर्स को परियोजना प्रबंधन से संबंधित विभिन्न कार्यों को स्वचालित करने का अधिकार मिलता है। इस ट्यूटोरियल में, हम आवश्यक चरणों और विचारों की खोज करते हुए, एमएसपी दस्तावेज़ों से एक्सपीएस फ़ाइलें उत्पन्न करने के लिए .NET के लिए Aspose.Tasks का लाभ उठाएंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET के लिए Aspose.Tasks की स्थापना: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[वेबसाइट](https://releases.aspose.com/tasks/net/).
2. Microsoft प्रोजेक्ट दस्तावेज़: Microsoft प्रोजेक्ट दस्तावेज़ (.mpp) तैयार करें जिसे आप XPS प्रारूप में कनवर्ट करना चाहते हैं।

## नामस्थान आयात करें
प्रक्रिया को किकस्टार्ट करने के लिए, अपने .NET प्रोजेक्ट में आवश्यक नामस्थान आयात करें:
```csharp

using Aspose.Tasks.Saving;
```

## चरण 1: दस्तावेज़ निर्देशिका पथ सेट करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
```
 प्रतिस्थापित करें`"Your Document Directory"` उस पथ के साथ जहां आपका एमएसपी दस्तावेज़ स्थित है।
## चरण 2: एमएसपी दस्तावेज़ लोड करें
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
 यहां, हम एक नया प्रारंभ करते हैं`Project` एमएसपी दस्तावेज़ का पथ पारित करके आपत्ति करें।
## चरण 3: एक्सपीएस सेव विकल्प बनाएं
```csharp
// एक्सपीएस सेव विकल्प बनाएं और पैरामीटर्स को ट्यून करें
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
 इस चरण में, हम त्वरित करते हैं`XpsOptions`और पैरामीटर कॉन्फ़िगर करें। सेटिंग`RenderMetafileAsBitmap` को`true` मेटाफ़ाइल्स का उचित प्रतिपादन सुनिश्चित करता है।
## चरण 4: दस्तावेज़ को XPS के रूप में सहेजें
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
 अंत में, हम कॉल करते हैं`Save` पर विधि`Project` ऑब्जेक्ट, आउटपुट फ़ाइल पथ निर्दिष्ट करता है और पहले से कॉन्फ़िगर किया गया है`XpsOptions`.

## निष्कर्ष
अंत में, .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट दस्तावेज़ों को प्रोग्रामेटिक रूप से XPS प्रारूप में परिवर्तित करने की प्रक्रिया को सरल बनाता है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, डेवलपर्स इस कार्यक्षमता को अपने .NET अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं, जिससे परियोजना प्रबंधन वर्कफ़्लो आसानी से बढ़ सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या .NET के लिए Aspose.Tasks जटिल एमएसपी फ़ाइलों को संभाल सकता है?
उत्तर: हां, .NET के लिए Aspose.Tasks विभिन्न प्रारूपों में सटीक रूपांतरण सुनिश्चित करते हुए, जटिल Microsoft प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक संभाल सकता है।
### प्रश्न: क्या .NET के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: क्या .NET के लिए Aspose.Tasks XPS के अलावा अन्य आउटपुट स्वरूपों का समर्थन करता है?
उत्तर: हाँ, .NET के लिए Aspose.Tasks पीडीएफ, HTML, PNG और JPEG जैसे विभिन्न आउटपुट स्वरूपों का समर्थन करता है।
### प्रश्न: क्या मैं आउटपुट फ़ाइल के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल, .NET के लिए Aspose.Tasks आपकी आवश्यकताओं के अनुसार रेंडरिंग मापदंडों को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### प्रश्न: मुझे .NET के लिए Aspose.Tasks के लिए अतिरिक्त समर्थन या सहायता कहां मिल सकती है?
 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) .NET के लिए Aspose.Tasks के संबंध में किसी भी प्रश्न या सहायता के लिए।