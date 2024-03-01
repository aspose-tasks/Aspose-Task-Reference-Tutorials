---
title: Aspose.Tasks'ta Fazla Mesaiyi, Kalan Maliyetleri ve Çalışmayı İzleyin
linktitle: Aspose.Tasks'ta Fazla Mesaiyi, Kalan Maliyetleri ve Çalışmayı İzleyin
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks'ı kullanarak fazla mesaiyi, kalan maliyetleri nasıl izleyeceğinizi ve Java projelerinde nasıl çalışacağınızı öğrenin. Etkili proje yönetimi için kolay adımlar.
type: docs
weight: 18
url: /tr/java/resource-assignments/overtime-remaining-costs-work/
---
## giriiş
Bu eğitimde, fazla mesaiyi, kalan maliyetleri ve bir projede çalışmayı izlemek için Aspose.Tasks for Java'yı nasıl kullanacağımızı öğreneceğiz. Bu, projelerin yolunda ve bütçe dahilinde kalmasını sağlamak için proje yöneticileri ve ekip liderleri için çok değerli olabilir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Aspose.Tasks for Java, Java SE 6 veya üzerini gerektirir.
2.  Aspose.Tasks for Java Library: Kütüphaneyi şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): Eclipse, IntelliJ IDEA veya NetBeans gibi herhangi bir Java IDE.

## Paketleri İçe Aktar
Gerekli paketleri Java dosyanıza aktararak başlayın:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 1. Adım: Veri Dizinini Ayarlayın
Proje dosyanızın bulunduğu dizini tanımlayın:
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` proje dosyanızın yolu ile birlikte.
## Adım 2: Projeyi Yükleyin
 Bir örnek oluştur`Project` nesneyi seçin ve proje dosyasını yükleyin:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Yer değiştirmek`"ResourceAssignmentOvertimes.mpp"` proje dosyanızın adıyla.
## 3. Adım: Kaynak Atamaları Yoluyla Yineleyin
Projedeki her kaynak atamasında döngü yapın:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Adım 4: Fazla Mesai Maliyetlerini ve Çalışmayı Yazdırın
Fazla mesai maliyetlerini alın ve yazdırın ve her kaynak ataması için çalışın:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Adım 5: Kalan Maliyetleri ve İşin Yazdırılması
Kalan maliyetleri alıp yazdırın ve her kaynak ataması için çalışın:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Adım 6: Kalan Fazla Mesai Maliyetlerini ve Çalışmayı Yazdırın
Kalan fazla mesai maliyetlerini alın ve yazdırın ve her kaynak ataması için çalışın:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Çözüm
Bir projedeki fazla mesaiyi, kalan maliyetleri ve çalışmayı izlemek, başarılı proje yönetimi için çok önemlidir. Aspose.Tasks for Java ile bu bilgilere kolayca erişebilir ve bunları takip edebilir, böylece projelerinizin zamanında ve bütçe dahilinde kalmasını sağlayabilirsiniz.
## SSS'ler
### Aspose.Tasks for Java'yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?
Evet, Aspose.Tasks for Java diğer Java kütüphaneleri ve çerçeveleriyle uyumludur.
### Aspose.Tasks farklı proje dosyası formatlarını destekliyor mu?
Evet, Aspose.Tasks MPP, XML ve daha fazlasını içeren çeşitli proje dosyası formatlarını destekler.
### Deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Sorunla karşılaşırsam nereden destek bulabilirim?
 Aspose.Tasks forumunu ziyaret edebilirsiniz[Burada](https://forum.aspose.com/c/tasks/15) destek için.
### Aspose.Tasks için nasıl lisans satın alabilirim?
 adresinden lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).