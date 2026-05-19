---
date: 2026-01-15
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट को PDF के रूप में सहेजना
  और MS Project के Resource Usage तथा Sheet व्यूज़ को रेंडर करना सीखें। प्रोजेक्ट
  को आसानी से PDF में निर्यात करने के लिए हमारे चरण‑दर‑चरण गाइड का पालन करें।
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट को PDF के रूप में सहेजें – Aspose.Tasks में रिसोर्स उपयोग और शीट
  व्यू को रेंडर करें
url: /hi/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट को PDF के रूप में सहेजें – Aspose.Tasks में रिसोर्स उपयोग और शीट व्यू रेंडर करें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि कैसे **save project as PDF** को Microsoft Project फ़ाइल के रिसोर्स उपयोग और शीट व्यू को रेंडर करते हुए सहेजा जाए। चाहे आपको स्टेकहोल्डर्स के लिए प्रिंटेबल रिपोर्ट बनानी हो या MPP फ़ाइलों को एक सार्वभौमिक रूप से देखी जा सकने वाली फ़ॉर्मेट में बदलना हो, Aspose.Tasks for Java प्रक्रिया को सरल बनाता है—Microsoft Project की कोई इंस्टॉलेशन आवश्यक नहीं।

## त्वरित उत्तर
- **“save project as pdf” क्या करता है?** यह एक प्रोजेक्ट फ़ाइल (MPP) को PDF दस्तावेज़ में बदलता है, चयनित व्यू को संरक्षित रखते हुए।  
- **कौन सा व्यू एक्सपोर्ट किया जा सकता है?** रिसोर्स उपयोग, शीट, गैंट, टास्क उपयोग, और अधिक।  
- **क्या मैं PDF में टाइमस्केल बदल सकता हूँ?** हाँ—विकल्पों में Days, ThirdsOfMonths, और Months शामिल हैं।  
- **क्या Microsoft Project इंस्टॉल होना आवश्यक है?** नहीं, Aspose.Tasks स्वतंत्र रूप से काम करता है।  
- **क्या प्रोडक्शन के लिए लाइसेंस आवश्यक है?** हाँ, गैर‑ट्रायल उपयोग के लिए एक कमर्शियल लाइसेंस चाहिए।

## “save project as PDF” क्या है?
प्रोजेक्ट को PDF के रूप में सहेजना एक स्थिर, हाई‑रेज़ोल्यूशन प्रतिनिधित्व बनाता है चुने हुए प्रोजेक्ट व्यू का। यह क्लाइंट्स के साथ शेयर करने, आर्काइव करने, या प्रिंट करने के लिए आदर्श है, बिना मूल प्रोजेक्ट फ़ाइल को उजागर किए।

## PDF में प्रोजेक्ट एक्सपोर्ट करने के लिए Aspose.Tasks क्यों उपयोग करें?
- **कोई बाहरी निर्भरताएँ नहीं** – Java को सपोर्ट करने वाले किसी भी प्लेटफ़ॉर्म पर काम करता है।  
- **सूक्ष्म नियंत्रण** – आप व्यू, टाइमस्केल, और लेआउट चुन सकते हैं।  
- **उच्च फ़िडेलिटी** – PDF मूल प्रोजेक्ट व्यू की उपस्थिति को प्रतिबिंबित करता है।  
- **ऑटोमेशन‑रेडी** – CI पाइपलाइन, रिपोर्टिंग सर्विसेज, या बैच कन्वर्टर्स में इंटीग्रेट करें।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Java Development Kit (JDK)** – नवीनतम संस्करण अनुशंसित।  
2. **Aspose.Tasks for Java** – [डाउनलोड पेज](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  

## पैकेज इम्पोर्ट करें
अपने Java प्रोजेक्ट में आवश्यक क्लासेज़ इम्पोर्ट करें:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## चरण‑दर‑चरण गाइड

### चरण 1: स्रोत प्रोजेक्ट पढ़ें
जिस MPP फ़ाइल को आप कन्वर्ट करना चाहते हैं उसे लोड करें।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### चरण 2: आवश्यक टाइमस्केल के साथ SaveOptions परिभाषित करें (प्रोजेक्ट को PDF में एक्सपोर्ट करें)
PDF एक्सपोर्ट विकल्प कॉन्फ़िगर करें और इच्छित टाइमस्केल सेट करें।  
*यहाँ हम **Days** का उदाहरण ले रहे हैं।*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### चरण 3: Presentation Format को ResourceUsage पर सेट करें
वह व्यू चुनें जिसे आप रेंडर करना चाहते हैं। इस मामले में, **Resource Usage** व्यू।

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### चरण 4: प्रोजेक्ट सहेजें (MPP को PDF में कन्वर्ट करें)
कन्वर्ज़न निष्पादित करें और PDF फ़ाइल जनरेट करें।

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### चरण 5: अन्य टाइमस्केल सेटिंग्स के लिए व्यू रेंडर करें (टाइमस्केल बदलें PDF)
पहले के चरणों को दोहराएँ ताकि **ThirdsOfMonths** और **Months** जैसे विभिन्न टाइमस्केल के साथ PDFs बन सकें।

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## सामान्य समस्याएँ और समाधान
- **फ़ाइल नहीं मिली त्रुटियाँ** – सुनिश्चित करें कि `dataDir` सही फ़ोल्डर की ओर इशारा कर रहा है और MPP फ़ाइल का नाम बिल्कुल मेल खाता है।  
- **खाली PDF आउटपुट** – सुनिश्चित करें कि `PresentationFormat` ऐसा व्यू है जिसमें डेटा मौजूद है (जैसे ResourceUsage)।  
- **गलत टाइमस्केल** – प्रत्येक `project.save()` से पहले `options.setTimescale()` को कॉल करना न भूलें।

## अक्सर पूछे जाने वाले प्रश्न

### क्या Aspose.Tasks रिसोर्स उपयोग और शीट के अलावा अन्य व्यू रेंडर कर सकता है?
Aspose.Tasks विभिन्न व्यू जैसे गैंट चार्ट, टास्क उपयोग, और कैलेंडर व्यू आदि को रेंडर करने का समर्थन करता है।

### क्या Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?
हाँ, Aspose.Tasks Microsoft Project फ़ाइल फ़ॉर्मेट्स की विस्तृत रेंज को सपोर्ट करता है, जिसमें MPP, MPT, और XML फ़ॉर्मेट शामिल हैं।

### क्या मैं Aspose.Tasks का उपयोग करके रेंडर किए गए व्यू की उपस्थिति को कस्टमाइज़ कर सकता हूँ?
बिल्कुल! Aspose.Tasks रेंडर किए गए व्यू की उपस्थिति और लेआउट को आपके विशिष्ट आवश्यकताओं के अनुसार कस्टमाइज़ करने के लिए व्यापक विकल्प प्रदान करता है।

### क्या Aspose.Tasks को सिस्टम पर Microsoft Project इंस्टॉल होना आवश्यक है?
नहीं, Aspose.Tasks एक स्टैंडअलोन लाइब्रेरी है और इसके कार्य करने के लिए Microsoft Project की आवश्यकता नहीं है।

### क्या Aspose.Tasks उपयोगकर्ताओं के लिए तकनीकी समर्थन उपलब्ध है?
हाँ, Aspose.Tasks उपयोगकर्ता [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) के माध्यम से तकनीकी समर्थन प्राप्त कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-01-15  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose