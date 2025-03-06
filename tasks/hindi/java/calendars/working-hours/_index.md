---
title: Aspose.Tasks का उपयोग करके कैलेंडर से कार्य के घंटे प्राप्त करें
linktitle: Aspose.Tasks का उपयोग करके कैलेंडर से कार्य के घंटे प्राप्त करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks के साथ आसानी से MS प्रोजेक्ट कैलेंडर से कार्य के घंटे निकालें। परियोजना प्रबंधन कार्यों को सरल बनाएं.
weight: 13
url: /hi/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks का उपयोग करके कैलेंडर से कार्य के घंटे प्राप्त करें

## परिचय
प्रभावी परियोजना प्रबंधन के लिए परियोजना कैलेंडर प्रबंधित करना और काम के घंटे निकालना आवश्यक है। जावा के लिए Aspose.Tasks एमएस प्रोजेक्ट कैलेंडर से काम के घंटे आसानी से प्राप्त करने के लिए मजबूत कार्यक्षमता प्रदान करता है। इस ट्यूटोरियल में, हम आपको चरण दर चरण प्रक्रिया के बारे में मार्गदर्शन देंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks डाउनलोड किया गया और आपके प्रोजेक्ट में जोड़ा गया। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. जावा प्रोग्रामिंग भाषा की बुनियादी समझ।
## पैकेज आयात करें
सबसे पहले, Java के लिए Aspose.Tasks के साथ काम करने के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.*;
```
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
अपनी MS प्रोजेक्ट फ़ाइल लोड करके प्रारंभ करें:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## चरण 2: कार्य और कैलेंडर जानकारी पुनः प्राप्त करें
प्रोजेक्ट से कार्य और कैलेंडर विवरण निकालें:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## चरण 3: प्रारंभ और समाप्ति तिथियां परिभाषित करें
कार्य के लिए आरंभ और समाप्ति तिथियां निर्धारित करें:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## चरण 4: तिथियों के माध्यम से पुनरावृति करें
कार्य अवधि के भीतर तिथियों के माध्यम से पुनरावृति करें:
```java
java.util.Calendar tempDate = calStartDate;
```
## चरण 5: अवधि की गणना करें
मिनटों, घंटों और दिनों में अवधि की गणना करें:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट कैलेंडर से कार्य के घंटों को पुनः प्राप्त करने का तरीका बताया है। इन चरणों का पालन करके, आप प्रोजेक्ट शेड्यूल को कुशलतापूर्वक प्रबंधित कर सकते हैं और कार्य अवधि की गणना आसानी से कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या जावा के लिए Aspose.Tasks जटिल परियोजना संरचनाओं को संभाल सकता है?
उत्तर: हां, जावा के लिए Aspose.Tasks कार्यों, संसाधनों और कैलेंडर सहित जटिल परियोजना संरचनाओं को संभालने के लिए व्यापक समर्थन प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks MS प्रोजेक्ट के विभिन्न संस्करणों के साथ संगत है?
उत्तर: बिल्कुल, जावा के लिए Aspose.Tasks एमएस प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है, जो विभिन्न वातावरणों में अनुकूलता सुनिश्चित करता है।
### प्रश्न: क्या मैं प्रोजेक्ट कैलेंडर में काम के घंटे और छुट्टियों को अनुकूलित कर सकता हूँ?
उत्तर: हां, आप जावा एपीआई के लिए Aspose.Tasks का उपयोग करके अपनी परियोजना की आवश्यकताओं के अनुसार काम के घंटों और छुट्टियों को आसानी से अनुकूलित कर सकते हैं।
### प्रश्न: क्या जावा के लिए Aspose.Tasks समर्थन और दस्तावेज़ीकरण प्रदान करता है?
उत्तर: हाँ, जावा के लिए Aspose.Tasks डेवलपर्स को अपनी सुविधाओं का प्रभावी ढंग से उपयोग करने में सहायता करने के लिए व्यापक दस्तावेज़ीकरण और समर्पित समर्थन फ़ोरम प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हां, आप जावा के लिए Aspose.Tasks के निःशुल्क परीक्षण संस्करण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
