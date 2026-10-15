---
date: 2026-10-15
description: Aspose.Tasks for Java के साथ activity बनाना, data directory सेट करना,
  table fields को customize करना और प्रोजेक्ट को MPP के रूप में सहेजना सीखें। Java
  डेवलपर्स के लिए चरण‑दर‑चरण गाइड।
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Aspose.Tasks for Java का उपयोग करके activity बनाना और data directory सेट
  करना कैसे करें
og_description: Aspose.Tasks for Java का उपयोग करके activity बनाना, table fields को
  customize करना और प्रोजेक्ट को MPP के रूप में सहेजना। तेज़ कार्यान्वयन के लिए इस
  विस्तृत गाइड का पालन करें।
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Aspose.Tasks for Java में activity बनाना और data directory सेट करना कैसे
  करें
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Aspose.Tasks for Java का उपयोग करके activity बनाना और data directory सेट करना
  कैसे करें
url: /hi/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके गतिविधि बनाना और डेटा डायरेक्टरी सेट करना

## परिचय
इस ट्यूटोरियल में आप **प्रोग्रामेटिक रूप से गतिविधि बनाना**, **डेटा डायरेक्टरी कॉन्फ़िगर करना**, और **प्रोजेक्ट को MPP के रूप में सहेजना** के साथ-साथ गैंट चार्ट दृश्य में **तालिका फ़ील्ड को अनुकूलित करना** सीखेंगे। Aspose.Tasks for Java एक शक्तिशाली API है जो 30 से अधिक इनपुट और आउटपुट फ़ॉर्मेट का समर्थन करता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना 10 000 कार्यों तक के प्रोजेक्ट को प्रोसेस कर सकता है। इस गाइड के अंत तक आप प्रोजेक्ट निर्माण को स्वचालित कर पाएँगे, कार्यों में कस्टम एट्रिब्यूट जोड़ पाएँगे, और Microsoft Project के लिए तैयार‑to‑open MPP फ़ाइल बना पाएँगे।

## त्वरित उत्तर
- **पहला कदम क्या है?** अपने प्रोजेक्ट फ़ाइलों के स्थित डेटा डायरेक्टरी पथ को सेट करें।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (आधिकारिक साइट से डाउनलोड योग्य)।  
- **क्या मैं कस्टम एट्रिब्यूट जोड़ सकता हूँ?** हाँ – आप विस्तारित एट्रिब्यूट परिभाषित कर सकते हैं और उन्हें गैंट चार्ट में दिखा सकते हैं।  
- **परीक्षण के लिए लाइसेंस चाहिए?** मूल्यांकन उद्देश्यों के लिए एक अस्थायी लाइसेंस उपलब्ध है।  
- **कौन सा IDE सबसे अच्छा है?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, NetBeans) काम करेगा।

## “डेटा डायरेक्टरी सेट” क्या है और यह क्यों महत्वपूर्ण है?
डेटा डायरेक्टरी सेट करने से Aspose.Tasks को प्रोजेक्ट फ़ाइलों को पढ़ने और लिखने का स्थान पता चलता है। सही पथ न होने पर API आपके `.mpp` फ़ाइलों को नहीं ढूँढ़ पाता, जिससे `FileNotFoundException` त्रुटि आती है। कोड की शुरुआत में इस डायरेक्टरी को परिभाषित करने से वर्कफ़्लो दोहराने योग्य बनता है और फ़ाइल‑सिस्टम संबंधी चिंताओं को बिज़नेस लॉजिक से अलग किया जा सकता है।

## गैंट चार्ट में तालिका फ़ील्ड को अनुकूलित क्यों करें?
कस्टम तालिका फ़ील्ड आपको अतिरिक्त जानकारी—जैसे कस्टम एट्रिब्यूट, रिसोर्स डेटा, या प्रोजेक्ट‑विशिष्ट नोट्स—सीधे गैंट दृश्य में प्रदर्शित करने की अनुमति देती है। इससे अलग‑अलग रिपोर्टों की आवश्यकता कम होती है और हितधारकों को एक ही डेटा‑समृद्ध दृश्य मिलता है, जिससे निर्णय‑लेने की गति में 30 % तक सुधार हो सकता है।

## नई गतिविधि कैसे बनाएं?
आप एक नया `Task` ऑब्जेक्ट बनाकर और उसे प्रोजेक्ट की रूट टास्क कलेक्शन में जोड़कर नई गतिविधि (टास्क) बनाते हैं। यह तरीका आपको बड़े शेड्यूल स्वचालित रूप से जनरेट करने, बाहरी सिस्टम से टास्क डेटा खींचने, या मैन्युअल एडिटिंग के बिना बल्क अपडेट लागू करने की सुविधा देता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Java Development Kit (JDK)** – संस्करण 8 या नया।  
2. **Aspose.Tasks for Java** – इसे **Aspose.Tasks Java रिलीज़ पेज** से डाउनलोड करें।  
3. **IDE** – IntelliJ IDEA, Eclipse, या कोई भी Java‑संगत एडिटर जो आप पसंद करते हैं।  

## पैकेज आयात करें
`com.aspose.tasks` नेमस्पेस में सभी क्लासेज़ हैं जो आपको प्रोजेक्ट मैनिपुलेशन के लिए चाहिए। इसे आयात करने से आप `Project`, `Task`, `ExtendedAttributeDefinition` और अन्य कोर टाइप्स तक पहुँच प्राप्त करेंगे।

```java
import com.aspose.tasks.*;
```

## Maven निर्भरता (वैकल्पिक)
यदि आप अपने प्रोजेक्ट को Maven से मैनेज करते हैं, तो `pom.xml` में Aspose.Tasks निर्भरता जोड़ें। इससे बिल्ड के दौरान लाइब्रेरी स्वचालित रूप से रिज़ॉल्व हो जाएगी।

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## चरण-दर-चरण मार्गदर्शिका

### चरण 1: डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपके प्रोजेक्ट फ़ाइलें हैं। `dataDir` वेरिएबल में पूर्ण पथ संग्रहीत होता है और ट्यूटोरियल में बार‑बार उपयोग किया जाता है।

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को उस फ़ोल्डर के पूर्ण पथ से बदलें जहाँ `project.mpp` स्थित है, उदाहरण के लिए `C:/Projects/MyGantt`।

### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
`Project` Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। मौजूदा फ़ाइल लोड करने से आपको उसके टास्क, रिसोर्स और टेबल्स तक पहुँच मिलती है।

```java
Project project = new Project(dataDir + "project.mpp");
```

### चरण 3: नई गतिविधि जोड़ें
`Task` शेड्यूल में एक व्यक्तिगत गतिविधि को दर्शाता है। रूट टास्क कलेक्शन में टास्क जोड़ने से वह प्रोजेक्ट हायरार्की के शीर्ष स्तर पर सम्मिलित हो जाता है।

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### चरण 4: कस्टम एट्रिब्यूट परिभाषित करें
`ExtendedAttributeDefinition` आपको एक पुन: उपयोग योग्य कस्टम फ़ील्ड बनाने की अनुमति देता है जिसे किसी भी टास्क, रिसोर्स या असाइनमेंट से जोड़ा जा सकता है।

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### चरण 5: टास्क में कस्टम एट्रिब्यूट जोड़ें
`ExtendedAttribute` कस्टम एट्रिब्यूट का ठोस उदाहरण है जिसे आप किसी विशिष्ट टास्क को असाइन करते हैं।

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### चरण 6: तालिका को अनुकूलित करें – कस्टम एट्रिब्यूट को कॉलम के रूप में जोड़ें
`TableField` गैंट चार्ट तालिका में एक कॉलम का वर्णन करता है। एक `TableField` जोड़कर जो कस्टम एट्रिब्यूट को संदर्भित करता है, आप उस एट्रिब्यूट को चार्ट दृश्य में दिखा सकते हैं।

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### चरण 7: प्रोजेक्ट सहेजें
`project.save` को कॉल करने से सभी परिवर्तन एक नई फ़ाइल में सहेजे जाते हैं। `SaveFileFormat.MPP` कॉन्स्टेंट Aspose.Tasks को फ़ाइल को Microsoft Project के मूल बाइनरी फ़ॉर्मेट में लिखने के लिए निर्देश देता है।

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **FileNotFoundException** प्रोजेक्ट लोड करते समय | **डेटा डायरेक्टरी** पथ गलत है या अंत में स्लैश नहीं है। | सुनिश्चित करें `dataDir` सही फ़ोल्डर की ओर इशारा करता है और उचित फ़ाइल सेपरेटर (`/` या `\\`) शामिल है। |
| कस्टम एट्रिब्यूट गैंट दृश्य में नहीं दिख रहा | तालिका फ़ील्ड गलत इंडेक्स पर जोड़ा गया या कॉलम की चौड़ाई बहुत छोटी है। | सुनिश्चित करें `table.getTableFields().add(3, attrField);` वैध इंडेक्स उपयोग करता है और `setWidth` आवश्यकतानुसार समायोजित करें। |
| LicenseException सहेजते समय | उत्पादन उपयोग के लिए वैध लाइसेंस लागू नहीं किया गया। | `project.save()` से पहले अस्थायी या स्थायी लाइसेंस लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ, Aspose.Tasks .NET, Java, और C++ के लिए उपलब्ध है।

**प्रश्न: क्या Aspose.Tasks के लिए कोई मुफ्त ट्रायल उपलब्ध है?**  
**उत्तर:** हाँ, आप **Aspose.Tasks free trial download page** से मुफ्त ट्रायल डाउनलोड कर सकते हैं।

**प्रश्न: मैं Aspose.Tasks के लिए समर्थन कहाँ पा सकता हूँ?**  
**उत्तर:** आप समर्थन पा सकते हैं और प्रश्न पूछ सकते हैं [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर।

**प्रश्न: मैं Aspose.Tasks के लिए लाइसेंस कैसे खरीद सकता हूँ?**  
**उत्तर:** आप **Aspose.Tasks purchase page** से लाइसेंस खरीद सकते हैं।

**प्रश्न: क्या परीक्षण उद्देश्यों के लिए मुझे एक अस्थायी लाइसेंस चाहिए?**  
**उत्तर:** हाँ, आप **temporary license request page** से अस्थायी लाइसेंस प्राप्त कर सकते हैं।

## निष्कर्ष
आप अब जानते हैं **कैसे गतिविधि बनाएं**, डेटा डायरेक्टरी सेट करें, कस्टम एट्रिब्यूट परिभाषित और टास्क से जोड़ें, और **प्रोजेक्ट को MPP के रूप में सहेजें** साथ ही **गैंट चार्ट दृश्य में तालिका फ़ील्ड को अनुकूलित करें** Aspose.Tasks for Java का उपयोग करके। ये क्षमताएँ आपको प्रोजेक्ट डेटा पर पूर्ण प्रोग्रामेटिक नियंत्रण देती हैं, जिससे स्वचालित शेड्यूल जनरेशन और आपके हितधारकों के लिए समृद्ध विज़ुअल रिपोर्टिंग संभव होती है।

---

**अंतिम अद्यतन:** 2026-10-15  
**परीक्षित संस्करण:** Aspose.Tasks Java 24.12 (latest)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks (MS Project) में खाली प्रोजेक्ट फ़ाइल कैसे बनाएं](/tasks/java/project-configuration/create-empty-project-file/)
- [MPP फ़ाइल कैसे बनाएं – Aspose.Tasks के साथ खाली प्रोजेक्ट को MPP फ़ॉर्मेट में बनाएं और सहेजें](/tasks/java/project-configuration/create-save-mpp/)
- [Aspose.Tasks में प्रोजेक्ट बनाएं – नई टास्क एट्रिब्यूट सेट करें](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}