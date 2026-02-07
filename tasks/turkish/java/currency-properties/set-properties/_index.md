---
date: 2026-02-07
description: Aspose.Tasks projelerinde para birimi kodunu Java’da nasıl ayarlayacağınızı,
  para birimi simgesini nasıl değiştireceğinizi ve Microsoft Project dosyaları için
  özel bir para birimi formatı nasıl uygulayacağınızı öğrenin.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: para birimi kodu java – Aspose.Tasks projelerinde nasıl ayarlanır
url: /tr/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks – Java Rehberi'nde Para Birimi Kodu Nasıl Ayarlanır

## Introduction
Bu öğreticide, Aspose.Tasks Java API'sini kullanarak bir Microsoft Project dosyası için **para birimi kodunu nasıl ayarlayacağınızı** öğreneceksiniz. Uluslararası ekipler için *para birimini değiştirme*, *para birimi simgesini* ayarlama veya **özel para birimi formatı** uygulama ihtiyacınız olsun, aşağıdaki adımlar size süreci açık açıklamalar ve çalıştırmaya hazır kodlarla gösterecek.

## Quick Answers
- **Gerekli kütüphane nedir?** Aspose.Tasks for Java.  
- **Para birimi simgesini değiştirebilir miyim?** Evet – `CurrencySymbolPositionType` ve `Prj.CURRENCY_SYMBOL` kullanın.  
- **Hangi dosya formatları destekleniyor?** XML, MPP ve `SaveFileFormat` aracılığıyla birçok diğer format.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü çalışır; üretim için lisans gereklidir.  
- **Uygulama ne kadar sürer?** Temel bir kurulum için yaklaşık 5‑10 dakika.

## Aspose.Tasks'te Java ile Para Birimi Kodu Nasıl Ayarlanır
Bir projenin para birimi, maliyet değerlerinin nasıl gösterileceğini tanımlar—kod (ör. `AUD`), ondalık basamak sayısı, simge (`$`) ve simgenin konumu. Bu özellikleri ayarlamak, her maliyetle ilgili alanın (kaynak oranları, görev bütçeleri vb.) izleyiciniz için doğru para birimi formatını yansıtmasını sağlar.

## Why Use Aspose.Tasks to Change Currency?
- **Microsoft Project kurulumu gerekmez** – dosyaları herhangi bir sunucuda işleyin.  
- **Tam API kapsamı** – tüm para birimiyle ilgili alanlar `Prj` sabitleri aracılığıyla sunulur.  
- **Çapraz platform** – Windows, Linux ve macOS'ta herhangi bir Java uyumlu IDE ile çalışır.  
- **Yüksek performans** – büyük proje dosyalarını hızlı ve güvenilir bir şekilde işleyin.  
- **Özel para birimi formatını destekler** – bölgesel standartlara uygun simgeler, ondalık basamaklar ve konumlandırma tanımlayabilirsiniz.

## Prerequisites
Başlamadan önce şunların yüklü olduğundan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – en son JAR dosyasını [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. **Bir IDE** – Eclipse, IntelliJ IDEA veya tercih ettiğiniz herhangi bir editör.  
4. **Yazılabilir bir klasör** – oluşturulan proje dosyasının kaydedileceği yer.

## Import Packages
İlk olarak, proje özelliklerine ve dosya işlemlerine erişim sağlayan sınıfları içe aktarın.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Adım 1: Veri Dizini Tanımlama  
Kaynak dosyalarınızı içeren ve çıktının yazılacağı klasörü belirtin.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Adım 2: Yeni Bir Project Örneği Oluşturma  
Yeni bir `Project` nesnesi oluşturun. Bu nesne, bellek içindeki bir Microsoft Project dosyasını temsil eder.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Adım 3: Para Birimi Özelliklerini Ayarlama  
Burada **para birimini nasıl ayarlayacağımız** kod, basamak, simge ve simge konumu gibi detayları ayarlıyoruz.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** Mevcut bir dosya için **proje para birimini değiştirmek** istiyorsanız, yukarıdaki ayarları uygulamadan önce `new Project("file.mpp")` ile yükleyin.

### Step 4: Save the Updated Project
Adım 4: Güncellenmiş Projeyi Kaydetme  
Projeyi istenen formatta diske yazın. Bu örnekte XML formatını kullanıyoruz, ancak `SaveFileFormat.MPP` de seçilebilir.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Adım 5: Başarıyı Doğrulama  
İşlemin hatasız tamamlandığını göstermek için dostça bir mesaj yazdırın.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **`project.save` üzerinde `NullPointerException`** | `dataDir` geçerli bir yol değil veya yazma izni yok. | Dizinin var olduğundan ve Java sürecinizin yazma erişimine sahip olduğundan emin olun. |
| **Para birimi simgesi görünmüyor** | Simge konumu bölgeniz için yanlış ayarlanmış. | Simge miktardan önce gelmesi gerekiyorsa `CurrencySymbolPositionType.Before` kullanın. |
| **Proje dosyası MS Project'te açılamıyor** | Eski bir formatta uyumsuz ayarlarla kaydedildi. | Son sürüm MS Project ile tam uyumluluk için `SaveFileFormat.MPP` ile kaydedin. |

## Frequently Asked Questions

**S: Aspose.Tasks kullanarak tek bir projede birden fazla para birimi ayarlayabilir miyim?**  
C: Evet, Aspose.Tasks, para birimi özelliklerini kaynak‑bazlı veya görev‑bazlı olarak ayarlayarak tek bir proje dosyasında birden fazla para birimini yönetmenize olanak tanır.

**S: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?**  
C: Kesinlikle. Kütüphane, Project 2000'den en yeni sürümlere kadar MPP dosyalarını, ayrıca XML ve diğer formatları destekler.

**S: Aspose.Tasks, özel para birimi formatları için destek sağlıyor mu?**  
C: Evet, herhangi bir bölgesel gereksinimi karşılamak için özel simgeler, ondalık basamaklar ve konumlandırma tanımlayabilirsiniz.

**S: Aspose.Tasks'i diğer Java kütüphaneleri veya çerçeveleriyle entegre edebilir miyim?**  
C: Elbette. API saf Java olduğundan Spring, Hibernate, Maven, Gradle ve diğer ekosistemlerle sorunsuz çalışır.

**S: Aspose.Tasks için ek destek veya yardım nereden bulabilirim?**  
C: Topluluk yardımı için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin veya ayrıntılı API referansları için resmi dokümantasyona bakın.

## Conclusion
Artık **para birimi kodunu java ile nasıl ayarlayacağınızı**, **para birimi** değerlerini nasıl **değiştireceğinizi** ve **para birimi simgesini** Aspose.Tasks for Java kullanarak nasıl **değiştireceğinizi** biliyorsunuz. Bu yetenekler, maliyet verilerini küresel ekipler için özelleştirmenize, yerel raporlar oluşturmanıza ve proje dosyalarınızı sınırlar arasında tutarlı tutmanıza olanak tanır.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}