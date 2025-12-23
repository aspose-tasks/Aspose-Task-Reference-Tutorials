---
date: 2025-12-23
description: Aspose.Tasks for Java का उपयोग करके MPP सारांश बनाना और प्रोजेक्ट लेखक
  को अपडेट करना सीखें। प्रोजेक्ट जानकारी को आसानी से सेट और प्राप्त करें।
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ MPP सारांश कैसे बनाएं और प्रोजेक्ट लेखक को अपडेट करें
url: /hi/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MPP प्रोजेक्ट सारांश लिखें

## परिचय
इस ट्यूटोरियल में आप **MPP सारांश** जानकारी को Microsoft Project फ़ाइल के लिए बनाना सीखेंगे और Aspose.Tasks लाइब्रेरी for Java का उपयोग करके **प्रोजेक्ट लेखक** विवरण को **अपडेट** करना सीखेंगे। चाहे आप प्रोजेक्ट‑मैनेजमेंट टूल बना रहे हों या रिपोर्टिंग को स्वचालित कर रहे हों, सारांश गुणों को प्रोग्रामेटिकली नियंत्रित करने से समय बचता है और आपके प्रोजेक्ट्स में स्थिरता बनी रहती है।

## त्वरित उत्तर
- **“MPP सारांश बनाना” का क्या मतलब है?** इसका अर्थ है उच्च‑स्तरीय प्रोजेक्ट गुण (लेखक, संशोधन, कीवर्ड आदि) सेट करना जो Microsoft Project के Project Summary Information डायलॉग में दिखते हैं।  
- **कौन सी लाइब्रेरी इसे संभालती है?** Aspose.Tasks for Java एक फ़्लुएंट API प्रदान करती है जिससे इन गुणों को पढ़ा और लिखा जा सकता है।  
- **क्या लाइसेंस की आवश्यकता है?** एक फ्री ट्रायल उपलब्ध है, लेकिन प्रोडक्शन उपयोग के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **क्या फ़ाइल सेव करने के बाद लेखक को बदल सकते हैं?** हाँ – आप `project.set(Prj.AUTHOR, "New Author")` कॉल करके **प्रोजेक्ट लेखक को अपडेट** कर सकते हैं और फिर फ़ाइल को पुनः‑सेव कर सकते हैं।  
- **कौन‑से फ़ाइल फ़ॉर्मेट समर्थित हैं?** दोनों MPP और XML (SaveFileFormat.Xml) पूरी तरह समर्थित हैं।

## “MPP सारांश बनाना” क्या है?
MPP सारांश बनाना प्रोजेक्ट की मेटा‑डेटा (लेखक, संशोधन संख्या, कीवर्ड, टिप्पणी, निर्माण तिथि, प्रिंट तिथि) को भरने से संबंधित है। यह मेटा‑डेटा Project Summary Information रिकॉर्ड के भीतर संग्रहीत होती है और Microsoft Project के **File → Info** सेक्शन में प्रदर्शित होती है।

## प्रोजेक्ट लेखक को अपडेट क्यों करें?
**प्रोजेक्ट लेखक** जानकारी को सटीक रखना ऑडिट ट्रेल, सहयोग और रिपोर्टिंग के लिए आवश्यक है। जब कई टीम सदस्य योगदान देते हैं, तो आप **प्रोजेक्ट लेखक** को अपडेट करके नवीनतम बदलावों को दर्शा सकते हैं या कार्य को सही ढंग से असाइन कर सकते हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
2. Aspose.Tasks for Java – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. IntelliJ IDEA, Eclipse, या NetBeans जैसे कोई IDE।

## पैकेज इम्पोर्ट करें
सबसे पहले, आवश्यक पैकेज को अपनी Java क्लास में इम्पोर्ट करें:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## चरण 1: प्रोजेक्ट सेट अप करें और सारांश जानकारी परिभाषित करें
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
ऊपर के कोड में हमने **MPP सारांश** फ़ील्ड जैसे लेखक, संशोधन, और कीवर्ड बनाए हैं। आप बाद में `project.set(Prj.AUTHOR, "New Name")` कॉल करके **प्रोजेक्ट लेखक को अपडेट** भी कर सकते हैं।

## चरण 2: प्रोजेक्ट सारांश जानकारी सहेजें
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
प्रोजेक्ट को सहेजने से सभी सारांश डेटा स्थायी रूप से संग्रहित हो जाता है।

## चरण 3: प्रोजेक्ट सारांश जानकारी पढ़ें
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
यह स्निपेट दर्शाता है कि कैसे **सारांश जानकारी को पढ़ा** जाए, जिससे पुष्टि हो सके कि **MPP सारांश बनाना** ऑपरेशन सफल रहा।

## सामान्य समस्याएँ और समाधान
- **पढ़ने के बाद Null मान:** सुनिश्चित करें कि प्रोजेक्ट को पुनः‑लोड करने से पहले सफलतापूर्वक सहेजा गया हो। फ़ाइल पाथ और अनुमतियों की जाँच करें।  
- **तारीख फ़ॉर्मेट अंतर:** `project.get(Prj.CREATION_DATE)` एक `java.util.Date` लौटाता है। यदि आपको कस्टम डिस्प्ले फ़ॉर्मेट चाहिए तो `SimpleDateFormat` का उपयोग करें।  
- **लाइसेंस सेट नहीं है:** वैध लाइसेंस के बिना, Aspose.Tasks इवैल्युएशन मोड में चलता है और वॉटरमार्क जोड़ सकता है। कोड में शुरुआती चरण में अपना लाइसेंस रजिस्टर करें।

## अक्सर पूछे जाने वाले प्रश्न
**प्र: क्या मैं Aspose.Tasks for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
उ: हाँ, Aspose.Tasks for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है जिससे आपके प्रोजेक्ट मैनेजमेंट क्षमताएँ बढ़ती हैं।

**प्र: क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?**  
उ: हाँ, आप इसे [here](https://releases.aspose.com/) से मुफ्त ट्रायल के रूप में डाउनलोड कर सकते हैं।

**प्र: Aspose.Tasks for Java कितनी बार अपडेट होता है?**  
उ: Aspose.Tasks for Java नियमित रूप से अपडेट किया जाता है ताकि यह नवीनतम Java संस्करणों और Microsoft Project फ़ाइलों के साथ संगत रहे।

**प्र: क्या मैं प्रोजेक्ट सारांश जानकारी को और अधिक कस्टमाइज़ कर सकता हूँ?**  
उ: बिल्कुल, Aspose.Tasks for Java विस्तृत विकल्प प्रदान करता है जिससे आप अपनी विशिष्ट आवश्यकताओं के अनुसार प्रोजेक्ट सारांश जानकारी को कस्टमाइज़ कर सकते हैं।

**प्र: Aspose.Tasks for Java के लिए सपोर्ट कहाँ प्राप्त कर सकता हूँ?**  
उ: आप Aspose.Tasks कम्युनिटी फ़ोरम से सपोर्ट ले सकते हैं [here](https://forum.aspose.com/c/tasks/15)।

## निष्कर्ष
इस ट्यूटोरियल में हमने दिखाया कि कैसे **MPP सारांश** डेटा बनाया जाए, **प्रोजेक्ट लेखक को अपडेट** किया जाए, और Aspose.Tasks for Java का उपयोग करके इन बदलावों की पुष्टि की जाए। इन चरणों को स्वचालित करके आप प्रोजेक्ट मेटा‑डेटा पर पूर्ण नियंत्रण प्राप्त करते हैं, जिससे आपके एप्लिकेशन अधिक मजबूत बनते हैं और प्रोजेक्ट रिपोर्ट अधिक सटीक होती हैं।

---

**अंतिम अपडेट:** 2025-12-23  
**टेस्टेड विथ:** Aspose.Tasks for Java 24.10  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}