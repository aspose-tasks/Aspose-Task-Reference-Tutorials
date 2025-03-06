---
title: Aspose.Tasks ile Takvimde Hafta Günlerini Tanımlayın
linktitle: Aspose.Tasks ile Takvimde Hafta Günlerini Tanımlayın
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project Takvim'de hafta içi günleri nasıl tanımlayacağınızı öğrenin. Çalışma günlerini ve zamanlamaları zahmetsizce özelleştirin.
type: docs
weight: 12
url: /tr/java/calendars/define-weekdays/
---
## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak bir MS Project Takviminde haftanın günlerini tanımlama sürecini anlatacağız. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmesine olanak tanıyan güçlü bir Java kitaplığıdır.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Oracle web sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) eğer henüz yapmadıysanız.
2.  Aspose.Tasks for Java Library: Aspose.Tasks for Java kütüphanesini aşağıdaki adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/tasks/java/). Belgelerde sağlanan kurulum talimatlarını izleyin.

## Paketleri İçe Aktar
Başlamak için Java projenizde Aspose.Tasks ile çalışmak için gereken gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## 1. Adım: Proje Örneği Oluşturun
Birlikte çalışacağınız MS Project dosyasını temsil eden bir Project nesnesi oluşturun:
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## 2. Adım: Takvimi Tanımlayın
Yeni bir takvim örneği oluşturun ve bunu projeye ekleyin:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## 3. Adım: Çalışma Günlerini Ekleyin
Varsayılan zamanlamalarla Pazartesi'den Perşembe'ye kadar çalışma günlerini tanımlayın:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## 4. Adım: Özel Çalışma Gününü Ayarlayın
Cumartesi ve Pazar'ı iş günü olarak tanımlayın:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Adım 5: Kısa Çalışma Gününü Ayarlayın
Cuma gününü özel çalışma saatleri ile kısa bir çalışma günü olarak ayarlayın:
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
## Adım 6: Projeyi Kaydet
Değiştirilen projeyi bir XML dosyasına kaydedin:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Çözüm
Tebrikler! Aspose.Tasks for Java'yı kullanarak MS Project Takviminde haftanın günlerini başarıyla tanımladınız. MS Project dosyalarını programlı olarak yönetmek için artık bu işlevselliği Java uygulamalarınıza entegre edebilirsiniz.
## SSS'ler
### S1: Aspose.Tasks for Java'yı kullanarak özel çalışma dışı günleri tanımlayabilir miyim?
 C: Evet, özel çalışma dışı günleri ayarlayarak tanımlayabilirsiniz.`DayWorking` mülkiyet`false` ilgili hafta içi gün için.
### S2: Tatilleri takvime nasıl ekleyebilirim?
 C: Örnekler oluşturarak tatil ekleyebilirsiniz.`CalendarExceptions`ve çalışılmayan tarihlerin belirtilmesi.
### S3: Aspose.Tasks, MS Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks, MPP, MPT ve XML formatları da dahil olmak üzere MS Project dosyalarının çeşitli sürümlerini destekler.
### S4: Bir MS Project dosyasındaki mevcut takvimleri değiştirebilir miyim?
C: Evet, mevcut bir projeye takvimler yükleyebilir, değişiklikler yapabilir ve ardından değişiklikleri orijinal dosyaya geri kaydedebilirsiniz.
### S5: Aspose.Tasks tekrarlanan görevler için destek sağlıyor mu?
C: Evet, Aspose.Tasks, yinelenme düzenlerini ve sürelerini tanımlamak dahil, yinelenen görevlerle çalışmanıza olanak tanır.