---
date: 2025-12-05
description: Ms Project para birimi basamaklarını Aspose.Tasks for Java kullanarak
  verimli bir şekilde nasıl yöneteceğinizi öğrenin. Java proje dosyası işleme ve mpp
  dosyalarını nasıl yükleyeceğinizi adım adım anlatan rehber.
language: tr
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile MS Project para birimi basamaklarını işleyin
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile ms project para birimi basamaklarını işleyin

## Giriş
Bu kapsamlı öğreticide **ms project para birimi** değerleriyle Java için Aspose.Tasks kütüphanesini nasıl kullanacağınızı keşfedeceksiniz. Bir raporlama aracı, bir geçiş yardımcı programı oluşturuyor ya da sadece bir **java proje dosyasından** para birimi ayarlarını okumanız gerekiyorsa, bu kılavuz *.mpp* dosyasını yüklemekten para birimi basamaklarını çıkarmaya kadar her adımı size gösterir. Sonunda, ms project para birimi verilerini kendi uygulamalarınızda rahatça işleyebileceksiniz.

## Hızlı Yanıtlar
- **MS Project dosyalarını okuyan kütüphane nedir?** Aspose.Tasks for Java.  
- **Para birimi basamaklarını almak için kaç satır kod gerekir?** Proje yüklendikten sonra sadece üç kısa satır.  
- **Geliştirme için lisans gerekir mi?** Test için ücretsiz deneme sürümü yeterlidir; üretim için ticari lisans gereklidir.  
- **Hangi Java sürümü desteklenir?** Java 8 ve üzeri (Aspose.Tasks'i çalıştırabilen herhangi bir JDK).  
- **Diğer Project özelliklerini alabilir miyim?** Evet – Aspose.Tasks, proje alanlarının tam bir setini (ör. başlangıç tarihi, maliyet oranları vb.) sunar.

## ms project para birimi nedir?
`ms project para birimi`, Microsoft Project'in para değerlerini gösterirken kullandığı sayısal hassasiyeti (ondalık basamak sayısı) ifade eder. Proje dosyasında **CURRENCY_DIGITS** özelliği olarak saklanır ve tutarların tam sayı, tek ondalık, iki ondalık vb. olarak görüntülenip görüntülenmeyeceğini belirler.

## ms project para birimini işlemek için Aspose.Tasks neden kullanılmalı?
- **Microsoft Project kurulumu gerekmez** – *.mpp* dosyalarıyla doğrudan, Java’yı destekleyen herhangi bir platformda çalışın.  
- **Güçlü tip güvenliği** – API, güçlü tipli değerler döndürür, ayrıştırma hatalarını azaltır.  
- **Performans‑optimizeli** – büyük projeleri hızlıca yükleyin ve yalnızca ihtiyacınız olan alanları çıkarın.  
- **Çapraz‑platform** – Windows, Linux veya macOS üzerinde değişiklik yapmadan çalışır.

## Önkoşullar
Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

1. **Java Geliştirme Ortamı** – JDK 8 veya daha yeni bir sürüm yüklü ve yapılandırılmış.  
2. **Aspose.Tasks for Java** – resmi siteden en son JAR dosyasını indirin: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Temel Java bilgisi** – bir Java projesi oluşturma, harici kütüphaneler ekleme ve bir `main` metodu çalıştırma konusunda rahat olmalısınız.  

## Paketleri İçe Aktar
İhtiyacımız olan sınıfları önce içe aktaralım.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Adım 1: Veri Dizinini Tanımla
**java proje dosyanızın** (`*.mpp`) bulunduğu klasörü belirtin.  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini `project.mpp` dosyasının bulunduğu mutlak ya da göreli yol ile değiştirin.

## Adım 2: MPP Dosyasını Yükle  
Şimdi **mpp** dosyalarını Aspose.Tasks ile nasıl yükleyeceğimizi göreceğiz.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Dosya adı tam olarak eşleşmelidir; aksi takdirde bir `IOException` fırlatılır.

## Adım 3: Para Birimi Basamaklarını Al  
Projeyi yükledikten sonra **ms project para birimi** basamaklarını almak tek satırda yapılır:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Bu çağrı, ondalık basamak sayısını temsil eden bir `Integer` döndürür (ör. cent için `2`). Değer konsola yazdırılır, ancak daha sonraki işlemler için bir değişkende saklanabilir.

## Yaygın Sorunlar ve İpuçları
- **Dosya bulunamadı** – `dataDir` yolunu iki kez kontrol edin ve dosya adının `.mpp` uzantısı dahil doğru olduğundan emin olun.  
- **Desteklenmeyen dosya sürümü** – Aspose.Tasks, Project 2000‑2024 formatlarını destekler; daha eski ya da bozuk dosyalar dönüştürme gerektirebilir.  
- **Lisans ayarlanmamış** – geliştirme aşamasında deneme sürümü çalışır, ancak üretimde değerlendirme filigranlarından kaçınmak için geçerli bir lisans uygulanmalıdır.

## Sık Sorulan Sorular

**S: Aspose.Tasks para birimi basamakları dışında başka Project özelliklerini de işleyebilir mi?**  
C: Evet, Aspose.Tasks, görevler, kaynaklar ve özel alanlar gibi Project dosyalarının çeşitli yönlerini manipüle etmek için geniş bir işlevsellik sunar.

**S: Aspose.Tasks kurumsal düzeyde uygulamalar için uygun mu?**  
C: Kesinlikle, Aspose.Tasks yüksek performans ve ölçeklenebilirlik sunarak kurumsal projelerin gereksinimlerini karşılayacak şekilde tasarlanmıştır.

**S: Aspose.Tasks çapraz‑platform geliştirmeyi destekliyor mu?**  
C: Evet, Java Runtime Environment (JRE) destekleyen herhangi bir platformda (Windows, Linux, macOS) Aspose.Tasks for Java kullanılabilir.

**S: Aspose.Tasks'i satın almadan önce deneyebilir miyim?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Tasks için destek nereden alınır?**  
C: Destek için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

---

**Son Güncelleme:** 2025-12-05  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11 (yazım anındaki en yeni)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}