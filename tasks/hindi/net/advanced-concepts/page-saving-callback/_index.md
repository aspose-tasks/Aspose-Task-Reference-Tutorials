---
title: Aspose.Tasks में पेज सेविंग कॉलबैक लागू करना
linktitle: Aspose.Tasks में पेज सेविंग कॉलबैक लागू करना
second_title: Aspose.Tasks .NET API
description: जानें कि .NET के लिए Aspose.Tasks में पेज सेविंग कॉलबैक को कैसे कार्यान्वित किया जाए, जिससे मल्टी-पेज दस्तावेज़ आउटपुट स्ट्रीम की अनुकूलित हैंडलिंग सक्षम हो सके।
weight: 12
url: /hi/net/advanced-concepts/page-saving-callback/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में पेज सेविंग कॉलबैक लागू करना

## परिचय

इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Tasks में पेज सेविंग कॉलबैक को कैसे लागू किया जाए। यह सुविधा हमें मल्टी-पेज दस्तावेज़ को उपयोगकर्ता द्वारा प्रदत्त स्ट्रीम में सहेजने की अनुमति देती है, जो आउटपुट को संभालने में लचीलापन और अनुकूलन प्रदान करती है।

## पूर्वावश्यकताएँ:

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. C# प्रोग्रामिंग भाषा का ज्ञान: आपको C# सिंटैक्स और अवधारणाओं की बुनियादी समझ होनी चाहिए।
   
2.  .NET के लिए Aspose.Tasks की स्थापना: सुनिश्चित करें कि आपने अपने विकास परिवेश में Aspose.Tasks लाइब्रेरी स्थापित की है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).

3. विकास परिवेश सेटअप: .NET विकास के लिए अपना पसंदीदा IDE सेट करें, जैसे विज़ुअल स्टूडियो।

## नामस्थान आयात करें:

आरंभ करने के लिए, आपको अपने C# कोड में आवश्यक नामस्थान आयात करने होंगे:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;

```

## चरण 1: एक प्रोजेक्ट ऑब्जेक्ट बनाएं

 त्वरित करें ए`Project` मौजूदा प्रोजेक्ट फ़ाइल लोड करके ऑब्जेक्ट करें:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## चरण 2: छवि सहेजें विकल्प कॉन्फ़िगर करें

 परिभाषित करना`ImageSaveOptions`और सेट करके पृष्ठ बचत व्यवहार को अनुकूलित करें`PageSavingCallback` संपत्ति:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

## चरण 3: कॉलबैक के साथ प्रोजेक्ट सहेजें

कॉन्फ़िगर किए गए छवि सहेजें विकल्पों का उपयोग करके प्रोजेक्ट को सहेजें:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## चरण 4: सहेजे गए पेज स्ट्रीम को संसाधित करें

प्रत्येक पृष्ठ को व्यक्तिगत रूप से संसाधित करने के लिए कॉलबैक द्वारा प्रदान की गई पृष्ठ स्ट्रीम के माध्यम से पुनरावृति करें:

```csharp
foreach (var stream in callback.PageStreams)
{
    // प्रत्येक पृष्ठ स्ट्रीम को संसाधित करें
}
```

## चरण 5: कस्टम पेज सेविंग कॉलबैक लागू करें

 एक क्लास बनाएं जो इसे लागू करे`IPageSavingCallback` पेज सेविंग को संभालने के लिए इंटरफ़ेस:

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // कोई भी सफ़ाई या अंतिम रूप देना
    }
}
```

## निष्कर्ष:

इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.Tasks में पेज सेविंग कॉलबैक को कैसे कार्यान्वित किया जाए, जिससे हम मल्टी-पेज दस्तावेज़ों को अलग-अलग स्ट्रीम में सहेज सकें। इन चरणों का पालन करके, आप अपने एप्लिकेशन की कार्यक्षमता बढ़ा सकते हैं और अनुकूलित आउटपुट हैंडलिंग प्राप्त कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: Aspose.Tasks में पेज सेविंग कॉलबैक क्या है?

A1: पेज सेविंग कॉलबैक Aspose.Tasks में एक सुविधा है जो उपयोगकर्ताओं को प्रत्येक पेज के लिए व्यक्तिगत रूप से स्ट्रीम प्रदान करके मल्टी-पेज दस्तावेज़ों की बचत प्रक्रिया को अनुकूलित करने में सक्षम बनाती है।

### Q2: क्या मैं इस कॉलबैक का उपयोग करके पृष्ठों को सहेजने के लिए विभिन्न प्रारूपों का उपयोग कर सकता हूँ?

उ2: हां, आप कॉलबैक के साथ पृष्ठों को सहेजने के लिए Aspose.Tasks द्वारा समर्थित विभिन्न फ़ाइल स्वरूपों, जैसे पीएनजी, जेपीईजी, पीडीएफ, आदि का उपयोग कर सकते हैं।

### Q3: क्या Aspose.Tasks .NET कोर के साथ संगत है?

A3: हाँ, Aspose.Tasks .NET Core का समर्थन करता है, जिससे डेवलपर्स को क्रॉस-प्लेटफ़ॉर्म अनुप्रयोगों में इसकी सुविधाओं का उपयोग करने की अनुमति मिलती है।

### Q4: मैं पृष्ठ सहेजने की प्रक्रिया के दौरान त्रुटियों को कैसे संभाल सकता हूँ?

A4: आप अपवादों को प्रबंधित करने और अपने एप्लिकेशन में मजबूती सुनिश्चित करने के लिए कॉलबैक विधियों के भीतर त्रुटि प्रबंधन तंत्र लागू कर सकते हैं।

### Q5: Aspose.Tasks के लिए मुझे अधिक संसाधन और समर्थन कहां मिल सकता है?

 A5: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सहायता के लिए, दस्तावेज़ तक पहुंचें[यहाँ](https://reference.aspose.com/tasks/net/) , या अतिरिक्त सुविधाओं और लाइसेंसिंग विकल्पों का पता लगाएं[Aspose.कार्य वेबसाइट](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
