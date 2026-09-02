---
date: 2026-04-06
description: Aspose.Tasks for .NET में सभी बेसलाइन को कैसे हटाएँ और बेसलाइन संग्रहों
  को कैसे प्रबंधित करें, चरण‑दर‑चरण कोड उदाहरणों के साथ सीखें।
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Aspose.Tasks बेसलाइन संग्रह के साथ सभी बेसलाइन हटाएँ
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks बेसलाइन संग्रह के साथ सभी बेसलाइन हटाएँ
url: /hi/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks बेसलाइन कलेक्शन के साथ सभी बेसलाइन हटाएँ

## परिचय

Aspose.Tasks for .NET आपको Microsoft Project फ़ाइलों को सीधे आपके .NET एप्लिकेशन से नियंत्रित करने की सुविधा देता है। सबसे शक्तिशाली सुविधाओं में से एक है **delete all baselines** करने की क्षमता, जो तब आवश्यक होती है जब आपको प्रोजेक्ट के ट्रैकिंग डेटा को रीसेट करना हो या नई बेसलाइन अवधि शुरू करनी हो। इस ट्यूटोरियल में हम पूरी प्रक्रिया को समझेंगे—एक प्रोजेक्ट फ़ाइल लोड करने से लेकर किसी विशिष्ट रिसोर्स से जुड़ी हर बेसलाइन को हटाने तक—स्पष्ट, संवादात्मक व्याख्याओं और तैयार‑चलाने‑योग्य C# कोड के साथ।

## त्वरित उत्तर
- **“delete all baselines” क्या करता है?** यह चयनित रिसोर्स के लिए संग्रहीत सभी बेसलाइन रिकॉर्ड को हटा देता है, जिससे ऐतिहासिक लागत और कार्य डेटा साफ़ हो जाता है।  
- **मुझे यह क्यों चाहिए?** प्रमुख प्रोजेक्ट परिवर्तन के बाद ट्रैकिंग रीसेट करने या जब मूल बेसलाइन अब प्रासंगिक न हों, तब।  
- **कौन सी लाइब्रेरी यह क्षमता प्रदान करती है?** Aspose.Tasks for .NET।  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है; एक फ्री ट्रायल उपलब्ध है।  
- **क्या कोड .NET 6+ के साथ संगत है?** हाँ, API .NET Framework 4.5+, .NET Core 3.1+, और .NET 5/6 के साथ काम करता है।

## बेसलाइन क्या है और सभी बेसलाइन क्यों हटाएँ?

एक बेसलाइन लागत, कार्य और शेड्यूल की मूल योजना को एक विशिष्ट समय बिंदु पर कैप्चर करती है। प्रोजेक्ट के जीवनकाल में आप कई बेसलाइन (Baseline 1, Baseline 2, आदि) बना सकते हैं ताकि वास्तविक प्रगति की तुलना विभिन्न योजना स्नैपशॉट्स से की जा सके। हालांकि, कुछ स्थितियों—जैसे प्रोजेक्ट का पुनः‑स्कोप या नई शुरुआत—में इन ऐतिहासिक बेसलाइन को रखना भ्रमित कर सकता है। सभी बेसलाइन को हटाने से आपको एक साफ़ स्लेट मिलता है, जिससे आप वर्तमान वास्तविकता को दर्शाने वाली नई बेसलाइन सेट कर सकते हैं।

## आवश्यकताएँ

1. **Visual Studio** – कोई भी नवीनतम संस्करण (Community, Professional, या Enterprise)।  
2. **Aspose.Tasks for .NET** – इसे [डाउनलोड लिंक](https://releases.aspose.com/tasks/net/) से डाउनलोड करें।  
3. **Basic C# knowledge** – आपको वेरिएबल्स, लूप्स, और कंसोल आउटपुट के साथ सहज होना चाहिए।  
4. **A Microsoft Project file** (`.mpp`) – उदाहरणों में *WorkWithBaselineCollection.mpp* नामक एक सैंपल फ़ाइल उपयोग की जाएगी।

## नेमस्पेस आयात करें

पहले, आवश्यक नेमस्पेस को स्कोप में लाएँ ताकि कंपाइलर को पता हो कि हम कौन-कौन सी क्लासेज़ उपयोग करेंगे।

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें

हम एक मौजूदा प्रोजेक्ट फ़ाइल को लोड करके शुरू करते हैं। `DataDir` को उस फ़ोल्डर की ओर इंगित करने के लिए समायोजित करें जहाँ आपकी `.mpp` फ़ाइल स्थित है।

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## चरण 2: लक्ष्य संसाधन प्राप्त करें

प्रदर्शन के लिए हम UID = 1 वाले रिसोर्स को प्राप्त करते हैं। वास्तविक दुनिया में आप रिसोर्स को नाम या किसी अन्य पहचानकर्ता से खोजेंगे।

```csharp
var resource = project.Resources.GetByUid(1);
```

## चरण 3: मौजूदा बेसलाइन जानकारी प्रदर्शित करें

किसी भी चीज़ को हटाने से पहले, यह देखना उपयोगी होता है कि रिसोर्स से वर्तमान में कौन‑सी बेसलाइन जुड़ी हुई हैं। यह आपको यह सुनिश्चित करने में मदद करता है कि आप सही डेटा हटा रहे हैं।

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## चरण 4: सभी बेसलाइन पर इटररेट करें

यहाँ हम प्रत्येक बेसलाइन पर लूप करते हैं, लागत, कार्य, और अर्जित वैल्यू (BCWP/BCWS) जैसे प्रमुख मीट्रिक प्रिंट करते हैं। यह चरण वैकल्पिक है लेकिन लॉगिंग या ऑडिट उद्देश्यों के लिए उपयोगी हो सकता है।

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## सभी बेसलाइन हटाएँ

अब हम मुख्य कार्रवाई करते हैं: चयनित रिसोर्स के लिए **delete all baselines**। हम पहले कलेक्शन को एक सूची में कॉपी करते हैं ताकि इटररेट करते समय कलेक्शन को संशोधित न करना पड़े, फिर प्रत्येक बेसलाइन को एक‑एक करके हटाते हैं।

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

इस ब्लॉक के चलने के बाद, `resource.Baselines.Count` `0` हो जाएगा, जिससे पुष्टि होती है कि सभी बेसलाइन रिकॉर्ड साफ़ हो गए हैं।

## सामान्य समस्याएँ और सुझाव

- **NullReferenceException** – सुनिश्चित करें कि प्रोजेक्ट फ़ाइल में वास्तव में वह रिसोर्स मौजूद है जिसे आप टारगेट कर रहे हैं; अन्यथा `GetByUid` `null` लौटाएगा।  
- **Licensing** – वैध Aspose.Tasks लाइसेंस के बिना आप आउटपुट में वॉटरमार्क देखेंगे और कार्यक्षमता सीमित रहेगी।  
- **Performance** – बहुत बड़े प्रोजेक्ट्स के लिए, हटाने की प्रक्रिया को तेज़ करने हेतु `Parallel.ForEach` का उपयोग करने पर विचार करें, लेकिन याद रखें कि अंतर्निहित कलेक्शन थ्रेड‑सेफ़ नहीं है।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Tasks बड़े प्रोजेक्ट फ़ाइलों को संभाल सकता है?**  
**उत्तर:** हाँ, Aspose.Tasks प्रदर्शन के लिए अनुकूलित है और मल्टी‑गिगाबाइट `.mpp` फ़ाइलों को कुशलता से प्रोसेस कर सकता है।

**प्रश्न: क्या लाइब्रेरी सभी Microsoft Project संस्करणों के साथ संगत है?**  
**उत्तर:** Aspose.Tasks Project 2000 से लेकर Project 2024 तक का समर्थन करता है, जिसमें पुराने `.mpp` फ़ॉर्मेट और नए XML‑आधारित फ़ाइलें दोनों शामिल हैं।

**प्रश्न: क्या मैं बेसलाइन को हटाने से पहले कस्टमाइज़ कर सकता हूँ?**  
**उत्तर:** बिल्कुल। आप किसी भी बेसलाइन प्रॉपर्टी (cost, work, dates) को पढ़ या संशोधित कर सकते हैं, फिर उसे हटाने का निर्णय ले सकते हैं।

**प्रश्न: क्या Aspose.Tasks क्लाउड प्लेटफ़ॉर्म पर काम करता है?**  
**उत्तर:** हाँ, API किसी भी .NET‑संगत वातावरण पर चलती है, जिसमें Azure App Service, AWS Lambda (.NET Core के माध्यम से), और Docker कंटेनर शामिल हैं।

**प्रश्न: मैं समुदाय से मदद कहाँ प्राप्त कर सकता हूँ?**  
**उत्तर:** अन्य डेवलपर्स और Aspose स्टाफ से जुड़ने के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जाएँ।

## निष्कर्ष

इस गाइड में हमने Aspose.Tasks for .NET का उपयोग करके **delete all baselines** करने का तरीका दिखाया। चरण‑दर‑चरण कोड का पालन करके आप बेसलाइन डेटा रीसेट कर सकते हैं, प्रोजेक्ट ट्रैकिंग को साफ़ रख सकते हैं, और नई योजना चक्र के लिए अपना शेड्यूल तैयार कर सकते हैं। हटाने के बाद नई बेसलाइन बनाने के साथ प्रयोग करने में संकोच न करें ताकि आप देख सकें कि लाइब्रेरी प्रोजेक्ट फ़ाइल को कैसे अपडेट करती है।

---

**अंतिम अपडेट:** 2026-04-06  
**परीक्षित संस्करण:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}