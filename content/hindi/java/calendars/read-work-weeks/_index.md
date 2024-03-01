---
title: Aspose.Tasks के साथ एमएस प्रोजेक्ट कैलेंडर से कार्य सप्ताह पढ़ें
linktitle: Aspose.Tasks के साथ कैलेंडर से कार्य सप्ताह पढ़ें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट कैलेंडर से कार्य सप्ताह पढ़ना सीखें। इस व्यापक ट्यूटोरियल में चरण-दर-चरण निर्देश प्राप्त करें।
type: docs
weight: 15
url: /hi/java/calendars/read-work-weeks/
---
## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Microsoft प्रोजेक्ट कैलेंडर से कार्य सप्ताहों की जानकारी पढ़ने के लिए Java के लिए Aspose.Tasks का उपयोग कैसे करें। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जो आपको Microsoft प्रोजेक्ट दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर और प्रबंधित करने की अनुमति देती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks डाउनलोड और इंस्टॉल किया गया। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
सबसे पहले, आइए अपने कोड के साथ आरंभ करने के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## चरण 1: अपनी डेटा निर्देशिका सेट करें
वह निर्देशिका पथ सेट करें जहाँ आपकी MS प्रोजेक्ट फ़ाइल स्थित है:
```java
String dataDir = "Your Data Directory";
```
## चरण 2: प्रोजेक्ट इंस्टेंस और एक्सेस कैलेंडर बनाएं
प्रोजेक्ट क्लास का एक नया उदाहरण बनाएं और कैलेंडर और कार्य सप्ताह संग्रह तक पहुंचें:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## चरण 3: कार्य सप्ताहों के माध्यम से पुनरावृति करें
कार्य सप्ताहों के संग्रह को दोहराएँ और उनकी जानकारी प्रदर्शित करें:
```java
for (WorkWeek workWeek : collection) {
    // कार्य सप्ताह का नाम, दिनांक से लेकर दिनांक तक प्रदर्शित करें
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // सप्ताह के दिनों और कार्य समय तक पहुंचें
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // यदि आवश्यक हो तो आगे की प्रक्रिया कार्य समय
    }
}
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Java के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट कैलेंडर से कार्य सप्ताहों की जानकारी कैसे पढ़ें। यह शक्तिशाली लाइब्रेरी प्रोजेक्ट फ़ाइलों के निर्बाध हेरफेर को सक्षम बनाती है, जिससे डेवलपर्स विभिन्न कार्यों को कुशलतापूर्वक स्वचालित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं जावा के लिए Aspose.Tasks का उपयोग करके कार्य सप्ताह की जानकारी को संशोधित कर सकता हूँ?
हां, Aspose.Tasks कार्य सप्ताहों और उनसे जुड़ी जानकारी को संशोधित करने, जोड़ने या हटाने के लिए एपीआई प्रदान करता है।
### क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
हाँ, Aspose.Tasks MPP और XML प्रारूपों सहित Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### क्या मैं Aspose.Tasks को अन्य जावा फ्रेमवर्क के साथ एकीकृत कर सकता हूँ?
बिल्कुल, Aspose.Tasks को उन्नत कार्यक्षमता के लिए अन्य जावा फ्रेमवर्क और लाइब्रेरी के साथ सहजता से एकीकृत किया जा सकता है।
### क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप Aspose.Tasks का निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
आप Aspose.Tasks फोरम पर समर्थन और सहायता पा सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).