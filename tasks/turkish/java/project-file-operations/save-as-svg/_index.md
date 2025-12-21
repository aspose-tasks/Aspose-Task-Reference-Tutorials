---
date: 2025-12-21
description: Java'da MPP dosyalarından SVG oluşturmayı ve Aspose.Tasks kütüphanesini
  kullanarak projeyi SVG olarak kaydetmeyi öğrenin. Kod örnekleriyle adım adım rehber.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks kullanarak Java'da MPP'den SVG nasıl oluşturulur
url: /tr/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da MPP'den SVG Oluşturma

## Giriş
Bu öğreticide Aspose.Tasks for Java kullanarak **create SVG from MPP** dosyalarını nasıl oluşturacağınızı öğreneceksiniz. Bir Microsoft Project (MPP) dosyasını ölçeklenebilir vektör grafiği (SVG) formatına dönüştürmek, yüksek kaliteli, çözünürlük bağımsız diyagramları doğrudan web sayfalarına, raporlara veya panellere yerleştirmenizi sağlar. Gerekli kurulumu adım adım gösterecek, ihtiyacınız olan tam kodu sunacak ve her adımı açıklayacağız, böylece kendi uygulamalarınızda **save project as SVG** işlemini güvenle yapabilirsiniz.

## Hızlı Yanıtlar
- **“create SVG from MPP” ne anlama geliyor?**  
  Bir Microsoft Project dosyasını (.mpp) kalite kaybı olmadan herhangi bir tarayıcıda görüntülenebilen bir SVG görüntüsüne dönüştürür.  
- **Dönüşümü hangi kütüphane gerçekleştiriyor?**  
  Aspose.Tasks for Java, dönüşümü gerçekleştirmek için tek satırlık bir `save` metodunu sağlar.  
- **Bir lisansa ihtiyacım var mı?**  
  Ticari kullanım için geçici bir lisans gereklidir; ücretsiz deneme sürümü mevcuttur.  
- **Önkoşullar nelerdir?**  
  Java JDK 8+ ve Aspose.Tasks for Java JAR dosyası.  
- **Dönüşüm ne kadar sürer?**  
  Standart proje dosyaları için genellikle bir saniyeden az sürer.

## “create SVG from MPP” nedir?
Bir MPP dosyasından SVG oluşturmak, proje takviminin—görevlerin, zaman çizelgelerinin ve kaynakların—görsel temsilini Scalable Vector Graphics formatına dışa aktarmak anlamına gelir. SVG, XML tabanlı, hafif ve yüksek çözünürlüklü ekranlarda mükemmel ölçeklenir.

## Projeyi SVG olarak kaydetmek için neden Aspose.Tasks kullanılmalı?
- **Microsoft Project kurulumu gerekmez** – kütüphane bağımsız çalışır.  
- **Tam doğruluk** – grafikler, Gantt çubukları ve kilometre taşları stillerini korur.  
- **Çapraz platform** – kodu Windows, Linux veya macOS üzerinde çalıştırabilirsiniz.  
- **Kolay entegrasyon** – tek satırlık API çağrısı mevcut Java iş akışlarına doğal olarak uyum sağlar.

## Önkoşullar
- **Java Development Kit (JDK)** – sürüm 8 veya üzeri. Oracle web sitesinden indirin.  
- **Aspose.Tasks for Java** – kütüphaneyi resmi indirme sayfasından **[here](https://releases.aspose.com/tasks/java/)** edinin.

## Paketleri İçe Aktarma
İlk olarak, ihtiyacınız olan sınıfları içe aktarın. İçe aktarma bloğu değişmeden kalır.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Adım 1: Veri Dizinini Tanımlama
Kaynak MPP dosyanızın bulunduğu yeri ve SVG'nin yazılacağı yeri belirtin.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `FileNotFoundException` hatasından kaçınmak için mutlak bir yol veya projenizin kaynak klasörüne göre bir yol kullanın.

## Adım 2: MPP Dosyasını Yükleme
Mevcut Microsoft Project dosyasını yükleyerek bir `Project` örneği oluşturun.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Bu satır, daha önce tanımladığınız klasörden *HomeMovePlan.mpp* dosyasını okur.

## Adım 3: Projeyi SVG Olarak Kaydetme
Artık tek bir komutla **save project as SVG** yapabilirsiniz.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Metod, aynı dizine `project5.svg` dosyasını yazar. Oluşan SVG, herhangi bir modern tarayıcıda açılabilir veya doğrudan HTML içine gömülebilir.

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **File not found** | Yanlış `dataDir` yolu | Dizin stringinin bir ayırıcı (`/` veya `\\`) ile bittiğini doğrulayın. |
| **Blank SVG output** | Proje görünümler olmadan yüklendi | Kaydetmeden önce MPP dosyasının bir Gantt şeması görünümü içerdiğinden emin olun. |
| **License exception** | Geçerli bir lisans uygulanmadı | `save` metodunu çağırmadan önce `License.setLicense("path/to/license.xml")` kullanarak geçici bir lisans uygulayın. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java tüm Microsoft Project dosya sürümleriyle uyumlu mu?**  
C: Evet, eski sürümlerden en yeni Project sürümlerine kadar MPP, MPT ve XML formatlarını destekler.

**S: SVG çıktısının görünümünü özelleştirebilir miyim?**  
C: Kesinlikle. `save` metodunu çağırmadan önce yazı tiplerini, renkleri ve düzen seçeneklerini ayarlamak için `SvgOptions` kullanın.

**S: Aspose.Tasks for Java ticari kullanım için lisans gerektiriyor mu?**  
C: Evet, üretim için geçerli bir lisans gerekir. Geçici bir lisans **[here](https://purchase.aspose.com/temporary-license/)** adresinden alabilirsiniz.

**S: Aspose.Tasks for Java'ı satın almadan önce deneyebilir miyim?**  
C: Evet, ücretsiz bir deneme sürümü **[here](https://purchase.aspose.com/buy)** adresinde mevcuttur.

**S: Aspose.Tasks for Java için destek nereden alınabilir?**  
C: Sorular sormak ve geri bildirim paylaşmak için topluluk forumunu **[here](https://forum.aspose.com/c/tasks/15)** ziyaret edin.

## Sonuç
Artık Java'da **create SVG from MPP** dosyalarını nasıl oluşturacağınızı ve Aspose.Tasks kullanarak **save project as SVG** işlemini verimli bir şekilde yapacağınızı biliyorsunuz. Bu yetenek, zengin proje görselleştirmelerini web portallarına, raporlama panellerine veya ölçeklenebilir grafiklerin gerektiği herhangi bir yere entegre etmenizi sağlar. Çıktıyı ince ayarlamak için `SvgOptions` ile deneyler yapın; böylece geliştirme araç kutunuzda güçlü bir araç elde etmiş olacaksınız.

---

**Son Güncelleme:** 2025-12-21  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}