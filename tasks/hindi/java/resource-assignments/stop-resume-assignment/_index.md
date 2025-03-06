---
title: Aspose.Tasks में संसाधन असाइनमेंट रोकें और फिर से शुरू करें
linktitle: Aspose.Tasks में संसाधन असाइनमेंट रोकें और फिर से शुरू करें
second_title: Aspose.Tasks जावा एपीआई
description: इस चरण-दर-चरण ट्यूटोरियल के साथ जानें कि जावा के लिए Aspose.Tasks में संसाधन असाइनमेंट को प्रभावी ढंग से कैसे प्रबंधित किया जाए।
weight: 23
url: /hi/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में संसाधन असाइनमेंट रोकें और फिर से शुरू करें

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि जावा के लिए Aspose.Tasks का उपयोग करके संसाधन असाइनमेंट को कैसे रोकें और फिर से शुरू करें। Aspose.Tasks एक शक्तिशाली जावा एपीआई है जो डेवलपर्स को अपने सिस्टम पर Microsoft प्रोजेक्ट स्थापित किए बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की अनुमति देता है। हम इस प्रक्रिया को प्रबंधनीय चरणों में विभाजित करेंगे ताकि इसका पालन करना आसान हो सके।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Tasks डाउनलोड किया गया। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
- जावा प्रोग्रामिंग की बुनियादी समझ.
## पैकेज आयात करें
सबसे पहले, आइए अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Data Directory";
// प्रोजेक्ट फ़ाइल लोड करें
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 इस चरण में, हम प्रोजेक्ट फ़ाइल को a में लोड करते हैं`Project` फ़ाइल पथ का उपयोग करके ऑब्जेक्ट।
## चरण 2: संसाधन असाइनमेंट के माध्यम से पुनरावृति करें
```java
// न्यूनतम तिथि परिभाषित करें
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// संसाधन असाइनमेंट के माध्यम से पुनरावृति करें
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
यहां, हम एक न्यूनतम तिथि परिभाषित करते हैं और प्रोजेक्ट में प्रत्येक संसाधन असाइनमेंट के माध्यम से पुनरावृत्ति शुरू करते हैं।
## चरण 3: रुकने और फिर से शुरू करने की तारीखें जांचें
```java
    // रुकने की तारीख जांचें
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // बायोडाटा की तारीख जांचें
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
इस चरण में, हम जांचते हैं कि प्रत्येक संसाधन असाइनमेंट की रोक और फिर से शुरू करने की तारीखें न्यूनतम तारीख से पहले हैं या नहीं। यदि वे हैं, तो हम "NA" प्रिंट करते हैं, अन्यथा, हम संबंधित तिथियां प्रिंट करते हैं।
## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Tasks में संसाधन असाइनमेंट को कैसे रोकें और फिर से शुरू करें। दिए गए चरणों का पालन करके, आप इस कार्यक्षमता को अपने जावा प्रोजेक्ट्स में आसानी से लागू कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Microsoft प्रोजेक्ट स्थापित किए बिना Aspose.Tasks का उपयोग कर सकता हूँ?
हाँ, Aspose.Tasks आपको आपके सिस्टम पर Microsoft प्रोजेक्ट स्थापित किए बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की अनुमति देता है।
### मुझे और अधिक दस्तावेज़ कहां मिल सकते हैं?
 आप विस्तृत दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/tasks/java/).
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### यदि मुझे कोई समस्या आती है तो मुझे सहायता कैसे मिल सकती है?
आपको समुदाय से समर्थन मिल सकता है[यहाँ](https://forum.aspose.com/c/tasks/15).
### क्या मैं अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप अस्थायी लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
