---
title: Aspose.Tasks में गैंट चार्ट टाइमस्केल टियर को कॉन्फ़िगर करना
linktitle: Aspose.Tasks में टाइमस्केल टियर को कॉन्फ़िगर करना
second_title: Aspose.Tasks .NET API
description: सटीक प्रोजेक्ट टाइमलाइन विज़ुअलाइज़ेशन के लिए अपने गैंट चार्ट दृश्य में टाइमस्केल स्तरों को कॉन्फ़िगर करने के लिए .NET के लिए Aspose.Tasks का अन्वेषण करें। #Aspose.Tasks #MS प्रोजेक्ट
weight: 16
url: /hi/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में गैंट चार्ट टाइमस्केल टियर को कॉन्फ़िगर करना

## परिचय
परियोजना प्रबंधन के गतिशील परिदृश्य में, समयसीमा और समय सीमा को समझने के लिए प्रभावी विज़ुअलाइज़ेशन महत्वपूर्ण है। .NET के लिए Aspose.Tasks एक शक्तिशाली टूलसेट प्रदान करता है, और इस ट्यूटोरियल में, हम यह पता लगाएंगे कि गैंट चार्ट दृश्य में इष्टतम प्रतिनिधित्व के लिए टाइमस्केल स्तरों को कैसे कॉन्फ़िगर किया जाए। अपने प्रोजेक्ट विज़ुअलाइज़ेशन को बढ़ाने के लिए इन चरण-दर-चरण निर्देशों का पालन करें।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# और .NET का बुनियादी ज्ञान।
-  .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
- .NET अनुप्रयोग विकास के लिए एक विकास वातावरण स्थापित किया गया।
## नामस्थान आयात करें
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
अब, आइए दिए गए उदाहरण के प्रत्येक चरण का विश्लेषण करें।
## चरण 1: प्रोजेक्ट आरंभ करें और कार्य लिंक जोड़ें
```csharp
// वें दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
यहां, हम एक प्रोजेक्ट बनाते हैं और "टास्क 1" और "टास्क 2" के बीच कार्य लिंक स्थापित करते हैं।
## चरण 2: गैंट चार्ट दृश्य कॉन्फ़िगर करें
```csharp
var view = (GanttChartView)project.DefaultView;
```
अनुकूलन के लिए गैंट चार्ट दृश्य तक पहुंचें।
## चरण 3: मध्य टाइमस्केल टियर को ट्यून करें
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
विशिष्ट लेबल और संरेखण के साथ सप्ताह प्रदर्शित करने के लिए मध्य समयमान स्तर को अनुकूलित करें।
## चरण 4: शीर्ष टाइमस्केल टियर जोड़ें
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
महीनों को दर्शाने के लिए एक शीर्ष टाइमस्केल टियर जोड़ें।
## चरण 5: मध्य स्तरीय तिथियों को अनुकूलित करें
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
बेहतर विज़ुअलाइज़ेशन के लिए महीने के लेबल को वैयक्तिकृत करें।
## चरण 6: प्रोजेक्ट टाइमस्केल सेट करें
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
समग्र समयरेखा को नियंत्रित करने के लिए प्रोजेक्ट टाइमस्केल को परिभाषित करें।
## चरण 7: प्रोजेक्ट को अनुकूलित टाइमस्केल के साथ सहेजें
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
प्रोजेक्ट को निर्धारित टाइमस्केल सेटिंग्स के साथ सहेजें।
## निष्कर्ष
अंत में, .NET के लिए Aspose.Tasks में टाइमस्केल स्तरों को कॉन्फ़िगर करने से प्रोजेक्ट टाइमलाइन के अधिक अनुरूप और दृश्यमान रूप से आकर्षक प्रतिनिधित्व की अनुमति मिलती है। ये चरण आपको एक गैंट चार्ट दृश्य बनाने के लिए सशक्त बनाते हैं जो आपकी परियोजना प्रबंधन आवश्यकताओं को सटीक रूप से पूरा करता है।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य .NET लाइब्रेरीज़ के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
हां, Aspose.Tasks अन्य .NET लाइब्रेरीज़ के साथ सहजता से एकीकृत होता है, जो आपके विकास स्टैक में लचीलापन प्रदान करता है।
### क्या परीक्षण प्रयोजनों के लिए अस्थायी लाइसेंस उपलब्ध है?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) मूल्यांकन के लिए।
### क्या गैंट चार्ट दृश्य के लिए अतिरिक्त अनुकूलन विकल्प हैं?
बिल्कुल, Aspose.Tasks विभिन्न परियोजना आवश्यकताओं के अनुरूप गैंट चार्ट दृश्य के लिए व्यापक अनुकूलन विकल्प प्रदान करता है।
### क्या मैं विभिन्न प्रारूपों में टाइमस्केल प्रस्तुत कर सकता हूँ?
निश्चित रूप से, आप अपने प्रोजेक्ट के संदर्भ में सर्वोत्तम रूप से फिट होने के लिए टाइमस्केल प्रतिनिधित्व के लिए विभिन्न प्रारूपों और शैलियों का पता लगा सकते हैं।
### क्या Aspose.Tasks समर्थन के लिए कोई सामुदायिक मंच है?
 हाँ, पर जाएँ[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
