---
date: 2026-03-08
description: Aspose.Tasks for .NET का उपयोग करके प्रोजेक्ट फ़ाइल को इम्पोर्ट करना
  सीखें, जिसमें फ़ाइल एन्कोडिंग निर्दिष्ट करना और Microsoft Project फ़ाइल को कुशलतापूर्वक
  लोड करना शामिल है।
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: प्रोजेक्ट फ़ाइल आयात – Aspose.Tasks में लोड करने के विकल्प
url: /hi/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Import Project File – Options for Loading in Aspose.Tasks

## Introduction

Aspose.Tasks for .NET Microsoft Project, Primavera, और अन्य फ़ॉर्मेट्स से **प्रोजेक्ट फ़ाइल** डेटा आयात करना आसान बनाता है। चाहे आपको पासवर्ड‑सुरक्षित फ़ाइल पढ़नी हो, कस्टम एन्कोडिंग सेट करनी हो, या पार्सिंग त्रुटियों को संभालना हो, लाइब्रेरी लोडिंग विकल्पों के माध्यम से आपको सूक्ष्म नियंत्रण देती है। इस ट्यूटोरियल में हम सबसे सामान्य परिदृश्यों को देखेंगे ताकि आप अपने .NET एप्लिकेशन में **Microsoft Project फ़ाइल** ऑब्जेक्ट्स को आत्मविश्वास के साथ **लोड** कर सकें।

## Quick Answers
- **प्रोजेक्ट फ़ाइल आयात करने का प्राथमिक तरीका क्या है?** `LoadOptions` इंस्टेंस के साथ `Project` कन्स्ट्रक्टर का उपयोग करें।  
- **क्या मैं पासवर्ड‑सुरक्षित फ़ाइलें खोल सकता हूँ?** हाँ—`LoadOptions` पर `Password` प्रॉपर्टी सेट करें।  
- **फ़ाइल एन्कोडिंग कैसे निर्दिष्ट करूँ?** `LoadOptions.Encoding` को एक `Encoding` ऑब्जेक्ट असाइन करें।  
- **क्या त्रुटि हैंडलिंग को कस्टमाइज़ किया जा सकता है?** बिल्कुल—`LoadOptions.ErrorHandler` को एक डेलीगेट प्रदान करें।  
- **क्या ये विकल्प Primavera फ़ाइलों के साथ काम करते हैं?** हाँ, `LoadOptions` के भीतर `PrimaveraReadOptions` के माध्यम से।

## Prerequisites

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **Visual Studio** (या कोई भी पसंदीदा .NET IDE)।  
2. **Aspose.Tasks for .NET** – इसे [वेबसाइट](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।  
3. **C#** सिंटैक्स और प्रोजेक्ट संरचना की बुनियादी समझ।

अब जब हम तैयार हैं, चलिए आवश्यक नेमस्पेस आयात करते हैं।

## Importing Namespaces

अपने C# प्रोजेक्ट में, नीचे दिए गए `using` स्टेटमेंट्स जोड़ें ताकि API क्लासेज उपलब्ध हों:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## How to Import Project File with Loading Options

नीचे चार व्यावहारिक उदाहरण दिए गए हैं जो सबसे अधिक उपयोग किए जाने वाले लोडिंग परिदृश्यों को कवर करते हैं।

### Step 1: Load a Password‑Protected Project

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Step 2: Load a Primavera Project with Custom Options

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Step 3: **Specify File Encoding** When Importing an XER File

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Step 4: Load a Primavera Project with Custom Error Handling

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

इन चरणों का पालन करके आप सटीक रूप से **प्रोजेक्ट फ़ाइल** डेटा आयात कर सकते हैं, लोडिंग प्रक्रिया को अपनी आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं, और अपने एप्लिकेशन को मजबूत बना सकते हैं।

## Common Issues & Tips

- **गलत पासवर्ड** – `Password` प्रॉपर्टी एक एक्सेप्शन फेंकेगी; लोड करने से पहले क्रेडेंशियल की जाँच करें।  
- **असमर्थित एन्कोडिंग** – सुनिश्चित करें कि आप जिस कोड पेज को निर्दिष्ट कर रहे हैं वह लक्ष्य मशीन पर मौजूद है (`Encoding.GetEncoding(1251)` सायरिलिक के लिए काम करता है)।  
- **Primavera विकल्प गायब** – यदि आपको टास्क UID संरक्षित रखने हैं, तो `PreserveUids = true` सेट करें; अन्यथा डुप्लिकेट IDs दिखाई दे सकती हैं।  
- **त्रुटि हैंडलर null लौटाता है** – `null` लौटाने से पार्सर समस्या वाले तत्व को स्किप कर देगा; आवश्यकतानुसार कस्टमाइज़ करें।

## Frequently Asked Questions

**Q: क्या Aspose.Tasks for .NET सभी Microsoft Project संस्करणों के साथ संगत है?**  
A: हाँ, यह Microsoft Project के कई संस्करणों को सपोर्ट करता है, इसलिए आप **Microsoft Project फ़ाइल** फ़ॉर्मेट्स को पुराने MPP फ़ाइलों से लेकर नवीनतम फ़ॉर्मेट्स तक **लोड** कर सकते हैं।

**Q: क्या मैं Aspose.Tasks for .NET को अन्य थर्ड‑पार्टी लाइब्रेरीज़ के साथ इंटीग्रेट कर सकता हूँ?**  
A: बिल्कुल। यह लाइब्रेरी अन्य .NET पैकेजों के साथ सहजता से काम करती है, जिससे आप इसे रिपोर्टिंग, UI, या डेटा‑एक्सेस फ्रेमवर्क के साथ संयोजित कर सकते हैं।

**Q: क्या Aspose.Tasks for .NET दस्तावेज़ीकरण और समर्थन संसाधन प्रदान करता है?**  
A: हाँ, आप व्यापक [दस्तावेज़ीकरण](https://reference.aspose.com/tasks/net/) देख सकते हैं और [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) के माध्यम से समर्थन प्राप्त कर सकते हैं।

**Q: क्या Aspose.Tasks for .NET के लिए लाइसेंसिंग विकल्प उपलब्ध हैं?**  
A: हाँ, आप विभिन्न लाइसेंसिंग विकल्पों का पता लगा सकते हैं, जिसमें फ्री ट्रायल और टेम्पररी लाइसेंस शामिल हैं, जो [Aspose.Tasks वेबसाइट](https://purchase.aspose.com/buy) पर उपलब्ध हैं।

**Q: Aspose.Tasks for .NET के लिए अपडेट और नई सुविधाएँ कितनी बार रिलीज़ होती हैं?**  
A: Aspose.Tasks नियमित रूप से अपडेट प्राप्त करता है जो नई सुविधाएँ जोड़ते हैं, प्रदर्शन सुधारते हैं, और नवीनतम Microsoft Project रिलीज़ के साथ संगतता बनाए रखते हैं।

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}