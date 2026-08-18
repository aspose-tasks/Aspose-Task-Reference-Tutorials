---
date: 2026-02-18
description: जानेँ कि Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइलों
  से समूह परिभाषा डेटा कैसे पढ़ें। यह ट्यूटोरियल दिखाता है कि समूह विवरण कैसे पढ़ें
  और कार्य समूहबद्ध जानकारी कैसे निकालें।
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में समूह परिभाषा डेटा कैसे पढ़ें
url: /hi/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में ग्रुप परिभाषा डेटा पढ़ें

## परिचय
Aspose.Tasks for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft Project फ़ाइलों को आसानी से हेरफेर करने की सुविधा देती है। इस ट्यूटोरियल में, **आप सीखेंगे कि ग्रुप परिभाषा कैसे पढ़ें** डेटा को चरण‑दर‑चरण पढ़ना, ताकि आप अपने Java अनुप्रयोगों में टास्क ग्रुप जानकारी निकाल सकें और उस पर काम कर सकें। **ग्रुप कैसे पढ़ें** विवरण को समझना आपको रिपोर्टिंग को स्वचालित करने, सेटिंग्स को माइग्रेट करने और प्रोजेक्ट संरचनाओं को प्रोग्रामेटिक रूप से वैध करने में सक्षम बनाता है।

## त्वरित उत्तर
- **“ग्रुप परिभाषा पढ़ना” का क्या अर्थ है?** यह Microsoft Project फ़ाइल से टास्क ग्रुप की परिभाषा (नाम, मानदंड, फ़ॉर्मेटिंग) निकालने को दर्शाता है।  
- **मुझे कौन सी लाइब्रेरी चाहिए?** Aspose.Tasks for Java।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से IDE समर्थित हैं?** कोई भी Java IDE जैसे IntelliJ IDEA या Eclipse।  
- **कितना कोड चाहिए?** प्रोजेक्ट लोड करने और ग्रुप विवरण दिखाने के लिए 30 लाइनों से कम Java कोड।

## ग्रुप परिभाषा डेटा कैसे पढ़ें
नीचे एक संक्षिप्त, चरण‑दर‑चरण मार्गदर्शिका है जो **ग्रुप कैसे पढ़ें** जानकारी को `.mpp` फ़ाइल से दिखाती है। प्रत्येक चरण में एक छोटा स्पष्टीकरण और चलाने के लिए सटीक कोड दिया गया है।

## ग्रुप परिभाषा क्या है?
Microsoft Project में *ग्रुप परिभाषा* यह बताती है कि टास्क को किन मानदंडों (जैसे, स्थिति, प्राथमिकता) के आधार पर समूहित किया गया है। इस परिभाषा को पढ़ने से आप प्रोग्रामेटिक रूप से ग्रुपिंग लॉजिक, रंग, फ़ॉन्ट और सॉर्टिंग क्रम का निरीक्षण कर सकते हैं जो प्रोजेक्ट फ़ाइल में लागू है।

## ग्रुप परिभाषा डेटा क्यों पढ़ें?
- **स्वचालन:** कस्टम रिपोर्ट बनाएं जो Project में दिखाए गए ग्रुपिंग को प्रतिबिंबित करती हों।  
- **माइग्रेशन:** ग्रुपिंग नियमों को दूसरे प्रोजेक्ट या किसी अलग प्रोजेक्ट‑मैनेजमेंट सिस्टम में ले जाएँ।  
- **वैधता:** बड़े अपडेट चलाने से पहले सुनिश्चित करें कि अपेक्षित ग्रुप मौजूद हैं।  
- **अनुकूलन:** ग्रुप के फ़ॉन्ट या रंग सेटिंग्स के आधार पर अतिरिक्त व्यावसायिक लॉजिक लागू करें।  
- **अंतर्दृष्टि:** **ग्रुप कैसे पढ़ें** डेटा जानने से आप अप्रत्याशित टास्क लेआउट को ट्रबलशूट कर सकते हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – कोई भी नवीनतम संस्करण (8 या उससे नया)।  
2. **Aspose.Tasks for Java Library** – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE** – IntelliJ IDEA, Eclipse, या आपका पसंदीदा कोई भी एडिटर।  

## पैकेज आयात करें
सबसे पहले, कोर Aspose.Tasks पैकेज आयात करें:

```java
import com.aspose.tasks.*;
```

## चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: अपना डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें वह `.mpp` फ़ाइल है जिसे आप निरीक्षण करना चाहते हैं।

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को अपने प्रोजेक्ट फ़ाइल स्थान के पूर्ण पथ से बदलें।

### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
अपने `.mpp` फ़ाइल की ओर इशारा करके एक `Project` इंस्टेंस बनाएं।

```java
Project project = new Project(dataDir + "project.mpp");
```

### चरण 3: टास्क ग्रुप्स की संख्या प्राप्त करें
प्रोजेक्ट में परिभाषित कुल टास्क ग्रुप्स की संख्या प्रिंट करें।

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### चरण 4: विशिष्ट टास्क ग्रुप जानकारी प्राप्त करें
एक विशेष ग्रुप (इस उदाहरण में इंडेक्स 1) को प्राप्त करें और उसका नाम तथा उसमें मौजूद मानदंडों की संख्या दिखाएँ।

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### चरण 5: ग्रुप मानदंड जानकारी प्राप्त करें
प्रत्येक ग्रुप में एक या अधिक मानदंड हो सकते हैं। नीचे दिया गया स्निपेट फ़ील्ड, ग्रुपिंग मोड, सेल रंग और पैटर्न जैसी जानकारी निकालता है।

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### चरण 6: पैरेंट ग्रुप जांचें
कभी‑कभी एक मानदंड पैरेंट ग्रुप से जुड़ा होता है। यह जांच संबंध की पुष्टि करती है।

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### चरण 7: मानदंड का फ़ॉन्ट जानकारी प्राप्त करें
ग्रुप मानदंडों में कस्टम फ़ॉन्ट स्टाइलिंग हो सकती है। निम्न कोड फ़ॉन्ट फ़ैमिली, आकार, शैली और सॉर्टिंग दिशा को प्रिंट करता है।

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | मानदंड का पैरेंट ग्रुप नहीं हो सकता। | तुलना करने से पहले null‑check जोड़ें। |
| **File not found** | `dataDir` पथ गलत है। | `Paths.get(dataDir, "project.mpp").toAbsolutePath()` का उपयोग करके सत्यापित करें। |
| **License not set** | Aspose लाइब्रेरी मूल्यांकन मोड में चल रही है और आउटपुट सीमित कर सकती है। | `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` के साथ लाइसेंस रजिस्टर करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट फ़ाइलों को संशोधित कर सकता हूँ?  
**उत्तर:** हाँ, लाइब्रेरी Microsoft Project फ़ाइलों के लिए पूर्ण पढ़ने/लिखने की क्षमताएँ प्रदान करती है।

**प्रश्न:** क्या Aspose.Tasks for Java सभी संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?  
**उत्तर:** यह कई संस्करणों में MPP, XML और अन्य सामान्य प्रोजेक्ट फ़ॉर्मेट्स को समर्थन देता है।

**प्रश्न:** Aspose.Tasks for Java के साथ काम करते समय त्रुटियों को कैसे संभालूँ?  
**उत्तर:** फ़ाइल संचालन को `try‑catch` ब्लॉकों में रखें और विस्तृत संदेशों के लिए `TasksException` की जाँच करें।

**प्रश्न:** क्या Aspose.Tasks for Java प्रोजेक्ट डेटा को अन्य फ़ॉर्मेट्स में निर्यात करने का समर्थन करता है?  
**उत्तर:** बिल्कुल – आप लाइब्रेरी के एक्सपोर्ट API का उपयोग करके PDF, XLSX, CSV और अधिक में निर्यात कर सकते हैं।

**प्रश्न:** Aspose.Tasks for Java के लिए अतिरिक्त संसाधन और समर्थन कहाँ मिल सकता है?  
**उत्तर:** पूर्ण API रेफ़रेंस के लिए [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) देखें और समुदाय सहायता के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

## निष्कर्ष
इस ट्यूटोरियल में हमने Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइल से **ग्रुप कैसे पढ़ें** परिभाषा डेटा को चरण‑दर‑चरण निकाला। ऊपर दिए गए चरणों का पालन करके आप ग्रुप नाम, मानदंड, फ़ॉर्मेटिंग और पैरेंट‑ग्रुप संबंध निकाल सकते हैं, जिससे आप कस्टम रिपोर्ट बना सकते हैं, सेटिंग्स माइग्रेट कर सकते हैं या अपने Java अनुप्रयोगों में वैधता लॉजिक को स्वचालित कर सकते हैं।

---

**अंतिम अपडेट:** 2026-02-18  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}