---
date: 2026-02-10
description: Aspose.Tasks kullanarak para birimi değerlerini nasıl alacağınızı, MS
  Project dosyasını nasıl okuyacağınızı ve proje dosyasını Java'ya nasıl dönüştüreceğinizi
  öğrenin. Para birimi rakamlarını çıkarmak için adım adım rehber.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks kullanarak MS Project’ten Para Birimini Nasıl Alabilirsiniz
url: /tr/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks kullanarak MS Project'ten Para Birimini Nasıl Alırsınız

## Giriş
Microsoft Project dosyasından **para birimi** bilgisini nasıl alacağınızı merak ediyorsanız, doğru yerdesiniz. Bu kapsamlı öğreticide, Aspose.Tasks Java kütüphanesini kullanarak **ms project currency** değerleriyle nasıl çalışılacağını keşfedeceksiniz. Raporlama aracı, taşıma yardımcı programı oluşturuyor ya da sadece bir **java project file** dosyasının para birimi ayarlarını okumak istiyor olun, bu kılavuz sizi her adımda yönlendirecek — *.mpp* dosyasını yüklemekten para birimi basamaklarını çıkarmaya kadar. Sonunda, ms project currency verilerini kendi uygulamalarınızda rahatça işleyebileceksiniz.

## Hızlı Yanıtlar
- **MS Project dosyalarını okuyan kütüphane nedir?** Aspose.Tasks for Java.  
- **Para birimi basamaklarını almak için kaç satır kod gerekir?** Proje yüklendikten sonra sadece üç kısa satır.  
- **Geliştirme için lisans gerekli mi?** Test için ücretsiz deneme sürümü yeterli; üretim için ticari lisans gerekir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri (Aspose.Tasks'i çalıştırabilen herhangi bir JDK).  
- **Diğer Project özelliklerini de alabilir miyim?** Evet – Aspose.Tasks, başlangıç tarihi, maliyet oranları vb. gibi tam bir Project alanı seti sunar.

## ms project currency nedir?
`ms project currency`, Microsoft Project'in para değerlerini gösterirken kullandığı sayısal hassasiyeti (ondalık basamak sayısı) ifade eder. Proje dosyasında **CURRENCY_DIGITS** özelliği olarak saklanır ve tutarların tam sayı, bir‑ondalık, iki‑ondalık vb. olarak görüntülenip görüntülenmeyeceğini belirler.

## Aspose.Tasks'i ms project currency için kullanmanın avantajları
- **Microsoft Project kurulumu gerekmez** – *.mpp* dosyalarıyla doğrudan, Java destekleyen herhangi bir platformda çalışın.  
- **Güçlü tip güvenliği** – API, güçlü tipli değerler döndürür, ayrıştırma hatalarını azaltır.  
- **Performans‑optimizasyonu** – büyük projeleri hızlıca yükleyin ve yalnızca ihtiyacınız olan alanları çıkarın.  
- **Çapraz‑platform** – Windows, Linux veya macOS üzerinde değişiklik yapmadan çalıştırabilirsiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Geliştirme Ortamı** – JDK 8 ve üzeri yüklü ve yapılandırılmış.  
2. **Aspose.Tasks for Java** – resmi siteden en son JAR dosyasını indirin: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Temel Java bilgisi** – bir Java projesi oluşturma, dış kütüphaneler ekleme ve bir `main` metodu çalıştırma konusunda rahat olmalısınız.  

## Paketleri İçe Aktarma
İhtiyacımız olan sınıfları ilk olarak içe aktaralım.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Adım 1: Veri Dizinini Tanımlama
**java project file** (`*.mpp`) dosyanızın bulunduğu klasörü belirtin.  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini `project.mpp` dosyasının bulunduğu mutlak ya da göreli yol ile değiştirin.

## Adım 2: MPP Dosyasını Yükleme  
Şimdi **mpp** dosyalarını Aspose.Tasks ile nasıl yükleyeceğimizi göreceğiz.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Dosya adı tam olarak eşleşmelidir; aksi takdirde bir `IOException` fırlatılır.

## Adım 3: Para Birimi Basamaklarını Almak  
Proje yüklendikten sonra **ms project currency** basamaklarını tek satırda alabilirsiniz:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Bu çağrı, ondalık basamak sayısını temsil eden bir `Integer` döndürür (ör. cent için `2`). Değer konsola yazdırılır, ancak daha sonra işlemek üzere bir değişkende saklayabilirsiniz.

## Yaygın Sorunlar ve İpuçları
- **Dosya bulunamadı** – `dataDir` yolunu iki kez kontrol edin ve dosya adının `.mpp` uzantısıyla birlikte doğru olduğundan emin olun.  
- **Desteklenmeyen dosya sürümü** – Aspose.Tasks, Project 2000‑2024 formatlarını destekler; daha eski ya da bozuk dosyalar dönüştürme gerektirebilir.  
- **Lisans ayarlanmamış** – geliştirme aşamasında deneme sürümü çalışır, ancak üretimde değerlendirme filigranlarını önlemek için geçerli bir lisans uygulanmalıdır.

## Sık Sorulan Sorular

**S: Aspose.Tasks para birimi basamakları dışında başka Project özelliklerini de işleyebilir mi?**  
C: Evet, Aspose.Tasks, görevler, kaynaklar ve özel alanlar gibi Project dosyalarının çeşitli yönlerini manipüle etmek için geniş bir işlevsellik sunar.

**S: Aspose.Tasks kurumsal‑düzey uygulamalar için uygun mu?**  
C: Kesinlikle, Aspose.Tasks yüksek performans ve ölçeklenebilirlik sunarak kurumsal projelerin gereksinimlerini karşılayacak şekilde tasarlanmıştır.

**S: Aspose.Tasks çapraz‑platform geliştirmeyi destekliyor mu?**  
C: Evet, Java Runtime Environment (JRE) destekleyen herhangi bir platformda (Windows, Linux, macOS) Aspose.Tasks for Java kullanılabilir.

**S: Aspose.Tasks'i satın almadan deneyebilir miyim?**  
C: Evet, ücretsiz deneme sürümünü [burada](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Tasks için destek nereden alınır?**  
C: Destek için [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) adresini ziyaret edebilirsiniz.

## Sonuç
Artık Aspose.Tasks for Java kullanarak bir MS Project dosyasından **para birimi** basamaklarını nasıl alacağınızı biliyorsunuz. İşlem basittir: projeyi yükleyin, `project.get(Prj.CURRENCY_DIGITS)` metodunu çağırın ve sonucu uygulamanızda kullanın. Aynı desenle diğer proje özelliklerini de keşfedebilir, bu mantığı daha büyük raporlama veya taşıma çözümlerine entegre edebilirsiniz.

---

**Son Güncelleme:** 2026-02-10  
**Test Edilen Versiyon:** Aspose.Tasks for Java (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}