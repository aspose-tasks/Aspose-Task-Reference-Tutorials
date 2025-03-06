---
title: Aspose.Tasks में इमेज सेविंग को संभालना
linktitle: Aspose.Tasks में इमेज सेविंग को संभालना
second_title: Aspose.Tasks .NET API
description: चरण-दर-चरण दिशानिर्देशों का उपयोग करके .NET के लिए Aspose.Tasks में छवि बचत को संभालना सीखें। अपने .NET अनुप्रयोगों में छवि बचत कार्यक्षमता को निर्बाध रूप से एकीकृत करें।
weight: 10
url: /hi/net/advanced-concepts/image-saving/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में इमेज सेविंग को संभालना

## परिचय

इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks में इमेज सेविंग को संभालने की प्रक्रिया के बारे में विस्तार से जानेंगे। Aspose.Tasks एक शक्तिशाली एपीआई है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने में सक्षम बनाता है। प्रोजेक्ट फ़ाइलों के साथ काम करते समय एक सामान्य कार्य छवियों को सहेजने की आवश्यकता होती है, जिसमें चार्ट, ग्राफ़ या अन्य दृश्य तत्व शामिल हो सकते हैं। हम पूरी प्रक्रिया में स्पष्टता और समझ सुनिश्चित करते हुए चरण दर चरण प्रक्रिया को तोड़ेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:

1. विजुअल स्टूडियो: सुनिश्चित करें कि आपके सिस्टम पर विजुअल स्टूडियो स्थापित है।
2.  .NET के लिए Aspose.Tasks: .NET के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/net/).
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।

## नामस्थान आयात करें

सबसे पहले, आइए अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## चरण 1: एक प्रोजेक्ट ऑब्जेक्ट बनाएं

अपनी Microsoft प्रोजेक्ट फ़ाइल से एक प्रोजेक्ट ऑब्जेक्ट बनाकर प्रारंभ करें:

```csharp
var project = new Project("Project1.mpp");
```

## चरण 2: सहेजें विकल्प परिभाषित करें

पेजों और अन्य सेटिंग्स को निर्दिष्ट करते हुए, अपने प्रोजेक्ट के लिए सेव विकल्पों को परिभाषित करें:

```csharp
var options = GetSaveOptions(1);
```

## चरण 3: प्रोजेक्ट को HTML के रूप में सहेजें

निर्दिष्ट विकल्पों के साथ प्रोजेक्ट को HTML के रूप में सहेजें:

```csharp
project.Save("document_out.html", options);
```

## चरण 4: इमेज सेविंग कॉलबैक लागू करें

छवि बचत को संभालने के लिए ImageSavingCallback इंटरफ़ेस लागू करें:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // छवि बचत तर्क यहाँ जाता है
    }
}
```

## चरण 5: छवियों को निर्दिष्ट निर्देशिका में सहेजें

ImageSaving विधि के भीतर, छवियों को वांछित निर्देशिका में सहेजने के लिए तर्क निर्दिष्ट करें:

```csharp
if (args.FileName.EndsWith("png"))
{
    // नेस्टेड संसाधनों को बचाएं
}
else
{
    // नियमित संसाधन बचाएं
}
```

## चरण 6: सहेजें विकल्प निर्दिष्ट करें

सीएसएस, फ़ॉन्ट और छवियों के लिए कॉलबैक सहित सेव विकल्प निर्दिष्ट करें:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // यहां सेव विकल्प निर्दिष्ट करें
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## निष्कर्ष

अंत में, .NET के लिए Aspose.Tasks में इमेज सेविंग को संभालने में सेव विकल्पों को परिभाषित करना और सेविंग प्रक्रिया को प्रभावी ढंग से प्रबंधित करने के लिए कॉलबैक लागू करना शामिल है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप छवि बचत कार्यक्षमता को अपने .NET अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं HTML के अलावा अन्य प्रारूपों में प्रोजेक्ट फ़ाइलों में हेरफेर करने के लिए Aspose.Tasks का उपयोग कर सकता हूँ?

A1: हाँ, Aspose.Tasks PDF, XLSX और MPP जैसे विभिन्न प्रारूपों का समर्थन करता है।

### Q2: क्या Aspose.Tasks क्लाउड स्टोरेज एकीकरण के लिए समर्थन प्रदान करता है?

A2: हाँ, Aspose.Tasks Amazon S3 और Google Drive जैसी लोकप्रिय क्लाउड स्टोरेज सेवाओं के साथ काम करने के लिए API प्रदान करता है।

### Q3: क्या Aspose.Tasks .NET कोर के साथ संगत है?

A3: हाँ, Aspose.Tasks .NET कोर के साथ संगत है, जो आपको क्रॉस-प्लेटफ़ॉर्म एप्लिकेशन विकसित करने की अनुमति देता है।

### Q4: क्या मैं सहेजी गई छवियों के स्वरूप को अनुकूलित कर सकता हूँ?

उ4: हां, आप कॉलबैक विधियों के भीतर छवि बचत तर्क को संशोधित करके सहेजी गई छवियों की उपस्थिति को अनुकूलित कर सकते हैं।

### Q5: क्या Aspose.Tasks मूल्यांकन उद्देश्यों के लिए परीक्षण संस्करण प्रदान करता है?

 A5: हाँ, आप Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
