---
title: Aspose.Tasks के साथ MS प्रोजेक्ट प्रोग्रेस लाइन्स को संभालना
linktitle: Aspose.Tasks में प्रगति रेखाओं को संभालना
second_title: Aspose.Tasks .NET API
description: प्रोजेक्ट विज़ुअलाइज़ेशन और प्रबंधन को बढ़ाते हुए, .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों में प्रगति रेखाओं में हेरफेर करना सीखें।
type: docs
weight: 15
url: /hi/net/project-management-integration/progress-lines/
---
## परिचय
माइक्रोसॉफ्ट प्रोजेक्ट (एमएस प्रोजेक्ट) परियोजना प्रबंधन के लिए एक शक्तिशाली उपकरण है, जो उपयोगकर्ताओं को अपनी परियोजनाओं के विभिन्न पहलुओं को ट्रैक करने की अनुमति देता है। एमएस प्रोजेक्ट की एक महत्वपूर्ण विशेषता प्रगति रेखाओं को देखने की क्षमता है, जो हितधारकों को परियोजना की स्थिति और प्रक्षेपवक्र को समझने में मदद करती है। इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks लाइब्रेरी का उपयोग करके MS प्रोजेक्ट में प्रगति रेखाओं को कैसे प्रबंधित किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. विजुअल स्टूडियो: विजुअल स्टूडियो या कोई अन्य पसंदीदा .NET विकास वातावरण स्थापित करें।
2.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना फायदेमंद होगा।

## नामस्थान आयात करना
आरंभ करने के लिए, आइए आवश्यक नामस्थान आयात करें:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
अब, आइए प्रगति रेखाओं को संभालने के प्रत्येक चरण का विश्लेषण करें:
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 यहां, हम MS प्रोजेक्ट फ़ाइल लोड करते हैं`Project2.mpp` और इसकी स्थिति तिथि निर्धारित करें।
## चरण 2: गैंट चार्ट दृश्य को परिभाषित करें
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
हमने आगे के हेरफेर के लिए प्रोजेक्ट के दृश्य को गैंट चार्ट दृश्य में डाल दिया।
## चरण 3: प्रगति रेखाएँ परिभाषित करें
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
हम गैंट चार्ट दृश्य के लिए प्रगति रेखाओं को प्रारंभ करते हैं।
## चरण 4: प्रगति रेखा सेटिंग्स कॉन्फ़िगर करें
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
यहां, हम प्रगति रेखाओं के लिए विभिन्न गुण निर्धारित करते हैं, जैसे रेखा का रंग, पैटर्न, फ़ॉन्ट, आदि।
## चरण 5: प्रगति रेखा विन्यास की जाँच करें
```csharp
// आउटपुट प्रगति लाइन सेटिंग्स
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// अन्य सेटिंग्स आउटपुट करें...
```
हम सत्यापन के लिए कॉन्फ़िगर की गई प्रगति रेखा सेटिंग्स को आउटपुट करते हैं।
## चरण 6: प्रोजेक्ट फ़ाइल सहेजें
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
अंत में, हम संशोधित प्रोजेक्ट फ़ाइल को प्रगति पंक्तियों के साथ सहेजते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट प्रगति लाइनों को कैसे संभालना है। इन चरणों का पालन करके, आप प्रोग्रामेटिक रूप से अपनी एमएस प्रोजेक्ट फ़ाइलों में प्रगति रेखाओं को प्रभावी ढंग से अनुकूलित और विज़ुअलाइज़ कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं प्रगति रेखाओं के स्वरूप को और अधिक अनुकूलित कर सकता हूँ?
उत्तर: हां, आप अपनी आवश्यकताओं के अनुरूप विभिन्न गुणों जैसे लाइन रंग, पैटर्न और फ़ॉन्ट को समायोजित कर सकते हैं।
### प्रश्न: क्या Aspose.Tasks अन्य परियोजना प्रबंधन सुविधाओं का समर्थन करता है?
उत्तर: हाँ, Aspose.Tasks कार्यों, संसाधनों और कैलेंडर सहित MS प्रोजेक्ट फ़ाइलों के विभिन्न पहलुओं में हेरफेर करने के लिए व्यापक समर्थन प्रदान करता है।
### प्रश्न: क्या मैं Aspose.Tasks को अन्य .NET लाइब्रेरीज़ के साथ एकीकृत कर सकता हूँ?
उत्तर: बिल्कुल, Aspose.Tasks को अन्य .NET लाइब्रेरीज़ के साथ सहजता से एकीकृत करने के लिए डिज़ाइन किया गया है, जिससे आप अपने प्रोजेक्ट प्रबंधन अनुप्रयोगों को और बेहतर बना सकते हैं।
### प्रश्न: क्या Aspose.Tasks समर्थन के लिए कोई सामुदायिक मंच है?
 उत्तर: हां, आप Aspose.Tasks फोरम पर सहायक संसाधन पा सकते हैं और सहायता मांग सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: क्या Aspose.Tasks मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस प्रदान करता है?
 उत्तर: हां, आप मूल्यांकन के लिए अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).