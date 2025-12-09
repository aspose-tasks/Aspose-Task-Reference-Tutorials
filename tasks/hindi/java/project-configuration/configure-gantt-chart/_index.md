---
date: 2025-12-09
description: Aspose.Tasks में Java का उपयोग करके डेटा डायरेक्टरी कैसे सेट करें और
  गैंट चार्ट व्यू को कैसे कॉन्फ़िगर करें, यह सीखें। यह गाइड यह भी दिखाता है कि तालिका
  फ़ील्ड को कैसे कस्टमाइज़ करें और गैंट चार्ट Java प्रोजेक्ट्स को चरण‑दर‑चरण कैसे
  कॉन्फ़िगर करें।
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में गैंट चार्ट व्यू के लिए डेटा डायरेक्टरी सेट करें
url: /hi/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में Gantt Chart View के लिए डेटा डायरेक्टरी सेट करें

## परिचय
इस ट्यूटोरियल में आप **डेटा डायरेक्टरी कैसे सेट करें** और Aspose.Tasks प्रोजेक्ट्स में Java का उपयोग करके Gantt MS Project Chart View को कॉन्फ़िगर करना सीखेंगे। Aspose.Tasks एक मजबूत Java API है जो आपको Microsoft Project फ़ाइलों को प्रोग्रामेटिकली मैनीपुलेट करने की सुविधा देता है। इस गाइड के अंत तक आप **टेबल फ़ील्ड्स को कस्टमाइज़** करना, डेटा डायरेक्टरी को समायोजित करना, और अपने प्रोजेक्ट को बिल्कुल वही तरीके से विज़ुअलाइज़ करना जान पाएँगे जैसा आपको चाहिए।

## त्वरित उत्तर
- **पहला कदम क्या है?** वह डेटा डायरेक्टरी पाथ सेट करें जहाँ आपके प्रोजेक्ट फ़ाइलें स्थित हैं।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (आधिकारिक साइट से डाउनलोड योग्य)।  
- **क्या मैं कस्टम एट्रिब्यूट जोड़ सकता हूँ?** हाँ – आप एक्सटेंडेड एट्रिब्यूट्स परिभाषित कर सकते हैं और उन्हें Gantt चार्ट में दिखा सकते हैं।  
- **परीक्षण के लिए लाइसेंस चाहिए?** मूल्यांकन उद्देश्यों के लिए एक टेम्पररी लाइसेंस उपलब्ध है।  
- **कौन सा IDE सबसे अच्छा है?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, NetBeans) काम करेगा।

## “डेटा डायरेक्टरी सेट” क्या है और यह क्यों महत्वपूर्ण है?
डेटा डायरेक्टरी सेट करने से Aspose.Tasks को पता चलता है कि प्रोजेक्ट फ़ाइलें कहाँ पढ़नी और लिखनी हैं। सही पाथ के बिना API आपके `.mpp` फ़ाइलों को नहीं ढूँढ पाती, जिससे **FileNotFound** त्रुटियाँ आती हैं। कोड की शुरुआत में इस डायरेक्टरी को परिभाषित करने से बाकी वर्कफ़्लो साफ़ और दोहराने योग्य बन जाता है।

## Gantt चार्ट में टेबल फ़ील्ड्स को कस्टमाइज़ क्यों करें?
कस्टम टेबल फ़ील्ड्स आपको अतिरिक्त जानकारी—जैसे कस्टम एट्रिब्यूट्स, रिसोर्स डेटा, या प्रोजेक्ट‑स्पेसिफिक नोट्स—सीधे Gantt व्यू में दिखाने की अनुमति देते हैं। इससे चार्ट स्टेकहोल्डर्स के लिए अधिक सूचनात्मक बनता है और कई रिपोर्ट्स के बीच स्विच करने की आवश्यकता कम होती है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Java Development Kit (JDK)** – कोई भी हालिया संस्करण (8+)।  
2. **Aspose.Tasks लाइब्रेरी** – इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE** – IntelliJ IDEA, Eclipse, या कोई भी Java‑संगत एडिटर जो आप पसंद करते हैं।

## पैकेज इम्पोर्ट करें
सबसे पहले, Aspose.Tasks नेमस्पेस को इम्पोर्ट करें ताकि आप उसकी क्लासेज़ का उपयोग कर सकें:

```java
import com.aspose.tasks.*;
```

## चरण‑दर‑चरण गाइड

### चरण 1: डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपके प्रोजेक्ट फ़ाइलें हैं। यह वही **डेटा डायरेक्टरी सेट** करने का चरण है जिस पर ट्यूटोरियल केंद्रित है।

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को उस फ़ोल्डर के एब्सोल्यूट पाथ से बदलें जहाँ `project.mpp` संग्रहीत है।

### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
एक मौजूदा Microsoft Project फ़ाइल को लोड करके `Project` इंस्टेंस बनाएं।

```java
Project project = new Project(dataDir + "project.mpp");
```

### चरण 3: नया एक्टिविटी जोड़ें
प्रोजेक्ट की रूट में एक नया टास्क (एक्टिविटी) इन्सर्ट करें।

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### चरण 4: कस्टम एट्रिब्यूट परिभाषित करें
एक कस्टम एट्रिब्यूट डिफ़िनिशन बनाएं जिसे बाद में टास्क्स से जोड़ा जा सके।

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### चरण 5: टास्क में कस्टम एट्रिब्यूट जोड़ें
नव निर्मित एट्रिब्यूट को उस टास्क से असाइन करें जिसे आपने बनाया था।

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### चरण 6: टेबल को कस्टमाइज़ करें – **customize table fields**
कस्टम एट्रिब्यूट को Gantt चार्ट टेबल में एक कॉलम के रूप में जोड़ें, जिसमें चौड़ाई, शीर्षक, और अलाइनमेंट निर्दिष्ट हों।

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

### चरण 7: प्रोजेक्ट सेव करें
परिवर्तनों को एक नई फ़ाइल में सहेजें जिसे Microsoft Project में खोला जा सकता है।

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **FileNotFoundException** प्रोजेक्ट लोड करते समय | **डेटा डायरेक्टरी** पाथ गलत है या ट्रेलिंग स्लैश नहीं है। | सुनिश्चित करें `dataDir` ठीक फ़ोल्डर की ओर इशारा कर रहा है और उचित फ़ाइल सेपरेटर (`/` या `\\`) शामिल है। |
| कस्टम एट्रिब्यूट Gantt व्यू में नहीं दिख रहा | टेबल फ़ील्ड गलत इंडेक्स पर जोड़ा गया या कॉलम की चौड़ाई बहुत छोटी है। | सुनिश्चित करें `table.getTableFields().add(3, attrField);` वैध इंडेक्स उपयोग कर रहा है और `setWidth` को आवश्यकतानुसार समायोजित करें। |
| LicenseException सेव करते समय | प्रोडक्शन उपयोग के लिए वैध लाइसेंस लागू नहीं किया गया। | `project.save()` से पहले एक टेम्पररी या परमानेंट लाइसेंस लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं में उपयोग कर सकता हूँ?**  
उ: हाँ, Aspose.Tasks कई प्रोग्रामिंग भाषाओं के लिए उपलब्ध है, जिसमें .NET, Java, और C++ शामिल हैं।

**प्र: क्या Aspose.Tasks का फ्री ट्रायल उपलब्ध है?**  
उ: हाँ, आप इसे [यहाँ](https://releases.aspose.com/) से फ्री ट्रायल के रूप में डाउनलोड कर सकते हैं।

**प्र: Aspose.Tasks के लिए सपोर्ट कहाँ मिल सकता है?**  
उ: आप [Aspose.Tasks फोरम](https://forum.aspose.com/c/tasks/15) पर सपोर्ट प्राप्त कर सकते हैं और प्रश्न पूछ सकते हैं।

**प्र: Aspose.Tasks का लाइसेंस कैसे खरीदें?**  
उ: आप लाइसेंस को [यहाँ](https://purchase.aspose.com/buy) से खरीद सकते हैं।

**प्र: परीक्षण उद्देश्यों के लिए क्या टेम्पररी लाइसेंस चाहिए?**  
उ: हाँ, आप टेम्पररी लाइसेंस को [यहाँ](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

## निष्कर्ष
आपने अब **डेटा डायरेक्टरी सेट करना**, नया एक्टिविटी जोड़ना, कस्टम एट्रिब्यूट परिभाषित और असाइन करना, और Aspose.Tasks for Java का उपयोग करके Gantt चार्ट व्यू में **टेबल फ़ील्ड्स को कस्टमाइज़** करना सीख लिया है। ये चरण आपको प्रोजेक्ट डेटा के प्रदर्शन पर पूर्ण नियंत्रण देते हैं, जिससे आपके Gantt चार्ट अधिक सूचनात्मक और स्टेकहोल्डर्स की आवश्यकताओं के अनुरूप बनते हैं।

---

**अंतिम अपडेट:** 2025-12-09  
**परीक्षित संस्करण:** Aspose.Tasks Java 24.12 (नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}