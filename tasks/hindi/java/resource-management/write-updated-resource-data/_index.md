---
date: 2026-01-15
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट में संसाधन जोड़ना, संसाधन
  डेटा को अपडेट करना, और प्रोजेक्ट को MPP के रूप में सहेजना सीखें।
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट में संसाधन जोड़ें
url: /hi/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट में रिसोर्स जोड़ें

## परिचय
इस हैंड‑ऑन ट्यूटोरियल में आप **प्रोजेक्ट में रिसोर्स कैसे जोड़ें** फ़ाइलों को प्रोग्रामेटिकली Aspose.Tasks Java API के साथ सीखेंगे। हम एक मौजूदा MS Project XML फ़ाइल लोड करने, नया रिसोर्स इंसर्ट करने, उसकी प्रॉपर्टीज़ अपडेट करने, और अंत में **प्रोजेक्ट को MPP के रूप में सेव करने** की प्रक्रिया को चरण‑बद्ध रूप से देखेंगे। अंत तक आपके पास एक स्पष्ट, दोहराने योग्य पैटर्न होगा जिसे आप किसी भी Java‑आधारित रिपोर्टिंग या ऑटोमेशन टूल में उपयोग कर सकते हैं।

## त्वरित उत्तर
- **“add resource to project” क्या मतलब है?** यह Microsoft Project फ़ाइल के भीतर एक नया रिसोर्स एंट्री (लोग, उपकरण, सामग्री) बनाता है।  
- **यह कौन सी लाइब्रेरी संभालती है?** Aspose.Tasks for Java – Microsoft Project को इंस्टॉल करने की आवश्यकता नहीं है।  
- **क्या मुझे लाइसेंस चाहिए?** डेवलपमेंट के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **क्या मैं XML को MPP में कनवर्ट कर सकता हूँ?** हाँ – XML फ़ाइल लोड करें और `project.save(...)` का उपयोग करके **प्रोजेक्ट को MPP के रूप में सेव करें**।  
- **कौन सा Java संस्करण आवश्यक है?** Java 6 या बाद का (Java 8+ की सिफारिश की जाती है)।

## “add resource to project” क्या है?
प्रोजेक्ट में रिसोर्स जोड़ना मतलब MS Project फ़ाइल की Resources टेबल में एक नई पंक्ति डालना है। यह पंक्ति नाम, लागत दरें, समूह, और कस्टम फ़ील्ड्स जैसी जानकारी संग्रहीत करती है, जिन्हें टास्क बाद में संदर्भित कर सकते हैं।

## Aspose.Tasks for Java का उपयोग क्यों करें?
- **No Microsoft Project dependency** – किसी भी OS या CI सर्वर पर काम करता है।  
- **Full fidelity** – फ़ॉर्मेट्स के बीच कनवर्ट करते समय सभी नेटिव Project फीचर्स बरकरार रहते हैं।  
- **Rich API** – आपको टास्क, रिसोर्स, कैलेंडर आदि को पढ़ने, लिखने और मैनीपुलेट करने की सुविधा देता है।

## पूर्वापेक्षाएँ
1. Java Development Kit (JDK) 8 या नया स्थापित होना चाहिए।  
2. Aspose.Tasks for Java लाइब्रेरी – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. Java सिंटैक्स और Maven/Gradle प्रोजेक्ट सेटअप की बुनियादी जानकारी।

## पैकेज इम्पोर्ट करें
अपने Java सोर्स फ़ाइल में आवश्यक Aspose.Tasks क्लासेज़ जोड़ें:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## चरण 1: अपना डेटा डायरेक्टरी सेट करें
स्रोत XML और परिणामी MPP फ़ाइलों के स्थान को परिभाषित करें:

```java
String dataDir = "Your Data Directory";
```

## चरण 2: इनपुट और आउटपुट फ़ाइलें निर्दिष्ट करें
उस XML फ़ाइल की ओर इशारा करें जिसे आप **XML को MPP में कनवर्ट करें** और लक्ष्य MPP फ़ाइल जो नया रिसोर्स रखेगी:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## चरण 3: प्रोजेक्ट लोड करें
XML स्रोत से एक `Project` ऑब्जेक्ट बनाएं:

```java
Project project = new Project(file);
```

## चरण 4: रिसोर्स जोड़ें और एट्रिब्यूट सेट करें
यहाँ हम **प्रोजेक्ट में रिसोर्स जोड़ें** और उसकी रेट्स व ग्रुप कॉन्फ़िगर करते हैं:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Pro tip:* आप `add` कॉल को लूप में दोहरा सकते हैं ताकि **कई रिसोर्स अपडेट करें** एक ही रन में।

## चरण 5: प्रोजेक्ट सेव करें
अंत में, **प्रोजेक्ट को MPP के रूप में सेव करें** ताकि बदलाव स्थायी हो जाएँ:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## निष्कर्ष
आपने अभी **प्रोजेक्ट में रिसोर्स कैसे जोड़ें**, उसकी प्रॉपर्टीज़ अपडेट करना, और Aspose.Tasks for Java का उपयोग करके **प्रोजेक्ट को MPP के रूप में सेव करना** सीख लिया है। यह तरीका ऑटोमेटेड रिपोर्टिंग पाइपलाइन, बल्क‑रिसोर्स इम्पोर्ट या किसी भी स्थिति में आदर्श है जहाँ आपको डेस्कटॉप एप्लिकेशन के बिना MS Project फ़ाइलों को मैनीपुलेट करना हो।

## अक्सर पूछे जाने वाले प्रश्न

**Q1: क्या मैं Aspose.Tasks for Java का उपयोग करके एक ही प्रोजेक्ट में कई रिसोर्स अपडेट कर सकता हूँ?**  
A: हाँ, `project.getResources()` पर इटरेट करें या `add` को बार‑बार कॉल करें, प्रत्येक रिसोर्स के फ़ील्ड्स आवश्यकतानुसार सेट करें।

**Q2: क्या Aspose.Tasks MS Project के अलावा अन्य फ़ाइल फ़ॉर्मेट्स को सपोर्ट करता है?**  
A: बिल्कुल – XML, MPP, MPX, Primavera, और कई अन्य फ़ॉर्मेट्स पूरी तरह सपोर्टेड हैं।

**Q3: क्या Aspose.Tasks विभिन्न Java संस्करणों के साथ संगत है?**  
A: लाइब्रेरी Java 6 और बाद के संस्करणों के साथ काम करती है; सर्वोत्तम प्रदर्शन के लिए Java 8+ की दृढ़ता से सिफारिश की जाती है।

**Q4: क्या मैं Aspose.Tasks के साथ MS Project फ़ाइलों पर अन्य ऑपरेशन्स कर सकता हूँ?**  
A: हाँ, आप टास्क, कैलेंडर, असाइनमेंट, कस्टम फ़ील्ड्स पढ़/लिख सकते हैं और यहाँ तक कि रिपोर्ट भी जेनरेट कर सकते हैं।

**Q5: Aspose.Tasks के लिए अतिरिक्त मदद या सपोर्ट कहाँ मिल सकता है?**  
A: समुदाय सहायता और आधिकारिक सपोर्ट के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) देखें।

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}