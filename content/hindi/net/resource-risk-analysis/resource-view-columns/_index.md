---
title: Aspose.Tasks में MS प्रोजेक्ट रिसोर्स व्यू कॉलम को कस्टमाइज़ करें
linktitle: Aspose.Tasks में संसाधन दृश्य कॉलम को अनुकूलित करना
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधन दृश्य कॉलम को कुशलतापूर्वक अनुकूलित करना सीखें। बेहतर परियोजना प्रबंधन के लिए अनुरूप विचार बनाएं।
type: docs
weight: 17
url: /hi/net/resource-risk-analysis/resource-view-columns/
---
## परिचय
.NET के लिए Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। परियोजना प्रबंधन में एक सामान्य कार्य विशिष्ट जानकारी प्रदर्शित करने के लिए दृश्यों को अनुकूलित करना है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधन दृश्य कॉलम को कैसे अनुकूलित किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Tasks: आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
2. माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल: परीक्षण के लिए एक नमूना एमएस प्रोजेक्ट फ़ाइल अपने पास रखें।
3. विकास पर्यावरण: .NET ढांचे के साथ स्थापित एक विकास वातावरण।
## नामस्थान आयात करें
सबसे पहले, आइए अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
Aspose.Tasks API का उपयोग करके MS प्रोजेक्ट फ़ाइल लोड करें:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## चरण 2: संसाधन प्राप्त करें और विकल्प परिभाषित करें
इसके बाद, वह संसाधन प्राप्त करें जिसके व्यू कॉलम को आप अनुकूलित करना चाहते हैं और पीडीएफ सेव विकल्पों को परिभाषित करना चाहते हैं:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## चरण 3: कस्टम कॉलम परिभाषित करें
अब, संसाधन दृश्य के लिए कस्टम कॉलम परिभाषित करें। आप विभिन्न फ़ील्ड निर्दिष्ट कर सकते हैं और यहां तक कि कस्टम गणना के लिए प्रतिनिधियों का उपयोग भी कर सकते हैं:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## चरण 4: कॉलमों पर पुनरावृति करें
परिभाषित स्तंभों पर पुनरावृति करें और उनके गुण प्रदर्शित करें:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## चरण 5: अनुकूलित दृश्य सहेजें
अंत में, कस्टम व्यू सेट करें और इसे पीडीएफ फाइल के रूप में सहेजें:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
इन चरणों का पालन करके, आप .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधन दृश्य कॉलम को कुशलतापूर्वक अनुकूलित कर सकते हैं।
## निष्कर्ष
आपके प्रोजेक्ट की आवश्यकताओं के अनुरूप प्रासंगिक जानकारी प्रदर्शित करने के लिए एमएस प्रोजेक्ट संसाधन दृश्य कॉलम को अनुकूलित करना आवश्यक है। .NET के लिए Aspose.Tasks के साथ, यह कार्य सीधा और कुशल हो जाता है, जिससे आप आसानी से अनुकूलित दृश्य बना सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं संसाधनों के अलावा अन्य तत्वों के लिए दृश्य अनुकूलित कर सकता हूँ?
हां, Aspose.Tasks कार्यों, असाइनमेंट और अन्य प्रोजेक्ट तत्वों के लिए भी अनुकूलन की अनुमति देता है।
### क्या Aspose.Tasks पीडीएफ के अलावा अन्य प्रारूपों में दृश्य सहेजने का समर्थन करता है?
हाँ, आप दृश्यों को XLSX, HTML और छवियों जैसे विभिन्न स्वरूपों में सहेज सकते हैं।
### क्या कस्टम व्यू पर फ़ॉर्मेटिंग लागू करना संभव है?
बिल्कुल, Aspose.Tasks आपके अनुकूलित दृश्यों की उपस्थिति को बढ़ाने के लिए व्यापक स्वरूपण विकल्प प्रदान करता है।
### क्या मैं बदलते प्रोजेक्ट डेटा के आधार पर कस्टम व्यू को गतिशील रूप से अपडेट कर सकता हूँ?
हां, जब भी अंतर्निहित प्रोजेक्ट डेटा बदलता है तो आप कस्टम व्यू को अपडेट और पुन: उत्पन्न कर सकते हैं।
### क्या Aspose.Tasks क्रॉस-प्लेटफ़ॉर्म विकास का समर्थन करता है?
.NET के लिए Aspose.Tasks मुख्य रूप से .NET प्लेटफ़ॉर्म को लक्षित करता है, लेकिन जावा और अन्य प्लेटफ़ॉर्म के लिए भी संस्करण उपलब्ध हैं।