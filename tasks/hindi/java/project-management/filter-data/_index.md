---
date: 2025-12-25
description: Aspose.Tasks for Java का उपयोग करके MPP फ़ाइलों को फ़िल्टर करना सीखें
  और फ़िल्टर मानदंड को अनुकूलित करके अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो को सुव्यवस्थित
  करें।
linktitle: How to Filter MPP Files Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java का उपयोग करके MPP फ़ाइलों को फ़िल्टर कैसे करें
url: /hi/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके MPP फ़ाइलों को फ़िल्टर करने का तरीका

## परिचय
यदि आप एक Java एप्लिकेशन में Microsoft Project फ़ाइलें (.mpp) के साथ काम कर रहे हैं, तो आपको अक्सर कार्यों, संसाधनों या असाइनमेंट को **फ़िल्टर** करने की आवश्यकता होगी ताकि आप वास्तव में महत्वपूर्ण डेटा पर ध्यान केंद्रित कर सकें। इस ट्यूटोरियल में हम **MPP फ़ाइलों को प्रोग्रामेटिकली फ़िल्टर करने** का तरीका Aspose.Tasks for Java के साथ दिखाएंगे, और यह बताएंगे कि **फ़िल्टर मानदंडों को कैसे कस्टमाइज़** किया जाए ताकि आपके प्रोजेक्ट‑विशिष्ट रिपोर्टिंग की जरूरतें पूरी हों। अंत तक, आपके पास एक स्पष्ट, चरण‑दर‑चरण उदाहरण होगा जिसे आप सीधे अपने कोडबेस में उपयोग कर सकते हैं।

## त्वरित उत्तर
- **“filter mpp” का क्या अर्थ है?** यह परिभाषित शर्तों के आधार पर प्रोजेक्ट डेटा के एक उपसमुच्चय को निकालने को दर्शाता है।  
- **कौन सी लाइब्रेरी इसे संभालती है?** Aspose.Tasks for Java फ़िल्टर बनाने और लागू करने के लिए एक समृद्ध API प्रदान करता है।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं कार्यों, संसाधनों और असाइनमेंट को फ़िल्टर कर सकता हूँ?** हाँ – प्रत्येक एंटिटी प्रकार की अपनी फ़िल्टर कलेक्शन होती है।  
- **क्या Java 8 या उससे ऊपर की आवश्यकता है?** Aspose.Tasks Java 8 और बाद के संस्करणों को सपोर्ट करता है।

## Java में “how to filter mpp” क्या है?
MPP फ़ाइल को फ़िल्टर करना मतलब Aspose.Tasks API का उपयोग करके मानदंड (जैसे कार्य प्रारंभ तिथि, लागत, या कस्टम फ़ील्ड) निर्धारित करना और फिर केवल उन आइटम्स को प्राप्त करना जो उन नियमों को पूरा करते हैं। यह आपको केंद्रित रिपोर्ट बनाने, स्थिति जांच को स्वचालित करने, या प्रोजेक्ट डेटा को अन्य सिस्टम्स के साथ एकीकृत करने में मदद करता है।

## फ़िल्टर मानदंडों को कस्टमाइज़ क्यों करें?
हर प्रोजेक्ट की अपनी प्राथमिकताएँ होती हैं। **फ़िल्टर मानदंडों को कस्टमाइज़** करके आप उच्च‑जोखिम वाले कार्य, देर से समाप्त होने वाले आइटम, या बजट से अधिक खर्च करने वाले संसाधनों को अलग कर सकते हैं, जिससे आपके प्रोजेक्ट डैशबोर्ड अधिक कार्रवाई‑योग्य बनते हैं और आपका कोड अधिक पुन: उपयोग योग्य होता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

1. **Java Development Kit (JDK)** – संस्करण 8 या नया।  
2. **Aspose.Tasks for Java** – इसे [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **एक IDE** – IntelliJ IDEA, Eclipse, या NetBeans ठीक काम करेंगे।  

## पैकेज आयात करें
अपने Java प्रोजेक्ट में आवश्यक क्लासेस को आयात करके शुरू करें:

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## चरण‑दर‑चरण गाइड

### चरण 1: प्रोजेक्ट सेट अप करें
सबसे पहले, एक `Project` इंस्टेंस बनाएँ जो उस MPP फ़ाइल की ओर इशारा करता हो जिसे आप उपयोग करना चाहते हैं।

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### चरण 2: फ़िल्टर प्राप्त करें
Aspose.Tasks पूर्वनिर्धारित फ़िल्टर (जैसे “All Tasks”, “Critical Tasks”) को संग्रहीत करता है। आवश्यक फ़िल्टर को इंडेक्स या नाम से प्राप्त करें।

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **प्रो टिप:** यदि आप नामित फ़िल्टर पसंद करते हैं तो `project.getTaskFilters().getByName("My Custom Filter")` का उपयोग करें।

### चरण 3: फ़िल्टर मानदंड तक पहुँचें
अब जब आपके पास `Filter` ऑब्जेक्ट है, आप उसकी मानदंड पंक्तियों और उन्हें जोड़ने वाले लॉजिकल ऑपरेशन (AND/OR) को देख सकते हैं।

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### चरण 4: मानदंड विवरण प्राप्त करें
प्रत्येक मानदंड पंक्ति में एक परीक्षण (जैसे “Equals”, “GreaterThan”) और वह फ़ील्ड शामिल होता है जिस पर यह लागू होता है (जैसे “Start”, “Cost”)।

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### चरण 5: मानदंड पंक्तियों पर इटररेट करें
जटिल फ़िल्टर में नेस्टेड मानदंड हो सकते हैं। यहाँ हम दूसरी‑स्तर की मानदंड समूह को देखते हैं।

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### चरण 6: मानदंड जानकारी प्रिंट करें
अंत में, प्रत्येक नेस्टेड मानदंड के विवरण को आउटपुट करें ताकि आप फ़िल्टर लॉजिक की पुष्टि कर सकें।

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **फ़िल्टर तक पहुँचते समय NullPointerException** | सुनिश्चित करें कि प्रोजेक्ट फ़ाइल वास्तव में टास्क फ़िल्टर रखती है; यदि आवश्यक हो तो आप प्रोग्रामेटिकली एक फ़िल्टर जोड़ सकते हैं। |
| **गलत फ़ील्ड नाम** | टाइपो से बचने के लिए `ItemType` एनेम (जैसे `ItemType.Task`) का उपयोग करें। |
| **फ़िल्टर कोई परिणाम नहीं देता** | परीक्षण ऑपरेटर और मानों को अपने MPP फ़ाइल के डेटा से मिलाएँ। |

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या Aspose.Tasks for Java विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?
A: हाँ, Aspose.Tasks for Java विभिन्न संस्करणों की Microsoft Project फ़ाइलों को सपोर्ट करता है, जिससे प्रोजेक्ट मैनेजमेंट कार्यों में संगतता और लचीलापन मिलता है।

### Q: क्या मैं प्रोजेक्ट की विशिष्ट आवश्यकताओं के आधार पर फ़िल्टर मानदंड को कस्टमाइज़ कर सकता हूँ?
A: बिल्कुल! Aspose.Tasks for Java आपको आपके प्रोजेक्ट की अनूठी जरूरतों के अनुसार फ़िल्टर मानदंड को टेलर करने की अनुमति देता है, जिससे लक्षित डेटा मैनिपुलेशन और विश्लेषण संभव होता है।

### Q: क्या Aspose.Tasks for Java छोटे और बड़े दोनों स्केल के प्रोजेक्ट्स के लिए उपयुक्त है?
A: हाँ, चाहे आप एक छोटे‑स्केल प्रोजेक्ट को मैनेज कर रहे हों या बड़े प्रोजेक्ट पोर्टफोलियो को संभाल रहे हों, Aspose.Tasks for Java विविध प्रोजेक्ट मैनेजमेंट परिदृश्यों के लिए आवश्यक स्केलेबिलिटी और परफ़ॉर्मेंस प्रदान करता है।

### Q: क्या Aspose.Tasks for Java व्यापक दस्तावेज़ीकरण और समर्थन संसाधन प्रदान करता है?
A: निश्चित रूप से! आप विस्तृत गाइड और API रेफ़रेंसेज़ के लिए [documentation](https://reference.aspose.com/tasks/java/) देख सकते हैं। अतिरिक्त रूप से, आप किसी भी प्रश्न या समस्या के लिए Aspose.Tasks कम्युनिटी फ़ोरम से सहायता ले सकते हैं।

### Q: क्या मैं खरीदारी से पहले Aspose.Tasks for Java की कार्यक्षमता का अन्वेषण कर सकता हूँ?
A: बिल्कुल! आप [website](https://releases.aspose.com/) से एक मुफ्त ट्रायल लेकर Aspose.Tasks for Java की विशेषताओं और क्षमताओं को स्वयं अनुभव कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**Q: प्रोग्रामेटिकली एक बिल्कुल नया फ़िल्टर कैसे बनाऊँ?**  
A: `project.getTaskFilters().add(new Filter("My Filter"))` का उपयोग करें और फिर उसकी `FilterCriteria` कलेक्शन को परिभाषित करें।

**Q: क्या मैं कार्यों के बजाय संसाधनों पर फ़िल्टर लागू कर सकता हूँ?**  
A: हाँ – संसाधन‑विशिष्ट फ़िल्टर के साथ काम करने के लिए `project.getResourceFilters()` का उपयोग करें।

**Q: क्या कई फ़िल्टर को OR लॉजिक के साथ संयोजित करना संभव है?**  
A: आप एक पैरेंट `FilterCriteria` बना सकते हैं जिसका `Operation` `OR` पर सेट हो और व्यक्तिगत मानदंडों को चाइल्ड के रूप में जोड़ सकते हैं।

**Q: क्या Aspose.Tasks कस्टम फ़ील्ड्स पर फ़िल्टरिंग को सपोर्ट करता है?**  
A: बिल्कुल। कस्टम फ़ील्ड्स को किसी अन्य फ़ील्ड की तरह ट्रीट किया जाता है; उन्हें उनके `CustomField` एनेम वैल्यू द्वारा रेफ़र करें।

**Q: बड़े MPP फ़ाइलों पर फ़िल्टरिंग का प्रदर्शन पर क्या प्रभाव पड़ता है?**  
A: फ़िल्टरिंग मेमोरी में की जाती है और सामान्यतः तेज़ होती है, लेकिन अत्यधिक बड़े प्रोजेक्ट्स के लिए आप `ProjectReader` का उपयोग करके केवल आवश्यक सेक्शन लोड करने पर विचार कर सकते हैं।

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}