---
date: 2025-12-11
description: Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइलों से समूह
  परिभाषा डेटा पढ़ना सीखें। हमारे चरण‑दर‑चरण ट्यूटोरियल का पालन करें।
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में समूह परिभाषा डेटा पढ़ें
url: /hi/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में समूह परिभाषा डेटा पढ़ें

## परिचय
Aspose.Tasks for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft Project फ़ाइलों को आसानी से संभालने की सुविधा देती है। इस ट्यूटोरियल में, **आप चरण‑दर‑चरण सीखेंगे कि प्रोजेक्ट फ़ाइल से समूह परिभाषा डेटा कैसे पढ़ें**, ताकि आप अपने Java अनुप्रयोगों में टास्क समूह जानकारी निकाल सकें और उसका उपयोग कर सकें।

## त्वरित उत्तर
- **“समूह परिभाषा पढ़ना” का क्या अर्थ है?** यह Microsoft Project फ़ाइल से टास्क समूहों (नाम, मानदंड, फ़ॉर्मेटिंग) की परिभाषा निकालने को दर्शाता है।  
- **कौन सी लाइब्रेरी चाहिए?** Aspose.Tasks for Java।  
- **क्या लाइसेंस चाहिए?** विकास के लिए मुफ्त ट्रायल चलती है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन‑से IDE समर्थित हैं?** कोई भी Java IDE जैसे IntelliJ IDEA या Eclipse।  
- **कोड की मात्रा कितनी चाहिए?** प्रोजेक्ट लोड करने और समूह विवरण दिखाने के लिए 30 लाइनों से कम Java कोड।

## समूह परिभाषा पढ़ना क्या है?
Microsoft Project में *समूह परिभाषा* यह बताती है कि टास्क को किन मानदंडों (जैसे स्थिति, प्राथमिकता) के आधार पर समूहित किया गया है। इस परिभाषा को पढ़ने से आप प्रोग्रामेटिक रूप से समूहिंग लॉजिक, रंग, फ़ॉन्ट और सॉर्टिंग क्रम का निरीक्षण कर सकते हैं।

## समूह परिभाषा डेटा क्यों पढ़ें?
- **स्वचालन:** कस्टम रिपोर्ट बनाएं जो Project में दिखाए गए समूहों को प्रतिबिंबित करती हों।  
- **स्थांतरण:** समूह नियमों को दूसरे प्रोजेक्ट या किसी अलग प्रोजेक्ट‑मैनेजमेंट सिस्टम में ले जाएँ।  
- **वैधता:** बड़े अपडेट चलाने से पहले सुनिश्चित करें कि अपेक्षित समूह मौजूद हैं।  
- **अनुकूलन:** समूह के फ़ॉन्ट या रंग सेटिंग्स के आधार पर अतिरिक्त व्यावसायिक लॉजिक लागू करें।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – कोई भी नवीनतम संस्करण (8 या उससे नया)।  
2. **Aspose.Tasks for Java Library** – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE** – IntelliJ IDEA, Eclipse, या कोई भी पसंदीदा एडिटर।

## पैकेज आयात करें
सबसे पहले, कोर Aspose.Tasks पैकेज आयात करें:

```java
import com.aspose.tasks.*;
```

## चरण‑दर‑चरण गाइड

### चरण 1: अपना डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें वह `.mpp` फ़ाइल है जिसे आप जांचना चाहते हैं।

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को अपनी प्रोजेक्ट फ़ाइल के पूर्ण पथ से बदलें।

### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
`.mpp` फ़ाइल की ओर इशारा करके एक `Project` इंस्टेंस बनाएं।

```java
Project project = new Project(dataDir + "project.mpp");
```

### चरण 3: टास्क समूहों की कुल संख्या प्राप्त करें
प्रोजेक्ट में परिभाषित टास्क समूहों की कुल संख्या प्रिंट करें।

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### चरण 4: विशिष्ट टास्क समूह जानकारी प्राप्त करें
एक विशेष समूह (इस उदाहरण में इंडेक्स 1) को प्राप्त करें और उसका नाम तथा उसमें मौजूद मानदंडों की संख्या दिखाएँ।

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### चरण 5: समूह मानदंड जानकारी प्राप्त करें
प्रत्येक समूह में एक या अधिक मानदंड हो सकते हैं। नीचे दिया गया स्निपेट फ़ील्ड, समूह मोड, सेल रंग और पैटर्न जैसी विवरण निकालता है।

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### चरण 6: पैरेंट समूह जाँचें
कभी‑कभी कोई मानदंड पैरेंट समूह से जुड़ा होता है। यह जाँच संबंध की पुष्टि करती है।

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### चरण 7: मानदंड का फ़ॉन्ट जानकारी प्राप्त करें
समूह मानदंडों में कस्टम फ़ॉन्ट स्टाइलिंग हो सकती है। निम्नलिखित कोड फ़ॉन्ट फ़ैमिली, आकार, शैली और सॉर्टिंग दिशा को प्रिंट करता है।

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | मानदंड का पैरेंट समूह नहीं हो सकता। | तुलना करने से पहले null‑जाँच जोड़ें। |
| **फ़ाइल नहीं मिली** | `dataDir` पथ गलत है। | `Paths.get(dataDir, "project.mpp").toAbsolutePath()` से सत्यापित करें। |
| **लाइसेंस सेट नहीं है** | Aspose लाइब्रेरी मूल्यांकन मोड में चल रही है और आउटपुट सीमित कर सकती है। | `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` के साथ लाइसेंस रजिस्टर करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट फ़ाइलों को संशोधित कर सकता हूँ?**  
उत्तर: हाँ, लाइब्रेरी Microsoft Project फ़ाइलों के लिए पूर्ण पढ़ने/लिखने की क्षमताएँ प्रदान करती है।

**प्रश्न: क्या Aspose.Tasks for Java सभी संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
उत्तर: यह MPP, XML और अन्य सामान्य प्रोजेक्ट फ़ॉर्मेट्स को कई संस्करणों में समर्थन देता है।

**प्रश्न: Aspose.Tasks for Java के साथ काम करते समय त्रुटियों को कैसे संभालूँ?**  
उत्तर: फ़ाइल संचालन को `try‑catch` ब्लॉकों में रखें और विस्तृत संदेशों के लिए `TasksException` की जाँच करें।

**प्रश्न: क्या Aspose.Tasks for Java प्रोजेक्ट डेटा को अन्य फ़ॉर्मेट्स में निर्यात करने का समर्थन करता है?**  
उत्तर: बिल्कुल – आप लाइबोर्ट API का उपयोग करके PDF, XLSX, CSV आदि में निर्यात कर सकते हैं।

**प्रश्न: Aspose.Tasks for Java के अतिरिक्त संसाधन और समर्थन कहाँ मिल सकते हैं?**  
उत्तर: पूर्ण API रेफ़रेंस के लिए [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) देखें और समुदाय सहायता के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जाएँ।

## निष्कर्ष
इस ट्यूटोरियल में हमने Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइल से **समूह परिभाषा** डेटा पढ़ने की प्रक्रिया को चरण‑दर‑चरण समझा। ऊपर दिए गए चरणों का पालन करके आप समूह नाम, मानदंड, फ़ॉर्मेटिंग और पैरेंट‑ग्रुप संबंध निकाल सकते हैं, जिससे आप कस्टम रिपोर्ट बना सकें, सेटिंग्स को माइग्रेट कर सकें या अपने Java अनुप्रयोगों में वैधता लॉजिक को स्वचालित कर सकें।

---

**अंतिम अपडेट:** 2025-12-11  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}