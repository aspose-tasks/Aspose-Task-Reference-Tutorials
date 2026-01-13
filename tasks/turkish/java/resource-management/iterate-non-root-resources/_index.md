---
date: 2026-01-13
description: Aspose.Tasks for Java kullanarak Microsoft Project dosyalarında kök olmayan
  kaynakları nasıl yineleyebileceğinizi öğrenin.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile Kök Olmayan Kaynakları Yineleme
url: /tr/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile Kök Dışı Kaynakları Döngüleme

## Giriş
Aspose.Tasks for Java, geliştiricilere Microsoft Project dosyalarıyla çalışmak için temiz, nesne‑yönelimli bir yol sunan güçlü bir kütüphanedir. Bu öğreticide **kök dışı kaynakları nasıl döngüleyeceğinizi** öğrenecek, böylece kök yer tutucusuyla uğraşmadan kaynak verilerini okuyabilir, değiştirebilir veya analiz edebilirsiniz. Raporlama aracı, taşıma betiği veya özel bir zamanlayıcı oluşturuyor olun, bu tekniği ustalaşmak kodunuzu daha kesin ve verimli hâle getirecektir.

## Hızlı Yanıtlar
- **“kök dışı kaynak” ne anlama gelir?** Varsayılan “Project” yer tutucusu (kök düğüm) olmayan bir kaynaktır.  
- **Neden kök kaynağı filtreleyelim?** Kök, faydalı zamanlama verisine sahip değildir ve raporları gereksiz yere doldurabilir.  
- **Hangi Aspose.Tasks sınıfı kaynak koleksiyonunu sağlar?** `Project.getResources()`.  
- **Bu kod için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ticari lisans gereklidir.  
- **Bunu Java 17 ile kullanabilir miyim?** Evet – Aspose.Tasks, Java 8 ve üzerini destekler.

## Ön Koşullar
Koda başlamadan önce şunların olduğundan emin olun:

1. **Java Development Kit (JDK)** – En son JDK’yı [Oracle web sitesinden](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirin.  
2. **Aspose.Tasks for Java kütüphanesi** – En son JAR’ı [indirme sayfasından](https://releases.aspose.com/tasks/java/) edinin.  

## Paketleri İçe Aktarma
Java projenizde, gerekli Aspose.Tasks sınıflarını içe aktarın:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Adım 1: Veri Dizinini Ayarlama
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini `.mpp` dosyalarınızın bulunduğu mutlak yol ile değiştirin.

## Adım 2: Proje Dosyasını Yükleme
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Bu, belirttiğiniz klasörden **ResourceCosts.mpp** dosyasını yükleyerek bir `Project` örneği oluşturur.

## Adım 3: Kök Dışı Kaynakları Döngüleme
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Döngü, projedeki her `Resource` nesnesi üzerinden geçer. `isRoot()` kontrolü yerleşik kök kaynağını atlar ve `System.out.println` ifadesi her **kök dışı kaynağın** adını yazdırır.

## Kök Dışı Kaynakları Nasıl Döngüleyebilirsiniz
Yukarıdaki kod parçacığı temel deseni gösterir:

1. `prj.getResources()` ile tam koleksiyonu alın.  
2. `isRoot()` kullanarak yer tutucuyu filtreleyin.  
3. Gerektiği gibi herhangi bir kaynak alanına (ör. `Rsc.NAME`, `Rsc.COST`) erişin.  

Bu deseni maliyetleri toplamak, CSV’ye dışa aktarmak veya özel iş kuralları uygulamak için genişletebilirsiniz.

## Yaygın Tuzaklar ve İpuçları
- **Null kontrolleri** – Bazı kaynakların isteğe bağlı alanları olabilir; `get()` çağırırken her zaman `null` kontrolü yapın.  
- **Performans** – Çok büyük projelerde, ara koleksiyonlar oluşturmaktan kaçınmak için indeks tabanlı bir döngü kullanmayı düşünün.  
- **Lisanslama** – Geçerli bir lisans olmadan kodu çalıştırmak dışa aktarılan dosyalara filigran ekler; lisansınızı uygulamanın erken aşamasında etkinleştirdiğinizden emin olun.

## Sonuç
Bu adımları izleyerek artık Aspose.Tasks for Java kullanarak **kök dışı kaynakları nasıl döngüleyeceğinizi** biliyorsunuz. Bu teknik, gerçek proje kaynaklarına odaklanmanıza, veri çıkarmalarını temizlemenize ve daha güvenilir proje‑yönetim çözümleri oluşturmanıza yardımcı olur.

## SSS
### Aspose.Tasks for Java ile yeni proje dosyaları oluşturabilir miyim?
Evet, Aspose.Tasks, MPP, MPT ve XML proje formatları için tam CRUD (Create, Read, Update, Delete) yetenekleri sunar.  

### Aspose.Tasks tüm Microsoft Project dosya sürümlerini destekliyor mu?
Kesinlikle. Project 2003‑2019 dosyalarını, en yeni MPP spesifikasyonları dahil olmak üzere işler.  

### Aspose.Tasks, Spring gibi Java çerçeveleriyle uyumlu mu?
Evet, kütüphaneyi Spring bean'lerine enjekte edebilir veya herhangi bir standart Java uygulamasında kullanabilirsiniz.  

### Aspose.Tasks ile proje veri alanlarını özelleştirebilir miyim?
Kesinlikle. API, görevlerde, kaynaklarda ve atamalarda özel alanlar eklemenize, değiştirmenize veya silmenize olanak tanır.  

### Aspose.Tasks geliştiriciler için destek ve dokümantasyon sağlıyor mu?
Ürün, kapsamlı API belgeleri, kod örnekleri ve hızlı yardım için özel bir destek forumu içerir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose