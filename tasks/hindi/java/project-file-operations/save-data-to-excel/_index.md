---
date: 2026-05-31
description: Aspose.Tasks for Java का उपयोग करके MPP को Excel में निर्यात करना और
  प्रोजेक्ट फ़ाइल को Excel में बदलना सीखें। Java डेवलपर्स के लिए सरल चरण।
keywords:
- export mpp to excel
- convert mpp to xlsx
- write excel workbook java
- project file to spreadsheet
- export project schedule excel
linktitle: Aspose.Tasks में डेटा को Excel में सहेजें
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  headline: How to Export MPP to Excel with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to export MPP to Excel and convert project file to Excel
    using Aspose.Tasks for Java. Simple steps for Java developers.
  name: How to Export MPP to Excel with Aspose.Tasks for Java
  steps:
  - name: Define the Data Directory Path
    text: Set the folder where your `.mpp` file resides. Replace the placeholder with
      your actual path. The `dataDir` string tells the API where to locate the source
      file and where to write the resulting Excel workbook. java String dataDir =
      "Your Data Directory";
  - name: Load the Project File
    text: Create a `Project` instance by loading the `.mpp` file you want to convert.
      The `Project` class represents a Microsoft Project file in memory, allowing
      further manipulation or direct export. java Project project = new Project(dataDir
      + "project5.mpp");
  - name: Save the Project as XLSX
    text: 'Finally, export the loaded project to an Excel workbook. The `SaveFileFormat`
      enum specifies the output file format; `SaveFileFormat.Xlsx` tells Aspose.Tasks
      to generate a modern `.xlsx` file, effectively **convert MPP file to XLSX**.
      You can also specify `SaveOptions` to fine‑tune column widths or '
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides extensive APIs to read, write, and
      modify project files, including tasks, resources, calendars, and custom fields.
    question: Can I use Aspose.Tasks for Java to manipulate project data programmatically?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: The official documentation is available [here](https://reference.aspose.com/tasks/java/).
    question: Where can I find documentation for Aspose.Tasks for Java?
  - answer: Support is provided through the Aspose.Tasks forum, reachable [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for issues or queries related to Aspose.Tasks
      for Java?
  - answer: Yes, a temporary license can be obtained from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ MPP को Excel में निर्यात करने का तरीका
url: /hi/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ MPP को Excel में निर्यात करने का तरीका

## परिचय
Aspose.Tasks for Java एक शक्तिशाली लाइब्रेरी है जो आपको **export MPP to Excel** जल्दी और भरोसेमंद तरीके से करने देती है। इस ट्यूटोरियल में हम आपको वह सटीक कदम दिखाएंगे जो Microsoft Project (.mpp) फ़ाइल को Excel वर्कबुक (.xlsx) में बदलने के लिए आवश्यक हैं। अंत तक आप समझेंगे कि **convert project file to Excel**, यह परिवर्तन क्यों उपयोगी है, और इस प्रक्रिया को किसी भी Java एप्लिकेशन में कैसे एकीकृत करें।

## त्वरित उत्तर
- **API क्या करता है?** यह Project फ़ाइलों को पढ़ता है और उन्हें सीधे XLSX वर्कबुक के रूप में सहेजता है।  
- **कौन सा फ़ॉर्मेट उत्पन्न होता है?** यह `SaveFileFormat.Xlsx` विकल्प का उपयोग करके एक Excel फ़ाइल बनाता है।  
- **क्या मुझे लाइसेंस चाहिए?** ट्रायल परीक्षण के लिए काम करता है; उत्पादन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।  
- **पूर्वापेक्षाएँ क्या हैं?** JDK स्थापित होना चाहिए और Aspose.Tasks for Java लाइब्रेरी को आपके प्रोजेक्ट में जोड़ना चाहिए।  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** आमतौर पर बुनियादी निर्यात के लिए 10 मिनट से कम समय लगता है।

## “MPP को Excel में निर्यात करने” क्या है?
MPP को Excel में निर्यात करने का मतलब है Microsoft Project फ़ाइल में संग्रहीत शेड्यूल, संसाधन और कार्य डेटा को लेकर उसे एक संरचित Excel स्प्रेडशीट में लिखना। इससे उन हितधारकों के साथ प्रोजेक्ट डेटा साझा करना आसान हो जाता है जिनके पास Project स्थापित नहीं है।

## MPP फ़ाइल को XLSX में क्यों बदलें?
MPP को Excel में निर्यात करने से आप प्रोजेक्ट जानकारी को एक सार्वभौमिक रूप से उपलब्ध फ़ॉर्मेट में साझा कर सकते हैं। **Direct answer:** MPP को XLSX में बदलने से हर व्यवसाय उपयोगकर्ता को Excel के मूल टूल—पिवट टेबल, चार्ट, और फ़ॉर्मूले—का उपयोग करके प्रोजेक्ट डेटा खोलने, संपादित करने और विश्लेषण करने की क्षमता मिलती है, बिना Microsoft Project स्थापित किए। इससे पहुँच बढ़ती है, रिपोर्टिंग तेज़ होती है, और ऑटोमेशन पाइपलाइन सक्षम होती हैं जो साधारण Excel फ़ाइलों को उपभोग करती हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – स्थापित है और आपके सिस्टम PATH में जोड़ा गया है।  
2. **Aspose.Tasks for Java library** – इसे [download link](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और JAR को अपने प्रोजेक्ट के classpath में जोड़ें।

## पैकेज आयात करें
`com.aspose.tasks` Project फ़ाइलों को संभालने के लिए कोर API प्रदान करता है, जबकि `java.io` फ़ाइल‑सिस्टम उपयोगिताएँ देता है।  
`Project` क्लास Aspose.Tasks की शीर्ष‑स्तरीय ऑब्जेक्ट है जो मेमोरी में एकल Microsoft Project फ़ाइल का प्रतिनिधित्व करती है। `Project` क्लास एक Microsoft Project फ़ाइल को मेमोरी में लोड करने का प्रतिनिधित्व करती है। API के साथ काम शुरू करने से पहले आवश्यक नेमस्पेस आयात करें।

```text
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
```

## चरण‑दर‑चरण मार्गदर्शिका

### Aspose.Tasks का उपयोग करके MPP को Excel में कैसे निर्यात करें?
अपने `.mpp` फ़ाइल को `new Project("yourfile.mpp")` से लोड करें और तुरंत `project.save("output.xlsx", SaveFileFormat.Xlsx)` को कॉल करें। यह दो‑लाइन पैटर्न पूर्ण रूपांतरण करता है, कार्य, संसाधन और कस्टम फ़ील्ड को संरक्षित रखते हुए। यह ऑपरेशन सामान्य 100‑कार्य प्रोजेक्ट्स के लिए एक मानक विकास मशीन पर एक सेकंड से कम समय में चलता है।

#### चरण 1: डेटा डायरेक्टरी पाथ निर्धारित करें
उस फ़ोल्डर को सेट करें जहाँ आपकी `.mpp` फ़ाइल स्थित है। प्लेसहोल्डर को अपने वास्तविक पाथ से बदलें। `dataDir` स्ट्रिंग API को बताती है कि स्रोत फ़ाइल कहाँ स्थित है और परिणामी Excel वर्कबुक कहाँ लिखनी है।

```text
```java
String dataDir = "Your Data Directory";
```
```

#### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
`Project` इंस्टेंस बनाएं `.mpp` फ़ाइल को लोड करके जिसे आप बदलना चाहते हैं। `Project` क्लास मेमोरी में एक Microsoft Project फ़ाइल का प्रतिनिधित्व करती है, जिससे आगे की हेरफेर या सीधे निर्यात की सुविधा मिलती है।

```text
```java
Project project = new Project(dataDir + "project5.mpp");
```
```

#### चरण 3: प्रोजेक्ट को XLSX के रूप में सहेजें
अंत में, लोड किए गए प्रोजेक्ट को एक Excel वर्कबुक में निर्यात करें। `SaveFileFormat` एन्नुम आउटपुट फ़ाइल फ़ॉर्मेट निर्दिष्ट करता है; `SaveFileFormat.Xlsx` Aspose.Tasks को एक आधुनिक `.xlsx` फ़ाइल बनाने के लिए कहता है, प्रभावी रूप से **convert MPP file to XLSX**। आप कॉलम चौड़ाई को सूक्ष्म‑समायोजित करने या केवल चयनित तालिकाओं को शामिल करने के लिए `SaveOptions` भी निर्दिष्ट कर सकते हैं।

```text
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
```

## सामान्य उपयोग मामलों
- **Executive reporting:** वरिष्ठ प्रबंधन के लिए Excel में उच्च‑स्तरीय प्रोजेक्ट स्नैपशॉट प्रदान करें।  
- **Data analysis:** कार्य और संसाधन डेटा को Excel के Power Query में फीड करें गहरी अंतर्दृष्टि के लिए।  
- **Integration:** निर्यातित Excel फ़ाइल को डाउनस्ट्रीम सिस्टम्स को पास करें जो केवल CSV/Excel इनपुट स्वीकार करते हैं।

## अतिरिक्त टिप्स और सर्वोत्तम प्रथाएँ
- **Performance tip:** 500 से अधिक कार्यों वाले प्रोजेक्ट्स के लिए `project.setReadWriteMode(ReadWriteMode.MemoryOptimized)` को सक्षम करें ताकि मेमोरी खपत कम हो। `ReadWriteMode.MemoryOptimized` बड़े प्रोजेक्ट्स को संभालते समय RAM उपयोग को न्यूनतम करता है।  
- **Formatting tip:** निर्यात में कस्टम फ़ील्ड शामिल करने के लिए `project.save("output.xlsx", SaveFileFormat.Xlsx, new XlsxSaveOptions { ExportAllFields = true })` का उपयोग करें। `XlsxSaveOptions` आपको Excel निर्यात को कस्टमाइज़ करने देता है, जैसे सभी फ़ील्ड निर्यात करना।  
- **Error handling:** लोड और सेव कॉल को try‑catch ब्लॉक में रैप करें ताकि `FileNotFoundException` या `LicenseException` को पकड़ सकें और स्पष्ट उपयोगकर्ता प्रतिक्रिया प्रदान कर सकें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट डेटा को प्रोग्रामेटिकली बदल सकता हूँ?**  
A: हाँ, Aspose.Tasks for Java विस्तृत APIs प्रदान करता है जो प्रोजेक्ट फ़ाइलों को पढ़ने, लिखने और संशोधित करने की सुविधा देता है, जिसमें कार्य, संसाधन, कैलेंडर और कस्टम फ़ील्ड शामिल हैं।

**Q: क्या Aspose.Tasks for Java के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण [here](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**Q: मैं Aspose.Tasks for Java की दस्तावेज़ीकरण कहाँ पा सकता हूँ?**  
A: आधिकारिक दस्तावेज़ीकरण [here](https://reference.aspose.com/tasks/java/) पर उपलब्ध है।

**Q: Aspose.Tasks for Java से संबंधित मुद्दों या प्रश्नों के लिए समर्थन कैसे प्राप्त करूँ?**  
A: समर्थन Aspose.Tasks फ़ोरम के माध्यम से उपलब्ध है, जिसे आप [here](https://forum.aspose.com/c/tasks/15) पर पहुँच सकते हैं।

**Q: क्या मैं Aspose.Tasks for Java के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?**  
A: हाँ, एक अस्थायी लाइसेंस आप [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

## निष्कर्ष
इस गाइड में हमने Aspose.Tasks for Java का उपयोग करके **how to export MPP to Excel** दिखाया। तीन सरल चरणों—डेटा डायरेक्टरी निर्धारित करना, प्रोजेक्ट फ़ाइल लोड करना, और उसे XLSX के रूप में सहेजना—का पालन करके आप आसानी से **export project data to Excel** कर सकते हैं और अपनी टीम को लचीले, साझा करने योग्य रिपोर्टों से सशक्त बना सकते हैं। लाइब्रेरी की **write Excel workbook Java** शैली कोड लिखने की क्षमता किसी भी Java‑आधारित वर्कफ़्लो के लिए एकीकरण को सहज बनाती है।

---

**अंतिम अपडेट:** 2026-05-31  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [MPP फ़ाइल कैसे बनाएं – Aspose.Tasks के साथ MPP फ़ॉर्मेट में खाली प्रोजेक्ट बनाएं और सहेजें](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks for Java के साथ प्रोजेक्ट को टेम्पलेट, CSV, और टेक्स्ट के रूप में सहेजें](/tasks/java/project-file-operations/save-csv-text-template/)
- [Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट की प्रारंभ तिथि सेट करें](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}