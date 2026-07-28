---
date: 2026-01-28
description: Aspose.Tasks for Java kullanarak takvim istisnası oluşturmayı, takvim
  istisnalarını verimli bir şekilde eklemeyi ve kaldırmayı ve proje planlamasını geliştirmeyi
  öğrenin.
linktitle: Add and Remove Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose for Java ile Takvim İstisnası Oluştur
url: /tr/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java için Aspose Takvim İstisnası Oluşturma

## Giriş
Doğru proje zamanlaması, **takvim istisnaları**—kaynakların kullanılamadığı veya çalışma programlarının değiştiği günlerin—ele alınmasına bağlıdır. **Aspose.Tasks for Java** ile **takvim istisnası** nesneleri oluşturabilir, bunları bir proje takvimine ekleyebilir veya artık ihtiyaç duyulmadığında kaldırabilirsiniz. Bu öğreticide, bir proje dosyasını yüklemekten yönetilen istisnaları doğrulamaya kadar tüm süreci adım adım inceleyeceğiz. Bu kılavuz, Java ortamında **takvim istisnası aspose** oluşturmanın tam olarak nasıl yapılacağını gösterir.

### Hızlı Cevaplar
- **“takvim istisnası oluşturma” ne anlama geliyor?** Standart çalışma takviminden sapma gösteren bir tarih aralığı tanımlamaktır.  
- **Bu yeteneği hangi kütüphane sağlıyor?** Aspose.Tasks for Java.  
- **Denemek için lisansa ihtiyacım var mı?** Ücretsiz bir deneme sürümü mevcuttur; üretim kullanımı için lisans gereklidir.  
- **Mevcut bir istisnayı kaldırabilir miyim?** Evet—takvimin istisna listesindeki öğeyi bulup silebilirsiniz.  
- **Bu, Microsoft Project dosyalarıyla uyumlu mu?** Kesinlikle; Aspose.Tasks tüm büyük .mpp sürümlerini okur ve yazar.

#### Önkoşullar
Başlamadan önce şunların yüklü olduğundan emin olun:

- Java Development Kit (JDK) kurulu.
- Aspose.Tasks for Java kütüphanesi projenizin sınıf yoluna eklenmiş.
- Java ve proje‑yönetimi terminolojisine temel bir anlayış.

## Java ile Aspose takvim istisnası nasıl oluşturulur
Aşağıda, her kod parçacığının amacını çalıştırmadan önce açıklayan adım adım bir rehber bulunmaktadır. Takvim istisnalarınızın doğru şekilde işlenmesini sağlamak için bu bölümleri sırayla izleyin.

## Paketleri İçe Aktar
Takvim manipülasyonunu sağlayan temel Aspose.Tasks sınıflarını içe aktarın.

```java
import com.aspose.tasks.*;
```

## Adım 1: Projeyi Yükleyin ve Takvimine Erişin
Mevcut bir Microsoft Project dosyasını (`input.mpp`) yükleyip koleksiyondaki ilk takvimi alın. Farklı bir takvim gerekiyorsa indeksi değiştirebilirsiniz.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Adım 2: Mevcut Bir İstisnayı Kaldırın (Gerekirse)
Bazen bir takvimde temizlemek istediğiniz istisnalar bulunur. Aşağıdaki kod, istisna listesi birden fazla öğe içeriyorsa ilk öğeyi kaldırır.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **İpucu:** Öğeleri kaldırmadan önce istisna listesinin boyutunu kontrol edin; aksi takdirde `IndexOutOfBoundsException` alabilirsiniz.

## Adım 3: Yeni Bir Takvim İstisnası Oluşturun (Ekle)
Şimdi **takvim istisnası** nesneleri **oluşturuyoruz**. Bu örnekte 1‑3 Ocak 2009 tarihlerini kapsayan bir istisna tanımlıyoruz. Tarihleri kendi proje zaman çizelgenize göre ayarlayın.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Neden Önemli:** İstisnalar eklemek, tatilleri, bakım pencerelerini veya herhangi bir çalışmayan dönemi doğrudan proje takvimine modellemenizi sağlar. Bu, **takvim istisnası aspose** işlevinin temelidir.

## Adım 4: Doğrulama İçin Tüm İstisnaları Görüntüleyin
İstisna ekledikten (veya kaldırdıktan) sonra, bunları ekrana yazdırmak iyi bir uygulamadır. Böylece takviminizin istenen değişiklikleri yansıtıp yansıtmadığını teyit edebilirsiniz.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|------|
| Çıktı gelmiyor | İstisna listesi boş | İterasyona başlamadan önce bir istisna eklediğinizden emin olun. |
| `NullPointerException` proje üzerinde | Dosya yolu hatalı | `dataDir` değişkeninin geçerli bir `.mpp` dosyasına işaret ettiğini doğrulayın. |
| Tarihler bir gün gecikiyor | Zaman dilimi farkları | Açık zaman dilimiyle `java.util.Calendar` veya `java.time` API kullanın. |

## Sık Sorulan Sorular

**S: Aspose.Tasks for Java kullanarak bir takvime birden fazla istisna ekleyebilir miyim?**  
C: Evet. Her tarih aralığı için yeni bir `CalendarException` oluşturup `cal.getExceptions()` koleksiyonuna bir döngü içinde ekleyebilirsiniz.

**S: Aspose.Tasks for Java, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mu?**  
C: Aspose.Tasks, Project 98'den en yeni sürümlere kadar geniş bir .mpp sürüm yelpazesini destekler, sorunsuz entegrasyon sağlar.

**S: Proje takvimlerinde yinelenen istisnalar (ör. haftalık toplantılar) nasıl yönetilir?**  
C: `CalendarException` sınıfının yineleme özelliklerini (`setRecurrencePattern`) kullanarak günlük, haftalık veya aylık gibi karmaşık desenler tanımlayabilirsiniz.

**S: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?**  
C: Evet, tüm özellikleri satın almadan keşfetmek için [web sitesinden](https://releases.aspose.com/) ücretsiz bir deneme indirebilirsiniz.

**S: Aspose.Tasks for Java ile ilgili sorunlar veya sorular için nereden destek alabilirim?**  
C: Java için Aspose.Tasks forumuna [web sitesinden](https://reference.aspose.com/tasks/java/) ulaşabilir, sorularınızı sorabilir veya doğrudan Aspose destek ekibiyle iletişime geçebilirsiniz.

## Sonuç
Takvim istisnalarını yönetmek, gerçekçi proje zaman çizelgeleri ve kaynak planlaması için kritiktir. **Aspose.Tasks for Java** ile **takvim istisnası** nesneleri oluşturabilir, herhangi bir proje takvimine ekleyebilir ve artık gerekli olmadığında kaldırabilirsiniz—bunun için sadece birkaç satır kod yeterlidir. Bu **takvim istisnası aspose** yeteneği, gerçek dünya kısıtlamalarını yansıtan takvimler oluşturmanızı sağlar.

---

**Son Güncelleme:** 2026-01-28  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}