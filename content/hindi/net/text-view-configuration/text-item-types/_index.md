---
title: Aspose.Tasks में टेक्स्ट आइटम प्रकार अनुकूलन गाइड
linktitle: Aspose.Tasks में टेक्स्ट आइटम प्रकारों को संभालना
second_title: Aspose.Tasks .NET API
description: इस चरण-दर-चरण मार्गदर्शिका के साथ .NET के लिए Aspose.Tasks में मास्टर टेक्स्ट आइटम प्रकार अनुकूलन। अपने प्रोजेक्ट प्रबंधन गेम को सहजता से उन्नत करें।
type: docs
weight: 10
url: /hi/net/text-view-configuration/text-item-types/
---
## परिचय
यदि आप एक .NET डेवलपर हैं जो Aspose.Tasks का उपयोग करके प्रोजेक्ट प्रबंधन में रुचि ले रहे हैं, तो आप सही जगह पर आए हैं! इस चरण-दर-चरण मार्गदर्शिका में, हम शक्तिशाली .NET लाइब्रेरी का उपयोग करके अनुकूलन पर ध्यान केंद्रित करते हुए, Aspose.Tasks में टेक्स्ट आइटम प्रकारों को संभालने की जटिलताओं का पता लगाएंगे।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Tasks: सुनिश्चित करें कि आपके पास Aspose.Tasks लाइब्रेरी स्थापित है। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. दस्तावेज़ निर्देशिका: अपने प्रोजेक्ट दस्तावेज़ों के लिए एक निर्देशिका सेट करें।
अब, आइए टेक्स्ट आइटम प्रकारों को संभालने की बारीकियों पर गौर करें।
## नामस्थान आयात करें
सबसे पहली बात, अपने प्रोजेक्ट को किकस्टार्ट करने के लिए आवश्यक नामस्थान आयात करें:
```csharp
    using Aspose.Tasks;
    using System.Collections.Generic;
    using System.Drawing;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```csharp
String DataDir = "Your Document Directory";
```
अपने प्रोजेक्ट दस्तावेज़ों के वास्तविक पथ के साथ "आपकी दस्तावेज़ निर्देशिका" को बदलना सुनिश्चित करें।
## चरण 2: प्रोजेक्ट लोड करें और अनुकूलित करें
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
Aspose.Tasks लाइब्रेरी का उपयोग करके अपनी प्रोजेक्ट फ़ाइल लोड करें (इस मामले में, "CreateProject2.mpp")।
## चरण 3: विकल्प और प्रस्तुति प्रारूप सहेजें
```csharp
SaveOptions options = new PdfSaveOptions
{
    PresentationFormat = PresentationFormat.ResourceSheet
};
```
सहेजें विकल्पों को परिभाषित करें, और अनुकूलन के लिए प्रस्तुति प्रारूप को संसाधन शीट पर सेट करें।
## चरण 4: टेक्स्ट शैली को अनुकूलित करें
```csharp
var style = new TextStyle(FontStyles.Italic | FontStyles.Bold)
{
    Color = Color.OrangeRed
};
style.ItemType = TextItemType.OverallocatedResources;
```
वांछित फ़ॉन्ट शैलियों, रंग के साथ एक टेक्स्ट शैली बनाएं और आइटम प्रकार को समग्र संसाधनों पर सेट करें।
## चरण 5: टेक्स्ट शैलियाँ लागू करें और सहेजें
```csharp
options.TextStyles = new List<TextStyle>
{
    style
};
project.Save(DataDir + "CustomizeTextStyle_out.pdf", options);
```
अपने प्रोजेक्ट में परिभाषित टेक्स्ट शैली लागू करें और अनुकूलित प्रोजेक्ट को पीडीएफ फाइल के रूप में सहेजें।
अन्य अनुकूलन आवश्यकताओं के लिए इन चरणों को दोहराएं, विभिन्न टेक्स्ट आइटम प्रकारों, फ़ॉन्ट शैलियों और रंगों के साथ प्रयोग करें।
## निष्कर्ष
बधाई हो! आपने अभी-अभी .NET के लिए Aspose.Tasks में टेक्स्ट आइटम प्रकारों को संभालने की सतह को खंगाला है। जैसे-जैसे आप अन्वेषण जारी रखें, देखें[प्रलेखन](https://reference.aspose.com/tasks/net/) गहन जानकारी के लिए.
### पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं Aspose.Tasks का निःशुल्क उपयोग कर सकता हूँ?
 उत्तर: Aspose.Tasks निःशुल्क परीक्षण प्रदान करता है। इसे ले लो[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
 उत्तर: Aspose.Tasks पर जाएँ[मंच](https://forum.aspose.com/c/tasks/15) विशेषज्ञ सहायता के लिए.
### प्रश्न: मैं अस्थायी लाइसेंस कैसे प्राप्त करूं?
 उत्तर: एक अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: क्या अन्य सुविधाओं के लिए कोई चरण-दर-चरण ट्यूटोरियल है?
उत्तर: Aspose.Tasks दस्तावेज़ में अधिक ट्यूटोरियल देखें।
### प्रश्न: मैं .NET के लिए Aspose.Tasks कहां से खरीद सकता हूं?
 उ: पुस्तकालय खरीदें[यहाँ](https://purchase.aspose.com/buy).