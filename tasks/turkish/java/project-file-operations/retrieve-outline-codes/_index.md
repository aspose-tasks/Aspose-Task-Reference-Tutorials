---
date: 2025-12-20
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

# Aspose.Tasks ile MS Project Outline Kodlarını Almak

## Giriş
Bu öğreticide, **ms project outline kodlarını** Aspose.Tasks for Java kullanarak nasıl alacağınızı keşfedeceksiniz. MS Project'teki outline kodları, görevleri, kaynakları ve atamaları sınıflandırmanın güçlü bir yolunu sunar; bunlara programlı olarak erişmek, özel raporlama, otomasyon veya entegrasyon çözümleri oluşturmanıza olanak tanır. Kendi projenize kopyalayabileceğiniz eksiksiz, adım adım bir örnek üzerinden ilerleyeceğiz.

## Hızlı Yanıtlar
- **Kod ne işe yarar?** Bir Project dosyasını yükler ve her outline kod tanımını, maskelerini ve değerlerini yazdırır.  
- **Hangi kütüphane gerekir?** Aspose.Tasks for Java (herhangi bir yeni sürüm).  
- **Lisans gerekli mi?** Geliştirme için deneme sürümü çalışır; üretim için tam lisans gerekir.  
- **Hangi Java sürümü desteklenir?** Java 8 ve üzeri.  
- **Kodları aldıktan sonra değiştirebilir miyim?** Evet – aynı API ile outline kodlarını ekleyebilir, düzenleyebilir veya silebilirsiniz.

## ms project outline kodları nedir?
Outline kodları, proje yöneticilerinin varsayılan hiyerarşinin ötesinde görevleri gruplandırıp filtrelemesini sağlayan özel alanlardır. Basit sayısal değerler, metinler veya kuruluş seviyesinde tanımlanan kurumsal özel kodlar olabilir. Bu kodları okuyarak panolar oluşturabilir, verileri dışa aktarabilir veya adlandırma kurallarını otomatik olarak uygulayabilirsiniz.

## Aspose.Tasks ile ms project outline kodlarını neden almalı?
- **Otomasyon:** Raporlar oluşturun veya manuel dışa aktarım olmadan iş akışlarını tetikleyin.  
- **Entegrasyon:** Outline kodlarını ERP, PPM veya BI araçlarıyla senkronize edin.  
- **Özelleştirme:** Kod değerlerine dayalı iş kuralları uygulayın (ör. maliyet tahsisi).  
- **Çapraz platform:** Windows, Linux ve macOS'ta çalışır, Microsoft Project UI'sinden bağımsızdır.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların kurulu olduğundan emin olun:

### 1. Java Geliştirme Ortamı
Sisteminizde Java Development Kit (JDK) yüklü olmalı. JDK'yı Oracle web sitesinden indirip kurabilirsiniz.

### 2. Aspose.Tasks Kütüphanesi
Aspose.Tasks kütüphanesini Java projenize dahil edin. Kütüphaneyi [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) adresinden indirebilirsiniz.

## Paketleri İçe Aktarma
İlk olarak, Java kodunuzda Aspose.Tasks'ten gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Şimdi sağlanan örnek kodu birden fazla adıma ayıralım:

## Adım 1: Projeyi Yükleme
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Bu adımda, verilen dosya adıyla Microsoft Project dosyasını bir `Project` nesnesine yüklüyoruz.

## Adım 2: Outline Kodlarını Getirme
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Projede tanımlı her outline kod tanımını döngüyle inceliyoruz.

## Adım 3: Outline Kod Özelliklerine Erişim
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Alias, Field ID ve Field Name gibi outline kod tanımının çeşitli özelliklerini alıp yazdırıyoruz.

## Adım 4: Kurumsal Özel Kodu Kontrol Etme
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Outline kodunun kurumsal bir özel kod olup olmadığını kontrol ediyor ve sonucu buna göre yazdırıyoruz.

## Adım 5: Outline Kod Maskelerini Görüntüleme
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Outline koduna bağlı her maskeyi dolaşıp seviyesini ve mask değerini yazdırıyoruz.

## Adım 6: Outline Kod Değerlerini Görüntüleme
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Her outline kod değerini dolaşıp açıklamasını, değer kimliğini, değerini ve tipini yazdırıyoruz.

## Yaygın Sorunlar ve Çözümleri
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Çıktı yok** | Proje dosyası yolu hatalı | `projectName`'in geçerli bir `.mpp` dosyasına işaret ettiğini doğrulayın. |
| **Null değerler** | Outline kod dosyada tanımlı değil | Proje dosyasının gerçekten outline kodları içerdiğini (MS Project UI'da kontrol edin) teyit edin. |
| **LicenseException** | Uygun aktivasyon olmadan deneme sürümü kullanılıyor | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` ile geçici veya tam lisans uygulayın. |

## Sık Sorulan Sorular

**S: Aspose.Tasks for Java kullanarak bir Project dosyasındaki outline kodlarını değiştirebilir miyim?**  
C: Evet, Aspose.Tasks for Java programlı olarak outline kodlarını değiştirmek için API'ler sunar. Aynı `Project` nesnesiyle tanımları ekleyebilir, düzenleyebilir veya silebilirsiniz.

**S: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?**  
C: Evet, Aspose.Tasks for Java'ın ücretsiz deneme sürümünü [Aspose.Tasks web sitesinden](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Tasks for Java için teknik destek nasıl alınır?**  
C: Teknik desteği, [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) sorularınızı paylaşarak alabilirsiniz.

**S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?**  
C: Evet, Aspose.Tasks for Java için geçici lisansı [satın alma sayfasından](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

**S: Aspose.Tasks for Java'ın tam belgelerine nereden ulaşabilirim?**  
C: Detaylı bilgi için [belgelere](https://reference.aspose.com/tasks/java/) göz atabilirsiniz.

## Sonuç
Bu öğreticide, Aspose.Tasks for Java kullanarak **ms project outline kodlarını** nasıl alacağınızı öğrendik. Sağlanan adımları izleyerek Java uygulamalarınızda outline kodlarına etkili bir şekilde erişebilir ve bunları manipüle edebilir, böylece özel raporlama, otomasyon ve diğer kurumsal sistemlerle entegrasyon gibi gelişmiş proje yönetimi yeteneklerini etkinleştirebilirsiniz.

---

**Son Güncelleme:** 2025-12-20  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (yazım anındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}