---
date: 2026-06-10
description: Aspose.Tasks for Java का उपयोग करके Resource Assignments के लिए Rate
  पढ़ना और Rate Scale लिखना कैसे सीखें। यह Material Resources, कई फ़ॉर्मेट्स और बड़े
  प्रोजेक्ट्स को सपोर्ट करता है।
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Aspose.Tasks में Resource Assignments के लिए Rate Scale पढ़ना और लिखना
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में Resource Assignments के लिए Rate Scale को पढ़ना और लिखना कैसे
  करें
url: /hi/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में रिसोर्स असाइनमेंट्स के लिए रेट स्केल को पढ़ने और लिखने का तरीका

इस ट्यूटोरियल में आप **how to read rate** स्केल सेटिंग्स को कैसे पढ़ें और Aspose.Tasks for Java का उपयोग करके रिसोर्स असाइनमेंट्स के लिए उन्हें कैसे समायोजित करें, यह जानेंगे। चाहे आप शेड्यूलर, रिपोर्टिंग टूल बना रहे हों, या प्रोजेक्ट अपडेट्स को ऑटोमेट करना चाहते हों, रेट स्केल मैनिपुलेशन में महारत हासिल करने से आपको मैटेरियल और वर्क रिसोर्सेज़ पर सूक्ष्म नियंत्रण मिलता है।

## त्वरित उत्तर
`ResourceAssignment` एक टास्क को रिसोर्स से जोड़ता है और असाइनमेंट‑विशिष्ट डेटा रखता है।  
`Asn` असाइनमेंट फ़ील्ड्स के कॉन्स्टेंट्स रखता है, जिसमें `RATE_SCALE` भी शामिल है।  
`RateScaleType` एनीम रेट स्केलिंग के संभावित टाइम यूनिट्स को सूचीबद्ध करता है।  

- **रेट हैंडलिंग के लिए मुख्य क्लास कौन सी है?** `ResourceAssignment` के साथ `Asn.RATE_SCALE` प्रॉपर्टी।  
- **स्केल विकल्पों को परिभाषित करने वाला एनीम कौन सा है?** `RateScaleType` (Day, Week, Month, आदि)।  
- **क्या सैंपल चलाने के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक फ्री इवैल्यूएशन लाइसेंस काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **सेव करने के बाद स्केल बदल सकते हैं?** हाँ – प्रोजेक्ट को री‑लोड करें और `Asn.RATE_SCALE` को नीचे दिखाए अनुसार संशोधित करें।  
- **समर्थित IDEs?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, NetBeans) कोड को कंपाइल कर सकता है।

## रिसोर्स असाइनमेंट्स के लिए रेट स्केल को कैसे पढ़ें?

प्रोजेक्ट लोड करें, इच्छित `ResourceAssignment` खोजें, और `getRateScale()` कॉल करें – यह एक `RateScaleType` वैल्यू लौटाता है जो बताता है कि रेट दिन, हफ़्ता, महीने या किसी अन्य यूनिट पर लागू है। उत्तर तुरंत मिलता है और केवल दो API कॉल्स की आवश्यकता होती है, जिससे यह ऑडिट स्क्रिप्ट्स या UI डिस्प्ले के लिए आदर्श बन जाता है।

## रिसोर्स असाइनमेंट्स के लिए रेट स्केल को कैसे लिखें?

एक `ResourceAssignment` ऑब्जेक्ट बनाएं या प्राप्त करें, उसकी `Asn.RATE_SCALE` प्रॉपर्टी को इच्छित `RateScaleType` (जैसे `RateScaleType.Week`) पर सेट करें, और फिर प्रोजेक्ट को सेव करें। यह एकल प्रॉपर्टी परिवर्तन स्वचालित रूप से लागत गणना को अपडेट करता है और सभी समर्थित फ़ाइल फ़ॉर्मैट्स में स्थायी रहता है। स्केल सेट करने के बाद, आपको रिसोर्स की स्टैंडर्ड रेट या ओवरटाइम रेट को भी नए टाइम यूनिट के अनुसार समायोजित करना पड़ सकता है, ताकि लागत गणना सटीक बनी रहे।

## रेट स्केल क्या है?

रेट स्केल वह टाइम यूनिट (दिन, हफ़्ता, महीना, आदि) निर्धारित करता है जिस पर रिसोर्स की लागत रेट लागू होती है। स्केल को समायोजित करने से आप मैटेरियल खपत या लेबर प्रयास को सटीक रूप से मॉडल कर सकते हैं। उदाहरण के लिए, स्केल को Week सेट करने पर लागत रेट को प्रति हफ़्ता लागत के रूप में समझा जाता है, और टास्क की कुल लागत रिसोर्स के असाइन किए गए हफ़्तों की संख्या के आधार पर गणना की जाती है।

## रेट स्केल को पढ़ना और लिखना क्यों आवश्यक है?

वर्तमान स्केल को पढ़ने से आप मौजूदा शेड्यूल्स का ऑडिट कर सकते हैं, जबकि नया स्केल लिखने से आप रिसोर्सेज़ को प्रोजेक्ट की बिलिंग या कंजम्प्शन नीतियों के साथ संरेखित कर सकते हैं। यह विशेष रूप से **material resource** लागतों को परिभाषित करते समय या गैर‑स्टैंडर्ड वर्क कैलेंडर के लिए **scale सेट** करने की आवश्यकता होने पर उपयोगी है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:
1. **Java Development Environment** – JDK 8 या उससे ऊपर स्थापित हो।  
2. **Aspose.Tasks for Java Library** – लाइब्रेरी को [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड और इंस्टॉल करें।

## पैकेज इम्पोर्ट करें
`ResourceAssignment` क्लास टास्क और रिसोर्स के बीच लिंक का प्रतिनिधित्व करती है, जबकि `RateScaleType` रेट के संभावित टाइम यूनिट्स को एनीमेट करता है। कोडिंग शुरू करने से पहले आवश्यक Aspose.Tasks क्लासेज़ इम्पोर्ट करें।  

`Project` वह मुख्य ऑब्जेक्ट है जो Microsoft Project फ़ाइलों को लोड और सेव करता है।  
`Resource` प्रोजेक्ट रिसोर्स को परिभाषित करता है जैसे वर्क या मैटेरियल।  
`ResourceType` एनीम यह निर्दिष्ट करता है कि रिसोर्स वर्क है या मैटेरियल।  
`Task` प्रोजेक्ट शेड्यूल में एक कार्य आइटम का प्रतिनिधित्व करता है।  
`SaveFileFormat` एनीम प्रोजेक्ट को सेव करने के आउटपुट फ़ॉर्मैट को परिभाषित करता है।

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
Maven या Gradle प्रोजेक्ट बनाएं और Aspose.Tasks JAR को अपने क्लासपाथ में जोड़ें। यह चरण सुनिश्चित करता है कि कंपाइलर इम्पोर्टेड क्लासेज़ को ढूंढ सके।

## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
जिस मौजूदा Microsoft Project फ़ाइल को आप काम करना चाहते हैं, उसे लोड करें।

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## चरण 3: एक टास्क जोड़ें
एक नया टास्क बनाएं जो बाद में रिसोर्स असाइनमेंट्स प्राप्त करेगा।

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## चरण 4: रिसोर्सेज़ परिभाषित करें
यहाँ हम **define material resource** और एक सामान्य वर्क रिसोर्स परिभाषित करते हैं। मैटेरियल‑टाइप रिसोर्स के लिए `ResourceType.Material` के उपयोग पर ध्यान दें।

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## चरण 5: टास्क को रिसोर्स असाइन करें
अब हम **assign resources to task** और `RateScaleType.Week` का उपयोग करके **how to set scale** निर्दिष्ट करते हैं। यह रेट स्केल को पढ़ने और लिखने दोनों को दर्शाता है।

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## चरण 6: प्रोजेक्ट को सेव करें
परिवर्तनों को एक नई फ़ाइल में सहेजें ताकि बाद में संग्रहीत रेट स्केल को सत्यापित किया जा सके।

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## चरण 7: रिसोर्स असाइनमेंट्स पुनः प्राप्त करें
सेव किए गए प्रोजेक्ट को री‑लोड करें और **read the rate** स्केल को पढ़ें ताकि यह पुष्टि हो सके कि यह सही ढंग से लिखा गया था।

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## सामान्य समस्याएँ और टिप्स
- **UID मिलान नहीं** – UID द्वारा असाइनमेंट्स प्राप्त करते समय सुनिश्चित करें कि UID मान निर्माण के दौरान असाइन किए गए मानों से मेल खाते हों।  
- **गलत रिसोर्स टाइप** – वर्क रिसोर्स के लिए `ResourceType.Material` का उपयोग करने से रेट गणना अप्रत्याशित रूप से व्यवहार करेगी।  
- **सेव फ़ॉर्मैट** – कस्टम फ़ील्ड्स जैसे रेट स्केल को संरक्षित रखने के लिए हमेशा `SaveFileFormat.Mpp` (या कोई अन्य समर्थित फ़ॉर्मैट) का उपयोग करें।  
- **बड़े प्रोजेक्ट्स** – Aspose.Tasks **500+ पेज** वाली फ़ाइलों को पूरी दस्तावेज़ को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, इसके स्ट्रीमिंग आर्किटेक्चर के कारण।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Tasks for Java को किसी भी Java IDE के साथ उपयोग कर सकता हूँ?**  
उ: हाँ, Aspose.Tasks for Java सभी प्रमुख Java IDEs, जैसे IntelliJ IDEA, Eclipse, और NetBeans, के साथ संगत है।

**प्र: क्या Aspose.Tasks MPP के अलावा अन्य फ़ाइल फ़ॉर्मैट्स का समर्थन करता है?**  
उ: हाँ, Aspose.Tasks विभिन्न फ़ाइल फ़ॉर्मैट्स, जैसे MPP, XML, और HTML, का समर्थन करता है।

**प्र: क्या Aspose.Tasks एंटरप्राइज़‑लेवल प्रोजेक्ट मैनेजमेंट के लिए उपयुक्त है?**  
उ: बिल्कुल, Aspose.Tasks में व्यापक फीचर्स हैं जो किसी भी स्केल के प्रोजेक्ट्स को मैनेज करने के लिए उपयुक्त हैं, जिससे यह एंटरप्राइज़‑लेवल प्रोजेक्ट मैनेजमेंट के लिए आदर्श बनता है।

**प्र: क्या मैं रेट स्केल के अलावा रिसोर्स असाइनमेंट्स को और कस्टमाइज़ कर सकता हूँ?**  
उ: हाँ, Aspose.Tasks लागत, कार्य, और अवधि समायोजन सहित रिसोर्स असाइनमेंट्स को कस्टमाइज़ करने की विस्तृत क्षमताएँ प्रदान करता है।

**प्र: क्या Aspose.Tasks सपोर्ट के लिए कोई कम्युनिटी फ़ोरम है?**  
उ: हाँ, आप Aspose.Tasks फ़ोरम पर समर्थन प्राप्त कर सकते हैं और अन्य उपयोगकर्ताओं के साथ इंटरैक्ट कर सकते हैं [यहाँ](https://forum.aspose.com/c/tasks/15)।

---

**अंतिम अपडेट:** 2026-06-10  
**टेस्टेड विथ:** Aspose.Tasks for Java 24.12 (लेखन के समय नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [How to Modify Assignments – Read Shared Resources with Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [How to Add Notes to Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}