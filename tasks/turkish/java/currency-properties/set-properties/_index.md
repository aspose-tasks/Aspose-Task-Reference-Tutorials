---
date: 2026-09-09
description: Aspose.Tasks Java projelerinde para birimi simgesini nasıl değiştireceğinizi
  öğrenin, para birimi kodlarını ayarlayın, simgeleri düzenleyin ve Microsoft Project
  dosyaları için özel biçimler uygulayın.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Aspose.Tasks Projelerinde Para Birimi Özelliklerini Ayarlama
og_description: Java kullanarak Aspose.Tasks'te para birimi simgesini nasıl değiştireceğinizi
  öğrenin. Adım adım talimatlar, ön koşullar ve proje maliyet biçimlendirmesini özelleştirme
  ipuçlarını keşfedin.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Aspose.Tasks'te para birimi simgesini değiştirme – Java rehberi
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Aspose.Tasks projelerinde para birimi simgesini değiştirme – Java rehberi
url: /tr/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks – Java rehberinde para birimi simgesini nasıl değiştiririz

## Giriş
Bu öğreticide, Aspose.Tasks Java API'sini kullanarak bir Microsoft Project dosyası için **para birimi simgesini nasıl değiştireceğinizi** öğreneceksiniz. Yurt dışı bir müşteri için raporlar hazırlıyor, birden fazla bölgeye bütçeleri konsolide ediyor ya da sadece şirketinizin muhasebe standartlarına uymanız gerekiyorsa, para birimi simgesini ayarlamak her maliyet‑alanının doğru para işaretini göstermesini sağlar. Kılavuz, geliştirme ortamını kurmaktan değişiklikleri yeni veya mevcut bir proje dosyasında kalıcı hale getirmeye kadar her adımı anlatır.

## Hızlı cevaplar
- **Gerekli kütüphane nedir?** Aspose.Tasks for Java.  
- **Para birimi simgesini değiştirebilir miyim?** Evet – `Prj.CURRENCY_SYMBOL` ayarlayın ve `CurrencySymbolPositionType` seçin.  
- **Hangi dosya formatları destekleniyor?** XML, MPP ve `SaveFileFormat` aracılığıyla birçok diğer format.  
- **Geliştirme için lisansa ihtiyacım var mı?** Ücretsiz deneme sürümü test için çalışır; üretim için bir lisans gereklidir.  
- **Uygulama ne kadar sürer?** Temel bir kurulum için yaklaşık 5‑10 dakika.

## Aspose.Tasks kullanarak Java'da para birimi simgesini nasıl değiştiririz?
Hedef projeyi yükleyin (veya yeni bir tane oluşturun), istenen para birimi özelliklerini ayarlayın ve dosyayı kaydedin. Tüm işlem üç API çağrısından oluşur: bir `Project` nesnesi oluşturmak veya yüklemek, para birimi kodunu, simgesini ve konumunu atamak, ardından `project.save` metodunu çağırmak. Bu yaklaşım, Microsoft Project'in yüklü olmasını gerektirmeden yeni projeler ve mevcut dosyalar için çalışır.

## Neden para birimini değiştirmek için Aspose.Tasks kullanmalısınız?
Aspose.Tasks, **30'dan fazla para birimiyle ilgili özelliği kapsayan tam API** sağlar; böylece kod, simge, ondalık basamaklar ve konumlandırmayı tek bir yerde tanımlayabilirsiniz. Kütüphane, tipik sunucu donanımında çok sayfalı Project dosyalarını bir saniyeden kısa sürede işler ve Windows, Linux ve macOS'ta ek bağımlılıklar olmadan çalışır.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK) 8 veya üzeri** – API en az JDK 8 gerektirir.  
2. **Aspose.Tasks for Java** – en son JAR dosyasını [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. **Bir IDE** – Eclipse, IntelliJ IDEA veya Java destekleyen herhangi bir editör.  
4. **Yazılabilir bir klasör** – oluşturulan proje dosyasının kaydedileceği yer.

## Paketleri içe aktar
Aşağıdaki sınıflar, proje özelliklerine, dosya işlemlerine ve para birimi ayarlarına erişim sağlar.  

`Project` – bellek içinde bir Microsoft Project dosyasını temsil eder.  
`Prj` – para birimi alanları dahil olmak üzere tüm proje‑seviyesi özellikleri için sabitleri içerir.  
`CurrencySymbolPositionType` – para birimi simgesinin olası konumlarını (miktardan önce veya sonra) sıralar.  

Bu içe aktarmalar, kodun bir projeyi manipüle edebilmesi için gereklidir.

## Adım adım kılavuz

### Adım 1: Veri dizinini tanımlayın
Kaynak dosyalarınızı tutan ve çıktının yazılacağı bir klasör seçin. Dizin mevcut olduğundan ve Java sürecinizin yazma iznine sahip olduğundan emin olun.

### Adım 2: Yeni bir proje örneği oluşturun
`Project` sınıfı, Aspose.Tasks'in bellek içinde tek bir Project dosyasını temsil eden üst‑seviye nesnesidir. Örneğini oluşturmak, yapılandırmaya hazır boş bir proje yaratır.

### Adım 3: Para birimi özelliklerini ayarlayın
Burada para birimi kodunu, ondalık basamak sayısını, simgeyi ve simgenin konumunu yapılandırırsınız.

- **Para birimi kodu** – `AUD` veya `USD` gibi üç harfli ISO 4217 kodu.  
- **Ondalık basamaklar** – çoğu para birimi için tipik olarak 2.  
- **Para birimi simgesi** – tutarlarla birlikte gösterilen karakter veya dize, ör. `$` veya `€`.  
- **Simge konumu** – `CurrencySymbolPositionType.Before` simgeyi sayıdan önce, `After` ise sonra yerleştirir.

Bu ayarlar, projedeki her maliyet‑alanını (kaynak oranları, görev bütçeleri vb.) etkiler.

> **Pro tip:** Mevcut bir dosyanın para birimini değiştirmeniz gerekiyorsa, yukarıdaki ayarları uygulamadan önce `new Project("file.mpp")` ile yükleyin.

### Adım 4: Güncellenmiş projeyi kaydedin
Projeyi istediğiniz formatta diske geri yazın. XML formatı insan tarafından okunabilirken, `SaveFileFormat.MPP` Microsoft Project ile tam uyumluluğu korur.

### Adım 5: Başarıyı doğrulayın
İşlemin hatasız tamamlandığını bilmek için kısa bir mesaj veya günlük girdisi yazdırın. Bu, özellikle otomatik süreçlerde faydalıdır.

## Yaygın sorunlar ve çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` geçerli bir yol değil veya yazma izni yok. | Dizin mevcut olduğundan ve Java sürecinizin yazma erişimine sahip olduğundan emin olun. |
| **Currency symbol not showing** | Simge konumu bölgeniz için yanlış ayarlanmış. | Simge miktardan önce gelmesi gerekiyorsa `CurrencySymbolPositionType.Before` kullanın. |
| **Project file does not open in MS Project** | Eski bir formatta uyumsuz ayarlarla kaydedildi. | Son sürüm MS Project ile tam uyumluluk için `SaveFileFormat.MPP` ile kaydedin. |

## Sıkça sorulan sorular

**S: Aspose.Tasks kullanarak tek bir projede birden fazla para birimi ayarlayabilir miyim?**  
A: Evet, proje‑seviyesi para birimi tanımlandıktan sonra, ilgili maliyet alanlarını değiştirerek bireysel kaynaklara veya görevlere farklı para birimi ayarları atayabilirsiniz.

**S: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?**  
A: Kesinlikle. Kütüphane, Project 2000'den en son sürümlere kadar MPP dosyalarını ve ayrıca XML ve diğer değişim formatlarını destekler.

**S: Aspose.Tasks, özel para birimi formatları için destek sağlıyor mu?**  
A: Evet, herhangi bir bölgesel gereksinimi karşılamak için özel simgeler, ondalık basamaklar ve konumlandırma tanımlayabilirsiniz; bu ayarlar kaydedilen dosyada kalıcıdır.

**S: Aspose.Tasks'i diğer Java çerçeveleriyle entegre edebilir miyim?**  
A: Elbette. API tamamen Java olduğundan Spring, Hibernate, Maven, Gradle ve diğer ekosistemlerle sorunsuz çalışır.

**S: Ek yardım veya örnekleri nereden bulabilirim?**  
A: Topluluk desteği için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin veya ayrıntılı API referansları için resmi belgelere bakın.

## Sonuç
Artık Aspose.Tasks projelerinde Java kullanarak **para birimi simgesini nasıl değiştireceğinizi**, para birimi kodunu nasıl ayarlayacağınızı, ondalık basamakları nasıl düzenleyeceğinizi ve özel bir simgeyi nasıl uygulayacağınızı biliyorsunuz. Bu yetenekler, bölge‑spesifik maliyet raporları oluşturmanıza, proje bütçelerini bölgesel muhasebe standartlarıyla uyumlu hale getirmenize ve Microsoft Project dosyalarınızı küresel ekipler arasında tutarlı tutmanıza olanak tanır.

---

**Son Güncelleme:** 2026-09-09  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## İlgili Öğreticiler

- [java proje özellikleri – Aspose.Tasks for Java kullanarak MPP'den para birimi simgesini çıkar](/tasks/java/currency/currency-symbols/)
- [Java ile Aspose.Tasks Projelerinde Para Birimi Özelliklerini Oku](/tasks/java/currency-properties/read-properties/)
- [Java ile Aspose.Tasks kullanarak Para Birimi Kodlarını Yönet](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}