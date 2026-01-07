---
date: 2026-01-07
description: Aspose.Tasks kullanarak Java projelerinde proje maliyet izlemeyi, fazla
  mesai takibini, kalan işi hesaplamayı ve maliyetleri yönetmeyi öğrenin. Etkili proje
  yönetimi için kolay adımlar.
linktitle: 'Project Cost Monitoring with Aspose.Tasks: Overtime & Work'
second_title: Aspose.Tasks Java API
title: 'Aspose.Tasks ile Proje Maliyet İzleme: Fazla Mesai ve İş'
url: /tr/java/resource-assignments/overtime-remaining-costs-work/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Proje Maliyet İzleme: Fazla Mesai ve İş

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak **proje maliyet izleme** nasıl yapılacağını keşfedeceksiniz. Fazla mesai, kalan maliyetler ve iş takibini adım adım inceleyecek, böylece projelerinizi zamanında ve bütçe içinde tutabileceksiniz. İster proje yöneticisi, ister ekip lideri olun, bu adımlar finansal ve kaynak ölçütleri üzerinde net bir görünürlük sağlamanıza yardımcı olacaktır.

## Hızlı Yanıtlar
- **Ne izleyebilirim?** Fazla mesai maliyeti, fazla mesai işi, kalan maliyet, kalan iş ve kalan fazla mesai maliyeti.
- **Hangi kütüphane gerekli?** Aspose.Tasks for Java.
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü yeterlidir; üretim için lisans gereklidir.
- **Mevcut .mpp dosyalarını yükleyebilir miyim?** Evet, dosyanın yolunu belirtmeniz yeterlidir.
- **Java 6 yeterli mi?** API, Java SE 6 ve üzeri sürümleri destekler.

## Proje maliyet izleme nedir?
Proje maliyet izleme, bir projenin tüm finansal yönlerini—bütçelenen maliyetler, gerçekleşen harcamalar ve tahmini kalan maliyetler—sürekli olarak takip etme uygulamasıdır. Bu izleme, kaynak atamalarıyla birleştirildiğinde, fazla mesai harcamaları ve iş ilerlemesi hakkında gerçek zamanlı içgörü sağlar.

## Neden fazla mesai ve kalan işi izlemelisiniz?
- **Bütçeleri kontrol edin:** Fazla mesai, beklenmedik maliyet aşımlarına yol açar.
- **Tahminleri iyileştirin:** Kalan işi bilmek, takvimleri proaktif olarak ayarlamanıza yardımcı olur.
- **Şeffaflığı artırın:** Paydaşlar, kaynakların tam olarak nerede tüketildiğini görebilir.

## Ön Koşullar
Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:
1. **Java Development Kit (JDK):** Aspose.Tasks for Java, Java SE 6 veya daha yeni bir sürüm gerektirir.  
2. **Aspose.Tasks for Java Kütüphanesi:** Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirin ve kurun.  
3. **Entegre Geliştirme Ortamı (IDE):** Eclipse, IntelliJ IDEA veya NetBeans gibi herhangi bir Java IDE'si.

## Paketleri İçe Aktarma
Java dosyanızda gerekli paketleri içe aktararak başlayın:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Adım 1: Veri Dizini Ayarlama
Proje dosyanızın bulunduğu dizini tanımlayın:
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini proje dosyanızın yolu ile değiştirin.

## Adım 2: Projeyi Yükleme
Bir `Project` nesnesi oluşturun ve proje dosyasını yükleyin:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
`"ResourceAssignmentOvertimes.mpp"` ifadesini MPP dosyanızın adıyla değiştirin. Bu adım **load mpp file** kullanımını gösterir.

## Adım 3: Kaynak Atamalarını Döngüyle İşleme
Projedeki her bir kaynak atamasını döngüyle işleyin:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```

## Adım 4: Fazla Mesai Maliyetlerini ve İşleri Yazdırma
Her bir kaynak ataması için fazla mesai maliyetlerini ve işleri alın ve yazdırın:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```

## Adım 5: Kalan Maliyetleri ve İşleri Yazdırma
Her bir kaynak ataması için kalan maliyetleri ve işleri alın ve yazdırın:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```

## Adım 6: Kalan Fazla Mesai Maliyetlerini ve İşleri Yazdırma
Her bir kaynak ataması için kalan fazla mesai maliyetlerini ve işleri alın ve yazdırın:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Yaygın Sorunlar ve Çözümler
- **Dosya bulunamadı:** `dataDir` yolunu iki kez kontrol edin ve MPP dosya adının doğru olduğundan emin olun.  
- **Null değerler:** Bazı atamalarda fazla mesai verisi olmayabilir; yazdırırken `null` kontrolü yapın.  
- **Sürüm uyumsuzluğu:** MPP dosya formatına uygun bir kütüphane sürümü kullanın (ör. daha yeni MS Project sürümleri).

## Sık Sorulan Sorular

**S: Aspose.Tasks for Java’yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?**  
C: Evet, Aspose.Tasks for Java diğer Java kütüphaneleri ve çerçeveleriyle uyumludur.

**S: Aspose.Tasks farklı proje dosya formatlarını destekliyor mu?**  
C: Evet, Aspose.Tasks MPP, XML ve daha fazlası dahil olmak üzere çeşitli formatları destekler.

**S: Deneme sürümü mevcut mu?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Sorun yaşarsam nereden destek alabilirim?**  
C: Destek için Aspose.Tasks forumunu [burada](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

**S: Aspose.Tasks için lisans nasıl satın alınır?**  
C: Lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

## Sonuç
Fazla mesai, kalan maliyetler ve işi izlemek, etkili **proje maliyet izleme**nin temel taşlarından biridir. Aspose.Tasks for Java ile bu ölçütleri programlı olarak çıkarabilir, projelerinizi zamanında tutmak ve bütçe sürprizlerinden kaçınmak için gerekli verilere sahip olabilirsiniz. Proje yönetimi araç setinizi daha da güçlendirmek için Aspose.Tasks’in diğer özelliklerini keşfedin.

---

**Son Güncelleme:** 2026-01-07  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}