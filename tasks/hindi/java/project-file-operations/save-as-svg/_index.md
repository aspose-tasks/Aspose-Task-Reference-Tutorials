---
date: 2026-03-27
description: Aspose.Tasks के साथ जावा में MPP को SVG में निर्यात करना सीखें। चरण‑दर‑चरण
  गाइड, कोड उदाहरण और तेज़ी से प्रोजेक्ट को SVG के रूप में सहेजने के टिप्स।
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks का उपयोग करके जावा में MPP को SVG में कैसे निर्यात करें
url: /hi/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java में MPP को SVG में निर्यात कैसे करें

## Export MPP to SVG – परिचय
इस ट्यूटोरियल में आप सीखेंगे कि **export MPP to SVG** फ़ाइलें Aspose.Tasks for Java का उपयोग करके कैसे निर्यात करें। Microsoft Project (MPP) फ़ाइल को Scalable Vector Graphics (SVG) इमेज में बदलने से आप उच्च‑गुणवत्ता, रिज़ॉल्यूशन‑स्वतंत्र डायग्राम सीधे वेब पेज, रिपोर्ट या डैशबोर्ड में एम्बेड कर सकते हैं। हम आवश्यक सेटअप को चरण‑दर‑चरण दिखाएंगे, आपको सटीक कोड प्रदान करेंगे, और प्रत्येक चरण की व्याख्या करेंगे ताकि आप अपने एप्लिकेशन में **save project as SVG** करने में आत्मविश्वास महसूस करें।

## त्वरित उत्तर
- **“export MPP to SVG” का क्या अर्थ है?**  
  यह Microsoft Project फ़ाइल (.mpp) को एक SVG इमेज में बदलता है जिसे किसी भी ब्राउज़र पर गुणवत्ता खोए बिना प्रदर्शित किया जा सकता है।  
- **कौन सा लाइब्रेरी रूपांतरण संभालता है?**  
  Aspose.Tasks for Java एक एक‑लाइन `save` मेथड प्रदान करता है जो रूपांतरण करता है।  
- **क्या मुझे लाइसेंस चाहिए?**  
  व्यावसायिक उपयोग के लिए एक अस्थायी लाइसेंस आवश्यक है; एक मुफ्त ट्रायल उपलब्ध है।  
- **पूर्वापेक्षाएँ क्या हैं?**  
  Java JDK 8+ और Aspose.Tasks for Java JAR।  
- **रूपांतरण में कितना समय लगता है?**  
  सामान्य प्रोजेक्ट फ़ाइलों के लिए आमतौर पर एक सेकंड से कम।

## “export MPP to SVG” क्या है?
MPP को SVG में निर्यात करने का मतलब है प्रोजेक्ट शेड्यूल के दृश्य प्रतिनिधित्व—टास्क, टाइमलाइन, और रिसोर्सेज—को SVG फ़ाइल के रूप में लिखना। SVG XML‑आधारित, हल्का, और हाई‑रेज़ॉल्यूशन डिस्प्ले पर पूरी तरह स्केल करता है।

## Aspose.Tasks के साथ MPP को SVG में निर्यात क्यों?
- **Microsoft Project इंस्टॉलेशन की आवश्यकता नहीं** – लाइब्रेरी स्वतंत्र रूप से काम करती है।  
- **पूर्ण फ़िडेलिटी** – चार्ट, गैंट बार, और माइलस्टोन अपने स्टाइल को बनाए रखते हैं।  
- **क्रॉस‑प्लेटफ़ॉर्म** – कोड को Windows, Linux, या macOS पर चलाएँ।  
- **एक‑लाइन API** – एक ही कॉल प्रोजेक्ट को SVG के रूप में सहेजता है, जिससे यह मौजूदा Java पाइपलाइन में सहजता से फिट हो जाता है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK)** – संस्करण 8 या बाद का। Oracle वेबसाइट से डाउनलोड करें।  
- **Aspose.Tasks for Java** – आधिकारिक डाउनलोड पेज से लाइब्रेरी प्राप्त करें **[here](https://releases.aspose.com/tasks/java/)**।  

## इम्पोर्ट पैकेज
सबसे पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। इम्पोर्ट ब्लॉक अपरिवर्तित रहता है।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## चरण 1: डेटा डायरेक्टरी निर्धारित करें
निर्दिष्ट करें कि आपका स्रोत MPP फ़ाइल कहाँ स्थित है और SVG कहाँ लिखी जाएगी।

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `FileNotFoundException` से बचने के लिए एक पूर्ण पाथ या आपके प्रोजेक्ट के रिसोर्सेज़ फ़ोल्डर के सापेक्ष पाथ का उपयोग करें।

## चरण 2: MPP फ़ाइल लोड करें
मौजूदा Microsoft Project फ़ाइल को लोड करके एक `Project` इंस्टेंस बनाएं।

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

यह पंक्ति *HomeMovePlan.mpp* को उस फ़ोल्डर से पढ़ती है जिसे आपने पहले परिभाषित किया था।

## चरण 3: प्रोजेक्ट को SVG के रूप में सहेजें
अब आप एक ही कमांड के साथ **export MPP to SVG** कर सकते हैं।

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

यह मेथड `project5.svg` को उसी डायरेक्टरी में लिखता है। उत्पन्न SVG किसी भी आधुनिक ब्राउज़र में खोला जा सकता है या सीधे HTML में एम्बेड किया जा सकता है।

## सामान्य उपयोग मामलों
- **प्रोजेक्ट डैशबोर्ड** – वेब पोर्टल में लाइव गैंट चार्ट एम्बेड करें बिना क्लाइंट को Microsoft Project इंस्टॉल करने की आवश्यकता के।  
- **स्वचालित रिपोर्टिंग** – PDF या HTML रिपोर्ट के लिए ऑन‑द‑फ़्लाई SVG इमेज जनरेट करें।  
- **क्रॉस‑टीम सहयोग** – एक दृश्य शेड्यूल शेयर करें जिसे केवल ब्राउज़र की आवश्यकता हो।

## सामान्य समस्याएँ और समाधान
| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** | Incorrect `dataDir` path | Verify the directory string ends with a separator (`/` or `\\`). |
| **Blank SVG output** | Project loaded without views | Ensure the MPP file contains a Gantt chart view before saving. |
| **License exception** | No valid license applied | Apply a temporary license using `License.setLicense("path/to/license.xml")` before calling `save`. |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks for Java सभी संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
A: हाँ, यह पुराने से लेकर नवीनतम Project रिलीज़ तक के MPP, MPT, और XML फ़ॉर्मैट्स को सपोर्ट करता है।

**Q: क्या मैं SVG आउटपुट की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
A: बिल्कुल। `SvgOptions` का उपयोग करके फ़ॉन्ट, रंग, और लेआउट विकल्प सेट करें और फिर `save` कॉल करें।

**Q: क्या Aspose.Tasks for Java को व्यावसायिक उपयोग के लिए लाइसेंस की आवश्यकता है?**  
A: हाँ, प्रोडक्शन के लिए एक वैध लाइसेंस आवश्यक है। आप एक अस्थायी लाइसेंस **[here](https://purchase.aspose.com/temporary-license/)** प्राप्त कर सकते हैं।

**Q: क्या मैं खरीदने से पहले Aspose.Tasks for Java को ट्राय कर सकता हूँ?**  
A: हाँ, एक मुफ्त ट्रायल उपलब्ध है **[here](https://purchase.aspose.com/buy)**।

**Q: Aspose.Tasks for Java के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?**  
A: प्रश्न पूछने और फीडबैक साझा करने के लिए कम्युनिटी फ़ोरम **[here](https://forum.aspose.com/c/tasks/15)** पर जाएँ।

## निष्कर्ष
अब आप जानते हैं कि Java में **export MPP to SVG** कैसे किया जाता है और Aspose.Tasks का उपयोग करके **save project as SVG** कैसे किया जाता है। यह क्षमता आपको वेब पोर्टल, रिपोर्टिंग डैशबोर्ड या किसी भी जगह जहाँ स्केलेबल ग्राफ़िक्स की आवश्यकता है, में समृद्ध प्रोजेक्ट विज़ुअलाइज़ेशन एकीकृत करने देती है। `SvgOptions` के साथ आउटपुट को फाइन‑ट्यून करें, और आपके विकास टूलकिट में एक शक्तिशाली उपकरण जोड़ें।

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}