---
title: Aspose.Tasks के साथ गैंट चार्ट कॉलम को अनुकूलित करें
linktitle: Aspose.Tasks में गैंट चार्ट कॉलम
second_title: Aspose.Tasks .NET API
description: विशिष्ट कार्य जानकारी को कुशलतापूर्वक प्रदर्शित करने के लिए .NET के लिए Aspose.Tasks में गैंट चार्ट कॉलम को अनुकूलित करना सीखें।
type: docs
weight: 21
url: /hi/net/tasks-project-management/gantt-chart-columns/
---
## परिचय
गैंट चार्ट परियोजना प्रबंधन में एक मौलिक उपकरण है, जो कार्यों, समयसीमा और संसाधनों का एक दृश्य प्रतिनिधित्व प्रदान करता है। .NET के लिए Aspose.Tasks विशिष्ट कार्य जानकारी प्रदर्शित करने के लिए कॉलम को अनुकूलित करने सहित गैंट चार्ट में हेरफेर करने के लिए शक्तिशाली क्षमताएं प्रदान करता है। इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks का उपयोग करके गैंट चार्ट कॉलम के साथ कैसे काम किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  इंस्टालेशन: .NET के लिए Aspose.Tasks आपके सिस्टम पर इंस्टॉल किया गया है। यदि नहीं, तो इसे यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
2. .NET विकास पर्यावरण: C# और .NET फ्रेमवर्क का कार्यसाधक ज्ञान।
3. नमूना प्रोजेक्ट फ़ाइल: एक नमूना Microsoft प्रोजेक्ट फ़ाइल रखें (`.mpp`) प्रयोग करने में आसान। यदि आपके पास एक नहीं है, तो आप एमएस प्रोजेक्ट में एक साधारण प्रोजेक्ट बना सकते हैं और उसे सहेज सकते हैं।

## नामस्थान आयात करें
सबसे पहले, आपको .NET के लिए Aspose.Tasks के साथ काम करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
 का उपयोग करके प्रोजेक्ट फ़ाइल लोड करें`Project` Aspose.Tasks द्वारा प्रदान की गई कक्षा:
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## चरण 2: गैंट चार्ट कॉलम को परिभाषित करें
उन स्तंभों को परिभाषित करें जिन्हें आप गैंट चार्ट में प्रदर्शित करना चाहते हैं। आप अंतर्निहित फ़ील्ड निर्दिष्ट कर सकते हैं या कस्टम फ़ील्ड बना सकते हैं:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## चरण 3: कॉलमों पर पुनरावृति करें
उनके गुणों तक पहुँचने और जानकारी प्रदर्शित करने के लिए परिभाषित स्तंभों पर पुनरावृति करें:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## चरण 4: गैंट चार्ट को सीएसवी में सहेजें
गैंट चार्ट को परिभाषित कॉलम के साथ CSV फ़ाइल में सहेजें:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
इन चरणों का पालन करके, आप .NET के लिए Aspose.Tasks में गैंट चार्ट कॉलम के साथ प्रभावी ढंग से काम कर सकते हैं, जिससे आप आवश्यकतानुसार कार्य जानकारी को अनुकूलित और प्रदर्शित कर सकते हैं।

## निष्कर्ष
.NET के लिए Aspose.Tasks में गैंट चार्ट कॉलम के हेरफेर में महारत हासिल करने से आपकी विशिष्ट आवश्यकताओं के लिए परियोजना प्रबंधन दृश्यों को तैयार करने की अनंत संभावनाएं खुलती हैं। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप कार्य जानकारी को कुशलतापूर्वक संभाल सकते हैं और परियोजना की स्पष्टता और संगठन को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं .NET के लिए Aspose.Tasks में कस्टम कॉलम बना सकता हूँ?
उ: हां, आप अपनी परियोजना आवश्यकताओं के अनुसार विशिष्ट कार्य विशेषताओं को प्रदर्शित करने के लिए कस्टम कॉलम परिभाषित कर सकते हैं।
### प्रश्न: क्या .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के सभी संस्करणों के साथ संगत है?
उत्तर: .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न प्रोजेक्ट परिवेशों में अनुकूलता सुनिश्चित करता है।
### प्रश्न: मैं .NET के लिए Aspose.Tasks के साथ जटिल परियोजना संरचनाओं को कैसे संभाल सकता हूं?
उत्तर: .NET के लिए Aspose.Tasks लचीलेपन और स्केलेबिलिटी की पेशकश करते हुए जटिल परियोजना संरचनाओं को प्रबंधित करने के लिए व्यापक एपीआई और सुविधाएँ प्रदान करता है।
### प्रश्न: क्या गैंट चार्ट में मेरे द्वारा जोड़े जा सकने वाले कॉलमों की संख्या की कोई सीमा है?
उ: .NET के लिए Aspose.Tasks व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे आप बिना किसी सीमा के गैंट चार्ट में महत्वपूर्ण संख्या में कॉलम जोड़ सकते हैं।
### प्रश्न: मुझे .NET के लिए Aspose.Tasks के लिए अतिरिक्त समर्थन और संसाधन कहां मिल सकते हैं?
उत्तर: आप व्यापक संसाधनों और सहायता तक पहुंचने के लिए .NET के लिए Aspose.Tasks द्वारा प्रदान किए गए दस्तावेज़, सामुदायिक मंच और समर्थन चैनलों का पता लगा सकते हैं।