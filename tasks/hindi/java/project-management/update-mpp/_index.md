---
date: 2025-12-28
description: Aspose.Tasks for Java, एक जावा प्रोजेक्ट मैनेजमेंट लाइब्रेरी का उपयोग
  करके टास्क जोड़ना और MPP फ़ाइलें अपडेट करना सीखें। हमारे चरण-दर-चरण गाइड का पालन
  करके MPP में टास्क बनाएं और प्रोजेक्ट को MPP के रूप में सहेजें।
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में कार्य जोड़ना और MPP फ़ाइल को अपडेट करना
url: /hi/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क जोड़ने और MPP फ़ाइल को अपडेट करने का तरीका

## परिचय
इस ट्यूटोरियल में हम आपको **how to add task** दिखाएंगे और Aspose.Tasks for Java, एक प्रमुख **java project management library** का उपयोग करके MPP फ़ाइल को अपडेट करेंगे। चाहे आप एक कस्टम शेड्यूलर बना रहे हों या प्रोग्रामेटिकली मौजूदा प्रोजेक्ट प्लान को संशोधित करना चाहते हों, यह गाइड आपको फ़ाइल लोड करने से लेकर बदलावों को नई MPP डॉक्यूमेंट के रूप में सेव करने तक हर कदम पर ले जाएगा।

## त्वरित उत्तर
- **“how to add task” इस संदर्भ में क्या मतलब है?** यह मौजूदा Microsoft Project (MPP) फ़ाइल के भीतर प्रोग्रामेटिकली एक नया टास्क बनाने को दर्शाता है।  
- **कौन सी लाइब्रेरी यह ऑपरेशन संभालती है?** Aspose.Tasks for Java, एक मजबूत java project management library।  
- **क्या मुझे लाइसेंस चाहिए?** डेवलपमेंट के लिए फ्री ट्रायल काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **क्या मैं परिणाम को MPP के रूप में सेव कर सकता हूँ?** हाँ—`project.save(..., SaveFileFormat.Mpp)` का उपयोग करके **save project as mpp** करें।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उसके बाद का संस्करण।

## MPP फ़ाइल में “how to add task” क्या है?
टास्क जोड़ना मतलब प्रोजेक्ट हायरार्की में एक नया कार्य आइटम डालना, उसके प्रारंभ/समाप्ति तिथियों को परिभाषित करना, और परिवर्तन को फिर से MPP फ़ाइल में सहेजना। Aspose.Tasks फ़ाइल फ़ॉर्मेट के लो‑लेवल विवरणों को एब्स्ट्रैक्ट करता है, जिससे आप बिज़नेस लॉजिक पर ध्यान केंद्रित कर सकते हैं।

## Aspose.Tasks for Java का उपयोग क्यों करें?
- **Full compatibility** Microsoft Project 2007‑2021 फ़ाइलों के साथ।  
- **No COM or Office installation** की आवश्यकता नहीं—शुद्ध Java API।  
- **Rich feature set**: टास्क लिंकिंग, रिसोर्स अलोकेशन, कस्टम फ़ील्ड्स, आदि।  
- **High performance** बड़े प्रोजेक्ट फ़ाइलों के लिए, जिससे यह सर्वर‑साइड ऑटोमेशन के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
1. **Java Development Environment** – JDK 8+ इंस्टॉल और कॉन्फ़िगर किया हुआ।  
2. **Aspose.Tasks for Java** – [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **Basic Java knowledge** – क्लासेज़, ऑब्जेक्ट्स, और डेट हैंडलिंग की समझ।

## पैकेज आयात करें
पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। यह आपको प्रोजेक्ट मैनिपुलेशन, टास्क प्रॉपर्टीज़, और डेट हैंडलिंग तक पहुँच देता है।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## चरण 1: डेटा डायरेक्टरी निर्धारित करें
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` को उस एब्सॉल्यूट पाथ से बदलें जहाँ आपका स्रोत MPP फ़ाइल स्थित है।

## चरण 2: मौजूदा प्रोजेक्ट पढ़ें
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
`Project` कंस्ट्रक्टर **SampleMSP2010.mpp** को लोड करता है, जिससे आपको एक मैनीपुलेटेबल ऑब्जेक्ट मॉडल मिलता है।

## चरण 3: नया टास्क बनाएं (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
यह लाइन **creates task in mpp** रूट टास्क में *Task1* नाम का चाइल्ड जोड़कर टास्क बनाती है।

## चरण 4: प्रारंभ और समाप्ति तिथियां सेट करें
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
यहाँ हम नए जोड़े गए टास्क के शेड्यूल को परिभाषित करते हैं। अपनी प्रोजेक्ट टाइमलाइन के अनुसार तिथियों को समायोजित करें।

## चरण 5: प्रोजेक्ट सहेजें (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
अपडेटेड प्रोजेक्ट, जिसमें अब नया टास्क शामिल है, **AfterLinking.mpp** के रूप में सहेजा जाता है।

## सामान्य समस्याएँ और समाधान
| Issue | Solution |
|-------|----------|
| **File not found** | Verify `dataDir` ends with a path separator (`/` or `\\`) and the file name is correct. |
| **Incorrect dates** | Remember that `Calendar` months are zero‑based; `Calendar.JULY` is correct for July. |
| **License exception** | Install a valid Aspose.Tasks license before calling any API to avoid evaluation watermarks. |

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या Aspose.Tasks for Java जटिल प्रोजेक्ट स्ट्रक्चर को संभाल सकता है?
A: हाँ, Aspose.Tasks for Java जटिल प्रोजेक्ट स्ट्रक्चर को प्रभावी ढंग से संभालने के लिए मजबूत फीचर्स प्रदान करता है।  
### Q: क्या Aspose.Tasks for Java के लिए फ्री ट्रायल उपलब्ध है?
A: हाँ, आप [website](https://releases.aspose.com/) से फ्री ट्रायल डाउनलोड कर सकते हैं।  
### Q: क्या Aspose.Tasks for Java विभिन्न संस्करणों की Microsoft Project फ़ाइलों को सपोर्ट करता है?
A: बिल्कुल, Aspose.Tasks for Java MPP, MPT, और XML सहित विभिन्न संस्करणों की Microsoft Project फ़ाइलों को सपोर्ट करता है।  
### Q: क्या मैं Aspose.Tasks for Java के लिए टेम्पररी लाइसेंस प्राप्त कर सकता हूँ?
A: हाँ, टेस्टिंग उद्देश्यों के लिए टेम्पररी लाइसेंस उपलब्ध हैं। आप उन्हें [temporary license page](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।  
### Q: Aspose.Tasks for Java के बारे में मदद या सपोर्ट कहाँ प्राप्त कर सकता हूँ?
A: आप किसी भी सहायता या प्रश्नों के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

## बार-बार पूछे जाने वाले प्रश्न
**Q: मैं एक साथ कई टास्क कैसे जोड़ूँ?**  
A: टास्क नामों के कलेक्शन पर लूप चलाएँ और लूप के अंदर “create task” ब्लॉक को दोहराएँ।

**Q: क्या मैं नए टास्क के लिए कस्टम फ़ील्ड सेट कर सकता हूँ?**  
A: हाँ—`task.set(Tsk.CUSTOM_FIELD_x, value)` का उपयोग करें जहाँ *x* फ़ील्ड इंडेक्स है।

**Q: क्या मौजूदा टास्क को टेम्पलेट के रूप में कॉपी करना संभव है?**  
A: स्रोत टास्क को क्लोन करें (`Task cloned = sourceTask.clone();`) और फिर इसे इच्छित पैरेंट में जोड़ें।

**Q: यदि मुझे नया टास्क जोड़ने के बजाय मौजूदा टास्क को अपडेट करना हो तो क्या करें?**  
A: टास्क को ID से प्राप्त करें (`Task existing = project.getRootTask().getChildren().getById(id);`) और उसकी प्रॉपर्टीज़ को संशोधित करें।

**Q: क्या Aspose.Tasks PDF या PNG जैसे अन्य फ़ॉर्मैट में सेव करने को सपोर्ट करता है?**  
A: हाँ—`project.save("output.pdf", SaveFileFormat.Pdf);` या विज़ुअल रिप्रेज़ेंटेशन के लिए `SaveFileFormat.Png` का उपयोग करें।

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}