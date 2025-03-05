---
title: Aspose.Tasks में छवि को अलग करने के लिए पेज प्रिंट करें
linktitle: Aspose.Tasks में छवि को अलग करने के लिए पेज प्रिंट करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks में छवियों को अलग करने के लिए पृष्ठों को प्रिंट करना सीखें। इस चरण-दर-चरण मार्गदर्शिका के साथ प्रोजेक्ट विज़ुअलाइज़ेशन में सुधार करें।
type: docs
weight: 22
url: /hi/java/project-management/print-pages/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके छवियों को अलग करने के लिए पृष्ठों को प्रिंट करने की प्रक्रिया में आपका मार्गदर्शन करेंगे। यह कार्यक्षमता विशेष रूप से तब उपयोगी हो सकती है जब आपको प्रोजेक्ट लेआउट या महत्वपूर्ण कार्यों को अलग से देखने की आवश्यकता हो।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें। आप इसे यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
अपनी जावा फ़ाइल की शुरुआत में आवश्यक पैकेज आयात करना सुनिश्चित करें:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## चरण 1: प्रोजेक्ट डेटा लोड करें
सबसे पहले, अपनी एमपीपी फ़ाइल से प्रोजेक्ट डेटा लोड करें:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## चरण 2: छवि सहेजें विकल्प सेट करें
छवि को सहेजने के विकल्पों को परिभाषित करें, जिसमें प्रारंभ तिथि, समाप्ति तिथि, महत्वपूर्ण कार्य, किंवदंती और ग्रिडलाइन शामिल हैं:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## चरण 3: ग्रिडलाइन्स को अनुकूलित करें
प्रकार, रंग और पैटर्न निर्दिष्ट करते हुए छवि के लिए ग्रिडलाइन कस्टमाइज़ करें:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## चरण 4: छवियाँ सहेजें
प्रोजेक्ट लेआउट को छवियों के रूप में सहेजें, एकल फ़ाइल और अलग फ़ाइलों दोनों के रूप में:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने दिखाया है कि जावा के लिए Aspose.Tasks का उपयोग करके छवियों को अलग करने के लिए पृष्ठों को कैसे प्रिंट किया जाए। ऊपर बताए गए चरणों का पालन करके, आप अपनी आवश्यकताओं के अनुसार प्रोजेक्ट लेआउट और महत्वपूर्ण कार्यों की कुशलता से कल्पना कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं प्रोजेक्ट लेआउट सहेजते समय छवि प्रारूप को अनुकूलित कर सकता हूँ?
 उ: हां, जावा के लिए Aspose.Tasks पीएनजी, जेपीईजी, बीएमपी आदि जैसे विभिन्न छवि प्रारूपों का समर्थन करता है। आप वांछित प्रारूप निर्दिष्ट कर सकते हैं`ImageSaveOptions` कक्षा।
### प्रश्न: क्या जावा के लिए Aspose.Tasks विभिन्न जावा विकास परिवेशों के साथ संगत है?
उत्तर: हां, जावा के लिए Aspose.Tasks अधिकांश जावा विकास परिवेशों के साथ संगत है, जिसमें Eclipse, IntelliJ IDEA और NetBeans शामिल हैं।
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks को अपने मावेन या ग्रैडल प्रोजेक्ट में एकीकृत कर सकता हूँ?
उत्तर: हाँ, आप अपने में उचित निर्भरता जोड़कर जावा के लिए Aspose.Tasks को अपने मावेन या ग्रैडल प्रोजेक्ट में आसानी से एकीकृत कर सकते हैं।`pom.xml` या`build.gradle` फ़ाइल।
### प्रश्न: क्या जावा के लिए Aspose.Tasks प्रोजेक्ट डेटा को छवियों के अलावा अन्य प्रारूपों में निर्यात करने का समर्थन करता है?
उत्तर: हां, जावा के लिए Aspose.Tasks प्रोजेक्ट डेटा को पीडीएफ, HTML, XLSX आदि जैसे विभिन्न प्रारूपों में निर्यात करने का समर्थन करता है, जो डेटा विज़ुअलाइज़ेशन और रिपोर्टिंग में लचीलापन प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks के लिए कोई सामुदायिक सहायता उपलब्ध है?
 उत्तर: हां, आप सामुदायिक सहायता पा सकते हैं, प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं के साथ जुड़ सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).