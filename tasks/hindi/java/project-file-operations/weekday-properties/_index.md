---
date: 2025-12-23
description: Aspose Tasks Java का उपयोग करके प्रोजेक्ट शेड्यूल को अपडेट करना, सप्ताह
  की शुरुआत का दिन सेट करना, महीने के दिनों को बदलना, और प्रोजेक्ट कैलेंडर को कुशलतापूर्वक
  कस्टमाइज़ करना सीखें।
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – सप्ताह के दिन की प्रॉपर्टीज़ का प्रबंधन
url: /hi/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – सप्ताह के दिन गुणों का प्रबंधन

## परिचय
Aspose.Tasks for Java (aspose tasks java) एक मजबूत API है जो Java डेवलपर्स को Microsoft Project फ़ाइलों के साथ काम करने की सुविधा देता है बिना Microsoft Project स्थापित किए। इस ट्यूटोरियल में आप सीखेंगे कि कैसे **MPP फ़ाइल लोड करें**, **सप्ताह की प्रारंभिक दिन सेट करें**, **प्रति माह दिनों की संख्या बदलें**, और अन्यथा **प्रोजेक्ट कैलेंडर को कस्टमाइज़ करें**—जो प्रोजेक्ट शेड्यूल को अपडेट करने के लिए आवश्यक कदम हैं। अंत तक, आप प्रोग्रामेटिक रूप से सप्ताह के दिन गुणों को समायोजित कर सकेंगे और आवश्यक फ़ॉर्मेट में बदलाव सहेज सकेंगे।

## त्वरित उत्तर
- **प्रोजेक्ट को संभालने के लिए मुख्य क्लास कौन सी है?** `Project` from the Aspose.Tasks library.  
- **सप्ताह की प्रारंभिक दिन कैसे बदलें?** Use `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **क्या मैं मौजूदा .mpp फ़ाइल लोड कर सकता हूँ?** Yes—instantiate `Project` with the file path.  
- **कौन सा मेथड प्रोजेक्ट को XML के रूप में सहेजता है?** `project.save(path, SaveFileFormat.Xml)`.  
- **क्या विकास के लिए लाइसेंस की आवश्यकता है?** एक मुफ्त ट्रायल मूल्यांकन के लिए काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **Java Development Kit (JDK)** – नवीनतम संस्करण स्थापित हो।  
- **Aspose.Tasks for Java library** – इसे [यहाँ](https://releases.aspose.com/tasks/java/) डाउनलोड करें।  
- **An IDE** जैसे IntelliJ IDEA, Eclipse, या NetBeans।  

## पैकेज आयात करें
शुरू करने के लिए, आवश्यक Aspose.Tasks क्लासेस आयात करें:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

अब चलिए सप्ताह के दिन गुणों के प्रबंधन के प्रत्येक चरण को देखते हैं।

## चरण 1: MPP फ़ाइल लोड करें
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*यहाँ हम **मौजूदा .mpp फ़ाइल लोड करते हैं** (`load mpp file`) ताकि हम इसके कैलेंडर सेटिंग्स की जाँच और संशोधन कर सकें।*

## चरण 2: वर्तमान सप्ताह के दिन गुण दिखाएँ
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
यह कोड वर्तमान **सप्ताह की प्रारंभिक दिन**, **प्रति माह दिनों की संख्या**, **प्रति दिन मिनट**, और **प्रति सप्ताह मिनट** को प्रिंट करता है—वे मुख्य तत्व जिन्हें आप अक्सर **प्रोजेक्ट कैलेंडर को कस्टमाइज़** करने के लिए आवश्यक होते हैं।

## चरण 3: नए सप्ताह के दिन गुण सेट करें
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
इस चरण में हम **सप्ताह की प्रारंभिक दिन** को Monday सेट करते हैं, **प्रति माह दिनों की संख्या** को 24 बदलते हैं, और दैनिक तथा साप्ताहिक मिनट गिनती को समायोजित करते हैं। ये सेटिंग्स सामान्यतः तब उपयोगी होती हैं जब आपको **प्रोजेक्ट शेड्यूल को अपडेट** करना हो ताकि वह एक गैर‑मानक कार्य कैलेंडर से मेल खाए।

## चरण 4: अपडेटेड प्रोजेक्ट को सहेजें
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
संशोधित प्रोजेक्ट को XML फ़ाइल के रूप में सहेजा जाता है, जिससे इसे अन्य टूल्स में साझा या आयात करना आसान हो जाता है।

## चरण 5: ऑपरेशन की पुष्टि करें
```java
System.out.println("Process completed Successfully");
```
एक सरल कंसोल संदेश आपको बताता है कि कार्यप्रवाह बिना त्रुटियों के समाप्त हो गया है।

## सामान्य समस्याएँ और सुझाव
- **गलत फ़ाइल पथ** – सुनिश्चित करें कि `dataDir` स्लैश पर समाप्त हो या प्लेटफ़ॉर्म‑स्वतंत्र पथों के लिए `Paths.get(...)` का उपयोग करें।  
- **लाइसेंस सेट नहीं है** – प्रोडक्शन वातावरण में, `Project` बनाने से पहले `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` कॉल करें।  
- **अप्रत्याशित सप्ताह प्रारंभिक दिन** – सुनिश्चित करें कि आप सही `DayType` enum मान (जैसे, `DayType.Sunday`) का उपयोग कर रहे हैं।  

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?**  
A: हाँ, Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को आसानी से संभालने के लिए व्यापक समर्थन प्रदान करता है।

**Q: क्या Aspose.Tasks for Java विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
A: बिल्कुल, Aspose.Tasks for Java विभिन्न संस्करणों की Microsoft Project फ़ाइलों का समर्थन करता है, जिससे प्लेटफ़ॉर्म के बीच संगतता सुनिश्चित होती है।

**Q: क्या मैं Aspose.Tasks for Java को अपने मौजूदा Java एप्लिकेशन में एकीकृत कर सकता हूँ?**  
A: हाँ, Aspose.Tasks for Java सहज एकीकरण क्षमताएँ प्रदान करता है, जिससे आप अपने Java एप्लिकेशन को शक्तिशाली प्रोजेक्ट मैनेजमेंट फीचर्स के साथ बढ़ा सकते हैं।

**Q: क्या Aspose.Tasks for Java दस्तावेज़ीकरण और समर्थन प्रदान करता है?**  
A: हाँ, आप Aspose.Tasks for Java के विस्तृत दस्तावेज़ीकरण और समुदाय समर्थन उनके [वेबसाइट](https://releases.aspose.com/) पर पा सकते हैं।

**Q: क्या Aspose.Tasks for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण उनके [वेबसाइट](https://reference.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं ताकि खरीदारी से पहले इसकी सुविधाओं का अन्वेषण कर सकें।

---

**अंतिम अपडेट:** 2025-12-23  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}