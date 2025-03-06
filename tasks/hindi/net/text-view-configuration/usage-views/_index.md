---
title: Aspose.Tasks में उपयोग दृश्य कॉन्फ़िगर करना
linktitle: Aspose.Tasks में उपयोग दृश्य कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks में कार्य उपयोग दृश्यों को कॉन्फ़िगर करना सीखें। विस्तृत चरणों के साथ प्रोजेक्ट विज़ुअलाइज़ेशन बढ़ाएँ। अभी लाइब्रेरी डाउनलोड करें!
weight: 17
url: /hi/net/text-view-configuration/usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में उपयोग दृश्य कॉन्फ़िगर करना

## परिचय
यदि आप एक .NET डेवलपर हैं जो अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाना चाहते हैं, तो Aspose.Tasks एक शक्तिशाली उपकरण है जो आपको आसानी से Microsoft प्रोजेक्ट फ़ाइलों में हेरफेर करने की अनुमति देता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks का उपयोग करके उपयोग दृश्यों को कॉन्फ़िगर करने पर ध्यान केंद्रित करेंगे। बेहतर प्रोजेक्ट विज़ुअलाइज़ेशन के लिए विवरण के साथ कार्य उपयोग दृश्य प्रस्तुत करने में अंतर्दृष्टि प्राप्त करने के लिए अनुसरण करें।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  Aspose.Tasks लाइब्रेरी: सुनिश्चित करें कि आपके पास Aspose.Tasks लाइब्रेरी आपके .NET प्रोजेक्ट में एकीकृत है। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/) और स्थापना निर्देशों का पालन करें.
- दस्तावेज़ निर्देशिका: एक निर्देशिका स्थापित करें जहाँ आपके प्रोजेक्ट दस्तावेज़ संग्रहीत हैं। कोड स्निपेट में "आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलें।
## नामस्थान आयात करें
प्रदान किए गए कोड स्निपेट में, आप कुछ नामस्थानों के उपयोग को देखेंगे। निर्बाध एकीकरण के लिए इन्हें अपने प्रोजेक्ट में शामिल करना सुनिश्चित करें:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## चरण 1: विवरण के साथ कार्य उपयोग दृश्य प्रस्तुत करें
आइए विवरण के साथ कार्य उपयोग दृश्य प्रस्तुत करके शुरुआत करें। इन चरणों का पालन करें:
## चरण 1.1: प्रोजेक्ट लोड करें
```csharp
// वें दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## चरण 1.2: दृश्य प्राप्त करें
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## चरण 1.3: दृश्य सेटिंग्स अनुकूलित करें
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## चरण 1.4: प्रोजेक्ट को पीडीएफ के रूप में सहेजें
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## चरण 2: विवरण हेडर कॉलम प्रदर्शित करें
इस चरण में, हम विवरण हेडर कॉलम प्रदर्शित करने और प्रोजेक्ट को पीडीएफ के रूप में सहेजने के लिए दृश्य सेटिंग्स को संशोधित करेंगे:
## चरण 2.1: विवरण हेडर कॉलम प्रदर्शित करें
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## चरण 2.2: सभी पंक्तियों पर विवरण शीर्षलेख दोहराएं
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## चरण 2.3: प्रोजेक्ट को पीडीएफ के रूप में सहेजें
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## निष्कर्ष
बधाई हो! आपने Aspose.Tasks में उपयोग दृश्य सफलतापूर्वक कॉन्फ़िगर कर लिया है। यह ट्यूटोरियल Aspose.Tasks लाइब्रेरी का उपयोग करके कुशल परियोजना प्रबंधन और विज़ुअलाइज़ेशन के लिए एक आधार प्रदान करता है।

### अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: मुझे Aspose.Tasks दस्तावेज़ कहाँ मिल सकते हैं?
 व्यापक दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tasks/net/).
### प्रश्न: मैं .NET के लिए Aspose.Tasks कैसे डाउनलोड कर सकता हूं?
 लाइब्रेरी डाउनलोड करें[यहाँ](https://releases.aspose.com/tasks/net/).
### प्रश्न: मैं Aspose.Tasks कहां से खरीद सकता हूं?
 आप Aspose.Tasks खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### प्रश्न: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, नि:शुल्क परीक्षण का अन्वेषण करें[यहाँ](https://releases.aspose.com/).
### प्रश्न: समर्थन की आवश्यकता है या प्रश्न हैं?
 सहायता फ़ोरम पर जाएँ[यहाँ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
