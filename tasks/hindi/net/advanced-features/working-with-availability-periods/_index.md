---
date: 2026-04-06
description: Aspose.Tasks for .NET का उपयोग करके प्रोजेक्ट में रिसोर्स जोड़ना और रिसोर्स
  की उपलब्धता अवधि सेट करना सीखें। रिसोर्स कैलेंडर प्रबंधन के लिए चरण‑दर‑चरण गाइड।
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Aspose.Tasks में उपलब्धता अवधि के साथ काम करना
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks में प्रोजेक्ट में संसाधन जोड़ें और उपलब्धता निर्धारित करें
url: /hi/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट में रिसोर्स जोड़ें और Aspose.Tasks में उपलब्धता सेट करें

## परिचय

इस ट्यूटोरियल में आप सीखेंगे **कैसे प्रोजेक्ट में रिसोर्स जोड़ें** और फिर Aspose.Tasks .NET लाइब्रेरी का उपयोग करके उसकी उपलब्धता अवधि निर्धारित करें। रिसोर्स कैलेंडर का प्रबंधन वास्तविक प्रोजेक्ट शेड्यूल के लिए आवश्यक है, और नीचे दिए गए चरण आपको पूरी प्रक्रिया के माध्यम से ले जाएंगे—प्रोजेक्ट इंस्टेंस बनाने से लेकर प्रत्येक अवधि के विवरण को प्रिंट करने तक।

## त्वरित उत्तर
- **मुख्य लक्ष्य क्या है?** प्रोजेक्ट में रिसोर्स जोड़ना और उसकी उपलब्धता अवधि कॉन्फ़िगर करना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for .NET.  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** हाँ, एक व्यावसायिक लाइसेंस आवश्यक है।  
- **समर्थित .NET संस्करण?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **इम्प्लीमेंटेशन समय?** आमतौर पर बुनियादी परिदृश्यों के लिए 15 मिनट से कम।

## “add resource to project” क्या है?

प्रोजेक्ट में रिसोर्स जोड़ने से एक प्लेसहोल्डर बनता है जो व्यक्ति, उपकरण, या सामग्री का प्रतिनिधित्व करता है जिसे कार्यों को असाइन किया जा सकता है। एक बार रिसोर्स मौजूद हो जाने पर, आप **रिसोर्स उपलब्धता सेट** कर सकते हैं, उसका कार्य कैलेंडर निर्धारित कर सकते हैं, और शेड्यूलर उन प्रतिबंधों का सम्मान करेगा।

## कार्य शेड्यूल और उपलब्धता अवधि को कॉन्फ़िगर क्यों करें?

- **सटीक योजना:** कार्य तभी शेड्यूल होते हैं जब रिसोर्स वास्तव में फ्री हो।  
- **लागत नियंत्रण:** उपलब्धता यूनिट्स पार्ट‑टाइम प्रयास को दर्शाते हैं, जिससे आप श्रम लागत सही ढंग से गणना कर सकते हैं।  
- **रिसोर्स लेवलिंग:** इंजन प्रत्येक रिसोर्स के कैलेंडर को जानने पर ओवर‑एलोकेशन को स्वचालित रूप से लेवल कर सकता है।

## पूर्वापेक्षाएँ

1. Visual Studio (या कोई भी .NET‑compatible IDE)।  
2. Aspose.Tasks for .NET – डाउनलोड करें [यहाँ](https://releases.aspose.com/tasks/net/).  
3. बेसिक C# ज्ञान।

## नेमस्पेस इम्पोर्ट करें

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## प्रोजेक्ट में रिसोर्स कैसे जोड़ें?

### चरण 1: नया `Project` इंस्टेंस बनाएं

```csharp
var project = new Project();
```

यह ऑब्जेक्ट मेमोरी में पूरे प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है।

### चरण 2: प्रोजेक्ट में एक रिसोर्स जोड़ें

```csharp
var resource = project.Resources.Add("Work Resource");
```

यह कॉल एक **रिसोर्स** बनाता है जिसका नाम *Work Resource* है, जिसे आप बाद में कार्यों से जोड़ सकते हैं।

### चरण 3: उपलब्धता अवधि निर्धारित करें

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` एक हेल्पर मेथड है (इम्प्लीमेंटेशन नहीं दिखाया गया) जो `AvailabilityPeriod` ऑब्जेक्ट्स का कलेक्शन रिटर्न करता है। प्रत्येक अवधि एक प्रारंभ तिथि, समाप्ति तिथि, और यूनिट्स (पूर्ण‑समय प्रयास का प्रतिशत) निर्दिष्ट करती है जिसमें रिसोर्स उपलब्ध है।

### चरण 4: अवधि को रिसोर्स में जोड़ें

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

यहाँ हम कलेक्शन पर लूप करके और प्रत्येक अवधि को रिसोर्स के कैलेंडर में जोड़कर **रिसोर्स उपलब्धता सेट** करते हैं।

### चरण 5: उपलब्धता विवरण दिखाएँ

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

कंसोल आउटपुट आपको यह सत्यापित करने देता है कि अवधि सही ढंग से संग्रहीत हुई हैं।

## सामान्य गलतियाँ और सुझाव

- **तारीख की सटीकता:** `AvailableFrom` और `AvailableTo` `DateTime` वैल्यूज़ हैं; यदि आप पूरे‑दिन की अवधि चाहते हैं तो उन्हें मध्यरात्रि पर सेट करें।  
- **यूनिट्स रेंज:** वैध मान 0‑100 % हैं; इस रेंज से बाहर के मान एक एक्सेप्शन थ्रो करेंगे।  
- **ओवर‑लैपिंग अवधि:** ओवरलैपिंग अवधि स्वचालित रूप से मर्ज हो जाती हैं, लेकिन स्पष्टता के लिए उन्हें अलग रखना बेहतर है।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं Aspose.Tasks for .NET को व्यावसायिक प्रोजेक्ट्स में उपयोग कर सकता हूँ?
A1: हाँ, Aspose.Tasks for .NET को व्यावसायिक प्रोजेक्ट्स में उपयोग किया जा सकता है। आप एक लाइसेंस खरीद सकते हैं [यहाँ](https://purchase.aspose.com/buy).

### Q2: क्या Aspose.Tasks for .NET के लिए कोई फ्री ट्रायल उपलब्ध है?
A2: हाँ, आप Aspose.Tasks for .NET का फ्री ट्रायल [यहाँ](https://releases.aspose.com/) प्राप्त कर सकते हैं।

### Q3: मैं Aspose.Tasks for .NET की डॉक्यूमेंटेशन कहाँ पा सकता हूँ?
A3: आप डॉक्यूमेंटेशन [यहाँ](https://reference.aspose.com/tasks/net/) पा सकते हैं।

### Q4: मैं Aspose.Tasks for .NET के लिए सपोर्ट कैसे प्राप्त कर सकता हूँ?
A4: आप कम्युनिटी फोरम [यहाँ](https://forum.aspose.com/c/tasks/15) से प्राप्त कर सकते हैं।

### Q5: क्या आप Aspose.Tasks for .NET के लिए टेम्पररी लाइसेंस प्रदान करते हैं?
A5: हाँ, टेम्पररी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) उपलब्ध हैं।

---

**अंतिम अपडेट:** 2026-04-06  
**परीक्षित संस्करण:** Aspose.Tasks for .NET (latest stable release)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}