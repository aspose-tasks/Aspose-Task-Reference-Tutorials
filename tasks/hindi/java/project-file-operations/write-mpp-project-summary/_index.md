---
date: 2026-03-29
description: Aspose.Tasks for Java का उपयोग करके MPP प्रोजेक्ट में कीवर्ड सेट करना
  और निर्माण तिथि सेट करना सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण मार्गदर्शिका।
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ MPP प्रोजेक्ट सारांश में कीवर्ड कैसे सेट करें
url: /hi/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ MPP प्रोजेक्ट सारांश में कीवर्ड सेट करने का तरीका

## परिचय
इस ट्यूटोरियल में आप Aspose.Tasks for Java का उपयोग करके MPP प्रोजेक्ट फ़ाइल के लिए **कीवर्ड सेट करने** और अन्य सारांश जानकारी को कैसे सेट किया जाए, यह जानेंगे। चाहे आपको लेखक विवरण, संशोधन संख्या, या एक कस्टम निर्माण तिथि एम्बेड करनी हो, यह गाइड आपको सटीक चरणों के माध्यम से ले जाएगा, तैयार‑से‑चलाने वाले कोड के साथ। अंत तक आप कीवर्ड सेट कर सकेंगे, Java में निर्माण तिथि सेट कर सकेंगे, और फ़ाइल से डेटा पुनः प्राप्त कर सकेंगे।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी उपयोग की जाती है?** Aspose.Tasks for Java  
- **मुख्य उद्देश्य?** MPP फ़ाइल में कीवर्ड, लेखक जानकारी, और निर्माण तिथि सेट करना  
- **कोड चरणों की संख्या?** तीन सरल कोड ब्लॉक (इनिशियलाइज़, सेव, रीड)  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है  
- **समर्थित Java संस्करण?** Java 8 और उससे ऊपर  

## MPP फ़ाइल में “कीवर्ड सेट करने” का क्या अर्थ है?
कीवर्ड्स Microsoft Project (MPP) फ़ाइल के भीतर संग्रहीत मेटाडाटा फ़ील्ड होते हैं। ये प्रोजेक्ट्स को वर्गीकृत करने, तेज़ खोज सक्षम करने, और डाउनस्ट्रीम टूल्स के लिए संदर्भात्मक जानकारी प्रदान करने में मदद करते हैं। Aspose.Tasks `Prj.KEYWORDS` प्रॉपर्टी को एक्सपोज़ करता है, जिससे इस मान को प्रोग्रामेटिक रूप से लिखना या अपडेट करना सरल हो जाता है।

## क्यों Aspose.Tasks for Java का उपयोग करके कीवर्ड और निर्माण तिथि सेट करें?
* **पूर्ण .MPP संगतता** – सभी Project 2007‑2023 फ़ॉर्मैट्स के साथ काम करता है।  
* **कोई COM या Office इंस्टॉलेशन आवश्यक नहीं** – शुद्ध Java, सर्वर‑साइड वातावरण के लिए उपयुक्त।  
* **समृद्ध API** – कीवर्ड्स के अलावा आप एक ही कॉल में लेखक, संशोधन, टिप्पणी, और तिथियां सेट कर सकते हैं।  
* **प्रदर्शन‑अनुकूलित** – बड़े प्रोजेक्ट फ़ाइलों के लिए भी तेज़ पढ़ना/लिखना।  

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – JDK 8 या नया स्थापित हो।  
2. **Aspose.Tasks for Java** – नवीनतम JAR [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, या कोई भी पसंदीदा एडिटर।  

## पैकेज इम्पोर्ट करें
पहले, उन क्लासों को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। ये इम्पोर्ट्स आपको `Project` ऑब्जेक्ट, सारांश फ़ील्ड्स के लिए `Prj` एनेमरेशन, और सेव करने के लिए `SaveFileFormat` एनेमरेशन तक पहुँच प्रदान करते हैं।

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## चरण 1: प्रोजेक्ट सेट अप करें और सारांश जानकारी निर्धारित करें
`Project` इंस्टेंस बनाएं, फिर `set` मेथड का उपयोग करके इच्छित मेटाडाटा लिखें। देखें कि हम कैसे `Calendar` ऑब्जेक्ट का उपयोग करके **कीवर्ड सेट करते हैं** और **Java में निर्माण तिथि सेट करते हैं**।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## चरण 2: प्रोजेक्ट सारांश जानकारी सहेजें
फ़ील्ड्स को भरने के बाद, बदलावों को स्थायी बनाएं। यहाँ हम प्रोजेक्ट को आसान निरीक्षण के लिए XML के रूप में सहेजते हैं, लेकिन आप इसे MPP में भी वापस सहेज सकते हैं।

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## चरण 3: प्रोजेक्ट सारांश जानकारी पढ़ें
यह सत्यापित करने के लिए कि मेटाडाटा सही ढंग से लिखा गया है, फ़ाइल को पुनः लोड करें और प्रत्येक प्रॉपर्टी को पढ़ें। यह चरण दर्शाता है कि **कीवर्ड सेट करने** का तरीका वास्तव में एंड‑टू‑एंड काम करता है।

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
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| **`project.get(Prj.CREATION_DATE)` पर NullPointerException** | सेव करने से पहले कैलेंडर कभी सेट नहीं किया गया था। | `save()` से पहले `project.set(Prj.CREATION_DATE, cal.getTime())` कॉल करना सुनिश्चित करें। |
| **Keywords Microsoft Project UI में नहीं दिख रहे हैं** | फ़ाइल को XML के रूप में सहेजा गया था और सीधे Project में खोला गया। | MPP (`SaveFileFormat.MPP`) में वापस सहेजें या Project में *Import* के माध्यम से XML खोलें। |
| **टाइमज़ोन के कारण Date मान शिफ्ट हो रहे हैं** | Java `Date` में टाइमज़ोन जानकारी शामिल होती है। | यदि आपको UTC तिथियां चाहिए तो `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks for Java को अन्य Java लाइब्रेरीज़ के साथ उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Tasks for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है ताकि आपके प्रोजेक्ट मैनेजमेंट क्षमताओं को बढ़ाया जा सके।

**Q: क्या Aspose.Tasks for Java के लिए कोई ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप एक मुफ्त ट्रायल संस्करण [यहाँ](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**Q: Aspose.Tasks for Java कितनी बार अपडेट किया जाता है?**  
A: Aspose.Tasks for Java नियमित रूप से अपडेट किया जाता है ताकि यह Java और Microsoft Project फ़ाइलों के नवीनतम संस्करणों के साथ संगतता सुनिश्चित कर सके।

**Q: क्या मैं प्रोजेक्ट सारांश जानकारी को और अधिक कस्टमाइज़ कर सकता हूँ?**  
A: बिल्कुल, Aspose.Tasks for Java आपके विशिष्ट आवश्यकताओं के अनुसार प्रोजेक्ट सारांश जानकारी को कस्टमाइज़ करने के लिए व्यापक विकल्प प्रदान करता है।

**Q: Aspose.Tasks for Java के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?**  
A: आप Aspose.Tasks कम्युनिटी फ़ोरम से समर्थन प्राप्त कर सकते हैं [यहाँ](https://forum.aspose.com/c/tasks/15)।

---

**अंतिम अपडेट:** 2026-03-29  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}