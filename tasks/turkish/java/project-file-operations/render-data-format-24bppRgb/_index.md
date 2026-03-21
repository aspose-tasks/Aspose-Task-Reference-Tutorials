---
date: 2026-03-21
description: Aspose.Tasks ile Java’da bir projeyi 24bppRgb görüntüsü olarak kaydederek
  ve görüntü çözünürlüğünü değiştirerek görüntü kalitesini artırmayı öğrenin. Bu kılavuz
  ayrıca proje görüntü formatlarını nasıl kaydedeceğinizi gösterir.
linktitle: Increase Image Quality – Save Project Image (24bppRgb)
second_title: Aspose.Tasks Java API
title: Görüntü Kalitesini Artır – Proje Görüntüsünü Kaydet (24bppRgb)
url: /tr/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Görüntü Kalitesini Artırma – Proje Görüntüsü (24bppRgb) Kaydetme Aspose.Tasks ile

## Giriş
Bu öğreticide, **görüntü kalitesini artırmayı** Aspose.Tasks for Java ile 24bppRgb piksel formatını kullanarak bir projeyi görüntü olarak kaydetme yoluyla öğreneceksiniz. MS Project verilerini bir görüntüye dönüştürmek, bir takvimin görsel anlık görüntüsünü paylaşmanız, bir rapora zaman çizelgesi eklemeniz veya bir proje‑portalı için küçük resimler oluşturmanız gerektiğinde kullanışlıdır. Ayrıca **change image resolution java** nasıl yapılacağını göstererek çıktının tam kalite gereksinimlerinizi karşılamasını sağlayacağız.

## Hızlı Yanıtlar
- **Bir projeyi görüntüye dönüştürebilir miyim?** Evet, Aspose.Tasks bir projeyi TIFF, PNG, JPEG vb. formatlarda kaydetmenizi sağlar.  
- **Hangi piksel formatı en iyi renk derinliğini verir?** `Format24bppRgb` gerçek‑renk (24‑bit) görüntüler sağlar.  
- **Görüntü çözünürlüğünü nasıl ayarlarım?** `ImageSaveOptions` üzerinde `setHorizontalResolution` ve `setVerticalResolution` metodlarını kullanın.  
- **Üretim ortamı için lisansa ihtiyacım var mı?** Değerlendirme dışı kullanım için ticari bir lisans gereklidir.  
- **Bu tüm Java sürümleriyle uyumlu mu?** Java 8 ve üzeri sürümlerle çalışır.

## “save project image” nedir?
Bir projeyi görüntü olarak kaydetmek, Microsoft Project dosyasının (`.mpp`) görsel temsilini raster bir formata (ör. TIFF) dönüştürür. Ortaya çıkan dosya tarayıcılarda görüntülenebilir, belgelere eklenebilir veya orijinal Project uygulamasına ihtiyaç duymadan yazdırılabilir.

## Neden 24bppRgb formatını **görüntü kalitesini artırmak** için kullanmalısınız?
24bppRgb piksel formatı, her pikseli kırmızı, yeşil ve mavi için 8 bit olmak üzere depolar ve alfa kanalı olmadan gerçek‑renk kalitesi sunar. Bu, renk doğruluğunun önemli olduğu yüksek netlikli raporlar için idealdir ve 32‑bit formatlara göre dosya boyutlarını makul tutar.

## Yaygın Kullanım Senaryoları
- **Gantt şeması görüntüsü kaydetme** proje durum panoları için.  
- **Proje küçük resmi oluşturma** web portalındaki ön izleme panelleri için.  
- **Proje görüntüsü** çıktı çözünürlüğünü yazdırma veya yüksek‑DPI ekranlar için özelleştirme.  
- **Proje görüntüsü kaydetme** farklı formatlarda (TIFF, PNG, JPEG) belgelemeler için.

## Önkoşullar
Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

1. **Java Development Kit (JDK)** – JDK 8 veya daha yeni bir sürüm makinenizde yüklü olmalı.  
2. **Aspose.Tasks for Java** – [buradan](https://releases.aspose.com/tasks/java/) indirin ve kurun.  
3. **Temel Java bilgisi** – Java sözdizimi ve proje kurulumu hakkında temel bilgi, kod parçacıklarını takip etmenizi kolaylaştırır.

## Paketleri İçe Aktarma
İlk olarak, gerekli Aspose.Tasks sınıflarını Java projenize içe aktarın:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Adım‑Adım Kılavuz

### Adım 1: Veri Dizinini Tanımlama
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini `.mpp` dosyanızın bulunduğu mutlak yol ile değiştirin.

### Adım 2: Proje Dosyasını Yükleme
```java
Project project = new Project(dataDir + "project.mpp");
```
Bu satır Microsoft Project dosyasını (`project.mpp`) okur ve Aspose.Tasks'in manipüle edebileceği bir `Project` nesnesi oluşturur.

### Adım 3: Görüntü Kaydetme Seçeneklerini Yapılandırma
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Burada çıktı formatını TIFF olarak ayarlıyor, **72 dpi** çözünürlüğü belirtiyoruz (ihtiyacınıza göre bu değerleri değiştirebilirsiniz – burada **change image resolution java** yapılır) ve gerçek‑renk çıkışı için 24bppRgb piksel formatını seçiyoruz.

### Adım 4: Proje Verilerini Görüntü Olarak Kaydetme
```java
project.save(dataDir + "resFile.tif", options);
```
`save` metodu, yukarıda tanımlanan seçenekleri kullanarak render edilen görüntüyü `resFile.tif` dosyasına yazar.

## Yaygın Sorunlar ve Çözümler
| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Boş görüntü çıktısı** | Proje görünümü boş olabilir. | Kaydetmeden önce `project.setDefaultView(ViewType.Gantt);` çağırın. |
| **Düşük‑kaliteli görüntü** | Çözünürlük çok düşük ayarlanmış. | `setHorizontalResolution` ve `setVerticalResolution` değerlerini artırın (ör. 150 dpi). |
| **Desteklenmeyen piksel formatı** | Eski bir Aspose.Tasks sürümü kullanılıyor. | En son Aspose.Tasks for Java sürümüne yükseltin. |

## Sonuç
Artık 24bppRgb formatını kullanarak bir projeyi görüntü olarak kaydetme ve Aspose.Tasks for Java ile çözünürlüğü ayarlama yoluyla **görüntü kalitesini artırma** konusunda bilgi sahibisiniz. Bu yöntem, proje takvimlerinizi paylaşmak, raporlamak veya arşivlemek için net, renk‑doğru görsel temsiller üretmenizi sağlar.

## Sıkça Sorulan Sorular

**S: Proje verilerini başka görüntü formatlarında da render edebilir miyim?**  
C: Evet, Aspose.Tasks PNG, JPEG, BMP gibi çeşitli görüntü formatlarında proje verilerini render edebilir.

**S: Aspose.Tasks farklı MS Project sürümleriyle uyumlu mu?**  
C: Evet, Aspose.Tasks 2003, 2007, 2010, 2013 ve 2016 dahil olmak üzere birçok MS Project sürümünü destekler.

**S: Render edilen görüntünün çözünürlüğünü ve piksel formatını özelleştirebilir miyim?**  
C: Evet, Aspose.Tasks kullanarak çözünürlük ve piksel formatını gereksinimlerinize göre özelleştirebilirsiniz.

**S: Aspose.Tasks ticari kullanım için lisans gerektiriyor mu?**  
C: Evet, Aspose.Tasks'in ticari kullanım için bir lisans satın almanız gerekir. Test amaçlı geçici bir lisans alabilirsiniz, [buradan](https://purchase.aspose.com/temporary-license/).

**S: Aspose.Tasks için destek nereden alınabilir?**  
C: Aspose.Tasks desteğini [Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) üzerinden alabilirsiniz.

**Son Güncelleme:** 2026-03-21  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}