---
date: 2026-05-31
description: Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलों से प्रोजेक्ट संस्करण
  प्राप्त करने और अंतिम सहेजी गई तिथि निकालने के तरीके सीखें। कोड उदाहरणों के साथ
  चरण-दर-चरण गाइड।
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Aspose.Tasks के साथ प्रोजेक्ट संस्करण निर्धारित करें
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट संस्करण कैसे प्राप्त करें – Aspose Tasks Java ट्यूटोरियल
url: /hi/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट संस्करण कैसे प्राप्त करें – Aspose Tasks Java ट्यूटोरियल

इस **Aspose Tasks Java ट्यूटोरियल** में आप Microsoft Project फ़ाइल का **प्रोजेक्ट संस्करण कैसे प्राप्त करें** और Aspose.Tasks लाइब्रेरी फॉर Java का उपयोग करके **अंतिम सहेजा गया दिनांक कैसे प्राप्त करें** सीखेंगे। फ़ाइल संस्करण और सहेजने का टाइमस्टैम्प जानने से आप संगतता समस्याओं से बच सकते हैं, माइग्रेशन नीतियों को लागू कर सकते हैं, और सटीक ऑडिट लॉग रख सकते हैं। हम हर चरण को—पर्यावरण सेटअप से लेकर संस्करण और दिनांक प्रिंट करने तक—विस्तार से दिखाएंगे, ताकि आप इस जाँच को किसी भी Java एप्लिकेशन में आत्मविश्वास के साथ एम्बेड कर सकें।

## त्वरित उत्तर
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Tasks for Java के साथ MS Project फ़ाइल संस्करण और अंतिम‑सहेजा गया तिथि निर्धारित करना।  
- **क्या मुझे Microsoft Project इंस्टॉल करना आवश्यक है?** नहीं, Aspose.Tasks Microsoft Project से स्वतंत्र रूप से काम करता है।  
- **कौन से फ़ाइल फ़ॉर्मेट समर्थित हैं?** XML‑आधारित प्रोजेक्ट फ़ाइलें जैसे MPP और XML पूरी तरह समर्थित हैं।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बुनियादी संस्करण जाँच के लिए लगभग 5‑10 मिनट।  
- **क्या लाइसेंस आवश्यक है?** मूल्यांकन के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन उपयोग के लिए एक कमर्शियल लाइसेंस आवश्यक है।

## Aspose Tasks Java ट्यूटोरियल क्या है?
`Aspose.Tasks` Java ट्यूटोरियल एक संक्षिप्त, हैंड‑ऑन गाइड है जो प्रोग्रामेटिक रूप से Microsoft Project डेटा के साथ इंटरैक्ट करना दर्शाता है। यह दिखाता है कि कैसे सर्वर पर Microsoft Project इंस्टॉल किए बिना प्रोजेक्ट जानकारी पढ़ें, संशोधित करें, और विश्लेषण करें। अतिरिक्त रूप से यह फ़ाइलों को लोड करने, प्रॉपर्टीज़ तक पहुँचने, और बदलाव सहेजने को कवर करता है, जिससे डेवलपर्स प्रोजेक्ट मैनेजमेंट कार्यों को प्रभावी रूप से ऑटोमेट कर सकते हैं।

## प्रोजेक्ट संस्करण निर्धारित करने के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks **सटीक संस्करण मेटाडेटा** और **अंतिम‑सहेजा गया टाइमस्टैम्प** प्रदान करता है, जबकि यह किसी भी OS पर चलता है जो Java को सपोर्ट करता है। यह मानक 2.5 GHz CPU पर **500 पेज तक की फ़ाइलें 2 सेकंड से कम समय में** प्रोसेस करता है, जिससे यह बैच ऑटोमेशन और बड़े‑पैमाने पर माइग्रेशन परिदृश्यों के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Java Development Kit (JDK)** – संस्करण 8 या नया।  
2. **Aspose.Tasks for Java JAR** – [वेबसाइट](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और इसे अपने प्रोजेक्ट की क्लासपाथ में जोड़ें।  
3. **MS Project फ़ाइल** – एक XML‑आधारित प्रोजेक्ट फ़ाइल (जैसे `input.xml`) जिसे आप निरीक्षण करना चाहते हैं।  

> **Pro tip:** प्रोजेक्ट फ़ाइल को एक समर्पित `data` फ़ोल्डर में रखें ताकि पाथ साफ़ रहें और आकस्मिक ओवरराइट से बचा जा सके।

## पैकेज आयात करें
सबसे पहले, आवश्यक Aspose.Tasks क्लासेस को इम्पोर्ट करें:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## प्रोजेक्ट डायरेक्टरी कैसे सेट करें
अपने एप्लिकेशन संरचना के भीतर एक समर्पित डायरेक्टरी बनाएं और सभी इनपुट फ़ाइलें वहाँ रखें। यह कोड को साफ़ रखता है और फ़ाइल लोड करते समय पाथ‑संबंधी त्रुटियों से बचाता है। डायरेक्टरी पाथ के लिए एक स्पष्ट वेरिएबल नाम उपयोग करें, जो प्रोजेक्ट रूट के सापेक्ष या पूर्ण पाथ हो सकता है।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को उस पूर्ण या सापेक्ष पाथ से बदलें जहाँ `input.xml` स्थित है।

## प्रोजेक्ट कैसे लोड करें
`Project` Aspose.Tasks का मुख्य ऑब्जेक्ट है जो मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है, जिससे आपको सभी प्रोजेक्ट प्रॉपर्टीज़ और कलेक्शन्स तक पहुँच मिलती है। `Project` इंस्टेंस बनाने के बाद आप उसके फ़ील्ड्स को क्वेरी कर सकते हैं, टास्क्स पर इटररेट कर सकते हैं, या फ़ाइल को डिस्क पर वापस सहेजने से पहले डेटा संशोधित कर सकते हैं।

```java
Project project = new Project(dataDir + "input.xml");
```

यदि आपकी फ़ाइल का नाम अलग है, तो `"input.xml"` को उसी अनुसार समायोजित करें।

## प्रोजेक्ट संस्करण कैसे निर्धारित करें
`Prj.SAVE_VERSION` वह प्रॉपर्टी है जो फ़ाइल को सहेजने वाले Microsoft Project के संस्करण संख्या को दर्शाती है। `Prj.LAST_SAVED` वह प्रॉपर्टी है जो फ़ाइल के अंतिम सहेजे जाने की तिथि और समय संग्रहीत करती है। `Prj.SAVE_VERSION` Microsoft Project एप्लिकेशन का संख्यात्मक संस्करण लौटाता है (जैसे 12 for Project 2010)। `Prj.LAST_SAVED` सबसे हालिया सहेजने की सटीक तिथि‑समय प्रदान करता है।

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

इन मानों के माध्यम से आप प्रोग्रामेटिक रूप से संस्करण‑विशिष्ट व्यावसायिक नियम लागू कर सकते हैं या ऑडिट रिपोर्ट जेनरेट कर सकते हैं।

## परिणाम कैसे प्रदर्शित करें
संस्करण और अंतिम‑सहेजा गया जानकारी प्राप्त करने के बाद, आमतौर पर आप इसे कंसोल या लॉग फ़ाइल में आउटपुट करना चाहते हैं। `System.out.println` का उपयोग करके मानों को प्रदर्शित करें, आवश्यकतानुसार तिथि को फ़ॉर्मेट करें। यह पुष्टि करता है कि निष्कर्षण सफल रहा और विकास या स्वचालित स्क्रिप्ट्स के दौरान त्वरित फीडबैक प्रदान करता है।

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| `project.get(...)` पर `NullPointerException` | फ़ाइल नहीं मिली या पथ गलत | `dataDir` और फ़ाइल नाम की जाँच करें; परीक्षण के लिए पूर्ण पाथ उपयोग करें। |
| अप्रत्याशित संस्करण संख्या (जैसे, 0) | गैर‑प्रोजेक्ट XML फ़ाइल लोड करना | फ़ाइल एक वैध Microsoft Project फ़ाइल (MPP/XML) है, यह सुनिश्चित करें। |
| लाइसेंस अपवाद | प्रोडक्शन में वैध लाइसेंस के बिना ट्रायल उपयोग करना | अपना Aspose.Tasks लाइसेंस लागू करें (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Tasks .NET, Java, और C++ सहित कई भाषाओं को सपोर्ट करता है।

**Q: क्या Aspose.Tasks बड़े‑पैमाने के प्रोजेक्ट्स के लिए उपयुक्त है?**  
A: बिल्कुल; यह कई‑सौ पेज वाले प्रोजेक्ट्स को सेकंड्स में प्रोसेस कर सकता है बिना पूरी फ़ाइल को मेमोरी में लोड किए।

**Q: क्या मैं Aspose.Tasks के साथ प्रोजेक्ट डेटा को कस्टमाइज़ कर सकता हूँ?**  
A: हाँ, आप API के माध्यम से टास्क्स, रिसोर्सेज़, कैलेंडर, और किसी भी प्रोजेक्ट एलिमेंट को संशोधित कर सकते हैं।

**Q: क्या Aspose.Tasks को Microsoft Project इंस्टॉलेशन की आवश्यकता है?**  
A: नहीं, लाइब्रेरी स्वतंत्र रूप से काम करती है और होस्ट मशीन पर Microsoft Project की आवश्यकता नहीं होती।

**Q: क्या Aspose.Tasks के लिए तकनीकी समर्थन उपलब्ध है?**  
A: हाँ, आप Aspose.Tasks फ़ोरम से मदद प्राप्त कर सकते हैं [यहाँ](https://forum.aspose.com/c/tasks/15)।

**अतिरिक्त प्रश्न‑उत्तर**

**Q: मैं अन्य प्रोजेक्ट प्रॉपर्टीज़ (जैसे, लेखक, कंपनी) कैसे प्राप्त करूँ?**  
A: `project.get(Prj.AUTHOR)` या `project.get(Prj.COMPANY)` का उपयोग उसी तरह करें जैसा आप संस्करण प्राप्त करते हैं।

**Q: क्या मैं MPP (बाइनरी) फ़ाइल का संस्करण जांच सकता हूँ?**  
A: हाँ, Aspose.Tasks सीधे `.mpp` फ़ाइलें लोड करता है; `Prj.SAVE_VERSION` प्रॉपर्टी बाइनरी फ़ॉर्मेट के लिए भी काम करती है।

**Q: क्या कोई तरीका है जिससे पुराने प्रोजेक्ट फ़ाइल को प्रोग्रामेटिक रूप से नए संस्करण में अपग्रेड किया जा सके?**  
A: पुराने फ़ाइल को लोड करें, फिर `project.save("newfile.mpp", SaveFileFormat.MPP);` के साथ सहेजें – Aspose.Tasks डिफ़ॉल्ट रूप से नवीनतम फ़ॉर्मेट में फ़ाइल लिखता है।

## निष्कर्ष
आपने अब **प्रोजेक्ट संस्करण कैसे प्राप्त करें** और **MS Project फ़ाइलों से अंतिम सहेजा गया दिनांक कैसे प्राप्त करें** Aspose.Tasks for Java का उपयोग करके सीख लिया है। इन स्निपेट्स को ऑटोमेशन पाइपलाइन, रिपोर्टिंग टूल्स, या माइग्रेशन यूटिलिटीज़ में शामिल करें ताकि आप हमेशा सटीक प्रोजेक्ट संस्करण की जानकारी रख सकें।

---

**अंतिम अपडेट:** 2026-05-31  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [MS Project में प्रोजेक्ट प्रारंभ तिथि सेट करें Aspose.Tasks for Java का उपयोग करके](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks for Java के साथ माइक्रोसॉफ्ट प्रोजेक्ट डेटाबेस पढ़ें](/tasks/java/project-data-reading/read-project-database/)
- [Aspose.Tasks for Java के साथ प्रोजेक्ट को टेम्प्लेट, CSV, और टेक्स्ट के रूप में सहेजें](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}