---
date: 2026-09-14
description: Aspose.Tasks kullanarak Java'da para birimi formatını nasıl değiştireceğinizi
  ve para birimi özelliklerini nasıl okuyacağınızı öğrenin. Para birimi kodunu çıkarın,
  para birimi simgesini alın ve MS Project dosyalarında proje para birimini güncelleyin.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: Para birimi formatını nasıl değiştirirsiniz
og_description: Aspose.Tasks kullanarak Java'da para birimi formatını nasıl değiştireceğinizi
  ve para birimi özelliklerini nasıl okuyacağınızı öğrenin. Para birimi kodunu çıkarmak
  ve proje para birimini güncellemek için adım adım rehber.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Java'da Aspose.Tasks ile para birimi formatını nasıl değiştirirsiniz
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Java'da Aspose.Tasks ile para birimi formatını nasıl değiştirirsiniz
url: /tr/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java ile Aspose.Tasks'de Para Birimi Özelliklerini Okuma

## Giriş
Bu öğreticide, Aspose.Tasks kullanan Java projelerinde **para birimi biçimini değiştirmeyi** ve para birimi özelliklerini okumayı öğreneceksiniz. Doğru finansal veriler çok uluslu ekipler için hayati öneme sahiptir ve bu API'lerde uzmanlaşmak, ISO‑4217 kodunu çıkarmanıza, para birimi simgesini almanıza ve proje para ayarlarını manuel elektronik tablo düzenlemelerine gerek kalmadan güncellemenize olanak tanır.

## Hızlı Yanıtlar
- **“read currency” ne anlama geliyor?** Bu, bir Project dosyası içinde depolanan para birimi kodunu, simgesini ve sayı‑formatı ayarlarını çıkarmak anlamına gelir.  
- **Neden para birimi ayarlarını ayarlamalısınız?** Maliyet raporlarını bölgesel geleneklerle uyumlu hale getirmek ve dönüşüm hatalarından kaçınmak için.  
- **Bir lisansa ihtiyacım var mı?** Evet – üretim için geçerli bir Aspose.Tasks for Java lisansı gereklidir; değerlendirme için ücretsiz deneme sürümü çalışır.  
- **Hangi Project sürümleri destekleniyor?** Hem *.mpp* (Project 2007‑2024) hem de *.xml* formatları tam olarak desteklenir, 20 yılı aşkın dosya sürümünü kapsar.  
- **Ek bir kurulum gerekli mi?** Sadece Aspose.Tasks for Java JAR dosyasını sınıf yolunuza ekleyin ve ilgili sınıfları içe aktarın.

## Aspose.Tasks projelerinde Java ile Para Birimi Özelliklerini Okuma
Proje yönetiminin dinamik dünyasında, para birimi detaylarını çıkarmak doğru mali analiz için gereklidir. Özel rehberimiz **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)**, bir proje dosyasını açmaktan para birimi kodunu, simgesini ve biçimini almaya kadar her adımı size gösterir. Öğreticiyi izleyerek şunları yapabileceksiniz:

* Proje boyunca kullanılan para birimi kodunu (ör. USD, EUR) alabilirsiniz.  
* Para birimi simgesine ve sayı‑biçimlendirme ayarlarına erişebilirsiniz.  
* Bu bilgileri yerelleştirilmiş mali raporlar oluşturmak veya finansal gösterge panellerine beslemek için kullanabilirsiniz.

## Aspose.Tasks ile Java’da para birimi kodunu nasıl çıkarılır
`Project.getCurrencyCode()` yöntemi, projenin para birimi birimi için üç harflik ISO‑4217 tanımlayıcısını döndürür.

**Doğrudan cevap:** `project.getCurrencyCode()` çağırarak **USD** veya **EUR** gibi bir para birimi kodu elde edebilirsiniz; ardından bu değeri saklayabilir, kaydedebilir veya dönüşüm için dış finansal servislere aktarabilirsiniz. Bu tek satırlık çağrı, tüm desteklenen Project sürümlerinde çalışan güvenilir, standart‑tabanlı bir tanımlayıcı sağlar.

Yöntem, standart bir kod bekleyen ERP sistemleriyle proje verilerini senkronize etmenin hızlı bir yolunu sunar.

## Aspose.Tasks ile Java’da para birimi biçimini nasıl ayarlarsınız
Parasal değerlerin görsel temsilini değiştirmek üç basit özellik aracılığıyla yapılır.

`project.setCurrencySymbol(String)` para değerleri için görüntülenen para birimi simgesini ayarlar.  
`project.setCurrencyDecimalSeparator(char)` tam sayı kısmını kesirli kısımdan ayırmak için kullanılan karakteri tanımlar.  
`project.setCurrencyThousandsSeparator(char)` binlik grupları ayırmak için kullanılan karakteri tanımlar.

**Doğrudan cevap:** Sırasıyla simge, ondalık ayırıcı ve binlik ayırıcıyı tanımlamak için `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")` ve `project.setCurrencyThousandsSeparator(".")` kullanın — bu, para birimi biçimini tek seferde tamamen değiştirir. Bu ayarları düzenlemek, tüm paydaşların sayıları tanıdık bir biçimde görmesini sağlar ve yanlış yorumlamaları azaltır.

* `project.setCurrencySymbol("€")` – görsel simgeyi ayarlar.  
* `project.setCurrencyDecimalSeparator(",")` – ondalık ayırıcıyı tanımlar.  
* `project.setCurrencyThousandsSeparator(".")` – binlik ayırıcıyı tanımlar.  

## Aspose.Tasks projelerinde para birimi özelliklerini nasıl ayarlarsınız
Bir proje yeni bir pazara gittiğinde veya bir müşteri farklı bir para birimi formatı talep ettiğinde, para birimini programlı olarak güncellemeniz gerekir.

`project.setCurrencyCode(String)` proje için ISO‑4217 para birimi kodunu tanımlar.

**Doğrudan cevap:** `project.setCurrencyCode("GBP")` ile birlikte `project.setCurrencySymbol("£")` ve uygun ayırıcıları çağırın, ardından projeyi kaydedin; kütüphane, mevcut mali verileri korurken tüm görüntüleme ayarlarını günceller. Bu yaklaşım, takviminizin finansal temsilini tam kontrol etmenizi sağlar.

Adım‑adım rehberimiz **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)** şunların nasıl yapılacağını açıklar:

* Tüm proje için yeni bir para birimi kodu ve simgesi tanımlayın.  
* Sayı biçimini (ondalık basamaklar, binlik ayırıcılar) yerel geleneklere uyacak şekilde ayarlayın.  
* Güncellenmiş proje dosyasını mevcut verileri kaybetmeden kaydedin.

Para birimini nasıl ayarlayacağınızı öğrenerek, USD, GBP, JPY veya desteklenen herhangi bir para birimi arasında anında geçiş yapabilirsiniz.

## Aspose.Tasks’te para birimi yönetimini neden öğrenmelisiniz?
Doğru para birimi yönetimi maliyetli yanlış yorumlamaları ortadan kaldırır ve küresel iş birliğini kolaylaştırır.

**Doğrudan cevap:** Para birimi yönetimini öğrenmek, maliyetleri her ekibin yerel formatında sunmanızı, doğru raporlama sağlamanızı, bölgesel muhasebe standartlarına uymanızı ve otomatik finansal iş akışlarını etkinleştirmenizi sağlar — proje başına saatler süren manuel yeniden biçimlendirmeyi tasarruf eder.

* **Küresel iş birliği:** Farklı ülkelerdeki ekipler maliyetleri kendi yerel formatlarında görebilir.  
* **Doğru raporlama:** Bütçeyi etkileyebilecek yuvarlama veya dönüşüm hatalarını önler.  
* **Uyumluluk:** Bölgesel muhasebe standartları ve müşteri gereksinimleriyle uyum sağlar.  
* **Otomasyon:** Proje oluşturulurken para birimi ayarlarını programlı olarak uygulayarak manuel düzenlemeleri azaltır.

## Gerçek dünya kullanım örnekleri
* **Çok uluslu projeler:** Avrupa ve Kuzey Amerika’da sahaları yöneten bir inşaat firması, bütçeleri hem EUR hem de USD olarak sunmalıdır.  
* **Finansal denetimler:** Denetçiler, her maliyet girişi için para birimi bağlamını net bir şekilde görmek ister.  
* **Dinamik fiyatlandırma modelleri:** SaaS sağlayıcıları, abonelik maliyetlerini müşterinin yerel para birimine göre ayarlar.

## Yaygın tuzaklar ve ipuçları
* **Tuzak:** Kodu değiştirdikten sonra para birimi simgesini güncellemeyi unutmak.  
  **İpucu:** Eşleşmeyen görüntülemeleri önlemek için kod ve simgeyi her zaman birlikte ayarlayın.  
* **Tuzak:** Kodu çalıştıran makinenin varsayılan yerel ayarına güvenmek.  
  **İpucu:** Ortamlar arasında tutarlılığı sağlamak için Aspose.Tasks kodunuzda istenen para birimi biçimini açıkça belirtin.  

## Para birimi özellikleri öğreticileri
### [Aspose.Tasks Projelerinde Para Birimi Özelliklerini Okuma](./read-properties/)
Aspose.Tasks for Java kullanarak MS Project dosyalarından para birimi bilgilerini nasıl çıkaracağınızı öğrenin. Adım‑adım rehber sağlanmıştır.

### [Aspose.Tasks Projelerinde Para Birimi Özelliklerini Ayarlama](./set-properties/)
Java kullanarak Aspose.Tasks projelerinde para birimi özelliklerini nasıl ayarlayacağınızı öğrenin. Microsoft Project dosyalarını zahmetsizce manipüle edin.

## Sıkça Sorulan Sorular

**Q: Proje zaten kaydedildikten sonra para birimini değiştirebilir miyim?**  
A: Evet. `Project.setCurrencyCode()` ve ilgili yöntemleri kullanın, ardından projeyi tekrar kaydedin.

**Q: Para birimini değiştirmek mevcut maliyet değerlerini etkiler mi?**  
A: Sayısal değerler değişmez; sadece görüntüleme biçimi (simge, ondalık ayırıcı) güncellenir. Para birimleri arasında dönüşüm gerekiyorsa maliyetleri yeniden hesaplamalısınız.

**Q: Tanımlayabileceğim para birimi sayısı konusunda bir sınırlama var mı?**  
A: Aspose.Tasks herhangi bir ISO‑4217 para birimi kodunu destekler, bu yüzden pratikte sınırsızdır.

**Q: Desteklenmeyen bir para birimi koduyla bir proje açarsam ne olur?**  
A: Kütüphane varsayılan para birimine (USD) geri döner ve bir uyarı kaydeder; istediğiniz para birimini manuel olarak ayarlayarak bunu geçersiz kılabilirsiniz.

**Q: Bir Project XML dosyasında para birimi özelliklerini okuma/yazma mümkün mü?**  
A: Kesinlikle. Aynı API hem *.mpp* hem de *.xml* formatları için çalışır.

**Son Güncelleme:** 2026-09-14  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [java proje özellikleri – Aspose.Tasks for Java kullanarak MPP'den para birimi simgesi çıkarma](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks ile MS Project'ten Para Birimi Nasıl Alınır](/tasks/java/currency/currency-codes/)
- [Project Özellikleri Java – Aspose.Tasks ile Meta Verileri Okuma](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}