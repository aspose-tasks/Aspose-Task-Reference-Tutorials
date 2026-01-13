---
date: 2026-01-13
description: Aspose.Tasks ile Java’da kaynak yüzdesi nasıl hesaplanır, MS Project
  kaynakları için tamamlanan iş yüzdesinin nasıl alınacağını öğrenin. Kod örnekleriyle
  adım adım rehber.
linktitle: Perform Percentage Calculations for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks kullanarak Java'da kaynak yüzdesi hesaplama
url: /tr/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Java’da kaynak yüzdesi hesaplama

## Giriş
Hoş geldiniz! Bu öğreticide Aspose.Tasks Java kütüphanesini kullanarak **kaynak yüzdesi nasıl hesaplanır** öğreneceksiniz. Microsoft Project dosyasındaki her bir kaynak için *tamamlanan iş yüzdesi* (percent work complete) değerini nasıl çıkaracağımızı adım adım gösterecek, bu ölçütün neden önemli olduğunu açıklayacak ve ihtiyacınız olan tam kodu sunacağız. Sonunda, kaynak‑yüzde hesaplamalarını herhangi bir Java‑tabanlı proje‑yönetim çözümüne entegre edebileceksiniz.

## Hızlı Yanıtlar
- **“Kaynak yüzdesi” ne anlama gelir?** Bir kaynağın toplam atanmış işine göre tamamladığı işin yüzdesidir.  
- **Bu değeri hangi API çağrısı döndürür?** `Resource` sınıfı üzerinden `Rsc.PERCENT_WORK_COMPLETE`.  
- **Lisans gerekli mi?** Üretim ortamı için geçici veya tam bir Aspose.Tasks lisansı gereklidir.  
- **Diğer Java çerçeveleriyle kullanılabilir mi?** Evet – API Spring, Hibernate ve düz Java projeleriyle çalışır.  
- **Hangi Aspose.Tasks sürümü gerekir?** `Rsc` enumını destekleyen herhangi bir yeni sürüm (ör. 24.x).

## calculate resource percentage java nedir?
Java’da kaynak yüzdesi hesaplamak, bir Microsoft Project dosyasını programlı olarak okuyup her bir kaynağın ne kadar işi tamamladığını belirlemektir. Bu bilgi, proje yöneticilerinin zaman çizelgelerini tahmin etmesine, iş yüklerini dengelemesine ve darboğazları tespit etmesine yardımcı olur.

## Tamamlanan iş yüzdesi neden alınmalı?
- **İlerleme takibi:** Hangi ekip üyelerinin programda olduğunu anında görebilirsiniz.  
- **Kapasite planlaması:** Gerçek performansa göre gelecekteki atamaları ayarlayın.  
- **Raporlama:** Paydaşlar için manuel hesaplamalara gerek kalmadan doğru durum raporları oluşturun.

## Önkoşullar
### Java Geliştirme Ortamı
Java Development Kit (JDK)’nin kurulu olduğundan emin olun. JDK’yi [buradan](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirebilirsiniz.

### Aspose.Tasks Kütüphanesi
Aspose.Tasks kütüphanesini [buradan](https://releases.aspose.com/tasks/java/) indirip projenize ekleyin ve belgelerdeki kurulum talimatlarını [buradan](https://reference.aspose.com/tasks/java/) izleyin.

## Paketleri İçe Aktarma
Kodlamaya başlamadan önce bu öğreticide ihtiyaç duyacağınız paketleri içe aktaralım:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Adım 1: Proje Dosyası Yolunu Ayarlama
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini Microsoft Project dosyanızın bulunduğu klasörle değiştirin.

## Adım 2: Projeyi Yükleme
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Bu kod, belirttiğiniz dizindeki **Software Development.mpp** dosyasını yükler.

## Adım 3: Kaynaklar Üzerinde Döngü
```java
for (Resource res : prj.getResources()) {
```
Projede tanımlı tüm kaynaklar üzerinde döngü kurarız.

## Adım 4: Kaynak Adını Kontrol Et ve Tamamlanan İş Yüzdesini Al
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Kod önce kaynağın bir adı olup olmadığını kontrol eder, ardından o kaynak için **tamamlanan iş yüzdesi** değerini yazdırır.

## Yaygın Sorunlar ve Çözümler
- **NullPointerException** – Proje dosyası yolunun doğru olduğundan ve dosyanın hatasız yüklendiğinden emin olun.  
- **Yanlış yüzdeler** – Kaynağın atanmış işi olduğundan emin olun; aksi takdirde yüzde `0` olur.  
- **Lisans hataları** – Çalışma zamanındaki kısıtlamaları önlemek için geçerli bir Aspose.Tasks lisansı veya geçici değerlendirme lisansı kullanın.

## Sık Sorulan Sorular (Orijinal)

### Aspose.Tasks for Java’yı diğer Java çerçeveleriyle kullanabilir miyim?
Evet, Aspose.Tasks for Java, Spring, Hibernate ve diğer çeşitli Java çerçeveleriyle uyumludur.

### Aspose.Tasks tüm Microsoft Project dosya sürümlerini destekliyor mu?
Aspose.Tasks, MPP, MPT, XML ve daha fazlası dahil olmak üzere tüm Microsoft Project dosya sürümlerini destekler.

### Aspose.Tasks ile proje takvimlerini manipüle edebilir miyim?
Kesinlikle, Aspose.Tasks görevler, kaynaklar, takvimler ve daha fazlası için kapsamlı manipülasyon özellikleri sunar.

### Aspose.Tasks desteği için bir topluluk forumu var mı?
Evet, Aspose.Tasks topluluk forumunda [burada](https://forum.aspose.com/c/tasks/15) yardım alabilir ve diğer kullanıcılarla etkileşime geçebilirsiniz.

### Değerlendirme amaçlı geçici lisanslar sunuluyor mu?
Evet, geçici bir lisans alabilirsiniz; detaylar [burada](https://purchase.aspose.com/temporary-license/) mevcuttur.

## Ek SSS

**S: Çıktıyı yüzde işaretiyle nasıl biçimlendiririm?**  
C: Sayısal değeri `res.get(Rsc.PERCENT_WORK_COMPLETE)` ile alıp `String.format("%.2f%%", value)` kullanarak biçimlendirin.

**S: Yüzdesi %50’nin altında olan kaynakları filtreleyebilir miyim?**  
C: Yazdırmadan önce `if (res.get(Rsc.PERCENT_WORK_COMPLETE) < 50)` koşulunu ekleyin.

**S: Yüzdeleri Project dosyasına geri yazabilir miyim?**  
C: `Rsc.PERCENT_WORK_COMPLETE` alanı yalnızca okunabilir; bunun yerine görev atamalarını ayarlamanız gerekir.

**S: Bu, Project Online (bulut) dosyalarıyla çalışır mı?**  
C: Önce .mpp dosyasını yerel olarak indirmeniz gerekir; Aspose.Tasks dosya formatı ile çalışır, doğrudan bulut hizmetiyle entegrasyon sağlamaz.

## Sonuç
Bu rehberde Aspose.Tasks kullanarak **kaynak yüzdesi nasıl hesaplanır** konusunu gösterdik ve her bir kaynak için *tamamlanan iş yüzdesi* değerini nasıl alacağınızı anlattık. Yukarıdaki adımları izleyerek Java uygulamalarınıza kesin kaynak‑yüzde analizleri ekleyebilir, proje sağlığı ve kaynak kullanımı hakkında daha iyi bir görünürlük elde edebilirsiniz.

---

**Son Güncelleme:** 2026-01-13  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}