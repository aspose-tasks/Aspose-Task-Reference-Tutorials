---
date: 2026-01-23
description: Aspose.Tasks for Java का उपयोग करके बेसलाइन अवधि सेट करना और प्रोजेक्ट
  इंस्टेंस बनाना सीखें। यह चरण‑दर‑चरण मार्गदर्शिका आपको टास्क बेसलाइन को प्रभावी ढंग
  से प्रबंधित करने में मदद करती है।
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java में बेसलाइन अवधि कैसे सेट करें
url: /hi/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java में बेसलाइन अवधि कैसे सेट करें

## परिचय
बेसलाइन सेट करना मूल योजना के खिलाफ प्रोजेक्ट प्रगति को ट्रैक करने का एक मूलभूत कदम है। इस ट्यूटोरियल में आप Microsoft Project में Aspose.Tasks लाइब्रेरी for Java का उपयोग करके कार्यों की **बेसलाइन कैसे सेट करें** अवधि सीखेंगे, और देखेंगे कि प्रारंभ में बेसलाइन स्थापित करने से बाद में समय और झंझट बच सकते हैं।

## त्वरित उत्तर
- **“set baseline” का क्या अर्थ है?** यह किसी कार्य की मूल प्रारंभ, समाप्ति, और अवधि को रिकॉर्ड करता है ताकि आप भविष्य के बदलावों की तुलना कर सकें।  
- **कौन सा Aspose.Tasks क्लास प्रोजेक्ट बनाता है?** `Project` क्लास – आप यह भी सीखेंगे कि **प्रोजेक्ट इंस्टेंस कैसे बनाएं** सही ढंग से।  
- **क्या कोड चलाने के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त इवैल्यूएशन लाइसेंस काम करता है; उत्पादन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।  
- **क्या मैं अंतरिम बेसलाइन प्राप्त कर सकता हूँ?** हाँ, Aspose.Tasks आपको अंतरिम बेसलाइन और उनके फिक्स्ड कॉस्ट को क्वेरी करने देता है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उसके बाद का संस्करण अनुशंसित है।

## टास्क बेसलाइन क्या है और इसे क्यों सेट करें?
टास्क बेसलाइन एक विशिष्ट समय बिंदु पर नियोजित शेड्यूल (प्रारंभ तिथि, समाप्ति तिथि, और अवधि) को कैप्चर करती है। बेसलाइन सेट करके आप एक संदर्भ बिंदु बनाते हैं जिससे प्रोजेक्ट के विकसित होते ही शेड्यूल ड्रिफ्ट, लागत अधिकता, और संसाधन ओवरएलोकेशन को आसानी से पहचान सकते हैं।

## बेसलाइन प्रबंधन के लिए Aspose.Tasks क्यों उपयोग करें?
- **पूर्ण .mpp संगतता** – Office स्थापित किए बिना मूल Microsoft Project फ़ाइलों को पढ़ें और लिखें।  
- **समृद्ध API** – प्रोग्रामेटिक रूप से बेसलाइन डेटा, अंतरिम बेसलाइन, और समय‑फेज़्ड जानकारी तक पहुँचें।  
- **क्रॉस‑प्लेटफ़ॉर्म** – Windows, Linux, और macOS पर किसी भी मानक JDK के साथ काम करता है।

## पूर्वापेक्षाएँ
1. **Java विकास पर्यावरण** – JDK 8+ स्थापित और कॉन्फ़िगर किया हुआ।  
2. **Aspose.Tasks for Java** – लाइब्रेरी को [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE या बिल्ड टूल** – Maven, Gradle, या कोई भी पसंदीदा IDE।

## पैकेज आयात करें
सबसे पहले, आवश्यक क्लासेज़ को अपने Java प्रोजेक्ट में आयात करें:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## चरण 1: प्रोजेक्ट इंस्टेंस बनाएं
प्रोजेक्ट इंस्टेंस बनाना किसी भी आगे की हेरफेर का आधार है। यह चरण दिखाता है कि Aspose.Tasks का उपयोग करके **प्रोजेक्ट इंस्टेंस कैसे बनाएं**:

```java
Project project = new Project();
```

## चरण 2: टास्क बेसलाइन बनाएं
प्रोजेक्ट की रूट में एक नया टास्क जोड़ें और उसकी बेसलाइन सेट करें। यह टास्क के मूल शेड्यूल को रिकॉर्ड करता है:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## चरण 3: टास्क बेसलाइन जानकारी प्रदर्शित करें
वह बेसलाइन प्राप्त करें जो आपने अभी बनाई है और उसकी मुख्य प्रॉपर्टीज़ को प्रिंट करें। यह सुनिश्चित करने में मदद करता है कि बेसलाइन सही ढंग से सेट हुई है:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## चरण 4: अंतरिम बेसलाइन और फिक्स्ड कॉस्ट जांचें
यदि आप अंतरिम बेसलाइन के साथ काम कर रहे हैं, तो आप क्वेरी कर सकते हैं कि वर्तमान बेसलाइन अंतरिम है या नहीं और कोई संबंधित फिक्स्ड कॉस्ट है या नहीं:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## चरण 5: टाइम‑फेज़्ड डेटा प्रिंट करें
टाइम‑फेज़्ड डेटा दिखाता है कि बेसलाइन समय के साथ कैसे वितरित होती है। प्रत्येक एंट्री को निरीक्षण करने के लिए कलेक्शन पर लूप करें:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

इन चरणों का पालन करके, आप किसी भी टास्क के लिए **बेसलाइन अवधि कैसे सेट करें** और Aspose.Tasks for Java का उपयोग करके विस्तृत बेसलाइन जानकारी प्राप्त कर सकते हैं।

## सामान्य समस्याएँ और समाधान
- **Baseline MS Project में नहीं दिख रहा है:** सुनिश्चित करें कि आपने टास्क जोड़ने के **बाद** `project.setBaseline(BaselineType.Baseline)` को कॉल किया है।  
- **`getBaselines()` पर NullPointerException:** बेसलाइन सेट करने से पहले सुनिश्चित करें कि टास्क प्रोजेक्ट में जोड़ा गया था।  
- **समय इकाई का मेल नहीं:** अवधि को सही ढंग से फॉर्मेट करने के लिए `TimeUnitType` का उपयोग करें, विशेषकर कस्टम कैलेंडर के साथ काम करते समय।

## अक्सर पूछे जाने वाले प्रश्न
### MS Project में टास्क बेसलाइन क्या है?
MS Project में टास्क बेसलाइन कार्य के प्रारंभ तिथि, समाप्ति तिथि और अवधि सहित प्रारंभिक नियोजित शेड्यूल का एक स्नैपशॉट है।

### टास्क बेसलाइन प्रबंधन क्यों महत्वपूर्ण है?
टास्क बेसलाइन प्रबंधन योजना शेड्यूल की वास्तविक प्रगति से तुलना करने में मदद करता है, जिससे बेहतर ट्रैकिंग और निर्णय‑लेना संभव होता है।

### क्या मैं सेट होने के बाद टास्क बेसलाइन को संशोधित कर सकता हूँ?
हाँ, आप MS Project में टास्क बेसलाइन को बदल सकते हैं ताकि प्रोजेक्ट योजना में हुए बदलावों को दर्शाया जा सके। हालांकि, मूल बेसलाइन से किसी भी विचलन को दस्तावेज़ित करना आवश्यक है।

### क्या Aspose.Tasks अन्य प्रोजेक्ट मैनेजमेंट कार्यात्मकताओं को समर्थन देता है?
हाँ, Aspose.Tasks प्रोजेक्ट मैनेजमेंट के लिए विस्तृत सुविधाएँ प्रदान करता है, जिसमें टास्क शेड्यूलिंग, संसाधन आवंटन, और गैंट चार्ट जनरेशन शामिल हैं।

### मैं Aspose.Tasks के लिए समर्थन कहाँ पा सकता हूँ?
आप Aspose.Tasks के समर्थन को [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर पा सकते हैं, जहाँ आप प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं के साथ इंटरैक्ट कर सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मुझे प्रत्येक टास्क के लिए अलग‑अलग `setBaseline` कॉल करना पड़ता है?**  
A: नहीं। `project.setBaseline(BaselineType.Baseline)` को कॉल करने से प्रोजेक्ट में सभी टास्क की बेसलाइन एक साथ रिकॉर्ड हो जाती है।

**Q: किसी विशिष्ट टास्क के लिए अंतरिम बेसलाइन कैसे सेट करूँ?**  
A: टास्क के शेड्यूल को अपडेट करने के बाद `project.setBaseline(BaselineType.Baseline1)` (या Baseline2‑Baseline10) का उपयोग करें।

**Q: क्या बेसलाइन डेटा को CSV में एक्सपोर्ट करना संभव है?**  
A: हाँ। `task.getBaselines()` पर इटरेट करें और मानक Java I/O का उपयोग करके इच्छित फ़ील्ड्स को CSV फ़ाइल में लिखें।

**Q: क्या मैं मौजूदा .mpp फ़ाइल पढ़ सकता हूँ जिसमें पहले से बेसलाइन मौजूद हैं?**  
A: बिल्कुल। फ़ाइल को `new Project("myproject.mpp")` से लोड करें और फिर ऊपर दिखाए अनुसार प्रत्येक टास्क की बेसलाइन तक पहुँचें।

**Q: क्या Aspose.Tasks मल्टी‑प्रोजेक्ट फ़ाइलों को संभालता है?**  
A: Aspose.Tasks सिंगल‑प्रोजेक्ट .mpp फ़ाइलों के साथ काम करता है। मल्टी‑प्रोजेक्ट परिदृश्यों के लिए, प्रोग्रामेटिक रूप से प्रोजेक्ट्स को संयोजित करें।

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}