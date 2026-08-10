---
date: 2026-03-27
description: Aspose.Tasks for Java kullanarak MS Project taslak kodlarını programlı
  olarak nasıl alacağınızı öğrenin. Proje yönetimi yeteneklerinizi geliştirin.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te MS Project Taslak Kodlarını Al
url: /tr/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Taslak Kodlarını Aspose.Tasks ile Almak

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak **ms project outline kodlarını nasıl alacağınızı** keşfedeceksiniz. MS Project'teki outline kodları, görevleri, kaynakları ve atamaları kategorize etmenin güçlü bir yolunu sunar ve bunlara programlı olarak erişmek, özel raporlama, otomasyon veya entegrasyon çözümleri oluşturmanıza olanak tanır. Kendi projenize kopyalayabileceğiniz eksiksiz, adım adım bir örnek üzerinden ilerleyeceğiz.

## Hızlı Yanıtlar
- **Kod ne yapıyor?** Bir Project dosyasını yükler ve her outline kod tanımını, maskelerini ve değerlerini yazdırır.  
- **Hangi kütüphane gerekli?** Aspose.Tasks for Java (herhangi bir güncel sürüm).  
- **Lisans gerekli mi?** Geliştirme için bir deneme sürümü çalışır; üretim için tam lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri.  
- **Kodları aldıktan sonra değiştirebilir miyim?** Evet – aynı API, outline kodlarını eklemenize, düzenlemenize veya silmenize olanak tanır.

## ms project outline kodları nedir?
Outline kodları, proje yöneticilerinin varsayılan hiyerarşinin ötesinde görevleri gruplandırıp filtrelemesini sağlayan özel alanlardır. Basit sayısal değerler, metin dizileri veya organizasyon seviyesinde tanımlanan kurumsal çapta özel kodlar olabilirler. Bu kodları okuyarak panoları besleyebilir, veri dışa aktarabilir veya adlandırma kurallarını otomatik olarak uygulayabilirsiniz.

## Aspose.Tasks ile ms project outline kodlarını neden almalı?
- **Otomasyon:** Raporlar oluşturun veya manuel dışa aktarım olmadan iş akışlarını tetikleyin.  
- **Entegrasyon:** Outline kodlarını ERP, PPM veya BI araçlarıyla senkronize edin.  
- **Özelleştirme:** Kod değerlerine dayalı iş kurallarını uygulayın (ör. maliyet tahsisi).  
- **Çapraz platform:** Windows, Linux ve macOS'ta çalışır, Microsoft Project UI'sinden bağımsızdır.

## Outline kodları için MPP dosyaları nasıl okunur?
MPP (Microsoft Project) dosyasını okumak, outline kodlarını çıkarmanın ilk adımıdır. Aspose.Tasks dosya formatını soyutlar, böylece ikili yapıyı kendiniz ayrıştırmanız gerekmez. `Project` sınıfı ağır işleri halleder ve gerçekten ihtiyacınız olan verilere odaklanmanızı sağlar.

## MS Project'teki özel alanlar
Outline kodları, MS Project'te bir **özel alan** türüdür. Standart alanlar tarihleri, süreleri ve kaynakları kapsarken, özel alanlar organizasyona özgü bilgileri depolamanıza olanak tanır. Aspose.Tasks aracılığıyla bunlara erişmek, aynı programatik esnekliği sağlar.

## Önkoşullar
Başlamadan önce, aşağıdaki önkoşulların kurulu olduğundan emin olun:

### 1. Java Development Environment
Sisteminizde Java Development Kit (JDK) yüklü olduğundan emin olun. JDK'yı Oracle web sitesinden indirip kurabilirsiniz.

### 2. Aspose.Tasks Library
Aspose.Tasks kütüphanesini Java projenize indirin ve ekleyin. Kütüphaneyi [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) adresinden indirebilirsiniz.

## Paketleri İçe Aktarma
İlk olarak, Java kodunuzda Aspose.Tasks'ten gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Şimdi sağlanan örnek kodu birden fazla adıma ayıralım:

## Adım 1: Projeyi Yükle
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Bu adımda, verilen dosya adını kullanarak Microsoft Project dosyasını bir `Project` nesnesine yüklüyoruz.

## Adım 2: Outline Kodlarını Al
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Projede bulunan her outline kod tanımı üzerinde döngü yapıyoruz.

## Adım 3: Outline Kod Özelliklerine Erişme
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Alias, Field ID ve Field Name gibi outline kod tanımının çeşitli özelliklerini alıp yazdırıyoruz.

## Adım 4: Kurumsal Özel Kodu Kontrol Et
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Outline kodunun kurumsal bir özel kod olup olmadığını kontrol ediyor ve sonuca göre yazdırıyoruz.

## Adım 5: Outline Kod Maskelerini Göster
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Outline koduna bağlı her maskeyi döngüyle işleyip seviyesini ve mask değerini yazdırıyoruz.

## Adım 6: Outline Kod Değerlerini Göster
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Her outline kod değerini döngüyle işleyip açıklamasını, değer ID'sini, değerini ve tipini yazdırıyoruz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Çıktı yok** | Proje dosyası yolu hatalı | `projectName`'in geçerli bir `.mpp` dosyasına işaret ettiğini doğrulayın. |
| **Null değerler** | Outline kodu dosyada tanımlı değil | Project dosyasının gerçekten outline kodları içerdiğinden emin olun (MS Project UI'da kontrol edin). |
| **LicenseException** | Uygun aktivasyon olmadan deneme sürümü kullanılıyor | Geçici veya tam lisansı şu şekilde uygulayın: `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java'ı bir Project dosyasındaki outline kodlarını değiştirmek için kullanabilir miyim?**  
A: Evet, Aspose.Tasks for Java, outline kodlarını programlı olarak değiştirmek için API'ler sağlar. Aynı `Project` nesnesini kullanarak tanımları ekleyebilir, düzenleyebilir veya silebilirsiniz.

**Q: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?**  
A: Evet, Aspose.Tasks for Java'ın ücretsiz deneme sürümünü [Aspose.Tasks web sitesinden](https://releases.aspose.com/) indirebilirsiniz.

**Q: Aspose.Tasks for Java için teknik destek nasıl alabilirim?**  
A: Teknik desteği, [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret ederek ve sorularınızı orada göndererek alabilirsiniz.

**Q: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?**  
A: Evet, Aspose.Tasks for Java için geçici lisansı [satın alma sayfasından](https://purchase.aspose.com/temporary-license/) satın alabilirsiniz.

**Q: Aspose.Tasks for Java için tam belgeleri nerede bulabilirim?**  
A: Aspose.Tasks for Java kullanımına ilişkin detaylı bilgi için [belgelere](https://reference.aspose.com/tasks/java/) başvurabilirsiniz.

## Sonuç
Bu öğreticide, Aspose.Tasks for Java kullanarak **ms project outline kodlarını** nasıl alacağımızı öğrendik. Sağlanan adımları izleyerek, Java uygulamalarınızda outline kodlarına etkili bir şekilde erişebilir ve bunları manipüle edebilir, özel raporlama, otomasyon ve diğer kurumsal sistemlerle entegrasyon gibi gelişmiş proje yönetimi yeteneklerini etkinleştirebilirsiniz.

---

**Son Güncelleme:** 2026-03-27  
**Test Edilen Versiyon:** Aspose.Tasks for Java (latest)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}