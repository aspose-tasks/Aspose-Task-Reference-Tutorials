---
title: .NET के लिए Aspose.Tasks में MS प्रोजेक्ट XLSX विकल्प कॉन्फ़िगर करें
linktitle: Aspose.Tasks में XLSX विकल्पों को कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks में MS Project XLSX विकल्पों को कॉन्फ़िगर करने का तरीका जानें। कॉलम, एन्कोडिंग और अधिक सहजता से अनुकूलित करें।
type: docs
weight: 11
url: /hi/net/file-format-options/configuring-xlsx-options/
---
## परिचय
माइक्रोसॉफ्ट प्रोजेक्ट (एमएस प्रोजेक्ट) प्रोजेक्ट प्रबंधन के लिए एक शक्तिशाली उपकरण है, और .NET के लिए Aspose.Tasks प्रोग्रामेटिक रूप से एमएस प्रोजेक्ट फ़ाइलों के साथ काम करने के लिए निर्बाध एकीकरण प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट XLSX विकल्पों को कॉन्फ़िगर करने की प्रक्रिया से गुजरेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
### 1. .NET के लिए Aspose.Tasks स्थापित
 सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए Aspose.Tasks स्थापित है। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[.NET डाउनलोड पेज के लिए Aspose.Tasks](https://releases.aspose.com/tasks/net/).
### 2. C# और .NET फ्रेमवर्क की बुनियादी समझ
इस ट्यूटोरियल के साथ सी# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क से परिचित होना आवश्यक है।
### 3. माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल
एक Microsoft प्रोजेक्ट फ़ाइल (MPP) तैयार रखें जिसे आप XLSX फ़ाइल के रूप में कॉन्फ़िगर और सहेजना चाहते हैं।

## नामस्थान आयात करना
आरंभ करने के लिए, आवश्यक नामस्थान आयात करें:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## चरण 1: प्रोजेक्ट लोड करें
```csharp
var project = new Project("YourProjectFile.mpp");
```
वह Microsoft प्रोजेक्ट फ़ाइल लोड करें जिसे आप कॉन्फ़िगर करना चाहते हैं।
## चरण 2: XlsxOptions को परिभाषित करें
```csharp
var options = new XlsxOptions();
```
 का एक उदाहरण बनाएं`XlsxOptions` XLSX के रूप में सहेजने के लिए सेटिंग्स कॉन्फ़िगर करने के लिए।
## चरण 3: गैंट चार्ट कॉलम जोड़ें
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
विकल्पों में वांछित गैंट चार्ट कॉलम जोड़ें।
## चरण 4: संसाधन दृश्य कॉलम जोड़ें
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
विकल्पों में संसाधन दृश्य के लिए वांछित कॉलम शामिल करें।
## चरण 5: असाइनमेंट व्यू कॉलम जोड़ें
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
विकल्पों में असाइनमेंट दृश्य के लिए वांछित कॉलम जोड़ें।
## चरण 6: एन्कोडिंग सेट करें
```csharp
options.Encoding = Encoding.Unicode;
```
आउटपुट फ़ाइल के लिए एन्कोडिंग सेट करें।
## चरण 7: प्रोजेक्ट को XLSX के रूप में सहेजें
```csharp
project.Save("OutputFile.xlsx", options);
```
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को XLSX फ़ाइल के रूप में सहेजें।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट XLSX विकल्पों को कैसे कॉन्फ़िगर किया जाए। इन चरणों का पालन करके, आप अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो के लचीलेपन और उपयोगिता को बढ़ाते हुए, अपनी आवश्यकताओं के अनुसार आउटपुट प्रारूप को अनुकूलित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या मैं गैंट चार्ट, रिसोर्स व्यू और असाइनमेंट व्यू के लिए अलग-अलग कॉलम कॉन्फ़िगर कर सकता हूं?

उत्तर: हाँ, आप .NET के लिए Aspose.Tasks का उपयोग करके प्रत्येक दृश्य के लिए कॉलम को स्वतंत्र रूप से अनुकूलित कर सकते हैं।

### प्रश्न: क्या .NET के लिए Aspose.Tasks खरीदने से पहले कोई परीक्षण संस्करण उपलब्ध है?

 उ: हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[.NET के लिए Aspose.Tasks पृष्ठ जारी करता है](https://releases.aspose.com/).

### प्रश्न: यदि कार्यान्वयन के दौरान मुझे कोई समस्या आती है या मेरे कोई प्रश्न हैं तो मैं सहायता कैसे प्राप्त कर सकता हूं?

 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समुदाय और Aspose सहायता टीम से सहायता के लिए।

### प्रश्न: क्या मैं गैर-विंडोज़ प्लेटफ़ॉर्म पर .NET के लिए Aspose.Tasks के साथ XLSX फ़ाइलें उत्पन्न कर सकता हूँ?

उ: .NET के लिए Aspose.Tasks मुख्य रूप से विंडोज़ प्लेटफ़ॉर्म के लिए डिज़ाइन किया गया है, लेकिन आप अन्य प्लेटफ़ॉर्म के लिए संगतता विकल्प तलाश सकते हैं।

### प्रश्न: क्या परीक्षण उद्देश्यों के लिए कोई अस्थायी लाइसेंस विकल्प उपलब्ध हैं?

 उत्तर: हां, आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[Aspose. कार्य अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/).