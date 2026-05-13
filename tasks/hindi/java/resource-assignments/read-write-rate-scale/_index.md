---
date: 2026-01-10
description: Aspose.Tasks for Java में रेट स्केल को पढ़ना और संसाधन असाइनमेंट को प्रबंधित
  करना सीखें। सामग्री संसाधन को परिभाषित करें, स्केल कैसे सेट करें, और कार्य को संसाधन
  असाइन करें।
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में संसाधन असाइनमेंट्स के लिए रेट स्केल को पढ़ने और लिखने का तरीका
url: /hi/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में रिसोर्स असाइनमेंट्स के लिए रेट स्केल को पढ़ने और लिखने का तरीका

इस ट्यूटोरियल में आप **रेट स्केल** सेटिंग्स को कैसे पढ़ें और Aspose.Tasks for Java का उपयोग करके रिसोर्स असाइनमेंट्स के लिए उन्हें कैसे समायोजित करें, यह जानेंगे। चाहे आप एक शेड्यूलर, रिपोर्टिंग टूल बना रहे हों, या सिर्फ प्रोजेक्ट अपडेट्स को ऑटोमेट करना चाहते हों, रेट स्केल को नियंत्रित करने से आप मैटेरियल और वर्क रिसोर्सेज़ पर सूक्ष्म नियंत्रण प्राप्त कर सकते हैं।

## त्वरित उत्तर
- **रेट हैंडलिंग के लिए मुख्य क्लास कौन सी है?** `ResourceAssignment` जिसमें `Asn.RATE_SCALE` प्रॉपर्टी होती है।  
- **कौन सा enum स्केल विकल्पों को परिभाषित करता है?** `RateScaleType` (Day, Week, Month, आदि)।  
- **क्या सैंपल चलाने के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक फ्री इवैल्यूएशन लाइसेंस काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **क्या सेव करने के बाद स्केल बदल सकते हैं?** हाँ – प्रोजेक्ट को पुनः लोड करें और `Asn.RATE_SCALE` को नीचे दिखाए अनुसार संशोधित करें।  
- **समर्थित IDEs?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, NetBeans) कोड को कंपाइल कर सकता है।

## रेट स्केल क्या है?
रेट स्केल निर्धारित करता है कि रिसोर्स की लागत दर किस समय इकाई (दिन, सप्ताह, माह, आदि) पर लागू होती है। स्केल को समायोजित करने से आप मैटेरियल खपत या श्रम प्रयास को सटीक रूप से मॉडल कर सकते हैं।

## रेट स्केल को पढ़ना और लिखना क्यों आवश्यक है?
वर्तमान स्केल को पढ़ने से आप मौजूदा शेड्यूल का ऑडिट कर सकते हैं, जबकि नया स्केल लिखने से आप रिसोर्सेज़ को प्रोजेक्ट की बिलिंग या खपत नीतियों के साथ संरेखित कर सकते हैं। यह विशेष रूप से **मैटेरियल रिसोर्स** की लागत निर्धारित करने या **नॉन‑स्टैंडर्ड वर्क कैलेंडर** के लिए स्केल सेट करने में उपयोगी है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. **Java Development Environment** – JDK 8 या उससे ऊपर स्थापित हो।  
2. **Aspose.Tasks for Java Library** – लाइब्रेरी को [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड और इंस्टॉल करें।

## पैकेज इम्पोर्ट करें
सबसे पहले, आवश्यक Aspose.Tasks क्लासेज़ को इम्पोर्ट करें।

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## चरण 1: अपना Java प्रोजेक्ट सेट अप करें
एक Maven या Gradle प्रोजेक्ट बनाएं और Aspose.Tasks JAR को अपने क्लासपाथ में जोड़ें। यह चरण सुनिश्चित करता है कि कंपाइलर इम्पोर्टेड क्लासेज़ को ढूंढ सके।

## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
उस मौजूदा Microsoft Project फ़ाइल को लोड करें जिस पर आप काम करना चाहते हैं।

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## चरण 3: एक टास्क जोड़ें
एक नया टास्क बनाएं जो बाद में रिसोर्स असाइनमेंट प्राप्त करेगा।

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## चरण 4: रिसोर्सेज़ परिभाषित करें
यहाँ हम **मैटेरियल रिसोर्स** और एक सामान्य वर्क रिसोर्स परिभाषित करते हैं। मैटेरियल‑टाइप रिसोर्स के लिए `ResourceType.Material` का उपयोग देखें।

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## चरण 5: टास्क को रिसोर्स असाइन करें
अब हम **रिसोर्सेज़ को टास्क पर असाइन** करते हैं और `RateScaleType.Week` का उपयोग करके **स्केल सेट करने का तरीका** निर्दिष्ट करते हैं। यह रेट स्केल को पढ़ने और लिखने दोनों को दर्शाता है।

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## चरण 6: प्रोजेक्ट सहेजें
परिवर्तनों को एक नई फ़ाइल में सहेजें ताकि बाद में संग्रहीत रेट स्केल की पुष्टि की जा सके।

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## चरण 7: रिसोर्स असाइनमेंट्स पुनः प्राप्त करें
सहेजे गए प्रोजेक्ट को पुनः लोड करें और **रेट स्केल** को पढ़ें ताकि यह पुष्टि हो सके कि इसे सही ढंग से लिखा गया था।

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## सामान्य समस्याएँ और टिप्स
- **UID मेल नहीं होना** – UID द्वारा असाइनमेंट्स प्राप्त करते समय सुनिश्चित करें कि UID मान निर्माण के दौरान असाइन किए गए मानों से मेल खाते हों।  
- **गलत रिसोर्स टाइप** – वर्क रिसोर्स के लिए `ResourceType.Material` का उपयोग करने से रेट कैलकुलेशन अप्रत्याशित रूप से व्यवहार कर सकता है।  
- **सेव फॉर्मेट** – हमेशा `SaveFileFormat.Mpp` (या कोई अन्य समर्थित फॉर्मेट) का उपयोग करके सहेजें ताकि रेट स्केल जैसे कस्टम फ़ील्ड्स संरक्षित रहें।

## निष्कर्ष
Aspose.Tasks for Java में रिसोर्स असाइनमेंट्स के लिए रेट स्केल को प्रबंधित और निरीक्षण करना सरल है, बशर्ते आप संबंधित क्लासेज़ और प्रॉपर्टीज़ को जानते हों। इस गाइड का पालन करके आप **रेट** जानकारी पढ़ सकते हैं, **मैटेरियल रिसोर्स** ऑब्जेक्ट्स परिभाषित कर सकते हैं, **स्केल सेट** कर सकते हैं, और **रिसोर्सेज़ को टास्क पर असाइन** कर सकते हैं, वह भी भरोसे के साथ।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for Java को किसी भी Java IDE के साथ उपयोग कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Tasks for Java सभी प्रमुख Java IDEs, जैसे IntelliJ IDEA, Eclipse, और NetBeans के साथ संगत है।

**प्रश्न: क्या Aspose.Tasks MPP के अलावा अन्य फ़ाइल फ़ॉर्मेट्स को समर्थन देता है?**  
उत्तर: हाँ, Aspose.Tasks विभिन्न फ़ाइल फ़ॉर्मेट्स, जैसे MPP, XML, और HTML को समर्थन देता है।

**प्रश्न: क्या Aspose.Tasks एंटरप्राइज़‑लेवल प्रोजेक्ट मैनेजमेंट के लिए उपयुक्त है?**  
उत्तर: बिल्कुल, Aspose.Tasks में व्यापक फीचर्स हैं जो किसी भी स्केल के प्रोजेक्ट्स को प्रबंधित करने में सक्षम बनाते हैं, जिससे यह एंटरप्राइज़‑लेवल प्रोजेक्ट मैनेजमेंट के लिए उपयुक्त है।

**प्रश्न: क्या मैं रेट स्केल से आगे रिसोर्स असाइनमेंट्स को कस्टमाइज़ कर सकता हूँ?**  
उत्तर: हाँ, Aspose.Tasks लागत, कार्य, और अवधि समायोजन सहित रिसोर्स असाइनमेंट्स को कस्टमाइज़ करने की विस्तृत क्षमताएँ प्रदान करता है।

**प्रश्न: क्या Aspose.Tasks सपोर्ट के लिए कोई कम्युनिटी फ़ोरम है?**  
उत्तर: हाँ, आप Aspose.Tasks फ़ोरम पर समर्थन प्राप्त कर सकते हैं और अन्य उपयोगकर्ताओं के साथ इंटरैक्ट कर सकते हैं [यहाँ](https://forum.aspose.com/c/tasks/15)।

---

**अंतिम अपडेट:** 2026-01-10  
**टेस्टेड विथ:** Aspose.Tasks for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}