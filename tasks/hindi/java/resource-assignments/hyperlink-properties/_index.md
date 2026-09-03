---
date: 2026-06-05
description: Aspose.Tasks for Java में रिसोर्स असाइनमेंट्स के लिए Hyperlink प्रॉपर्टीज़
  सेट करना सीखें, जिसमें बिल्कुल **how to set hyperlink** दिखाया गया है और सहयोग को
  बेहतर बनाएं।
keywords:
- how to set hyperlink
- validate hyperlink java
- Aspose.Tasks hyperlink
- resource assignment hyperlink
- Java project hyperlink
linktitle: Aspose.Tasks में रिसोर्स असाइनमेंट्स के लिए Hyperlink प्रॉपर्टीज़ प्रबंधित
  करें
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to set hyperlink properties for resource assignments in Aspose.Tasks
    for Java, showing exactly **how to set hyperlink** and improve collaboration.
  headline: How to Set Hyperlink Properties for Assignments in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, you can repeat the assignment process for each URL, setting different
      `HYPERLINK_ADDRESS` values on the same `Asn` object.
    question: Can I add multiple hyperlinks to a single resource assignment?
  - answer: Aspose.Tasks focuses on data management; visual styling is handled by
      the client application that renders the project file.
    question: Is it possible to customize the appearance of hyperlinks in Aspose.Tasks?
  - answer: The library does not impose strict length limits, but keeping URLs under
      2,000 characters maintains compatibility with most browsers and tools.
    question: Are there any limitations on the length of hyperlinks in Aspose.Tasks?
  - answer: Yes, assign `null` or an empty string to the `HYPERLINK`, `HYPERLINK_ADDRESS`,
      and `HYPERLINK_SUB_ADDRESS` fields to clear them.
    question: Can I remove hyperlinks from resource assignments programmatically?
  - answer: The library stores hyperlink data but does not validate URLs automatically;
      you should implement custom validation logic in Java.
    question: Does Aspose.Tasks support hyperlink validation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में असाइनमेंट के लिए Hyperlink प्रॉपर्टीज़ कैसे सेट करें
url: /hi/java/resource-assignments/hyperlink-properties/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में असाइनमेंट के लिए हाइपरलिंक प्रॉपर्टीज़ सेट करने का तरीका

## परिचय
इस गाइड में आप Aspose.Tasks for Java का उपयोग करके संसाधन असाइनमेंट पर **हाइपरलिंक सेट करने** की प्रॉपर्टीज़ को जानेंगे। ट्यूटोरियल के अंत तक आप क्लिक करने योग्य URL संलग्न कर सकेंगे, उन्हें सत्यापित कर सकेंगे, और प्रोग्रामेटिक रूप से क्वेरी कर सकेंगे—जिससे आपके प्रोजेक्ट फ़ाइलें एक संदर्भात्मक जानकारी के हब बन जाएँगी, जिस पर आपकी पूरी टीम भरोसा कर सकेगी।

## त्वरित उत्तर
- **“set hyperlink” क्या करता है?** यह एक क्लिक करने योग्य URL (और वैकल्पिक सब‑एड्रेस) को एक संसाधन असाइनमेंट से जोड़ता है, साधारण टेक्स्ट को सीधे नेविगेशन लिंक में बदल देता है।  
- **कौन सा क्लास हाइपरलिंक डेटा संग्रहीत करता है?** `Asn` क्लास `HYPERLINK`, `HYPERLINK_ADDRESS`, और `HYPERLINK_SUB_ADDRESS` फ़ील्ड प्रदान करता है।  
- **क्या इस फीचर को उपयोग करने के लिए लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है; परीक्षण के लिए एक मुफ्त ट्रायल काम करता है।  
- **क्या मैं Java में हाइपरलिंक को वैध कर सकता हूँ?** हाँ—असाइन करने से पहले `java.net.URL` या Apache Commons Validator का उपयोग करें।  
- **क्या यह तरीका किसी भी Java प्रोजेक्ट के साथ संगत है?** बिल्कुल; यह किसी भी Java प्रोजेक्ट के साथ काम करता है जिसमें Aspose.Tasks लाइब्रेरी शामिल है।

## Aspose.Tasks में “हाइपरलिंक सेट करने” क्या है?
**हाइपरलिंक सेट करना मतलब एक URL (और वैकल्पिक रूप से एक सब‑एड्रेस) को एक संसाधन असाइनमेंट पर असाइन करना है ताकि प्रोजेक्ट स्टेकहोल्डर सीधे असाइनमेंट व्यू से संबंधित वेब पेज, दस्तावेज़, या आंतरिक प्रोजेक्ट सेक्शन पर तुरंत नेविगेट कर सकें।** यह क्षमता संचार को सुव्यवस्थित करती है और बाहरी रेफ़रेंस स्प्रेडशीट की आवश्यकता को कम करती है।

## टास्क असाइनमेंट में हाइपरलिंक क्यों जोड़ें?
असाइनमेंट में हाइपरलिंक संलग्न करने से **टीम के सदस्य बिना प्रोजेक्ट फ़ाइल छोड़े स्पेसिफिकेशन, डिज़ाइन, या इश्यू‑ट्रैकर टिकट्स पर क्लिक करके जा सकते हैं**, जिससे सहयोग में सुधार होता है। यह जानकारी को केंद्रीकृत भी करता है—हर संबंधित URL प्रोजेक्ट के भीतर रहता है, जिससे एकल सत्य स्रोत और ऑडिट ट्रेल बनता है जिसे क्वेरी या रिपोर्टिंग के लिए एक्सपोर्ट किया जा सकता है। मात्रात्मक लाभ: Aspose.Tasks **10,000 तक टास्क और 5,000 तक रिसोर्स को संभाल सकता है जबकि हाइपरलिंक फ़ील्ड्स तक सब‑सेकंड एक्सेस बनाए रखता है**।

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग का मूल ज्ञान।  
- Java Development Kit (JDK) 8 या बाद का स्थापित हो।  
- Aspose.Tasks for Java लाइब्रेरी आपके प्रोजेक्ट के क्लासपाथ में जोड़ी गई हो।  
- कोड को संपादित और चलाने के लिए IntelliJ IDEA या Eclipse जैसे IDE का उपयोग।  
- (वैकल्पिक) प्रोडक्शन बिल्ड्स के लिए वैध Aspose.Tasks लाइसेंस फ़ाइल।

## पैकेज इम्पोर्ट करें
`Project`, `Task`, `Resource`, और `Asn` क्लासेस `com.aspose.tasks` नेमस्पेस में स्थित हैं। API के साथ काम शुरू करने से पहले इन्हें इम्पोर्ट करें।

`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में पूरे प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है।  
`Task` क्लास प्रोजेक्ट हाइरार्की के भीतर एकल कार्य आइटम को मॉडल करता है।  
`Resource` क्लास एक व्यक्ति, उपकरण, या सामग्री को परिभाषित करता है जिसे टास्क को असाइन किया जा सकता है।  
`Asn` क्लास `Task` और `Resource` के बीच लिंक को दर्शाता है और असाइनमेंट‑लेवल प्रॉपर्टीज़, जिसमें हाइपरलिंक फ़ील्ड्स शामिल हैं, को संग्रहीत करता है।

## चरण 1: प्रोजेक्ट इंस्टेंस बनाएं
एक नया प्रोजेक्ट फ़ाइल लोड करें या बनाएं। यह सभी बाद के ऑब्जेक्ट्स के लिए कंटेनर है।

## चरण 2: प्रोजेक्ट में टास्क जोड़ें
एक टास्क बनाएं जो बाद में अपने असाइनमेंट के माध्यम से हाइपरलिंक प्राप्त करेगा।

## चरण 3: रिसोर्स जोड़ें
एक रिसोर्स परिभाषित करें (जैसे, एक डेवलपर या उपकरण) जिसे आप टास्क को असाइन करेंगे।

## चरण 4: रिसोर्स असाइनमेंट बनाएं
टास्क और रिसोर्स को साथ लिंक करें, जिससे एक `Asn` ऑब्जेक्ट बनता है जो असाइनमेंट‑विशिष्ट डेटा रखता है।

## चरण 5: हाइपरलिंक प्रॉपर्टीज़ सेट करें
हाइपरलिंक एड्रेस और वैकल्पिक सब‑एड्रेस को `Asn` ऑब्जेक्ट में असाइन करें। आप `HYPERLINK` फ़ील्ड के माध्यम से डिस्प्ले टेक्स्ट भी सेट कर सकते हैं।

## चरण 6: हाइपरलिंक प्रॉपर्टीज़ प्रिंट करें
संग्रहीत हाइपरलिंक मानों को प्राप्त करें और प्रदर्शित करें ताकि यह पुष्टि हो सके कि असाइनमेंट सही ढंग से कॉन्फ़िगर किया गया है।

## चरण 7: प्रक्रिया पूर्णता
एक मित्रवत संदेश आउटपुट करें जो दर्शाता है कि हाइपरलिंक सेटअप बिना त्रुटियों के पूरा हो गया।

## मैं Java में हाइपरलिंक को कैसे वैध कर सकता हूँ?
**असाइन करने से पहले `java.net.URL` ऑब्जेक्ट बनाकर URL को वैध करें; यदि कंस्ट्रक्टर `MalformedURLException` फेंकता है, तो स्ट्रिंग एक वैध URL नहीं है।** यह सरल जांच रनटाइम त्रुटियों को रोकती है और सुनिश्चित करती है कि केवल पहुंच योग्य लिंक ही प्रोजेक्ट फ़ाइल में संग्रहीत हों।

## सामान्य समस्याएँ और समाधान
- **अमान्य URL फ़ॉर्मेट:** असाइन करने से पहले `java.net.URL` का उपयोग करके URL को वैध करें ताकि रनटाइम त्रुटियों से बचा जा सके।  
- **नल हाइपरलिंक मान:** यदि आपको आवश्यकता है तो सभी तीन प्रॉपर्टीज़ (`HYPERLINK`, `HYPERLINK_ADDRESS`, `HYPERLINK_SUB_ADDRESS`) सेट करें; अन्यथा, अनउपयोगी को `null` या खाली स्ट्रिंग सेट करें।  
- **लाइसेंस नहीं मिला:** यदि आपको लाइसेंसिंग त्रुटियां मिलती हैं, तो `Project` ऑब्जेक्ट बनाने से पहले Aspose.Tasks लाइसेंस फ़ाइल सही ढंग से लोड हुई है या नहीं, जांचें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही रिसोर्स असाइनमेंट में कई हाइपरलिंक जोड़ सकता हूँ?**  
A: हाँ, आप प्रत्येक URL के लिए असाइनमेंट प्रक्रिया दोहरा सकते हैं, एक ही `Asn` ऑब्जेक्ट पर विभिन्न `HYPERLINK_ADDRESS` मान सेट करके।

**Q: क्या Aspose.Tasks में हाइपरलिंक की उपस्थिति को कस्टमाइज़ करना संभव है?**  
A: Aspose.Tasks डेटा प्रबंधन पर केंद्रित है; हाइपरलिंक की दृश्य शैली को क्लाइंट एप्लिकेशन संभालता है जो प्रोजेक्ट फ़ाइल को रेंडर करता है।

**Q: क्या Aspose.Tasks में हाइपरलिंक की लंबाई पर कोई प्रतिबंध है?**  
A: लाइब्रेरी कड़े लंबाई प्रतिबंध नहीं लगाती, लेकिन URLs को 2,000 अक्षरों से कम रखने से अधिकांश ब्राउज़र और टूल्स के साथ संगतता बनी रहती है।

**Q: क्या मैं प्रोग्रामेटिक रूप से रिसोर्स असाइनमेंट से हाइपरलिंक हटा सकता हूँ?**  
A: हाँ, `HYPERLINK`, `HYPERLINK_ADDRESS`, और `HYPERLINK_SUB_ADDRESS` फ़ील्ड्स को `null` या खाली स्ट्रिंग असाइन करके उन्हें साफ़ कर सकते हैं।

**Q: क्या Aspose.Tasks हाइपरलिंक वैधता को सपोर्ट करता है?**  
A: लाइब्रेरी हाइपरलिंक डेटा संग्रहीत करती है लेकिन URLs को स्वचालित रूप से वैध नहीं करती; आपको Java में कस्टम वैधता लॉजिक लागू करना चाहिए।

**Q: यह बड़े Java प्रोजेक्ट हाइपरलिंक रणनीति में कैसे फिट बैठता है?**  
A: प्रोजेक्ट फ़ाइल के भीतर URLs को केंद्रीकृत करने से एक खोज योग्य “java प्रोजेक्ट हाइपरलिंक मैप” बनता है जिसे एक्सपोर्ट, ऑडिट या डॉक्यूमेंटेशन जेनरेटर के साथ इंटीग्रेट किया जा सकता है।

## निष्कर्ष
इन चरणों का पालन करके आप अब Aspose.Tasks for Java में रिसोर्स असाइनमेंट के लिए **हाइपरलिंक सेट करने** की प्रॉपर्टीज़, उन URLs को वैध करने, और यह प्रैक्टिस सहयोग और ट्रेसेबिलिटी को कैसे बढ़ाती है, जानते हैं। इस पैटर्न को अपने बड़े प्रोजेक्ट‑ऑटोमेशन पाइपलाइन में शामिल करें ताकि हर स्टेकहोल्डर को सही समय पर सही जानकारी से जोड़ा जा सके।

---

**अंतिम अपडेट:** 2026-06-05  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में रिसोर्स असाइनमेंट बनाएं](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks में रिसोर्स असाइनमेंट में नोट्स कैसे जोड़ें](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Aspose.Tasks का उपयोग करके Java में असाइनमेंट बजट प्रबंधित करें](/tasks/java/resource-assignments/assignment-budget/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

```java
Project prj = new Project();
```

```java
Task task = prj.getRootTask().getChildren().add("Task 1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

```java
Resource resource = prj.getResources().add("Resource 1");
```

```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

```java
assignment.set(Asn.HYPERLINK, "Click to visit our site");
assignment.set(Asn.HYPERLINK_ADDRESS, "https://products.aspose.com");
assignment.set(Asn.HYPERLINK_SUB_ADDRESS, "/total/net");
```

```java
System.out.println("Hyperlink: " + assignment.get(Asn.HYPERLINK));
System.out.println("Hyperlink Address: " + assignment.get(Asn.HYPERLINK_ADDRESS));
System.out.println("Hyperlink Sub Address: " + assignment.get(Asn.HYPERLINK_SUB_ADDRESS));
```

```java
System.out.println("Process completed Successfully");
```