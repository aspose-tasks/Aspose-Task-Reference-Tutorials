---
date: 2026-03-29
description: Aspose.Tasks for Java में महीने के दिनों को बदलना और अन्य सप्ताह के दिन
  गुणों को प्रबंधित करना सीखें। सप्ताह की प्रारंभ तिथियों को अनुकूलित करें, प्रोजेक्ट
  कैलेंडर को संशोधित करें, और प्रोजेक्ट को XML के रूप में सहेजें।
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks सप्ताह के दिन गुणों के साथ प्रति माह दिनों को बदलें
url: /hi/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# महीने में दिनों की संख्या बदलें Aspose.Tasks सप्ताह के दिन गुणों के साथ

## परिचय
Aspose.Tasks for Java आपको **महीने में दिनों की संख्या बदलने** और अन्य सप्ताह के दिन सेटिंग्स को बारीकी से समायोजित करने की सुविधा देता है, बिना Microsoft Project स्थापित किए। चाहे आप प्रोजेक्ट कैलेंडर को गैर‑मानक वित्तीय महीने के साथ संरेखित कर रहे हों या केवल सप्ताह की शुरुआत का दिन बदलना चाहते हों, यह ट्यूटोरियल आपको सबसे सामान्य परिदृश्यों के माध्यम से ले जाता है—वर्तमान सप्ताह शुरू होने का दिन प्राप्त करना, सप्ताह शुरू होने की तिथि को अनुकूलित करना, प्रोजेक्ट कैलेंडर को संशोधित करना, और प्रोजेक्ट को XML के रूप में सहेजना।

## त्वरित उत्तर
- **क्या मैं महीने में दिनों की संख्या बदल सकता हूँ?** हाँ, `Project` ऑब्जेक्ट पर `Prj.DAYS_PER_MONTH` का उपयोग करें।  
- **मैं सप्ताह शुरू होने की तिथि को कैसे अनुकूलित करूँ?** `Prj.WEEK_START_DAY` को एक `DayType` मान पर सेट करें (जैसे, `DayType.Monday`).  
- **मैं प्रोजेक्ट को निर्यात करने के लिए कौन सा फ़ॉर्मेट उपयोग कर सकता हूँ?** उदाहरण फ़ाइल को XML के रूप में `SaveFileFormat.Xml` के साथ सहेजता है।  
- **उत्पादन उपयोग के लिए लाइसेंस आवश्यक है?** गैर‑मूल्यांकन तैनाती के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **कौन से IDE समर्थित हैं?** कोई भी Java IDE जैसे IntelliJ IDEA, Eclipse, या NetBeans काम करता है।

## Aspose.Tasks में “महीने में दिनों की संख्या बदलें” क्या है?
महीने में दिनों की संख्या बदलना मतलब `Project` इंस्टेंस की `Prj.DAYS_PER_MONTH` प्रॉपर्टी को अपडेट करना है। यह प्रॉपर्टी इंजन को बताती है कि प्रत्येक महीने में कितने कार्य दिवसों को माना जाए, जो सीधे टास्क शेड्यूलिंग और लागत गणना को प्रभावित करता है।

## प्रोजेक्ट कैलेंडर गुणों को संशोधित क्यों करें?
- क्षेत्रीय कार्यसप्ताहों के साथ शेड्यूल को संरेखित करें।  
- गैर‑मानक कार्य पैटर्न (जैसे, 4‑दिन के सप्ताह) को मॉडल करें।  
- कस्टम कैलेंडर उपयोग करने वाले अनुबंधों के लिए सटीक रिपोर्टिंग सुनिश्चित करें।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK)** – Oracle से नवीनतम JDK स्थापित करें।  
- **Aspose.Tasks for Java library** – इसे आधिकारिक साइट [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
- **IDE of your choice** – IntelliJ IDEA, Eclipse, या NetBeans।

## पैकेज आयात करें
सबसे पहले, आवश्यक Aspose.Tasks क्लासेस को आयात करें:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
यह निर्दिष्ट फ़ोल्डर से मौजूदा Microsoft Project फ़ाइल (`project.mpp`) को लोड करता है।

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## चरण 2: सप्ताह के दिन गुण प्रदर्शित करें
यहाँ हम वर्तमान सप्ताह के दिन सेटिंग्स को प्राप्त और प्रिंट करते हैं, जिसमें **सप्ताह शुरू होने का दिन** और **महीने में दिनों की संख्या** शामिल हैं।

```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```

## चरण 3: सप्ताह के दिन गुण सेट करना
इस चरण में हम **महीने में दिनों की संख्या** को 24 पर बदलते हैं, सप्ताह को सोमवार से शुरू करते हैं, और दिन/सप्ताह के मिनटों को समायोजित करते हैं। यह दर्शाता है कि कैसे प्रोग्रामेटिक रूप से **प्रोजेक्ट कैलेंडर** मानों को **संशोधित** किया जाए।

```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```

## चरण 4: प्रोजेक्ट सहेजें
संशोधित प्रोजेक्ट को **प्रोजेक्ट को XML के रूप में सहेजें** फ़ॉर्मेट का उपयोग करके स्थायी किया जाता है, जो अन्य टूल्स के साथ एकीकरण या संस्करण‑नियंत्रित संग्रहण के लिए उपयोगी है।

```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```

## चरण 5: परिणाम प्रदर्शित करें
एक सरल पुष्टि कि संचालन बिना त्रुटियों के समाप्त हो गया।

```java
System.out.println("Process completed Successfully");
```

## सप्ताह शुरू होने की तिथि को कैसे अनुकूलित करें
यदि आपका संगठन रविवार‑पहले कैलेंडर का पालन करता है, तो `DayType.Monday` को `DayType.Sunday` से बदलें। वही प्रॉपर्टी (`Prj.WEEK_START_DAY`) उपयोग की जाती है, जिससे परिवर्तन सरल हो जाता है।

## सप्ताह शुरू होने का दिन कैसे प्राप्त करें
आप किसी भी बिंदु पर `project.get(Prj.WEEK_START_DAY)` को कॉल करके **सप्ताह शुरू होने का दिन** जानकारी प्राप्त कर सकते हैं, जैसा कि चरण 2 में दिखाया गया है।

## प्रोजेक्ट कैलेंडर को कैसे संशोधित करें
सप्ताह शुरू होने के दिन के अलावा, आप `Prj.MINUTES_PER_DAY` और `Prj.MINUTES_PER_WEEK` को भी कस्टम कार्य घंटे या शिफ्ट पैटर्न को दर्शाने के लिए समायोजित कर सकते हैं।

## सामान्य समस्याएँ और समाधान
- **गलत दिन प्रकार मान** – सुनिश्चित करें कि आप `DayType` enum का उपयोग कर रहे हैं (जैसे, `DayType.Monday`).  
- **फ़ाइल पथ त्रुटियाँ** – पुष्टि करें कि `dataDir` उचित फ़ाइल विभाजक (`/` या `\`) के साथ समाप्त होता है।  
- **लाइसेंस सेट नहीं है** – यदि आप लाइसेंसिंग चेतावनियाँ देखते हैं, तो `Project` ऑब्जेक्ट बनाने से पहले अपना Aspose.Tasks लाइसेंस रजिस्टर करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?**  
**उत्तर:** हाँ, Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को आसानी से संभालने के लिए व्यापक समर्थन प्रदान करता है।

**प्रश्न: क्या Aspose.Tasks for Java विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
**उत्तर:** बिल्कुल, Aspose.Tasks for Java विभिन्न संस्करणों की Microsoft Project फ़ाइलों का समर्थन करता है, जिससे विभिन्न प्लेटफ़ॉर्म पर संगतता सुनिश्चित होती है।

**प्रश्न: क्या मैं Aspose.Tasks for Java को अपने मौजूदा Java अनुप्रयोगों में एकीकृत कर सकता हूँ?**  
**उत्तर:** हाँ, Aspose.Tasks for Java सहज एकीकरण क्षमताएँ प्रदान करता है, जिससे आप अपने Java अनुप्रयोगों को शक्तिशाली प्रोजेक्ट प्रबंधन सुविधाओं से समृद्ध कर सकते हैं।

**प्रश्न: क्या Aspose.Tasks for Java दस्तावेज़ीकरण और समर्थन प्रदान करता है?**  
**उत्तर:** हाँ, आप उनके [website](https://releases.aspose.com/) पर Aspose.Tasks for Java के विस्तृत दस्तावेज़ीकरण और समुदाय समर्थन तक पहुँच सकते हैं।

**प्रश्न: क्या Aspose.Tasks for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
**उत्तर:** हाँ, आप उनके [website](https://reference.aspose.com/tasks/java/) से Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण डाउनलोड कर सकते हैं ताकि खरीदारी से पहले इसकी सुविधाओं का अन्वेषण कर सकें।

---

**अंतिम अपडेट:** 2026-03-29  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}