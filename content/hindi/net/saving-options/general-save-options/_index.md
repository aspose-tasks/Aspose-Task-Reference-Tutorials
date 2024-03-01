---
title: Aspose.Tasks के लिए MS प्रोजेक्ट सेव विकल्पों में महारत हासिल करना
linktitle: Aspose.Tasks के लिए सामान्य सहेजें विकल्प
second_title: Aspose.Tasks .NET API
description: .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक सहेजना सीखें। अपनी परियोजनाओं के लिए आउटपुट विकल्पों को सहजता से अनुकूलित करें।
type: docs
weight: 17
url: /hi/net/saving-options/general-save-options/
---
## परिचय
.NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Tasks द्वारा उपलब्ध कराए गए विभिन्न विकल्पों का उपयोग करके MS प्रोजेक्ट फ़ाइलों को सहेजने की जटिलताओं के बारे में जानेंगे। विशेष रूप से, हम Aspose.Tasks के लिए उपलब्ध सामान्य बचत विकल्पों पर ध्यान केंद्रित करेंगे, जिससे आप आउटपुट को अपनी विशिष्ट आवश्यकताओं के अनुरूप बना सकेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1.  .NET के लिए Aspose.Tasks की स्थापना: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/net/).
2. .NET फ्रेमवर्क की बुनियादी समझ: .NET प्रोग्रामिंग अवधारणाओं से परिचित होना फायदेमंद है।

## नामस्थान आयात करना
कोड में गोता लगाने से पहले, आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
सबसे पहले, आपको Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइल लोड करनी होगी:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## चरण 2: सहेजें विकल्प परिभाषित करें
 अपनी आवश्यकताओं के अनुसार सेव विकल्पों को परिभाषित करें। इस उदाहरण में, हम उपयोग कर रहे हैं`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## चरण 3: दृश्य कॉलम को अनुकूलित करें
आप गैंट चार्ट, संसाधन दृश्य और असाइनमेंट दृश्य जैसे दृश्य कॉलम को अनुकूलित कर सकते हैं। यहां प्रत्येक में कॉलम जोड़ने का तरीका बताया गया है:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## चरण 4: प्रोजेक्ट को विकल्पों के साथ सहेजें
अंत में, निर्दिष्ट विकल्पों के साथ प्रोजेक्ट को सहेजें:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## निष्कर्ष
.NET के लिए Aspose.Tasks के साथ सामान्य एमएस प्रोजेक्ट सेव विकल्पों में महारत हासिल करना आपको अपने प्रोजेक्ट की जरूरतों के अनुसार आउटपुट प्रारूप को कुशलतापूर्वक अनुकूलित करने का अधिकार देता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
उत्तर: हाँ, Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न वातावरणों में अनुकूलता सुनिश्चित करता है।
### प्रश्न: क्या मैं खरीदने से पहले Aspose.Tasks आज़मा सकता हूँ?
 उत्तर: हां, आप नि:शुल्क परीक्षण के साथ Aspose.Tasks का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे Aspose.Tasks के लिए दस्तावेज़ कहाँ मिल सकते हैं?
 उत्तर: विस्तृत दस्तावेज़ पाया जा सकता है[यहाँ](https://reference.aspose.com/tasks/net/), Aspose.Tasks सुविधाओं का उपयोग करने पर व्यापक मार्गदर्शन प्रदान करता है।
### प्रश्न: मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 उत्तर: मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: Aspose.Tasks से संबंधित प्रश्नों के लिए मैं कहां से सहायता मांग सकता हूं?
 उत्तर: आप Aspose.Tasks सामुदायिक मंच में शामिल हो सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15)विशेषज्ञों और साथी डेवलपर्स से सहायता प्राप्त करने के लिए।