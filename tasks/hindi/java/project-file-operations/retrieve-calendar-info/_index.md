---
title: Aspose.Tasks में MS प्रोजेक्ट कैलेंडर जानकारी पुनः प्राप्त करें
linktitle: Aspose.Tasks में कैलेंडर जानकारी पुनः प्राप्त करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट कैलेंडर जानकारी पुनर्प्राप्त करना सीखें। प्रोग्रामेटिक रूप से कैलेंडर विवरण तक पहुँचने के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 14
url: /hi/java/project-file-operations/retrieve-calendar-info/
---
## परिचय
इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा लाइब्रेरी के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों से कैलेंडर जानकारी कैसे प्राप्त करें। Aspose.Tasks प्रोजेक्ट डेटा में हेरफेर करने के लिए शक्तिशाली सुविधाएं प्रदान करता है, जिसमें कार्य दिवस और घंटों जैसे कैलेंडर विवरण तक पहुंच शामिल है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Tasks। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
सबसे पहले, आपको Aspose.Tasks कार्यात्मकताओं का उपयोग करने के लिए अपने जावा कोड में आवश्यक पैकेज आयात करने की आवश्यकता है।
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
आइए अब बेहतर समझ के लिए दिए गए उदाहरण को कई चरणों में तोड़ें।
## चरण 1: डेटा निर्देशिका सेट करें
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करें`"Your Data Directory"` आपके प्रोजेक्ट फ़ाइल निर्देशिका के पथ के साथ।
## चरण 2: समय इकाइयों को परिभाषित करें
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
ये स्थिरांक माइक्रोसेकंड में समय इकाइयों का प्रतिनिधित्व करते हैं।
## चरण 3: प्रोजेक्ट इंस्टेंस बनाएं
```java
Project project = new Project(dataDir + "project.mpp");
```
 यह पंक्ति इसका एक उदाहरण बनाती है`Project` क्लास, इसे प्रोजेक्ट फ़ाइल के पथ के साथ प्रारंभ करना (`project.mpp`).
## चरण 4: कैलेंडर जानकारी पुनर्प्राप्त करें
```java
CalendarCollection alCals = project.getCalendars();
```
यहां, हम प्रोजेक्ट फ़ाइल में मौजूद कैलेंडरों का एक संग्रह पुनः प्राप्त करते हैं।
## चरण 5: कैलेंडर के माध्यम से पुनरावृति करें
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // कैलेंडर सूचना
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // सप्ताह के दिनों में पुनरावृति करें
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // समय मिलीसेकंड में
            double time = ts / (OneHour); // घंटों में कनवर्ट करें
            if (wd.getDayWorking()) {
                // कार्य दिवस और घंटे प्रदर्शित करें
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
यह लूप प्रत्येक कैलेंडर के माध्यम से पुनरावृत्त होता है और उसके यूआईडी, नाम और कार्य दिवसों को संबंधित कार्य घंटों के साथ प्रिंट करता है।
## चरण 6: समापन संदेश प्रदर्शित करें
```java
System.out.println("Process completed Successfully");
```
अंत में, प्रक्रिया पूरी होने का संकेत देने वाला एक संदेश प्रदर्शित होता है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से कैलेंडर जानकारी कैसे प्राप्त करें। इन चरणों का पालन करके, आप अपने जावा अनुप्रयोगों में प्रोजेक्ट डेटा तक कुशलतापूर्वक पहुंच और हेरफेर कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हाँ, Aspose.Tasks .NET, C सहित कई प्लेटफ़ॉर्म और प्रोग्रामिंग भाषाओं का समर्थन करता है++, पायथन और जावा।
### प्रश्न: क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हां, आप यहां से नि:शुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं Aspose.Tasks के लिए समर्थन कैसे प्राप्त कर सकता हूं?
उत्तर: आप Aspose.Tasks समुदाय मंच से समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: क्या मैं Aspose.Tasks के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
 उत्तर: हां, अस्थायी लाइसेंस खरीद के लिए उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मुझे Aspose.Tasks के लिए विस्तृत दस्तावेज़ कहां मिल सकते हैं?
 उत्तर: आप दस्तावेज़ का संदर्भ ले सकते हैं[यहाँ](https://reference.aspose.com/tasks/java/).