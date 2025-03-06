---
title: Aspose.Tasks ile MS Project Takviminden Çalışma Haftalarını Okuyun
linktitle: Aspose.Tasks ile Takvimden Çalışma Haftalarını Okuyun
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project takviminden çalışma haftalarını nasıl okuyacağınızı öğrenin. Bu kapsamlı eğitimde adım adım talimatlar alın.
type: docs
weight: 15
url: /tr/java/calendars/read-work-weeks/
---
## giriiş
Bu eğitimde, Microsoft Project takviminden çalışma haftası bilgilerini okumak için Aspose.Tasks for Java'nın nasıl kullanılacağını keşfedeceğiz. Aspose.Tasks, Microsoft Project belgelerini programlı olarak değiştirmenize ve yönetmenize olanak tanıyan güçlü bir Java kitaplığıdır.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Tasks for Java kütüphanesi indirildi ve kuruldu. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
İlk olarak kodumuza başlamak için gerekli paketleri içe aktaralım:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## 1. Adım: Veri Dizininizi Kurun
MS Project dosyanızın bulunduğu dizin yolunu ayarlayın:
```java
String dataDir = "Your Data Directory";
```
## 2. Adım: Proje Örneği Oluşturun ve Takvime Erişin
Project sınıfının yeni bir örneğini oluşturun ve takvim ve çalışma haftaları koleksiyonuna erişin:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## 3. Adım: Çalışma Haftaları Boyunca Yineleyin
Çalışma haftalarının toplanması boyunca yineleyin ve bilgilerini görüntüleyin:
```java
for (WorkWeek workWeek : collection) {
    // Çalışma haftasının adını, başlangıç ve bitiş tarihlerini görüntüle
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Hafta günlerine ve çalışma saatlerine erişin
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Gerekirse daha fazla proses çalışma süresi
    }
}
```
## Çözüm
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak bir Microsoft Project takviminden çalışma haftası bilgilerinin nasıl okunacağını öğrendik. Bu güçlü kitaplık, Proje dosyalarının sorunsuz şekilde değiştirilmesine olanak tanıyarak geliştiricilerin çeşitli görevleri verimli bir şekilde otomatikleştirmesine olanak tanır.
## SSS'ler
### Aspose.Tasks for Java'yı kullanarak çalışma haftası bilgilerini değiştirebilir miyim?
Evet, Aspose.Tasks, çalışma haftalarını ve bunlarla ilgili bilgileri değiştirmek, eklemek veya silmek için API'ler sağlar.
### Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?
Evet, Aspose.Tasks, MPP ve XML formatları da dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### Aspose.Tasks'i diğer Java çerçeveleriyle entegre edebilir miyim?
Kesinlikle Aspose.Tasks, gelişmiş işlevsellik için diğer Java çerçeveleri ve kitaplıklarıyla sorunsuz bir şekilde entegre edilebilir.
### Aspose.Tasks'ın deneme sürümü mevcut mu?
 Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Tasks için desteği nerede bulabilirim?
Aspose.Tasks forumunda destek ve yardım bulabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).