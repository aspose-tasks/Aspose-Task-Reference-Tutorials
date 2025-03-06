---
title: Aspose.Tasks'ı kullanarak Takvim'den Çalışma Saatlerini alın
linktitle: Aspose.Tasks'ı kullanarak Takvim'den Çalışma Saatlerini alın
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java ile MS Project takvimlerinden çalışma saatlerini kolayca çıkarın. Proje yönetimi görevlerini basitleştirin.
weight: 13
url: /tr/java/calendars/working-hours/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ı kullanarak Takvim'den Çalışma Saatlerini alın

## giriiş
Proje takvimlerini yönetmek ve çalışma saatlerini çıkarmak, etkili proje yönetimi için çok önemlidir. Aspose.Tasks for Java, MS Project takvimlerinden çalışma saatlerini zahmetsizce almak için güçlü işlevsellik sağlar. Bu eğitimde size süreç boyunca adım adım rehberlik edeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Tasks for Java kütüphanesi indirildi ve projenize eklendi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Java programlama dilinin temel anlayışı.
## Paketleri İçe Aktar
Öncelikle Aspose.Tasks for Java ile çalışmak için gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.*;
```
## Adım 1: Proje Dosyasını Yükleyin
MS Project dosyanızı yükleyerek başlayın:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 2. Adım: Görev ve Takvim Bilgilerini Alın
Projeden görev ve takvim ayrıntılarını çıkarın:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## 3. Adım: Başlangıç ve Bitiş Tarihlerini Tanımlayın
Görevin başlangıç ve bitiş tarihlerini ayarlayın:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Adım 4: Tarihler Arasında Yineleme Yapın
Görev süresi içinde tarihler arasında yineleme yapın:
```java
java.util.Calendar tempDate = calStartDate;
```
## Adım 5: Süreyi Hesaplayın
Süreyi dakika, saat ve gün cinsinden hesaplayın:
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
## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak bir MS Project takviminden çalışma saatlerinin nasıl alınacağını ele aldık. Bu adımları izleyerek proje programlarını verimli bir şekilde yönetebilir ve görev sürelerini kolaylıkla hesaplayabilirsiniz.
## SSS'ler
### S: Aspose.Tasks for Java karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks for Java, görevler, kaynaklar ve takvimler de dahil olmak üzere karmaşık proje yapılarının yönetilmesi için kapsamlı destek sağlar.
### S: Aspose.Tasks for Java, MS Project'in farklı sürümleriyle uyumlu mudur?
C: Kesinlikle, Aspose.Tasks for Java, MS Project'in çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### S: Proje takvimlerinde çalışma saatlerini ve tatilleri özelleştirebilir miyim?
C: Evet, Aspose.Tasks for Java API'lerini kullanarak çalışma saatlerini ve tatillerini proje gereksinimlerinize göre kolayca özelleştirebilirsiniz.
### S: Aspose.Tasks for Java destek ve dokümantasyon sunuyor mu?
C: Evet, Aspose.Tasks for Java, geliştiricilerin özelliklerini etkili bir şekilde kullanmalarına yardımcı olmak için kapsamlı belgeler ve özel destek forumları sağlar.
### S: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks for Java'nın ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
