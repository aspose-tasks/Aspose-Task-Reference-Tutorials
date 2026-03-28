---
date: 2026-01-28
description: Aspose.Tasks for Java का उपयोग करके विस्तारित टास्क एट्रिब्यूट्स को पढ़ना
  सीखें और कस्टम फ़ील्ड प्रकार को कुशलतापूर्वक बदलें।
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ विस्तारित कार्य गुण पढ़ें
url: /hi/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ विस्तारित टास्क एट्रिब्यूट पढ़ें

## परिचय
इस व्यापक ट्यूटोरियल में आप Microsoft Project फ़ाइलों से **विस्तारित टास्क एट्रिब्यूट** को Aspose.Tasks लाइब्रेरी for Java का उपयोग करके पढ़ना सीखेंगे। चाहे आप रिपोर्टिंग टूल बना रहे हों, डेटा सिंक्रनाइज़ कर रहे हों, या केवल कस्टम फ़ील्ड्स की गहरी जानकारी चाहिए, इस फीचर में महारत हासिल करने से आप प्रोजेक्ट में संग्रहीत हर जानकारी को निकाल सकेंगे। हम आवश्यक सेटअप दिखाएंगे, एट्रिब्यूट प्रोसेस करते समय कस्टम फ़ील्ड प्रकार कैसे स्विच करें बताएँगे, और सामान्य समस्याओं से बचने के व्यावहारिक टिप्स देंगे।

## त्वरित उत्तर
- **“विस्तारित टास्क एट्रिब्यूट पढ़ना” का क्या अर्थ है?** यह प्रोजेक्ट फ़ाइल में डिफ़ॉल्ट टास्क प्रॉपर्टीज़ से परे कस्टम फ़ील्ड मानों को निकालने को दर्शाता है।  
- **कौन सा क्लास इन एट्रिब्यूट्स तक पहुँच प्रदान करता है?** Aspose.Tasks में `ExtendedAttribute` क्लास।  
- **कोड चलाने के लिए लाइसेंस चाहिए?** विकास के लिए फ्री ट्रायल चल सकता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **क्या रनटाइम पर एट्रिब्यूट प्रकार बदल सकते हैं?** हाँ – `CustomFieldType` के आधार पर **कस्टम फ़ील्ड प्रकार स्विच** करने के लिए `switch` स्टेटमेंट का उपयोग करें।  
- **क्या यह Java 8 और उसके बाद के संस्करणों के साथ संगत है?** बिल्कुल, API JDK 8+ को सपोर्ट करता है।

## विस्तारित टास्क एट्रिब्यूट क्या हैं?
विस्तारित टास्क एट्रिब्यूट उपयोगकर्ता‑परिभाषित फ़ील्ड्स (टेक्स्ट, डेट, नंबर, फ़्लैग आदि) हैं जो Microsoft Project में मानक टास्क प्रॉपर्टीज़ को पूरक करते हैं। Aspose.Tasks प्रत्येक `Task` ऑब्जेक्ट से जुड़े `ExtendedAttribute` कलेक्शन के माध्यम से इन्हें प्रोग्रामेटिकली पढ़ने या संशोधित करने की सुविधा देता है।

## विस्तारित टास्क एट्रिब्यूट क्यों पढ़ें?
- **पूर्ण दृश्यता:** शेड्यूल में स्टेकहोल्डर्स द्वारा जोड़े गए कस्टम डेटा को समझें।  
- **ऑटोमेशन:** डैशबोर्ड भरें, कस्टम रिपोर्ट जनरेट करें, या डेटा को मैन्युअल एक्सपोर्ट के बिना अन्य सिस्टम में माइग्रेट करें।  
- **लचीलापन:** टेक्स्ट, डेट, ड्यूरेशन, कॉस्ट, फ़्लैग आदि किसी भी कस्टम फ़ील्ड प्रकार के साथ काम करें, प्रत्येक केस को उचित रूप से हैंडल करके।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- IntelliJ IDEA या Eclipse जैसे IDE।

## पैकेज इम्पोर्ट करें
Aspose.Tasks प्रोजेक्ट के लिए आवश्यक क्लासेज़ को इम्पोर्ट करके शुरू करें:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## चरण 1: टास्क और विस्तारित एट्रिब्यूट्स तक पहुँच
एक प्रोजेक्ट फ़ाइल लोड करें और प्रत्येक टास्क को इटररेट करके उसके विस्तारित एट्रिब्यूट्स तक पहुँचें:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## चरण 2: फ़ील्ड ID और वैल्यू GUID प्राप्त करना
आंतरिक पहचानकर्ताओं को प्रिंट करें जो आपको यह समझने में मदद करेंगे कि आप किस कस्टम फ़ील्ड के साथ काम कर रहे हैं:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## चरण 3: विस्तारित टास्क एट्रिब्यूट पढ़ते समय कस्टम फ़ील्ड प्रकार कैसे स्विच करें
`CustomFieldType` पर `switch` स्टेटमेंट का उपयोग करके प्रत्येक संभावित डेटा टाइप को सही ढंग से हैंडल करें:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

इन चरणों को अपने प्रोजेक्ट के प्रत्येक टास्क के लिए दोहराएँ ताकि आप सभी विस्तारित टास्क एट्रिब्यूट्स का अन्वेषण और हेरफेर कर सकें।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **नल वैल्यू रिटर्न हो रही है** | सुनिश्चित करें कि कस्टम फ़ील्ड स्रोत .mpp फ़ाइल में वास्तव में पॉप्युलेटेड है। |
| **गलत प्रकार दिख रहा है** | `switch` स्टेटमेंट में सही `CustomFieldType` का उपयोग करें; टाइप मिसमैच से डिफ़ॉल्ट वैल्यूज़ आ सकती हैं। |
| **बड़ी प्रोजेक्ट्स पर प्रदर्शन धीमा हो रहा है** | टास्क को बैच में प्रोसेस करें या `project.getRootTask().getChildren().stream()` के साथ उपयुक्त प्रेडिकेट्स लगाकर केवल आवश्यक टास्क फ़िल्टर करें। |

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं प्रोग्रामेटिकली विस्तारित टास्क एट्रिब्यूट्स को संशोधित कर सकता हूँ?
हां, आप Aspose.Tasks for Java का उपयोग करके विस्तारित टास्क एट्रिब्यूट्स को संशोधित कर सकते हैं। विस्तृत निर्देशों के लिए दस्तावेज़ देखें।

### क्या कोई ट्रायल संस्करण उपलब्ध है?
हां, आप मुफ्त ट्रायल **[यहाँ](https://releases.aspose.com/)** प्राप्त कर सकते हैं।

### Aspose.Tasks for Java के लिए सपोर्ट कहाँ मिल सकता है?
सपोर्ट के लिए, **[Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15)** पर जाएँ।

### अस्थायी लाइसेंस कैसे प्राप्त करें?
आप अस्थायी लाइसेंस **[यहाँ](https://purchase.aspose.com/temporary-license/)** से प्राप्त कर सकते हैं।

### Aspose.Tasks for Java का पूर्ण संस्करण कहाँ खरीदें?
आप पूर्ण संस्करण **[यहाँ](https://purchase.aspose.com/buy)** से खरीद सकते हैं।

---

**अंतिम अपडेट:** 2026-01-28  
**टेस्टेड विथ:** Aspose.Tasks Java API (नवीनतम स्थिर रिलीज)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}