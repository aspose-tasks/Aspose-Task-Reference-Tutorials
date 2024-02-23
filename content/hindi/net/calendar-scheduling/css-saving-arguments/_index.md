---
title: Aspose.Tasks में CSS सेविंग आर्गुमेंट्स
linktitle: Aspose.Tasks में CSS सेविंग आर्गुमेंट्स
second_title: Aspose.Tasks .NET API
description: HTML आउटपुट को अनुकूलित करने के लिए .NET के लिए Aspose.Tasks में CSS तर्कों को सहेजना सीखें। अनुकूलित सीएसएस सेटिंग्स के साथ प्रस्तुतिकरण को बेहतर बनाएं।
type: docs
weight: 20
url: /hi/net/calendar-scheduling/css-saving-arguments/
---
## परिचय

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks का उपयोग करके CSS तर्कों को सहेजने की प्रक्रिया के बारे में विस्तार से जानेंगे। HTML तत्वों की प्रस्तुति को परिभाषित करने के लिए कैस्केडिंग स्टाइल शीट्स (सीएसएस) महत्वपूर्ण हैं। Aspose.Tasks हमें इन CSS विशेषताओं को कुशलतापूर्वक हेरफेर करने और सहेजने की अनुमति देता है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1.  इंस्टालेशन: सुनिश्चित करें कि आपने .NET के लिए Aspose.Tasks इंस्टॉल कर लिया है। आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/tasks/net/).

2. बुनियादी ज्ञान: C# और .NET विकास परिवेश से परिचित होने की अनुशंसा की जाती है।

## नामस्थान आयात करें

आरंभ करने के लिए, आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## चरण 1: सीएसएस सेविंग कॉलबैक को परिभाषित करें

सबसे पहले, हम सीएसएस फ़ाइलों की बचत को संभालने के लिए सीएसएस बचत कॉलबैक विधियों को परिभाषित करते हैं:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // अपना सीएसएस बचत तर्क यहां लागू करें
    }
}
```

## चरण 2: फ़ॉन्ट और छवि सेविंग कॉलबैक लागू करें

इसके बाद, फ़ॉन्ट और छवि बचत कॉलबैक विधियों को इसी तरह लागू करें:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // अपना फ़ॉन्ट बचत तर्क यहां लागू करें
}

public void ImageSaving(ImageSavingArgs args)
{
    // अपना छवि बचत तर्क यहां लागू करें
}
```

## चरण 3: सहेजें विकल्प कॉन्फ़िगर करें

अब, कार्यान्वित कॉलबैक का उपयोग करने के लिए HTML सेव विकल्पों को कॉन्फ़िगर करें:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // HTML बचत विकल्प कॉन्फ़िगर करें
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## चरण 4: अनुकूलित सीएसएस के साथ प्रोजेक्ट सहेजें

अंत में, अनुकूलित सीएसएस सेटिंग्स के साथ अपना प्रोजेक्ट सहेजें:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि .NET के लिए Aspose.Tasks का उपयोग करके CSS तर्कों को कैसे सहेजा जाए। सीएसएस सेविंग कॉलबैक को परिभाषित करके और HTML सेविंग विकल्पों को कॉन्फ़िगर करके, हम अपनी आवश्यकताओं के अनुसार सीएसएस विशेषताओं में कुशलतापूर्वक हेरफेर कर सकते हैं।

## पूछे जाने वाले प्रश्न

### Q1: .NET के लिए Aspose.Tasks क्या है?

A1: .NET के लिए Aspose.Tasks एक शक्तिशाली .NET API है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने में सक्षम बनाता है।

### Q2: क्या Aspose.Tasks के साथ HTML फ़ाइलों को सहेजते समय क्या मैं CSS विशेषताओं को अनुकूलित कर सकता हूँ?

उ2: हां, आप अपनी आवश्यकताओं के अनुसार सीएसएस विशेषताओं को अनुकूलित करने के लिए सीएसएस सेविंग कॉलबैक को परिभाषित कर सकते हैं।

### Q3: क्या .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के सभी संस्करणों के साथ संगत है?

A3: .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न वातावरणों में अनुकूलता सुनिश्चित करता है।

### Q4: मुझे .NET के लिए Aspose.Tasks के लिए व्यापक दस्तावेज़ कहाँ मिल सकते हैं?

 A4: आप इसका उल्लेख कर सकते हैं[प्रलेखन](https://reference.aspose.com/tasks/net/) विस्तृत जानकारी और उदाहरणों के लिए.

### Q5: क्या .NET के लिए Aspose.Tasks डेवलपर्स के लिए समर्थन प्रदान करता है?

 A5: हाँ, आप Aspose. Tasks समुदाय के माध्यम से समर्थन प्राप्त कर सकते हैं[मंच](https://forum.aspose.com/c/tasks/15).