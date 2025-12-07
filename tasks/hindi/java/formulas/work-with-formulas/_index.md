---
date: 2025-12-07
description: Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइलों को संभालते
  हुए **टेस्ट प्रोजेक्ट बनाना** और **कस्टम फ़ील्ड जोड़ना** सीखें।
language: hi
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ टेस्ट प्रोजेक्ट बनाएं और फ़ॉर्मूले उपयोग करें
url: /java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ टेस्ट प्रोजेक्ट बनाएं और फ़ॉर्मूले उपयोग करें

## परिचय
इस ट्यूटोरियल में आप **टेस्ट प्रोजेक्ट** फ़ाइलें बनाएँगे, एक कस्टम फ़ील्ड जोड़ेंगे, और Aspose.Tasks लाइब्रेरी for Java का उपयोग करके MS Project फ़ॉर्मूले के साथ काम करेंगे। Aspose.Tasks प्रोग्रामेटिक रूप से **Microsoft Project** डेटा को संभालना आसान बनाता है—चाहे आपको शेड्यूल बनाना हो, तिथियों की गणना करनी हो, या रिपोर्टिंग को स्वचालित करना हो। गाइड के अंत तक आपके पास एक चलाने योग्य उदाहरण होगा जो विस्तारित एट्रिब्यूट को परिभाषित करता है, एक टास्क की डेडलाइन सेट करता है, और प्रोजेक्ट को MPP फ़ाइल के रूप में सहेजता है।

## त्वरित उत्तर
- **ट्यूटोरियल क्या कवर करता है?** टेस्ट प्रोजेक्ट बनाना, कस्टम फ़ील्ड जोड़ना, विस्तारित एट्रिब्यूट परिभाषित करना, और फ़ॉर्मूला के साथ टास्क की डेडलाइन सेट करना।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (नवीनतम संस्करण)।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **मैं कौन सा IDE उपयोग कर सकता हूँ?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, VS Code) जो JDK 8+ को सपोर्ट करता है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** कोड कॉपी करने और चलाने में लगभग 10‑15 मिनट।

## Aspose.Tasks में “टेस्ट प्रोजेक्ट” क्या है?
एक **टेस्ट प्रोजेक्ट** एक हल्की Microsoft Project फ़ाइल है जिसे प्रोग्रामेटिक रूप से कार्यक्षमता दिखाने या सत्यापित करने के लिए बनाया जाता है। इसमें टास्क, रिसोर्सेज, और कस्टम फ़ील्ड का न्यूनतम सेट होता है जिसे आप वास्तविक प्रोजेक्ट डेटा को प्रभावित किए बिना हेर-फेर कर सकते हैं।

## Microsoft Project को हेर-फेर करने के लिए Aspose.Tasks क्यों उपयोग करें?
- **पूर्ण API कवरेज** – प्रत्येक Project, Task, और Resource प्रॉपर्टी तक पहुँच।  
- **Office इंस्टॉलेशन की आवश्यकता नहीं** – सर्वर, CI पाइपलाइन, और Docker कंटेनर पर काम करता है।  
- **क्रॉस‑प्लेटफ़ॉर्म** – वही Java कोड के साथ Windows, Linux, और macOS पर चलता है।  
- **मज़बूत फ़ॉर्मूला इंजन** – तिथियों, अवधि, और कस्टम फ़ील्ड को सीधे प्रोजेक्ट फ़ाइल में गणना करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Java Development Kit (JDK) 8+** – Oracle वेबसाइट से डाउनलोड करें या OpenJDK अपनाएँ।  
- **Aspose.Tasks for Java** – नवीनतम JAR [Aspose.Tasks for Java डाउनलोड पेज](https://releases.aspose.com/tasks/java/) से प्राप्त करें और इसे अपने प्रोजेक्ट की classpath या Maven/Gradle डिपेंडेंसीज़ में जोड़ें।

## पैकेज इम्पोर्ट करें
पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी हमें आवश्यकता होगी:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## चरण‑दर‑चरण गाइड

### चरण 1: कस्टम फ़ील्ड के साथ टेस्ट प्रोजेक्ट बनाएं
हम **टेस्ट प्रोजेक्ट बनाकर** शुरू करते हैं और एक कस्टम फ़ील्ड जोड़ते हैं जो बाद में हमारे फ़ॉर्मूला परिणाम को रखेगा।

```java
Project project = CreateTestProjectWithCustomField();
```

*प्रो टिप:* `CreateTestProjectWithCustomField()` एक हेल्पर मेथड है जो न्यूनतम शेड्यूल बनाता है और फ़ॉर्मूला असाइनमेंट के लिए तैयार एक विस्तारित एट्रिब्यूट रजिस्टर करता है।

### चरण 2: विस्तारित एट्रिब्यूट परिभाषित करें (कस्टम फ़ील्ड जोड़ें)
अगला, हम **विस्तारित एट्रिब्यूट परिभाषित** करते हैं – मूलतः कस्टम फ़ील्ड – और इसे एक उपयोगकर्ता‑मित्र एलियास देते हैं। यही वह जगह है जहाँ हम **कस्टम फ़ील्ड** लॉजिक जोड़ते हैं।

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **एलियास** फ़ील्ड को Project में पढ़ने योग्य बनाता है।  
- **फ़ॉर्मूला** टास्क की *Finish* तिथि और उसके *Deadline* के बीच दिनों की संख्या गणना करता है।

### चरण 3: टास्क के लिए डेडलाइन सेट करें (डेडलाइन टास्क जोड़ें और टास्क डेडलाइन सेट करें)
अब हम एक विशिष्ट टास्क पर *Deadline* प्रॉपर्टी सेट करके **डेडलाइन टास्क** डेटा जोड़ते हैं।

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` इंस्टेंस सटीक डेडलाइन समय को परिभाषित करता है।  
- `set(Tsk.DEADLINE, …)` चुने हुए टास्क के लिए **टास्क डेडलाइन सेट** करता है।

### चरण 4: प्रोजेक्ट सहेजें (Microsoft Project फ़ाइल को हेर-फेर करें)
अंत में, हम परिवर्तन को MPP फ़ाइल में सहेजकर **Microsoft Project** को हेर-फेर करते हैं।

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

आप `SaveFile.mpp` को Microsoft Project में खोल सकते हैं ताकि कस्टम फ़ील्ड, फ़ॉर्मूला परिणाम, और डेडलाइन को शेड्यूल में प्रतिबिंबित देख सकें।

## सामान्य समस्याएँ और समाधान
| Issue | Solution |
|-------|----------|
| **फ़ॉर्मूला मूल्यांकन नहीं हो रहा** | सुनिश्चित करें कि एट्रिब्यूट की `Formula` स्ट्रिंग सही फ़ील्ड नामों (जैसे, `[Deadline]`, `[Finish]`) का उपयोग करती है। |
| **टास्क नहीं मिला** | जाँचें कि टास्क ID (`1` उदाहरण में) मौजूद है; डिबग करने के लिए `project.getRootTask().getChildren().size()` का उपयोग करें। |
| **लाइसेंस अपवाद** | किसी भी API मेथड को कॉल करने से पहले एक वैध Aspose.Tasks लाइसेंस लागू करें (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?  
**उत्तर:** हाँ, Aspose.Tasks .NET, Java, और अन्य प्लेटफ़ॉर्म के लिए APIs प्रदान करता है, जिससे आप **Microsoft Project** फ़ाइलों को अपनी पसंद की भाषा में हेर-फेर कर सकते हैं।

**प्रश्न:** क्या Aspose.Tasks के लिए फ्री ट्रायल उपलब्ध है?  
**उत्तर:** बिल्कुल। आप पूरी तरह कार्यात्मक ट्रायल [Aspose.Tasks डाउनलोड पेज](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**प्रश्न:** मैं Aspose.Tasks की विस्तृत दस्तावेज़ीकरण कहाँ पा सकता हूँ?  
**उत्तर:** आधिकारिक दस्तावेज़ [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) पर होस्ट किए गए हैं।

**प्रश्न:** मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूँ?  
**उत्तर:** समुदाय से प्रश्न पूछने और अनुभव साझा करने के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जाएँ।

**प्रश्न:** क्या मूल्यांकन के लिए एक अस्थायी लाइसेंस चाहिए?  
**उत्तर:** अस्थायी लाइसेंस अल्पकालिक परीक्षण के लिए उपलब्ध है; आप इसे [यहाँ](https://purchase.aspose.com/temporary-license/) से अनुरोध कर सकते हैं।

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}