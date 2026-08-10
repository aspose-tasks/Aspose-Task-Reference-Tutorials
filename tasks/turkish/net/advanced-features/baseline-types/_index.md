---
date: 2026-04-30
description: Aspose.Tasks for .NET kullanarak temel çizgiyi nasıl ayarlayacağınızı
  ve proje temel çizgilerini verimli bir şekilde nasıl yöneteceğinizi öğrenin.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Aspose.Tasks'te Farklı Baseline Türleri
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Temel Çizgi Nasıl Ayarlanır – Farklı Temel Çizgi Türleri
url: /tr/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Farklı Baseline Türleri

## Giriş

Proje yönetiminde, **baseline nasıl ayarlanır** sorusunun doğru yanıtı, projenin yolunda gitmesi ile kontrolden çıkması arasındaki farkı yaratabilir. Aspose.Tasks for .NET, baseline'ları oluşturmak, güncellemek ve karşılaştırmak için tam özellikli bir API sağlar ve **proje ilerlemesini** orijinal plana karşı izleyebilmenizi sağlar. Bu öğreticide, bir baseline nasıl ayarlanır, birden fazla baseline türüyle nasıl çalışılır ve verileri projenizin **baseline ile gerçek takvim** karşılaştırması için nasıl analiz edebileceğinizi öğreneceksiniz.

## Hızlı Yanıtlar
- **Baseline nedir?** Projede belirli bir noktada alınan takvim, maliyet ve iş verilerinin bir anlık görüntüsü.  
- **Aspose.Tasks kaç baseline depolayabilir?** Proje başına en fazla 11 ayrı baseline.  
- **Baseline neden ayarlanır?** Gerçek performansı orijinal planla karşılaştırmak ve sapmaları belirlemek için.  
- **Bunu denemek için lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim kullanımı için lisans gereklidir.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Tasks'te “baseline nasıl ayarlanır” nedir?
Baseline ayarlamak, bir `Project` nesnesi üzerinde `SetBaseline` metodunu çağırmak anlamına gelir. API, birden fazla `BaselineType` değerinden (Baseline, Baseline1 … Baseline10) seçim yapmanıza olanak tanır, böylece projenin ilerlemesi sırasında tarihsel anlık görüntüleri tutabilirsiniz.

## Proje baseline'larını neden yönetmeliyiz?
- **Varyansı ölç:** Görevlerin takvimde ileride mi yoksa geride mi olduğunu hızlıca görün.  
- **Maliyet kontrolü:** Baseline maliyetini gerçek harcama ile karşılaştırın.  
- **Paydaş raporlaması:** Baseline verilerini PDF, XLSX veya diğer formatlarda dışa aktararak net iletişim sağlayın.  
- **Senaryo planlaması:** “Ne olurdu” takvimlerini değerlendirmek için birden fazla baseline saklayın.

## Önkoşullar

### 1. C# ve .NET Framework'e aşinalık
C# sınıfları, metodları ve nesne‑yönelimli kavramlar hakkında temel bir anlayış gereklidir.

### 2. Aspose.Tasks for .NET'in kurulumu
Kütüphanenin projenize eklendiğinden emin olun. [Aspose.Tasks web sitesinden](https://releases.aspose.com/tasks/net/) indirebilir veya NuGet üzerinden kurabilirsiniz.

### 3. Entegre Geliştirme Ortamı (IDE)
C# kodunu yazmak, derlemek ve hata ayıklamak için Visual Studio (veya uyumlu herhangi bir IDE) önerilir.

## Ad Alanlarını İçe Aktarma

Aspose.Tasks ile C# projemizde çalışmaya başlamadan önce, gerekli sınıflara ve metodlara erişmek için gerekli ad alanlarını içe aktarmamız gerekir. Aşağıdaki adımları izleyin:

```csharp

```

Önkoşullarımızı kurup gerekli ad alanlarını içe aktardığımıza göre, Aspose.Tasks for .NET kullanarak farklı baseline türlerini ayarlamaya başlayalım. Her örneği netlik ve anlaşılabilirlik için birden fazla adıma ayıracağız.

## Aspose.Tasks'te Baseline Nasıl Ayarlanır

### Adım 1: Proje Dosyasını Yükle
İlk olarak, baseline'ı ayarlamayı planladığımız proje dosyasını yüklememiz gerekir. Bu adım, bir `Project` nesnesi başlatmayı ve proje dosyasını yüklemeyi içerir. İşte nasıl yapabileceğiniz:

```csharp
var project = new Project("Project2.mpp");
```

### Adım 2: Baseline Ayarla
Proje yüklendikten sonra, baseline'ı ayarlamaya geçebiliriz. Baseline'lar, projenin ilk takvimine ait bir anlık görüntü sağlar ve proje ilerledikçe karşılaştırma için bir referans noktası olur. Baseline'ı ayarlamak için `SetBaseline` metodunu kullanın. Örneğin, tüm proje için baseline ayarlamak istiyorsanız `BaselineType.Baseline` enum'ını kullanın:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Adım 3: Proje Baseline'larıyla Çalış
Baseline ayarlandıktan sonra, proje ilerlemesini doğru bir şekilde analiz etmek ve izlemek için çeşitli proje baseline alanlarıyla çalışabilirsiniz. Bu adım, başlangıç tarihleri, bitiş tarihleri, süreler ve maliyetler gibi baseline verilerine erişmeyi içerir. İhtiyacınıza göre baseline verilerini işlemek için Aspose.Tasks'in sunduğu zengin özelliklerden yararlanabilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **Baseline uygulanmadı:** `SetBaseline` metodunu çağırdıktan sonra proje dosyasının kaydedildiğinden emin olun. Değişiklikleri kalıcı hale getirmek için `project.Save("output.mpp");` kullanın.  
- **Birden fazla baseline çakışması:** Birden fazla baseline ayarlarken doğru `BaselineType` değerini (ör. `Baseline1`, `Baseline2`) belirtin.  
- **Sürüm uyumsuzluğu:** Aspose.Tasks DLL sürümünün hedef .NET çalışma zamanı ile eşleştiğini doğrulayın.

## Sıkça Sorulan Sorular

**Q:** Aspose.Tasks for .NET kullanarak tek bir proje için birden fazla baseline ayarlayabilir miyim?  
**A:** Evet, Aspose.Tasks bir proje için 11'e kadar baseline ayarlamaya izin verir ve kapsamlı izleme yetenekleri sunar.

**Q:** Aspose.Tasks farklı proje dosyası formatlarıyla uyumlu mu?  
**A:** Kesinlikle! Aspose.Tasks, MPP, XML ve MPX gibi çeşitli proje dosyası formatlarını destekler ve farklı platformlarda uyumluluk sağlar.

**Q:** Projemde baseline verilerini nasıl görselleştirebilirim?  
**A:** Aspose.Tasks'i kullanarak proje verilerini PDF veya XLSX gibi popüler dosya formatlarına dışa aktarabilir, böylece baseline bilgilerini kolayca görselleştirip paylaşabilirsiniz.

**Q:** Aspose.Tasks, proje yönetim araçlarıyla entegrasyon desteği sunuyor mu?  
**A:** Aspose.Tasks, geliştiricilerin özelliklerini popüler proje yönetim araçları ve platformlarıyla sorunsuz bir şekilde entegre etmelerine yardımcı olmak için kapsamlı belgeler ve destek forumları sağlar.

**Q:** Aspose.Tasks'i satın almadan önce deneyebilir miyim?  
**A:** Evet, web sitesinde bulunan ücretsiz deneme sürümüyle Aspose.Tasks'i keşfedebilir ve yeteneklerini doğrudan deneyimleyebilirsiniz.

---

**Son Güncelleme:** 2026-04-30  
**Test Edilen:** Aspose.Tasks for .NET (latest stable release)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}