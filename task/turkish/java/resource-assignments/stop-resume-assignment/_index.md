---
title: Aspose.Tasks'ta Kaynak Atamalarını Durdurun ve Sürdürün
linktitle: Aspose.Tasks'ta Kaynak Atamalarını Durdurun ve Sürdürün
second_title: Aspose.Tasks Java API'si
description: Bu adım adım eğitimle Aspose.Tasks for Java'da kaynak atamalarını etkili bir şekilde nasıl yöneteceğinizi öğrenin.
type: docs
weight: 23
url: /tr/java/resource-assignments/stop-resume-assignment/
---
## giriiş
Bu eğitimde Aspose.Tasks for Java'yı kullanarak kaynak atamalarını nasıl durduracağımızı ve devam ettireceğimizi öğreneceğiz. Aspose.Tasks, geliştiricilerin sistemlerinde Microsoft Project'in kurulu olmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmasına olanak tanıyan güçlü bir Java API'sidir. Takip edilmesini kolaylaştırmak için süreci yönetilebilir adımlara ayıracağız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Tasks for Java kütüphanesi indirildi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
- Java programlamanın temel anlayışı.
## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projemize aktaralım:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Adım 1: Proje Dosyasını Yükleyin
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
// Proje dosyasını yükleyin
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 Bu adımda proje dosyasını bir klasöre yüklüyoruz.`Project` dosya yolunu kullanarak nesne.
## Adım 2: Kaynak Atamaları Yoluyla Yineleyin
```java
// Minimum tarihi tanımlayın
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Kaynak atamalarını yineleyin
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Burada minimum bir tarih tanımlıyoruz ve projedeki her kaynak atamasını yinelemeye başlıyoruz.
## 3. Adım: Durdurma ve Devam Etme Tarihlerini Kontrol Edin
```java
    // Durdurma tarihini kontrol edin
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Özgeçmiş tarihini kontrol edin
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Bu adımda her kaynak atamasının durma ve devam etme tarihlerinin minimum tarihten önce olup olmadığını kontrol ederiz. Eğer öyleyse, "NA" yazdırırız, aksi halde ilgili tarihleri yazdırırız.
## Çözüm
Bu eğitimde Aspose.Tasks for Java'da kaynak atamalarını nasıl durduracağımızı ve devam ettireceğimizi öğrendik. Verilen adımları takip ederek bu işlevselliği Java projelerinize kolayca uygulayabilirsiniz.

## SSS'ler
### Aspose.Tasks'ı Microsoft Project yüklü olmadan kullanabilir miyim?
Evet, Aspose.Tasks, sisteminizde Microsoft Project'in kurulu olmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmanıza olanak tanır.
### Daha fazla belgeyi nerede bulabilirim?
 Ayrıntılı belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/tasks/java/).
### Ücretsiz deneme mevcut mu?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### Herhangi bir sorunla karşılaşırsam nasıl destek alabilirim?
Toplumdan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).
### Geçici lisans satın alabilir miyim?
 Evet, geçici lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).