---
date: 2025-12-17
description: Aspose.Tasks for Java kullanarak projeyi görüntü olarak kaydetmeyi ve
  görüntü çözünürlüğünü değiştirmeyi öğrenin. Bu adım adım kılavuz, MS Project verilerini
  24bppRgb formatında render etmeyi gösterir.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Projeyi Görüntü Olarak Kaydet – Aspose.Tasks ile 24bppRgb Formatı
url: /tr/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeyi Görüntü Olarak Kaydet – 24bppRgb Formatı ile Aspose.Tasks

## Giriş
Bu öğreticide, Aspose.Tasks for Java ile 24bppRgb piksel formatını kullanarak **save project as image** öğreneceksiniz. MS Project verilerini bir görüntüye dönüştürmek, bir zaman çizelgesinin görsel bir anlık görüntüsünü paylaşmanız, bir rapora zaman çizelgesi eklemeniz veya bir proje‑portalı için küçük resimler oluşturmanız gerektiğinde kullanışlıdır. Ayrıca kalite gereksinimlerinize uymak için **change image resolution java** nasıl yapacağınızı da göstereceğiz.

## Hızlı Yanıtlar
- **Projeyi bir görüntüye render edebilir miyim?** Evet, Aspose.Tasks bir projeyi TIFF, PNG, JPEG vb. formatlarda kaydetmenizi sağlar.  
- **En iyi renk derinliğini hangi piksel formatı verir?** `Format24bppRgb` gerçek renk (24‑bit) görüntüler sağlar.  
- **Görüntü çözünürlüğünü nasıl ayarlarım?** `ImageSaveOptions` üzerinde `setHorizontalResolution` ve `setVerticalResolution` kullanın.  
- **Üretim için lisansa ihtiyacım var mı?** Değerlendirme dışı kullanım için ticari bir lisans gereklidir.  
- **Bu tüm Java sürümleriyle uyumlu mu?** Java 8 ve üzeri sürümlerle çalışır.

## “save project as image” nedir?
Bir projeyi görüntü olarak kaydetmek, Microsoft Project dosyasının (`.mpp`) görsel temsilini bir raster formata (ör. TIFF) dönüştürür. Ortaya çıkan dosya tarayıcılarda görüntülenebilir, belgelere eklenebilir veya orijinal Project uygulamasına ihtiyaç duymadan yazdırılabilir.

## Neden 24bppRgb formatı kullanılır?
24bppRgb piksel formatı, her pikseli kırmızı, yeşil ve mavi için 8 bit olarak depolar ve alfa kanalı olmadan gerçek renk kalitesi sunar. Bu, renk doğruluğunun önemli olduğu yüksek netlikte raporlar için idealdir ve 32‑bit formatlara kıyasla dosya boyutlarını makul tutar.

## Ön Koşullar
1. **Java Development Kit (JDK)** – Makinenizde JDK 8 veya daha yeni bir sürüm yüklü olmalıdır.  
2. **Aspose.Tasks for Java** – [buradan](https://releases.aspose.com/tasks/java/) indirip kurun.  
3. **Basic Java knowledge** – Java sözdizimi ve proje kurulumuna aşina olmak kod parçacıklarını takip etmenize yardımcı olur.

## Paketleri İçe Aktarma
İlk olarak, gerekli Aspose.Tasks sınıflarını Java projenize içe aktarın:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Adım‑Adım Kılavuz

### Adım 1: Veri Dizinini Tanımla
`"Your Data Directory"` ifadesini `.mpp` dosyanızın bulunduğu mutlak yol ile değiştirin.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

### Adım 2: Proje Dosyasını Yükle
Bu satır Microsoft Project dosyasını (`project.mpp`) okur ve Aspose.Tasks'in manipüle edebileceği bir `Project` nesnesi oluşturur.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Adım 3: Görüntü Kaydetme Seçeneklerini Yapılandır
Burada çıktı formatını TIFF olarak ayarlıyoruz, **72 dpi** çözünürlüğü belirtiyoruz (bu değerleri ihtiyacınıza göre değiştirebilirsiniz – burada **change image resolution java** yapıyorsunuz) ve gerçek renk çıktısı için 24bppRgb piksel formatını seçiyoruz.

```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```

### Adım 4: Proje Verilerini Görüntü Olarak Kaydet
`save` metodu, yukarıda tanımlanan seçenekleri kullanarak render edilen görüntüyü `resFile.tif` dosyasına yazar.

```java
project.save(dataDir + "resFile.tif", options);
```

## Yaygın Sorunlar ve Çözümleri

| Sorun | Sebep | Çözüm |
|-------|--------|-----|
| **Boş görüntü çıktısı** | Proje görünümü boş olabilir. | Kaydetmeden önce `project.setDefaultView(ViewType.Gantt);` çağırın. |
| **Düşük kalite görüntü** | Çözünürlük çok düşük ayarlanmış. | `setHorizontalResolution` ve `setVerticalResolution` değerlerini artırın (ör. 150 dpi). |
| **Desteklenmeyen piksel formatı** | Eski bir Aspose.Tasks sürümü kullanılıyor. | En son Aspose.Tasks for Java sürümüne yükseltin. |

## Sonuç
Artık 24bppRgb formatı ile **save project as image** yapmayı ve Aspose.Tasks for Java kullanarak çözünürlüğü ayarlamayı biliyorsunuz. Bu yöntem, proje takvimlerinizi paylaşmak, raporlamak veya arşivlemek için net ve renk‑doğru görsel temsiller oluşturmanızı sağlar.

## SSS

### Q: Projeyi diğer görüntü formatlarında render edebilir miyim?
A: Evet, Aspose.Tasks proje verilerini PNG, JPEG, BMP vb. gibi çeşitli görüntü formatlarına render etmeyi destekler.

### Q: Aspose.Tasks farklı MS Project sürümleriyle uyumlu mu?
A: Evet, Aspose.Tasks 2003, 2007, 2010, 2013 ve 2016 dahil olmak üzere çeşitli MS Project sürümlerini destekler.

### Q: Render edilen görüntünün çözünürlüğünü ve piksel formatını özelleştirebilir miyim?
A: Evet, Aspose.Tasks kullanarak çözünürlüğü ve piksel formatını gereksinimlerinize göre özelleştirebilirsiniz.

### Q: Aspose.Tasks'in ticari kullanım için lisansa ihtiyacı var mı?
A: Evet, Aspose.Tasks'in ticari kullanım için bir lisans satın almanız gerekir. Test amaçlı geçici bir lisans alabilirsiniz [buradan](https://purchase.aspose.com/temporary-license/).

### Q: Aspose.Tasks için desteği nereden alabilirim?
A: Aspose.Tasks için desteği [Aspose.Tasks forumundan](https://forum.aspose.com/c/tasks/15) alabilirsiniz.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}