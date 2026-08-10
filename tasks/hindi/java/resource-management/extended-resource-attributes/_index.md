---
date: 2026-06-10
description: Java में विस्तारित एट्रिब्यूट कैसे बनाएं, Microsoft Project फ़ाइल लोड
  करें, संख्यात्मक मान सेट करें, और Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट
  को XML के रूप में सहेजें, यह सीखें।
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Aspose.Tasks में विस्तारित रिसोर्स एट्रिब्यूट्स को संभालें
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Java में Aspose.Tasks के साथ विस्तारित एट्रिब्यूट कैसे बनाएं
url: /hi/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में Aspose.Tasks के साथ विस्तारित एट्रिब्यूट कैसे बनाएं

## परिचय
इस व्यावहारिक मार्गदर्शिका में आप Aspose.Tasks का उपयोग करके Microsoft Project फ़ाइल के लिए **जावा में विस्तारित एट्रिब्यूट बनाएँगे**। हम मौजूदा प्रोजेक्ट को लोड करने, नया संख्यात्मक एट्रिब्यूट परिभाषित करने, संसाधन को मान असाइन करने, और अंत में परिवर्तन को XML फ़ाइल के रूप में सहेजने की प्रक्रिया को चरण‑दर‑चरण दिखाएंगे। अंत तक आपके पास एक पुन: उपयोग योग्य कोड पैटर्न होगा जिसे किसी भी जावा‑आधारित प्रोजेक्ट‑मैनेजमेंट समाधान में डाला जा सकता है।

## त्वरित उत्तर
- **विस्तारित एट्रिब्यूट क्या है?**  
  एक उपयोगकर्ता‑परिभाषित फ़ील्ड (जैसे, आयु, कौशल स्तर) जो संसाधनों या कार्यों के लिए अतिरिक्त डेटा संग्रहीत करता है।  
- **कौन सा API इसे बनाता है?**  
  Aspose.Tasks for Java `ExtendedAttributeDefinition` क्लास प्रदान करता है जो कस्टम एट्रिब्यूट को परिभाषित और प्रबंधित करता है।  
- **क्या मुझे लाइसेंस चाहिए?**  
  विकास के लिए एक अस्थायी मूल्यांकन लाइसेंस काम करता है; उत्पादन परिनियोजन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या मैं संख्याएँ संग्रहीत कर सकता हूँ?**  
  हां – सटीक दशमलव मान असाइन करने के लिए `setNumericValue(BigDecimal)` का उपयोग करें।  
- **मैं परिवर्तन कैसे सहेजूँ?**  
  `project.save("output.xml", SaveFileFormat.Xml)` को कॉल करके अपडेटेड प्रोजेक्ट को XML फ़ॉर्मेट में लिखें।

## कस्टम एट्रिब्यूट क्या है?
एक **कस्टम एट्रिब्यूट** (जिसे विस्तारित एट्रिब्यूट भी कहा जाता है) Microsoft Project में संसाधनों या कार्यों में जोड़ी जा सकने वाली अतिरिक्त कॉलम है। यह आपको उन डेटा को कैप्चर करने की अनुमति देता है जो अंतर्निहित फ़ील्ड में नहीं होते, जैसे कर्मचारी की आयु, प्रमाणन स्तर, या कोई भी व्यावसायिक‑विशिष्ट मीट्रिक।

## जावा में विस्तारित एट्रिब्यूट क्यों बनाएं?
जावा में विस्तारित एट्रिब्यूट बनाना आपको प्रोग्रामेटिक रूप से प्रोजेक्ट डेटा को समृद्ध करने, फ़ाइलों में स्थिरता सुनिश्चित करने और स्वचालित रिपोर्टिंग सक्षम करने देता है। एट्रिब्यूट को एक बार परिभाषित करके, आप इसे कई संसाधनों या कार्यों पर मैन्युअल एंट्री के बिना लागू कर सकते हैं, जिससे समय बचता है और त्रुटियों में कमी आती है।

- **अपने संगठन के अनुसार डेटा को अनुकूलित करें** – मैन्युअल Excel वर्कअराउंड के बिना कोई भी मीट्रिक संग्रहीत करें।  
- **समृद्ध रिपोर्टिंग सक्षम करें** – बाद में डैशबोर्ड या एनालिटिक्स के लिए कस्टम फ़ील्ड को क्वेरी करें।  
- **स्थिरता बनाए रखें** – कई प्रोजेक्ट्स में एक ही परिभाषा को प्रोग्रामेटिक रूप से लागू करें, जिससे मानवीय त्रुटि समाप्त हो जाती है।  
- **परफॉर्मेंस‑टेस्टेड** – Aspose.Tasks उत्पाद बेंचमार्क के अनुसार 10 000 कार्य और 5 000 संसाधनों वाले प्रोजेक्ट्स को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, **सुनिश्चित** करें कि आपके पास है:

1. **Java Development Kit** – JDK 8 या नया स्थापित हो।  
2. **Aspose.Tasks for Java** – नवीनतम रिलीज़ **यहाँ** से डाउनलोड करें [यहाँ](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, या कोई भी Java‑संगत विकास वातावरण।

## जावा में विस्तारित एट्रिब्यूट कैसे बनाएं?
अपने प्रोजेक्ट को लोड करें, एट्रिब्यूट को परिभाषित करें, इसे एक संसाधन से जोड़ें, और फ़ाइल को सहेजें – सभी कुछ कुछ सरल चरणों में। निम्नलिखित अनुभाग प्रत्येक चरण को संक्षिप्त व्याख्या में विभाजित करते हैं, जिसके बाद आपका वास्तविक कोड रहने वाला प्लेसहोल्डर आता है।

### चरण‑दर‑चरण मार्गदर्शिका

#### पैकेज आयात करें
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` और संबंधित क्लासेस `com.aspose.tasks` नेमस्पेस में स्थित हैं। इन्हें अपनी जावा फ़ाइल के शीर्ष पर आयात करें।

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### चरण 1: डेटा डायरेक्टरी परिभाषित करें
`Paths` एक यूटिलिटी क्लास है जो प्लेटफ़ॉर्म‑स्वतंत्र तरीके से फ़ाइल सिस्टम पाथ प्राप्त करने के लिए मेथड्स प्रदान करती है।

```java
String dataDir = "Your Data Directory";
```

#### चरण 2: Microsoft Project फ़ाइल लोड करें
`Project` मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है, जिससे इसकी सामग्री को पढ़ने और लिखने की अनुमति मिलती है।

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### चरण 3: कस्टम एट्रिब्यूट परिभाषित करें
`ExtendedAttributeDefinition` एक नए कस्टम फ़ील्ड की स्कीमा को परिभाषित करता है जिसे संसाधनों या कार्यों से जोड़ा जा सकता है।

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### चरण 4: जावा में संख्यात्मक मान सेट करें
`ExtendedAttributeResource` किसी विशिष्ट संसाधन इंस्टेंस के लिए कस्टम एट्रिब्यूट का मान रखता है।

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### चरण 5: संसाधन जोड़ें और कस्टम एट्रिब्यूट संलग्न करें
`Resource` प्रोजेक्ट संसाधन को मॉडल करता है जैसे व्यक्ति, उपकरण, या सामग्री।

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### चरण 6: प्रोजेक्ट को XML के रूप में सहेजें
`SaveFileFormat` प्रोजेक्ट को सहेजने के लिए समर्थित आउटपुट फ़ॉर्मेट्स को सूचीबद्ध करता है, जिसमें XML भी शामिल है।

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### चरण 7: परिणाम प्रदर्शित करें
`System.out.println` मानक कंसोल आउटपुट पर एक पंक्ति टेक्स्ट प्रिंट करता है।

```java
System.out.println("Process completed Successfully");
```

## सामान्य कठिनाइयाँ और टिप्स
- **एट्रिब्यूट ID टकराव:** नया परिभाषा बनाने से पहले हमेशा `project.getExtendedAttributes().getById(id)` कॉल करें ताकि डुप्लिकेट पहचानकर्ता न बनें।  
- **प्रेसिजन हैंडलिंग:** सटीक संख्यात्मक मानों के लिए `float`/`double` के बजाय `BigDecimal` को प्राथमिकता दें; यह रिपोर्टिंग में राउंडिंग त्रुटियों से बचाता है।  
- **फ़ाइल पाथ विश्वसनीयता:** `Paths.get(...).toAbsolutePath()` का उपयोग करें या अपने IDE की कार्यशील डायरेक्टरी को कॉन्फ़िगर करें ताकि `FileNotFoundException` से बचा जा सके।  

## अक्सर पूछे जाने वाले प्रश्न

**Q:** क्या मैं कार्यों के साथ-साथ संसाधनों के लिए भी कस्टम एट्रिब्यूट बना सकता हूँ?  
**A:** हाँ – एट्रिब्यूट स्कीमा परिभाषित करते समय `ExtendedAttributeResource` के बजाय `ExtendedAttributeTask` का उपयोग करें।

**Q:** क्या एक साथ कई कस्टम एट्रिब्यूट जोड़ना संभव है?  
**A:** बिल्कुल। प्रत्येक एट्रिब्यूट के लिए अलग-अलग `ExtendedAttributeDefinition` ऑब्जेक्ट बनाएं और उन्हें इच्छित संसाधनों या कार्यों से जोड़ें।

**Q:** मैं प्रोजेक्ट को किन फ़ॉर्मेट्स में सहेज सकता हूँ?  
**A:** Aspose.Tasks XML, MPP, PDF, HTML, और 30 से अधिक अतिरिक्त फ़ॉर्मेट्स को सपोर्ट करता है। इस उदाहरण में हमने `SaveFileFormat.Xml` का उपयोग किया।

**Q:** क्या विकास बिल्ड्स के लिए मुझे लाइसेंस चाहिए?  
**A:** परीक्षण के लिए एक अस्थायी मूल्यांकन लाइसेंस पर्याप्त है। किसी भी उत्पादन परिनियोजन के लिए पूर्ण व्यावसायिक लाइसेंस आवश्यक है।

**Q:** बाद में कस्टम एट्रिब्यूट मानों को कैसे पढ़ूँ?  
**A:** `resource.getExtendedAttributes()` को कॉल करें और संग्रह पर इटररेट करें; संग्रहीत मान को `getNumericValue()` या `getTextValue()` से प्राप्त करें।

---

**अंतिम अपडेट:** 2026-06-10  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [जावा के लिए Aspose.Tasks के साथ संसाधन बनाना – रिसोर्स मैनेजमेंट](/tasks/java/resource-management/)
- [कस्टम फ़ील्ड बनाएं – विस्तारित एट्रिब्यूट संभालें](/tasks/java/project-management/extended-attributes/)
- [प्रोजेक्ट बनाना – Aspose.Tasks के साथ नए कार्य एट्रिब्यूट सेट करें](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}