---
date: 2026-06-05
description: Aspose.Tasks for Java का उपयोग करके MPP फ़ाइलों को फ़िल्टर करना सीखें,
  फ़िल्टर मानदंड को अनुकूलित करें, और परियोजना प्रबंधन को सुगम बनाने के लिए तिथि के
  आधार पर कार्यों को फ़िल्टर करें।
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Aspose.Tasks for Java का उपयोग करके MPP फ़ाइलों को फ़िल्टर कैसे करें
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java का उपयोग करके MPP फ़ाइलों को फ़िल्टर कैसे करें
url: /hi/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके MPP फ़ाइलों को फ़िल्टर कैसे करें

## परिचय
यदि आप Java एप्लिकेशन में Microsoft Project फ़ाइलों (*.mpp*) के साथ काम कर रहे हैं, तो आपको अक्सर **MPP फ़ाइलों को फ़िल्टर** करने की आवश्यकता होगी ताकि आप सबसे महत्वपूर्ण कार्य, संसाधन या असाइनमेंट को अलग कर सकें। इस ट्यूटोरियल में हम Aspose.Tasks for Java के साथ प्रोग्रामेटिक रूप से **MPP फ़ाइलों को फ़िल्टर करने** की प्रक्रिया दिखाएंगे, आपको **फ़िल्टर मानदंड को अनुकूलित** करने का तरीका बताएंगे, और एक व्यावहारिक “तारीख के अनुसार कार्य फ़िल्टर” परिदृश्य प्रदर्शित करेंगे। अंत तक आपके पास एक तैयार‑से‑उपयोग स्निपेट होगा जिसे आप किसी भी Java प्रोजेक्ट में जोड़ सकते हैं।

## त्वरित उत्तर
- **“filter mpp” का क्या अर्थ है?** इसका मतलब है परिभाषित शर्तों के आधार पर प्रोजेक्ट डेटा का एक उपसमुच्चय निकालना।  
- **कौन सी लाइब्रेरी इसे संभालती है?** Aspose.Tasks for Java फ़िल्टर बनाने और लागू करने के लिए एक व्यापक API प्रदान करती है।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं कार्य, संसाधन और असाइनमेंट को फ़िल्टर कर सकता हूँ?** हाँ – प्रत्येक इकाई प्रकार का अपना फ़िल्टर संग्रह होता है।  
- **क्या Java 8 या उससे ऊपर की आवश्यकता है?** Aspose.Tasks Java 8 और बाद के संस्करणों को समर्थन देता है।

## Java में “how to filter mpp” क्या है?
`How to filter mpp` Aspose.Tasks के `Filter` ऑब्जेक्ट्स का उपयोग करके उन प्रोजेक्ट तत्वों को चुनने की प्रक्रिया है जो प्रारंभ तिथि, लागत या कस्टम फ़ील्ड जैसे विशिष्ट शर्तों को पूरा करते हैं। एक `Project` लोड करें, एक `Filter` प्राप्त करें, और API आपके मानदंडों से मेल खाने वाला संग्रह लौटाता है, जिससे केंद्रित रिपोर्टिंग या डाउनस्ट्रीम इंटीग्रेशन संभव होता है।

## फ़िल्टर मानदंड को अनुकूलित क्यों करें?
कस्टम फ़िल्टर मानदंड आपको उच्च‑जोखिम वाले कार्य, अतिदेय आइटम या बजट‑ओवररन संसाधनों को लक्षित करने की अनुमति देते हैं, जिससे एक बड़े प्रोजेक्ट फ़ाइल को एक संक्षिप्त, क्रियाशील दृश्य में बदला जा सकता है। Aspose.Tasks **50+ पूर्वनिर्धारित फ़िल्टर प्रकार** का समर्थन करता है और आपको असीमित कस्टम फ़िल्टर बनाने देता है, जिससे मैन्युअल डेटा‑छंटाई का समय 70 % तक घटाया जा सकता है।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – संस्करण 8 या नया।  
2. **Aspose.Tasks for Java** – इसे [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **एक IDE** – IntelliJ IDEA, Eclipse, या NetBeans ठीक काम करेंगे।  

## पैकेज आयात करें
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType`, और `Project` कोर क्लासेज़ हैं जो प्रोजेक्ट डेटा पर फ़िल्टर को परिभाषित और लागू करने के लिए उपयोग होते हैं।

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: प्रोजेक्ट सेट अप करें
सबसे पहले, एक `Project` इंस्टेंस बनाएं जो उस MPP फ़ाइल की ओर संकेत करता हो जिसे आप विश्लेषण करना चाहते हैं, फिर इसे मेमोरी में लोड करें। यह एकल चरण पूरे प्रोजेक्ट मॉडल को फ़िल्टरिंग, वैधता, और आगे की हेरफेर के लिए तैयार करता है, जिससे आप API के माध्यम से कार्य, संसाधन, और असाइनमेंट तक पहुंच सकते हैं।

### मैं MPP फ़ाइलों को फ़िल्टर करने के लिए प्रोजेक्ट कैसे सेट अप करूँ?
`Project` क्लास मेमोरी में एक MPP फ़ाइल को लोड करती है और उसका प्रतिनिधित्व करती है। एक `Project` इंस्टेंस बनाएं जो उस MPP फ़ाइल की ओर संकेत करता हो जिसे आप विश्लेषण करना चाहते हैं, फिर इसे मेमोरी में लोड करें। यह एकल चरण पूरे प्रोजेक्ट मॉडल को फ़िल्टरिंग, वैधता, और आगे की हेरफेर के लिए तैयार करता है, जिससे आप API के माध्यम से कार्य, संसाधन, और असाइनमेंट तक पहुंच सकते हैं।

### मैं फ़िल्टर को कैसे प्राप्त करूँ और निरीक्षण करूँ?
`Filter` ऑब्जेक्ट्स प्रोजेक्ट आइटम्स को चुनने के लिए उपयोग किए जाने वाले फ़िल्टर परिभाषाओं को संलग्न करते हैं। Aspose.Tasks “All Tasks” या “Critical Tasks” जैसे पूर्वनिर्धारित फ़िल्टर संग्रहीत करता है। `project.getTaskFilters().getByName("My Filter")` या इंडेक्स‑आधारित एक्सेस का उपयोग करके एक `Filter` ऑब्जेक्ट प्राप्त करें, फिर उसके `FilterCriteria` संग्रह की जाँच करें ताकि प्रत्येक नियम और उन्हें संयोजित करने वाला लॉजिकल ऑपरेटर (AND/OR) देखा जा सके, यह सुनिश्चित करते हुए कि फ़िल्टर आपकी आवश्यकताओं से मेल खाता है।

### नेस्टेड मानदंड पंक्तियों के माध्यम से कैसे इटररेट करें?
`FilterCriteriaGroup` एक समूह का प्रतिनिधित्व करता है जिसमें फ़िल्टर मानदंड लॉजिकल ऑपरेटर के साथ संयोजित होते हैं। फ़िल्टर में मानदंड समूह हो सकते हैं, प्रत्येक का अपना ऑपरेटर होता है। `filter.getCriteria().getRows()` पर लूप करें और किसी भी पंक्ति के लिए जो `FilterCriteriaGroup` है, उसके चाइल्ड पंक्तियों में पुनरावृत्ति करें। यह ट्रैवर्सल आपको जटिल फ़िल्टर लॉजिक जैसे “(Start < today AND Cost > 1000) OR Priority = High” को पूरी तरह समझने और आवश्यकतानुसार मानदंड समायोजित करने में मदद करता है।

### डिबगिंग के लिए मानदंड जानकारी कैसे प्रिंट करें?
मानदंड ट्री को ट्रैवर्स करने के बाद, प्रत्येक पंक्ति के फ़ील्ड नाम, टेस्ट ऑपरेटर, और मान को कंसोल में आउटपुट करें। यह सरल डम्प आपको यह सत्यापित करने में मदद करता है कि फ़िल्टर बड़े प्रोजेक्ट्स पर लागू करने से पहले इच्छित व्यावसायिक नियमों से मेल खाता है, और गलत ऑपरेटर या मानों को पहचानना आसान बनाता है।

### प्रोग्रामेटिक रूप से एक नया फ़िल्टर कैसे बनाएँ?
`new Filter("My Filter")` के साथ एक `Filter` इंस्टैंसिएट करें, फिर `project.getTaskFilters().add(filter)` का उपयोग करके इसे प्रोजेक्ट के टास्क फ़िल्टर संग्रह में जोड़ें। उसके बाद, इच्छित पंक्तियों के साथ उसके `FilterCriteria` संग्रह को भरें, फ़ील्ड नाम, टेस्ट ऑपरेटर, और मान निर्दिष्ट करके यह परिभाषित करें कि फ़िल्टर लागू होने पर किन कार्यों को शामिल किया जाना चाहिए।

### क्या मैं कार्यों के बजाय संसाधनों पर फ़िल्टर लागू कर सकता हूँ?
`ResourceFilters` संग्रह संसाधनों पर लागू होने वाले फ़िल्टर परिभाषाओं को रखता है। हाँ – `project.getResourceFilters()` का उपयोग करके आप टास्क फ़िल्टर की तरह ही रिसोर्स‑स्पेसिफिक फ़िल्टर के साथ काम कर सकते हैं। फ़िल्टर जोड़ने या प्राप्त करने के बाद, उसके `FilterCriteria` को टास्क की तरह ही कॉन्फ़िगर करें, फिर इसे रिसोर्स कलेक्शन पर लागू करें ताकि फ़िल्टर किया गया रिसोर्स सेट प्राप्त हो सके।

### क्या कई फ़िल्टरों को OR लॉजिक के साथ संयोजित करना संभव है?
एक पैरेंट `FilterCriteriaGroup` बनाएं और उसका `Operation` `OR` पर सेट करें, फिर व्यक्तिगत `FilterCriteria` ऑब्जेक्ट्स को चाइल्ड के रूप में जोड़ें। यह समूह प्रत्येक चाइल्ड मानदंड का मूल्यांकन करेगा और उन आइटम्स को लौटाएगा जो किसी भी एक को संतुष्ट करते हैं, जिससे आप कई सरल फ़िल्टरों को एक व्यापक चयन में संयोजित कर सकते हैं।

### क्या Aspose.Tasks कस्टम फ़ील्ड्स पर फ़िल्टरिंग का समर्थन करता है?
`CustomField` एनीम प्रोजेक्ट में परिभाषित कस्टम फ़ील्ड्स के पहचानकर्ता प्रदान करता है। बिल्कुल। `CustomField` एनीम के माध्यम से कस्टम फ़ील्ड्स को संदर्भित करें, और वे फ़िल्टर अभिव्यक्तियों में किसी भी बिल्ट‑इन फ़ील्ड की तरह व्यवहार करेंगे। आप उन्हें `FilterCriteria` पंक्तियों में शामिल कर सकते हैं, समान ऑपरेटर और मानों का उपयोग करके, जिससे उपयोगकर्ता‑परिभाषित डेटा के साथ मानक प्रोजेक्ट एट्रिब्यूट्स पर शक्तिशाली क्वेरी संभव हो जाती है।

### बड़े MPP फ़ाइलों पर फ़िल्टरिंग का प्रदर्शन प्रभाव क्या है?
फ़िल्टरिंग पूरी तरह मेमोरी में चलती है और आमतौर पर 1,000‑टास्क प्रोजेक्ट को 200 ms से कम समय में प्रोसेस करती है। कई‑हजार‑टास्क फ़ाइलों के लिए, `ProjectReader` का उपयोग करके केवल आवश्यक सेक्शन लोड करने पर विचार करें और चयनात्मक लोडिंग के बाद फ़िल्टर लागू करें, जिससे मेमोरी उपयोग कम रहता है और बहुत बड़े प्रोजेक्ट्स पर भी तेज़ प्रतिक्रिया समय बना रहता है।

---

**अंतिम अपडेट:** 2026-06-05  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.10  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [MPP फ़ाइल लोड करें Java - Aspose.Tasks के साथ प्रोजेक्ट प्रॉपर्टीज़ प्रबंधित करें](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - सहज MS Project ऑनलाइन डेटा पढ़ना](/tasks/java/project-data-reading/read-project-online/)
- [Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट प्रारंभ तिथि सेट करें](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```