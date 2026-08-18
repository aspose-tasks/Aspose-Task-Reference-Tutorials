---
date: 2026-02-20
description: Aspose.Tasks का उपयोग करके जावा में प्रोजेक्ट लागत विचलन की गणना करना
  और कार्य लागतों का प्रबंधन करना सीखें। लागत निर्धारित करने और बजट नियंत्रित करने
  के लिए हमारे चरण‑दर‑चरण मार्गदर्शिका का पालन करें।
linktitle: Manage Task Costs in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ प्रोजेक्ट लागत विचलन की गणना करें
url: /hi/java/task-properties/manage-task-cost/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ प्रोजेक्ट लागत विचलन की गणना करें

## परिचय
इस व्यापक ट्यूटोरियल में आप **प्रोजेक्ट लागत विचलन की गणना कैसे करें** और Aspose.Tasks के साथ अपने Java अनुप्रयोगों में टास्क लागत को कुशलतापूर्वक प्रबंधित करना सीखेंगे। चाहे आप एक छोटा आंतरिक प्रोजेक्ट ट्रैक कर रहे हों या बड़े‑स्तर के एंटरप्राइज़ रोल‑आउट, लागत विचलन को समझना बजट को ट्रैक पर रखने और ओवररन को जल्दी पहचानने में मदद करता है।

## त्वरित उत्तर
- **लागत विचलन क्या है?** नियोजित (स्थिर) लागत और वास्तविक (शेष) लागत के बीच का अंतर।  
- **कौन सा API मेथड टास्क की लागत सेट करता है?** `task.set(Tsk.COST, BigDecimal.valueOf(...))`।  
- **क्या विकास के लिए लाइसेंस की आवश्यकता है?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए वाणिज्यिक लाइसेंस आवश्यक है।  
- **क्या मैं प्रोजेक्ट‑स्तर की लागत डेटा प्राप्त कर सकता हूँ?** हाँ, रूट टास्क की लागत प्रॉपर्टीज़ को एक्सेस करके।  
- **कौन सा Java संस्करण समर्थित है?** Aspose.Tasks Java 8 और उसके बाद के संस्करणों के साथ काम करता है।

## “प्रोजेक्ट लागत विचलन की गणना” क्या है?
प्रोजेक्ट लागत विचलन की गणना का अर्थ है **स्थिर लागत** (जो आपने टास्क या प्रोजेक्ट के लिए मूल रूप से नियोजित की थी) की तुलना **शेष लागत** (जो अभी भी किया जाना बाकी है) से करना। यह विचलन बताता है कि आप बजट के भीतर हैं या उससे अधिक, जिससे सक्रिय समायोजन संभव होते हैं।

## Aspose.Tasks के साथ प्रोजेक्ट लागत विचलन की गणना क्यों करें?
- **पूरी तरह से .NET‑मुक्त Java API** – कोई नेटिव लाइब्रेरी आवश्यक नहीं।  
- **समृद्ध लागत‑प्रबंधन प्रॉपर्टीज़** (`COST`, `FIXED_COST`, `REMAINING_COST`, `COST_VARIANCE`)।  
- **मौजूदा Maven/Gradle प्रोजेक्ट्स के साथ आसान एकीकरण**।  
- **सटीक रिपोर्टिंग** जिसे MS Project® फ़ाइलों में निर्यात किया जा सकता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

1. **Java Development Kit (JDK)** – Java 8 या उसके बाद का संस्करण स्थापित हो।  
2. **Aspose.Tasks for Java लाइब्रेरी** – इसे आधिकारिक साइट से **[यहाँ](https://releases.aspose.com/tasks/java/)** डाउनलोड करें।  
3. एक IDE या बिल्ड टूल (IntelliJ, Eclipse, Maven, Gradle) ताकि आप सैंपल कोड को कंपाइल और रन कर सकें।

## पैकेज इम्पोर्ट करें
आवश्यक Aspose.Tasks क्लासेज़ को अपने Java स्रोत फ़ाइल में जोड़ें ताकि आप प्रोजेक्ट्स और टास्क्स के साथ काम कर सकें।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Import Aspose.Tasks classes
```

## चरण‑दर‑चरण गाइड

### चरण 1: अपना प्रोजेक्ट सेट‑अप करें
पहले, एक नया `Project` इंस्टेंस बनाएं और उस फ़ोल्डर की ओर इशारा करें जहाँ आप उत्पन्न फ़ाइलें संग्रहीत करेंगे।

```java
// Set the path to your document directory
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project();
```

### चरण 2: नया टास्क जोड़ें
रूट टास्क के अंतर्गत एक टास्क जोड़ें। यहाँ हम लागत असाइन करेंगे।

```java
// Add a new task to the root task
Task task = project.getRootTask().getChildren().add("Task");
```

### चरण 3: टास्क लागत सेट करें – **लागत कैसे सेट करें**
टास्क को नियोजित लागत असाइन करें। वास्तविक परिदृश्य में यह लागत बजट स्प्रेडशीट से आ सकती है।

```java
// Set the task cost to 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```

### चरण 4: लागत जानकारी प्राप्त करें और प्रदर्शित करें – **लागत कैसे प्रबंधित करें**
अब हम विभिन्न लागत प्रॉपर्टीज़ को पढ़ेंगे, जिसमें गणना किया गया लागत विचलन भी शामिल है।

```java
// Retrieve and print task information
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Retrieve and print project-level cost information
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```

**आपको जो दिखाई देगा:**  
- `Remaining Cost` वह कार्य दर्शाता है जो अभी पूरा होना बाकी है।  
- `Fixed Cost` वह बेसलाइन है जो आपने सेट की (इस उदाहरण में 800)।  
- `Cost Variance` स्वचालित रूप से **Fixed – Remaining** के रूप में गणना किया जाता है।  
- वही मान प्रोजेक्ट (रूट टास्क) स्तर पर भी उपलब्ध होते हैं, जिससे आप **सभी टास्क्स के बीच प्रोजेक्ट लागत विचलन की गणना** कर सकते हैं।

### चरण 5: अतिरिक्त टास्क्स के लिए दोहराएँ (वैकल्पिक)
यदि आपके प्रोजेक्ट में कई चरण हैं, तो प्रत्येक टास्क के लिए चरण 2‑4 दोहराएँ। व्यक्तिगत विचलनों को जोड़ने से आपको समग्र प्रोजेक्ट लागत विचलन मिलेगा।

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| `NullPointerException` जब टास्क प्रॉपर्टीज़ एक्सेस की जाती हैं | टास्क प्रोजेक्ट हाइरार्की में नहीं जोड़ा गया था। | `project.getRootTask().getChildren().add(...)` को कॉल करने के बाद ही लागत सेट करें। |
| लागत मान `0` दिख रहा है | `int` के बजाय `BigDecimal` का उपयोग किया गया। | हमेशा `BigDecimal.valueOf(...)` जैसा दिखाया गया है, वैसा ही उपयोग करें। |
| अप्रत्याशित विचलन (नकारात्मक) | `REMAINING_COST` `FIXED_COST` से अधिक है। | कार्य प्रगति के साथ शेष लागत को अपडेट करना सुनिश्चित करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: Aspose.Tasks for Java की दस्तावेज़ीकरण कहाँ मिल सकती है?**  
उ: आप दस्तावेज़ीकरण **[यहाँ](https://reference.aspose.com/tasks/java/)** पर पहुँच सकते हैं।

**प्र: Aspose.Tasks for Java लाइब्रेरी कैसे डाउनलोड करें?**  
उ: लाइब्रेरी **[यहाँ](https://releases.aspose.com/tasks/java/)** से डाउनलोड करें।

**प्र: Aspose.Tasks for Java कहाँ खरीद सकते हैं?**  
उ: आप इसे **[यहाँ](https://purchase.aspose.com/buy)** खरीद सकते हैं।

**प्र: Aspose.Tasks for Java के लिए मुफ्त ट्रायल उपलब्ध है क्या?**  
उ: हाँ, आप मुफ्त ट्रायल **[यहाँ](https://releases.aspose.com/)** प्राप्त कर सकते हैं।

**प्र: Aspose.Tasks for Java के लिए समर्थन कहाँ प्राप्त करें?**  
उ: समर्थन फ़ोरम **[यहाँ](https://forum.aspose.com/c/tasks/15)** पर देखें।

---

**अंतिम अपडेट:** 2026-02-20  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}