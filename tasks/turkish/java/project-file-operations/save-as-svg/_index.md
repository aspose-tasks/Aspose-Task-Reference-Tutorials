---
date: 2026-03-27
description: Aspose.Tasks ile Java’da MPP’yi SVG’ye nasıl dışa aktaracağınızı öğrenin.
  Adım adım rehber, kod örnekleri ve bir projeyi hızlıca SVG olarak kaydetmek için
  ipuçları.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Java'da Aspose.Tasks kullanarak MPP'yi SVG'ye nasıl dışa aktarılır
url: /tr/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da MPP'yi SVG'ye Nasıl Dışa Aktarılır

## Export MPP to SVG – Giriş
Bu öğreticide Aspose.Tasks for Java kullanarak **export MPP to SVG** dosyalarını nasıl dışa aktaracağınızı öğreneceksiniz. Bir Microsoft Project (MPP) dosyasını Scalable Vector Graphics (SVG) görüntüsüne dönüştürmek, yüksek kaliteli, çözünürlük bağımsız diyagramları doğrudan web sayfalarına, raporlara veya panolara yerleştirmenizi sağlar. Gerekli kurulumu adım adım gösterecek, ihtiyacınız olan tam kodu sunacak ve her adımı açıklayacağız, böylece kendi uygulamalarınızda **save project as SVG** işlemini güvenle yapabilirsiniz.

## Hızlı Yanıtlar
- **“export MPP to SVG” ne anlama geliyor?**  
  Bir Microsoft Project dosyasını (.mpp) herhangi bir tarayıcıda kalite kaybı olmadan görüntülenebilen bir SVG resmine dönüştürür.  
- **Dönüşümü hangi kütüphane gerçekleştirir?**  
  Aspose.Tasks for Java, dönüşümü gerçekleştirmek için tek satırlık bir `save` yöntemi sağlar.  
- **Bir lisansa ihtiyacım var mı?**  
  Ticari kullanım için geçici bir lisans gereklidir; ücretsiz bir deneme sürümü mevcuttur.  
- **Önkoşullar nelerdir?**  
  Java JDK 8+ ve Aspose.Tasks for Java JAR.  
- **Dönüşüm ne kadar sürer?**  
  Standart proje dosyaları için genellikle bir saniyeden az sürer.

## “export MPP to SVG” nedir?
Export MPP to SVG, bir proje zaman çizelgesinin—görevler, zaman çizelgeleri ve kaynakların—görsel temsilini alıp bir SVG dosyası olarak yazmak anlamına gelir. SVG, XML tabanlı, hafif ve yüksek çözünürlüklü ekranlarda mükemmel ölçeklenir.

## Aspose.Tasks ile MPP'yi SVG'ye neden dışa aktarılır?
- **Microsoft Project kurulumu gerekmez** – kütüphane bağımsız çalışır.  
- **Tam doğruluk** – grafikler, Gantt çubukları ve kilometre taşları stillerini korur.  
- **Çapraz platform** – kodu Windows, Linux veya macOS üzerinde çalıştırabilirsiniz.  
- **Tek satır API** – tek bir çağrıyla proje SVG olarak kaydedilir, mevcut Java iş akışlarına doğal olarak uyum sağlar.

## Önkoşullar
- **Java Development Kit (JDK)** – sürüm 8 veya üzeri. Oracle web sitesinden indirin.  
- **Aspose.Tasks for Java** – kütüphaneyi resmi indirme sayfasından **[buradan](https://releases.aspose.com/tasks/java/)** edinin.

## Import Packages
İlk olarak, ihtiyacınız olan sınıfları içe aktarın. İçe aktarma bloğu değişmeden kalır.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Step 1: Define the Data Directory
Kaynak MPP dosyanızın bulunduğu yeri ve SVG'nin yazılacağı konumu belirtin.

```java
String dataDir = "Your Data Directory";
```

> **Pro ipucu:** `FileNotFoundException` hatasından kaçınmak için mutlak bir yol veya projenizin kaynak klasörüne göre göreceli bir yol kullanın.

## Step 2: Load the MPP File
Mevcut Microsoft Project dosyasını yükleyerek bir `Project` örneği oluşturun.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Bu satır, daha önce tanımladığınız klasörden *HomeMovePlan.mpp* dosyasını okur.

## Step 3: Save the Project as SVG
Artık tek bir komutla **export MPP to SVG** yapabilirsiniz.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metot, `project5.svg` dosyasını aynı dizine yazar. Oluşan SVG, herhangi bir modern tarayıcıda açılabilir veya doğrudan HTML içine yerleştirilebilir.

## Yaygın Kullanım Senaryoları
- **Proje panoları** – müşterinin Microsoft Project kurmasını gerektirmeden web portallarına canlı Gantt grafiklerini yerleştirin.  
- **Otomatik raporlama** – PDF veya HTML raporları için anlık SVG görüntüleri oluşturun.  
- **Ekipler arası iş birliği** – sadece bir tarayıcıyla görüntüleyebilen paydaşlarla görsel bir takvimi paylaşın.

## Common Issues and Solutions
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Dosya bulunamadı** | Yanlış `dataDir` yolu | Dizin dizgisinin bir ayırıcı (`/` veya `\\`) ile bittiğini doğrulayın. |
| **Boş SVG çıktısı** | Proje görünümler olmadan yüklendi | Kaydetmeden önce MPP dosyasının bir Gantt grafik görünümü içerdiğinden emin olun. |
| **Lisans istisnası** | Geçerli bir lisans uygulanmadı | `save` metodunu çağırmadan önce `License.setLicense("path/to/license.xml")` kullanarak geçici bir lisans uygulayın. |

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java tüm Microsoft Project dosyası sürümleriyle uyumlu mu?**  
A: Evet, eski sürümlerden en yeni Project sürümlerine kadar MPP, MPT ve XML formatlarını destekler.

**Q: SVG çıktısının görünümünü özelleştirebilir miyim?**  
A: Kesinlikle. `save` metodunu çağırmadan önce yazı tiplerini, renkleri ve düzen seçeneklerini ayarlamak için `SvgOptions` kullanın.

**Q: Aspose.Tasks for Java ticari kullanım için lisans gerektiriyor mu?**  
A: Evet, üretim için geçerli bir lisans gereklidir. Geçici bir lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** edinebilirsiniz.

**Q: Aspose.Tasks for Java'ı satın almadan önce deneyebilir miyim?**  
A: Evet, ücretsiz bir deneme sürümü **[buradan](https://purchase.aspose.com/buy)** mevcuttur.

**Q: Aspose.Tasks for Java için destek nereden alınabilir?**  
A: Sorular sormak ve geri bildirim paylaşmak için topluluk forumunu **[buradan](https://forum.aspose.com/c/tasks/15)** ziyaret edin.

## Sonuç
Artık Java'da **export MPP to SVG** yapmayı ve Aspose.Tasks kullanarak **save project as SVG** işlemini verimli bir şekilde gerçekleştirmeyi biliyorsunuz. Bu özellik, zengin proje görselleştirmelerini web portallarına, raporlama panolarına veya ölçeklenebilir grafiklerin gerektiği herhangi bir yere entegre etmenizi sağlar. Çıktıyı ince ayarlamak için `SvgOptions` ile deneyler yapın; böylece geliştirme araç setinizde güçlü bir araca sahip olacaksınız.

---

**Son Güncelleme:** 2026-03-27  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}