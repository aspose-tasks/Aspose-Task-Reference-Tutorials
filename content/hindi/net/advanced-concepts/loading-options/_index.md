---
title: Aspose.Tasks में लोड करने के विकल्प
linktitle: Aspose.Tasks में लोड करने के विकल्प
second_title: Aspose.Tasks .NET API
description: चरण-दर-चरण मार्गदर्शन के साथ Microsoft प्रोजेक्ट दस्तावेज़ों को कुशलतापूर्वक प्रबंधित करने के लिए .NET के लिए Aspose.Tasks की शक्ति का उपयोग करना सीखें।
type: docs
weight: 16
url: /hi/net/advanced-concepts/loading-options/
---
## परिचय

.NET के लिए Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देती है। चाहे आपको प्रोजेक्ट फ़ाइलें बनाने, पढ़ने, लिखने या परिवर्तित करने की आवश्यकता हो, Aspose.Tasks आपके कार्यों को सुव्यवस्थित करने के लिए कार्यात्मकताओं की एक विस्तृत श्रृंखला प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Tasks का उपयोग करने की अनिवार्यताओं के बारे में विस्तार से जानेंगे, प्रमुख प्रक्रियाओं को सरल, कार्रवाई योग्य चरणों में विभाजित करेंगे।

## आवश्यक शर्तें

.NET के लिए Aspose.Tasks में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ स्थापित हैं:

1. विजुअल स्टूडियो: विजुअल स्टूडियो या अपनी पसंद का कोई अन्य आईडीई इंस्टॉल करें।
2.  .NET के लिए Aspose.Tasks: .NET लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें।[वेबसाइट](https://releases.aspose.com/tasks/net/).
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।

अब जब हमने अपनी पूर्वापेक्षाएँ कवर कर ली हैं, तो आइए आवश्यक नामस्थानों का पता लगाएं और चरण-दर-चरण मार्गदर्शिका में गोता लगाएँ।

## नामस्थान आयात करना

अपने C# प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करें:

1. Aspose.Tasks: यह नेमस्पेस प्रोजेक्ट दस्तावेजों के साथ काम करने के लिए मुख्य कक्षाएं और इंटरफेस प्रदान करता है।

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

अब, आइए विभिन्न कार्यों को चरण-दर-चरण मार्गदर्शिकाओं में विभाजित करें।

## चरण 1: पासवर्ड-संरक्षित प्रोजेक्ट लोड हो रहे हैं

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // प्रोजेक्ट फ़ाइल लोड करने के लिए FileStream प्रारंभ करें
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // LoadOptions उदाहरण बनाएँ
        var options = new LoadOptions
        {
            Password = "password" // पासवर्ड सेट करें
        };

        // प्रोजेक्ट को निर्दिष्ट विकल्पों के साथ लोड करें
        var project = new Project(stream, options);

        // प्रोजेक्ट का नाम प्रदर्शित करें
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

## चरण 2: प्रिमावेरा प्रोजेक्ट्स को कस्टम विकल्पों के साथ लोड करना

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // LoadOptions उदाहरण बनाएँ
    var loadOptions = new LoadOptions();

    // प्रिमावेरा पढ़ने के विकल्प कॉन्फ़िगर करें
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // प्रोजेक्ट यूआईडी सेट करें
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // प्रिमावेरा पढ़ने के विकल्प सेट करें
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // प्राइमेरा प्रोजेक्ट को निर्दिष्ट विकल्पों के साथ लोड करें
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // प्रोजेक्ट का नाम प्रदर्शित करें
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // लोड किए गए प्रोजेक्ट के साथ आगे की कार्रवाई करें
}
```

## चरण 3: फ़ाइल एन्कोडिंग निर्दिष्ट करना

```csharp
public void SpecifyFileEncoding()
{
    // LoadOptions उदाहरण बनाएँ
    LoadOptions lo = new LoadOptions();

    // प्रिमावेरा एक्सईआर फ़ाइल से प्रोजेक्ट खोलते समय एन्कोडिंग निर्दिष्ट करें
    lo.Encoding = Encoding.GetEncoding(1251);

    // प्रोजेक्ट को निर्दिष्ट एन्कोडिंग के साथ लोड करें
    var project = new Project("encoding1251.xer", lo);

    // लोड किए गए प्रोजेक्ट के साथ आगे की कार्रवाई करें
}
```

## चरण 4: त्रुटि प्रबंधन के साथ प्रिमावेरा प्रोजेक्ट्स को लोड करना

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // LoadOptions उदाहरण बनाएँ
    var loadOptions = new LoadOptions();

    // प्रिमावेरा पढ़ने के विकल्प कॉन्फ़िगर करें
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // प्रोजेक्ट यूआईडी सेट करें
    };

    // प्रिमावेरा पढ़ने के विकल्प सेट करें
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    //कस्टम त्रुटि प्रबंधन सेट करें
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // प्राइमेरा प्रोजेक्ट को निर्दिष्ट विकल्पों और त्रुटि प्रबंधन के साथ लोड करें
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // लोड किए गए प्रोजेक्ट के साथ आगे की कार्रवाई करें
}

// कस्टम त्रुटि हैंडलर विधि
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // कस्टम त्रुटि प्रबंधन तर्क लागू करें
}
```

इन चरणों का पालन करके, आप अपनी आवश्यकताओं के अनुसार प्रोजेक्ट दस्तावेज़ों में हेरफेर करने के लिए .NET के लिए Aspose.Tasks में लोडिंग विकल्पों का प्रभावी ढंग से उपयोग कर सकते हैं।

## निष्कर्ष

इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Tasks में लोडिंग विकल्पों के साथ काम करने के बुनियादी सिद्धांतों का पता लगाया है। पासवर्ड-सुरक्षित प्रोजेक्ट लोड करने से लेकर कस्टम त्रुटि प्रबंधन निर्दिष्ट करने तक, इन तकनीकों में महारत हासिल करने से आप अपने .NET अनुप्रयोगों के भीतर प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक प्रबंधित करने में सशक्त होंगे।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट के सभी संस्करणों के साथ संगत है?

A1: हाँ, .NET के लिए Aspose.Tasks Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न वातावरणों में अनुकूलता सुनिश्चित करता है।

### Q2: क्या मैं .NET के लिए Aspose.Tasks को अन्य तृतीय-पक्ष लाइब्रेरीज़ के साथ एकीकृत कर सकता हूँ?

A2: बिल्कुल, .NET के लिए Aspose.Tasks अन्य .NET लाइब्रेरीज़ के साथ सहजता से एकीकृत होता है, जो उन्नत कार्यक्षमता और लचीलेपन की पेशकश करता है।

### Q3: क्या .NET के लिए Aspose.Tasks दस्तावेज़ीकरण और समर्थन संसाधन प्रदान करता है?

 उ3: हाँ, आप व्यापक का उल्लेख कर सकते हैं[प्रलेखन](https://reference.aspose.com/tasks/net/) और के माध्यम से समर्थन तक पहुंचें[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).

### Q4: क्या .NET के लिए Aspose.Tasks के लिए कोई लाइसेंसिंग विकल्प उपलब्ध हैं?

 उ4: हां, आप नि:शुल्क परीक्षण और अस्थायी लाइसेंस सहित विभिन्न लाइसेंसिंग विकल्प तलाश सकते हैं[Aspose.कार्य वेबसाइट](https://purchase.aspose.com/buy).

### Q5: .NET के लिए Aspose.Tasks के लिए अपडेट और नई सुविधाएँ कितनी बार जारी की जाती हैं?

A5: .NET के लिए Aspose.Tasks को विकसित प्रौद्योगिकियों के साथ इष्टतम प्रदर्शन और अनुकूलता सुनिश्चित करने के लिए नियमित अपडेट और फीचर संवर्द्धन प्राप्त होते हैं।