---
title: Aspose.Tasks में MS प्रोजेक्ट फ़ाइलों को विभिन्न स्वरूपों में सहेजना
linktitle: Aspose.Tasks में विभिन्न प्रारूपों में फ़ाइलें सहेजना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों को विभिन्न स्वरूपों में सहेजना सीखें। कुशल परियोजना प्रबंधन के लिए आसान कदम.
type: docs
weight: 17
url: /hi/net/rate-recurring-tasks/save-file-formats/
---
## परिचय
इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks का उपयोग करके Microsoft Project फ़ाइलों को विभिन्न स्वरूपों में कैसे सहेजा जाए। Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर और प्रबंधित करने की अनुमति देता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
2. विकास परिवेश: एक .NET विकास परिवेश स्थापित करें, जैसे विज़ुअल स्टूडियो।
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा।

## नामस्थान आयात करें
अपनी C# फ़ाइल की शुरुआत में आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp

using Aspose.Tasks.Saving;
```
## चरण 1: एक प्रोजेक्ट ऑब्जेक्ट बनाएं
सबसे पहले, एक प्रोजेक्ट ऑब्जेक्ट बनाएं और अपनी Microsoft प्रोजेक्ट फ़ाइल लोड करें।
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## चरण 2: प्रोजेक्ट को सीएसवी प्रारूप में सहेजें
अब, प्रोजेक्ट को CSV प्रारूप में सहेजते हैं। 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## चरण 3: अन्य प्रारूपों का अन्वेषण करें
 Aspose.Tasks प्रोजेक्ट फ़ाइलों को सहेजने के लिए विभिन्न स्वरूपों का समर्थन करता है, जैसे XML, PDF, XLSX, और बहुत कुछ। आप बस इन्हें बदलकर इन प्रारूपों का पता लगा सकते हैं`SaveFileFormat` में पैरामीटर`Save` तरीका।
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
इन चरणों का पालन करके, आप .NET के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों को विभिन्न स्वरूपों में आसानी से सहेज सकते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों को विभिन्न स्वरूपों में कैसे सहेजा जाए। Aspose.Tasks डेवलपर्स को लचीलापन और दक्षता प्रदान करते हुए, प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने की प्रक्रिया को सरल बनाता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट के सभी संस्करणों के साथ संगत है?
उत्तर: Aspose.Tasks Microsoft Project 2003 XML, Microsoft Project 2007 MPP और Microsoft Project 2010 MPP स्वरूपों का समर्थन करता है।
### प्रश्न: क्या मैं खरीदने से पहले Aspose.Tasks आज़मा सकता हूँ?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 उत्तर: आप Aspose.Tasks समुदाय मंच से समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: क्या Aspose.Tasks के लिए अस्थायी लाइसेंस उपलब्ध हैं?
 उत्तर: हां, मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस उपलब्ध हैं। आप एक प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: Aspose.Tasks की कीमत क्या है?
 उ: मूल्य निर्धारण की जानकारी Aspose.Tasks खरीद पृष्ठ पर पाई जा सकती है[यहाँ](https://purchase.aspose.com/buy).