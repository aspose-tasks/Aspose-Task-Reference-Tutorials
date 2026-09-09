---
date: 2026-09-09
description: Aspose.Tasks for Java का उपयोग करके क्रॉस प्रोजेक्ट टास्क की पहचान करना
  सीखें। सहज एकीकरण, कुशल प्रबंधन, और वास्तविक उदाहरणों की खोज करें।
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Aspose.Tasks में क्रॉस प्रोजेक्ट टास्क की पहचान करें
og_description: Aspose.Tasks for Java में क्रॉस प्रोजेक्ट टास्क की पहचान करें। दस्तावेज़
  डायरेक्टरी सेट करना, टास्क आईडी प्राप्त करना, और लिंक्ड प्रोजेक्ट्स को कुशलता से
  प्रबंधित करना सीखें।
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Aspose.Tasks में क्रॉस प्रोजेक्ट टास्क की पहचान – Java गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Aspose.Tasks में क्रॉस प्रोजेक्ट टास्क की पहचान करें
url: /hi/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में क्रॉस प्रोजेक्ट टास्क पहचानें

## परिचय
इस ट्यूटोरियल में आप Aspose.Tasks for Java के साथ **क्रॉस प्रोजेक्ट टास्क कैसे पहचानें** सीखेंगे। चाहे आप परस्पर निर्भर शेड्यूल का पोर्टफोलियो बनाए रखें या बाहरी निर्भरताओं का ऑडिट करना चाहें, नीचे दिए गए चरण आपको दिखाते हैं कि कैसे उन टास्क को खोजें जो अन्य प्रोजेक्ट फ़ाइलों का संदर्भ देते हैं, उनके पहचानकर्ता प्राप्त करें, और उन्हें प्रोग्रामेटिक रूप से उपयोग करें।

## त्वरित उत्तर
- **“क्रॉस प्रोजेक्ट टास्क पहचानें” का क्या अर्थ है?** इसका मतलब है उन टास्क को ढूँढ़ना जो किसी अन्य प्रोजेक्ट फ़ाइल में टास्क का संदर्भ देते हैं या उस पर निर्भर होते हैं।  
- **कौन सा मेथड टास्क ID प्रिंट करता है?** टास्क ID प्रिंट करने के लिए `externalTask.get(Tsk.ID)` का उपयोग करें।  
- **डॉक्यूमेंट डायरेक्टरी कैसे सेट करें?** फ़ोल्डर पाथ को एक `String` वेरिएबल (जैसे `dataDir`) में असाइन करें।  
- **कौन सी प्रॉपर्टी UID द्वारा टास्क प्राप्त करती है?** `getChildren().getByUid(yourUid)` को कॉल करें।  
- **प्रोडक्शन उपयोग के लिए लाइसेंस चाहिए?** हाँ, व्यावसायिक डिप्लॉयमेंट के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।

## “क्रॉस प्रोजेक्ट टास्क पहचानें” क्या है?
क्रॉस‑प्रोजेक्ट टास्क की पहचान करने से आप कई Microsoft Project फ़ाइलों में फैले टास्कों के बीच संबंधों को ट्रेस कर सकते हैं। बाहरी शेड्यूल का संदर्भ देने या उन पर निर्भर रहने वाले टास्कों को ढूँढ़कर आप समझ सकते हैं कि कार्य आइटम प्रोजेक्ट सीमाओं के पार कैसे इंटरैक्ट करते हैं, डुप्लिकेट प्रयास को रोकते हैं, और सटीक टाइमलाइन बनाए रखते हैं। यह क्षमता बड़े‑पैमाने के पोर्टफोलियो के लिए आवश्यक है जहाँ टास्क साझा किए जाते हैं या बाहरी शेड्यूल पर निर्भर होते हैं।

## Java के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks for Java **50+ इनपुट और आउटपुट फ़ॉर्मेट** (जैसे MPP, MPX, XML, और CSV) को सपोर्ट करता है और **10,000 तक टास्क** वाले प्रोजेक्ट को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है। यह लाइब्रेरी किसी भी JVM‑संगत प्लेटफ़ॉर्म पर काम करती है, Microsoft Project की इंस्टॉलेशन की आवश्यकता नहीं होती, और IDs, UIDs, external IDs, और लिंकिंग मेटाडेटा तक पूर्ण API एक्सेस प्रदान करती है।

## पूर्वापेक्षाएँ
- एक कार्यशील Java विकास वातावरण (JDK 8 या उससे ऊपर)।  
- Aspose.Tasks for Java स्थापित है। आप इसे **[here](https://releases.aspose.com/tasks/java/)** से डाउनलोड कर सकते हैं।  
- यदि आप कोड को प्रोडक्शन में चलाने की योजना बना रहे हैं तो एक वैध Aspose.Tasks लाइसेंस फ़ाइल।

## पैकेज आयात करें
`Project` क्लास एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है, `Task` एक व्यक्तिगत टास्क का, और `Tsk` टास्क फ़ील्ड कॉन्स्टैंट्स प्रदान करता है।  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## चरण 1: डॉक्यूमेंट डायरेक्टरी सेट करें
`dataDir` स्ट्रिंग आपके `.mpp` फ़ाइलों वाले फ़ोल्डर का पाथ रखती है।  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## चरण 2: बाहरी प्रोजेक्ट लोड करें
`Project externalProject` निर्दिष्ट बाहरी प्रोजेक्ट फ़ाइल को निरीक्षण के लिए लोड करता है।  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## चरण 3: UID द्वारा बाहरी टास्क प्राप्त करें
`externalProject.getChildren().getByUid(uid)` बाहरी प्रोजेक्ट की टास्क कलेक्शन से उसके यूनिक आइडेंटिफायर का उपयोग करके टास्क प्राप्त करता है।  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## चरण 4: टास्क ID प्रिंट करें (मुख्य उपयोग‑केस)
`externalTask.get(Tsk.ID)` दिए गए टास्क के लिए Aspose.Tasks द्वारा असाइन किया गया आंतरिक ID लौटाता है।  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## चरण 5: मूल (बाहरी) टास्क ID प्रिंट करें
`externalTask.get(Tsk.ExternalID)` स्रोत प्रोजेक्ट फ़ाइल में परिभाषित टास्क की मूल ID प्राप्त करता है।  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

उपरोक्त चरणों को किसी भी अतिरिक्त टास्क के लिए दोहराएँ जिन्हें आपको प्रोजेक्ट्स के बीच ट्रैक करना है।

## सामान्य समस्याएँ और टिप्स
- **पाथ त्रुटियाँ** – सुनिश्चित करें कि `dataDir` उचित फ़ाइल सेपरेटर (`/` या `\\`) के साथ समाप्त हो।  
- **UID नहीं मिला** – पुष्टि करें कि UID बाहरी प्रोजेक्ट में मौजूद है; उपलब्ध UIDs की सूची के लिए `externalProject.getRootTask().getChildren().size()` का उपयोग करें।  
- **लाइसेंस अपवाद** – गायब या अमान्य लाइसेंस रनटाइम पर लाइसेंसिंग अपवाद फेंकेगा।  
- **बड़े प्रोजेक्ट** – 5,000 से अधिक टास्क वाले प्रोजेक्ट्स के लिए `ProjectReader` को `LoadOptions` फ़्लैग के साथ उपयोग करने पर विचार करें ताकि डेटा स्ट्रीम किया जा सके और मेमोरी खपत कम हो।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Tasks कई भाषाओं को सपोर्ट करता है, जिसमें Java, .NET, और अन्य शामिल हैं।

**Q: Aspose.Tasks for Java की विस्तृत डॉक्यूमेंटेशन कहाँ मिल सकती है?**  
A: डॉक्यूमेंटेशन के लिए **[here](https://reference.aspose.com/tasks/java/)** देखें।

**Q: क्या Aspose.Tasks for Java के लिए कोई फ्री ट्रायल उपलब्ध है?**  
A: हाँ, आप फ्री ट्रायल **[here](https://releases.aspose.com/)** प्राप्त कर सकते हैं।

**Q: Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: अस्थायी लाइसेंस **[here](https://purchase.aspose.com/temporary-license/)** से प्राप्त करें।

**Q: सहायता चाहिए या विशेष प्रश्न हैं?**  
A: Aspose.Tasks सपोर्ट फ़ोरम **[here](https://forum.aspose.com/c/tasks/15)** पर जाएँ।

---

**अंतिम अपडेट:** 2026-09-09  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11 (लेखन के समय नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में प्रोजेक्ट मैनेजमेंट टास्क डिपेंडेंसी बनाएं](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks में प्रोजेक्ट स्टार्ट डेट सेट करें और पैरेंट व चाइल्ड टास्क प्रबंधित करें](/tasks/java/task-properties/parent-child-tasks/)
- [MPP प्रोजेक्ट जावा बनाएं – Aspose.Tasks के साथ टास्क प्रोग्रेस बदलें](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}