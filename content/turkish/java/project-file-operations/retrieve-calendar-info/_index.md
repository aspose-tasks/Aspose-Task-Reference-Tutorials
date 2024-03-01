---
title: Aspose.Tasks'ta MS Project Takvim Bilgilerini Alma
linktitle: Aspose.Tasks'ta Takvim Bilgilerini Alma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project takvim bilgilerini nasıl alacağınızı öğrenin. Takvim ayrıntılarına programlı olarak erişmek için adım adım kılavuz.
type: docs
weight: 14
url: /tr/java/project-file-operations/retrieve-calendar-info/
---
## giriiş
Bu eğitimde Aspose.Tasks for Java kütüphanesini kullanarak Microsoft Project dosyalarından takvim bilgilerinin nasıl alınacağını inceleyeceğiz. Aspose.Tasks, çalışma günleri ve saatleri gibi takvim ayrıntılarına erişim de dahil olmak üzere proje verilerini yönetmek için güçlü özellikler sunar.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Tasks Java kütüphanesi için. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Aspose.Tasks işlevlerini kullanmak için öncelikle Java kodunuza gerekli paketleri içe aktarmanız gerekir.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Şimdi daha iyi anlamak için verilen örneği birden fazla adıma ayıralım.
## 1. Adım: Veri Dizinini Ayarlayın
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` proje dosyaları dizininizin yolu ile.
## Adım 2: Zaman Birimlerini Tanımlayın
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Bu sabitler mikrosaniye cinsinden zaman birimlerini temsil eder.
## 3. Adım: Proje Örneği Oluşturun
```java
Project project = new Project(dataDir + "project.mpp");
```
 Bu satır şunun bir örneğini oluşturur:`Project` sınıf, onu proje dosyasının yolu ile başlatıyor (`project.mpp`).
## 4. Adım: Takvim Bilgilerini Alın
```java
CalendarCollection alCals = project.getCalendars();
```
Burada proje dosyasında bulunan takvimlerin bir koleksiyonunu alıyoruz.
## Adım 5: Takvimleri Yineleyin
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Takvim Bilgileri
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Hafta İçi Günler Boyunca Yineleyin
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Milisaniye cinsinden süre
            double time = ts / (OneHour); // Saatlere dönüştür
            if (wd.getDayWorking()) {
                // Çalışma Günlerini ve Saatlerini Görüntüle
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Bu döngü her takvimde yinelenir ve UID'sini, adını ve çalışma günlerini ilgili çalışma saatleriyle birlikte yazdırır.
## Adım 6: Tamamlama Mesajını Görüntüleyin
```java
System.out.println("Process completed Successfully");
```
Son olarak işlemin tamamlandığını belirten bir mesaj görüntülenir.
## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak MS Project dosyalarından takvim bilgilerinin nasıl alınacağını öğrendik. Bu adımları izleyerek Java uygulamalarınızdaki proje verilerine verimli bir şekilde erişebilir ve bunları yönetebilirsiniz.

## SSS'ler
### S: Aspose.Tasks'ı diğer programlama dilleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks, .NET, C dahil olmak üzere birden fazla platformu ve programlama dilini destekler++, Python ve Java.
### S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks için nasıl destek alabilirim?
C: Aspose.Tasks topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks için geçici lisans satın alabilir miyim?
 C: Evet, geçici lisanslar satın alınabilir[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks için ayrıntılı belgeleri nerede bulabilirim?
 C: Belgelere başvurabilirsiniz[Burada](https://reference.aspose.com/tasks/java/).