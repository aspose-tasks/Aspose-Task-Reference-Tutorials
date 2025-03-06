---
title: Aspose.Tasks में कैलेंडर अपवाद प्रबंधित करें
linktitle: Aspose.Tasks में कैलेंडर अपवाद जोड़ें और हटाएँ
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks में कैलेंडर अपवादों को कुशलतापूर्वक जोड़ने और हटाने का तरीका जानें। परियोजना प्रबंधन वर्कफ़्लो को सहजता से बढ़ाएँ।
weight: 10
url: /hi/java/calendar-exceptions/add-remove/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कैलेंडर अपवाद प्रबंधित करें


## परिचय
परियोजना प्रबंधन में, कार्यों को सटीक रूप से शेड्यूल करने और संसाधनों के प्रबंधन के लिए कैलेंडर के भीतर अपवादों को संभालना महत्वपूर्ण है। जावा के लिए Aspose.Tasks कैलेंडर अपवादों को आसानी से जोड़ने और हटाने के लिए शक्तिशाली कार्यक्षमता प्रदान करता है। इस ट्यूटोरियल में, हम आपको चरण दर चरण प्रक्रिया के बारे में मार्गदर्शन देंगे।
#### आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है
- जावा लाइब्रेरी के लिए Aspose.Tasks को आपके प्रोजेक्ट में डाउनलोड और कॉन्फ़िगर किया गया है
- जावा प्रोग्रामिंग भाषा और परियोजना प्रबंधन अवधारणाओं की बुनियादी समझ

## पैकेज आयात करें
सबसे पहले, Aspose.Tasks कार्यक्षमताओं का प्रभावी ढंग से उपयोग करने के लिए अपने जावा क्लास में आवश्यक पैकेज आयात करना सुनिश्चित करें।
```java
import com.aspose.tasks.*;
```
## चरण 1: प्रोजेक्ट लोड करें और कैलेंडर एक्सेस करें
अपनी प्रोजेक्ट फ़ाइल लोड करके और उस कैलेंडर तक पहुँचकर शुरुआत करें जिसमें आप अपवाद जोड़ना या हटाना चाहते हैं।
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```
## चरण 2: एक अपवाद हटाएँ
कैलेंडर से किसी मौजूदा अपवाद को हटाने के लिए, जांचें कि क्या कोई अपवाद मौजूद है और फिर वांछित अपवाद को हटा दें।
```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```
## चरण 3: एक अपवाद जोड़ें
 कैलेंडर में एक नया अपवाद जोड़ने के लिए, एक बनाएं`CalendarException` ऑब्जेक्ट करें और इसकी आरंभ और समाप्ति तिथियां परिभाषित करें।
```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```
## चरण 4: अपवाद प्रदर्शित करें
अंत में, आप सत्यापन या आगे की प्रक्रिया के लिए अतिरिक्त अपवाद प्रदर्शित कर सकते हैं।
```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From" + calExc1.getFromDate().toString());
    System.out.println("To" + calExc1.getToDate().toString());
}
```

## निष्कर्ष
सटीक प्रोजेक्ट शेड्यूलिंग और संसाधन आवंटन के लिए कैलेंडर अपवादों को प्रबंधित करना आवश्यक है। जावा के लिए Aspose.Tasks के साथ, आप आसानी से अपवाद जोड़ और हटा सकते हैं ताकि यह सुनिश्चित हो सके कि आपकी परियोजना की समयसीमा प्रभावी ढंग से बनी रहे।

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks का उपयोग करके एक कैलेंडर में एकाधिक अपवाद जोड़ सकता हूँ?

उत्तर: हां, आप अपवाद सूची को दोहराकर और प्रत्येक को अलग-अलग जोड़कर एक कैलेंडर में कई अपवाद जोड़ सकते हैं।

### प्रश्न: क्या जावा के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के सभी संस्करणों के साथ संगत है?

उ: जावा के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ अनुकूलता प्रदान करता है, जो आपके प्रोजेक्ट प्रबंधन वर्कफ़्लो के साथ सहज एकीकरण सुनिश्चित करता है।

### प्रश्न: मैं प्रोजेक्ट कैलेंडर में आवर्ती अपवादों को कैसे संभाल सकता हूं?

उत्तर: जावा के लिए Aspose.Tasks प्रोजेक्ट कैलेंडर में आवर्ती अपवादों को संभालने के लिए मजबूत सुविधाएँ प्रदान करता है, जिससे आप जटिल पुनरावृत्ति पैटर्न को आसानी से परिभाषित कर सकते हैं।

### प्रश्न: क्या जावा के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?

 उत्तर: हां, आप जावा के लिए Aspose.Tasks के निःशुल्क परीक्षण संस्करण तक पहुंच सकते हैं[वेबसाइट](https://releases.aspose.com/) खरीदारी करने से पहले इसकी विशेषताओं का पता लगाएं।

### प्रश्न: मैं जावा के लिए Aspose.Tasks से संबंधित किसी भी मुद्दे या प्रश्न के लिए समर्थन कहां से प्राप्त कर सकता हूं?

 उ: आप जावा के लिए Aspose.Tasks फोरम पर जा सकते हैं[वेबसाइट](https://reference.aspose.com/tasks/java/) समुदाय से सहायता लेने के लिए या वैयक्तिकृत सहायता के लिए सहायता टीम से सीधे संपर्क करने के लिए।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
