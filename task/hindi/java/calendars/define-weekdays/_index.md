---
title: Aspose.Tasks के साथ कैलेंडर में सप्ताह के दिनों को परिभाषित करें
linktitle: Aspose.Tasks के साथ कैलेंडर में सप्ताह के दिनों को परिभाषित करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट कैलेंडर में कार्यदिवसों को परिभाषित करना सीखें। कार्य दिवसों और समयों को सहजता से अनुकूलित करें।
type: docs
weight: 12
url: /hi/java/calendars/define-weekdays/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट कैलेंडर में कार्यदिवसों को परिभाषित करने की प्रक्रिया से गुजरेंगे। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने में सक्षम बनाती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) यदि आपने पहले से नहीं किया है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को यहां से डाउनलोड और इंस्टॉल करें[डाउनलोड पेज](https://releases.aspose.com/tasks/java/). दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में Aspose.Tasks के साथ काम करने के लिए आवश्यक आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## चरण 1: एक प्रोजेक्ट इंस्टेंस बनाएं
एक प्रोजेक्ट ऑब्जेक्ट को इंस्टेंटियेट करें, जो उस एमएस प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है जिसके साथ आप काम करेंगे:
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## चरण 2: कैलेंडर परिभाषित करें
एक नया कैलेंडर इंस्टेंस बनाएं और इसे प्रोजेक्ट में जोड़ें:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## चरण 3: कार्य दिवस जोड़ें
सोमवार से गुरुवार को डिफ़ॉल्ट समय के साथ जोड़कर कार्य दिवसों को परिभाषित करें:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## चरण 4: कस्टम कार्य दिवस निर्धारित करें
शनिवार और रविवार को कार्य दिवस के रूप में परिभाषित करें:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## चरण 5: लघु कार्य दिवस निर्धारित करें
शुक्रवार को कस्टम कार्य समय के साथ एक छोटे कार्य दिवस के रूप में सेट करें:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## चरण 6: प्रोजेक्ट सहेजें
संशोधित प्रोजेक्ट को XML फ़ाइल में सहेजें:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## निष्कर्ष
बधाई हो! आपने Java के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट कैलेंडर में कार्यदिवसों को सफलतापूर्वक परिभाषित किया है। अब आप एमएस प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए इस कार्यक्षमता को अपने जावा अनुप्रयोगों में एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Q1: क्या मैं Java के लिए Aspose.Tasks का उपयोग करके कस्टम गैर-कार्य दिवस परिभाषित कर सकता हूँ?
 उत्तर: हां, आप इसे सेट करके कस्टम गैर-कार्य दिवसों को परिभाषित कर सकते हैं`DayWorking` संपत्ति को`false` संबंधित कार्यदिवस के लिए.
### Q2: मैं कैलेंडर में छुट्टियाँ कैसे जोड़ सकता हूँ?
 उ: आप उदाहरण बनाकर छुट्टियाँ जोड़ सकते हैं`CalendarExceptions`और गैर-कार्य तिथियों को निर्दिष्ट करना।
### Q3: क्या Aspose.Tasks MS प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
उत्तर: हां, Aspose.Tasks एमपीपी, एमपीटी और एक्सएमएल प्रारूपों सहित एमएस प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### Q4: क्या मैं MS प्रोजेक्ट फ़ाइल में मौजूदा कैलेंडर को संशोधित कर सकता हूँ?
उ: हां, आप किसी मौजूदा प्रोजेक्ट को कैलेंडर के साथ लोड कर सकते हैं, संशोधन कर सकते हैं और फिर परिवर्तनों को मूल फ़ाइल में वापस सहेज सकते हैं।
### Q5: क्या Aspose.Tasks आवर्ती कार्यों के लिए सहायता प्रदान करता है?
उत्तर: हाँ, Aspose.Tasks आपको आवर्ती कार्यों के साथ काम करने की अनुमति देता है, जिसमें उनके पुनरावृत्ति पैटर्न और अवधि को परिभाषित करना भी शामिल है।