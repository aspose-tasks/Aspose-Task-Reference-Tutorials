---
title: Aspose.Tasks'ta Takvim İstisnalarını Yönetin
linktitle: Aspose.Tasks'ta Takvim İstisnaları Ekleme ve Kaldırma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'da takvim istisnalarını verimli bir şekilde nasıl ekleyip kaldıracağınızı öğrenin. Proje yönetimi iş akışlarını zahmetsizce geliştirin.
type: docs
weight: 10
url: /tr/java/calendar-exceptions/add-remove/
---

## giriiş
Proje yönetiminde, takvimlerdeki istisnaların ele alınması, görevlerin doğru şekilde planlanması ve kaynakların yönetilmesi açısından çok önemlidir. Aspose.Tasks for Java, takvim istisnalarını zahmetsizce eklemek ve kaldırmak için güçlü işlevler sağlar. Bu eğitimde size süreç boyunca adım adım rehberlik edeceğiz.
#### Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Sisteminizde kurulu Java Geliştirme Kiti (JDK)
- Aspose.Tasks for Java kütüphanesi indirilip projenizde yapılandırıldı
- Java programlama dili ve proje yönetimi kavramlarına ilişkin temel anlayış

## Paketleri İçe Aktar
Aspose.Tasks işlevlerini etkili bir şekilde kullanmak için öncelikle Java sınıfınıza gerekli paketleri içe aktardığınızdan emin olun.
```java
import com.aspose.tasks.*;
```
## 1. Adım: Projeyi Yükleyin ve Takvime Erişin
Proje dosyanızı yükleyerek ve istisna eklemek veya kaldırmak istediğiniz takvime erişerek başlayın.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```
## 2. Adım: Bir İstisnayı Kaldırma
Mevcut bir istisnayı takvimden kaldırmak için, herhangi bir istisna olup olmadığını kontrol edin ve ardından istediğiniz istisnayı kaldırın.
```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```
## 3. Adım: Bir İstisna Ekleyin
 Takvime yeni bir istisna eklemek için bir`CalendarException` nesneyi oluşturun ve başlangıç ve bitiş tarihlerini tanımlayın.
```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```
## Adım 4: İstisnaları Görüntüleyin
Son olarak, doğrulama veya daha ileri işlemler için eklenen istisnaları görüntüleyebilirsiniz.
```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From" + calExc1.getFromDate().toString());
    System.out.println("To" + calExc1.getToDate().toString());
}
```

## Çözüm
Takvim istisnalarını yönetmek, doğru proje planlaması ve kaynak tahsisi için çok önemlidir. Aspose.Tasks for Java ile proje zaman çizelgelerinizin etkili bir şekilde korunmasını sağlamak için istisnaları zahmetsizce ekleyip kaldırabilirsiniz.

## SSS'ler
### S: Aspose.Tasks for Java'yı kullanarak bir takvime birden fazla istisna ekleyebilir miyim?

C: Evet, istisnalar listesini yineleyerek ve her birini ayrı ayrı ekleyerek bir takvime birden fazla istisna ekleyebilirsiniz.

### S: Aspose.Tasks for Java, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mudur?

C: Aspose.Tasks for Java, Microsoft Project dosyalarının çeşitli sürümleriyle uyumluluk sağlayarak proje yönetimi iş akışlarınızla kusursuz entegrasyon sağlar.

### S: Proje takvimlerinde yinelenen istisnaları nasıl ele alabilirim?

C: Aspose.Tasks for Java, proje takvimlerinde yinelenen istisnaları ele almak için güçlü özellikler sunarak, karmaşık yineleme modellerini kolaylıkla tanımlamanıza olanak tanır.

### S: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?

 C: Evet, Aspose.Tasks for Java'nın ücretsiz deneme sürümüne şu adresten erişebilirsiniz:[İnternet sitesi](https://releases.aspose.com/) Bir satın alma işlemi yapmadan önce özelliklerini keşfetmek için.

### S: Aspose.Tasks for Java ile ilgili herhangi bir sorun veya soru için nereden destek alabilirim?

 C: Java için Aspose.Tasks forumunu ziyaret edebilirsiniz.[İnternet sitesi](https://reference.aspose.com/tasks/java/) topluluktan yardım istemek veya kişiselleştirilmiş yardım için doğrudan destek ekibiyle iletişime geçmek.
