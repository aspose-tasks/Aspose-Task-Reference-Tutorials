---
title: Aspose.Tasks'ta MS Project Verilerini 24bppRgb Formatında İşleyin
linktitle: Aspose.Tasks'ta Verileri 24bppRgb Formatında İşleme
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks'ı kullanarak MS Project verilerini Java'da görüntü olarak nasıl oluşturacağınızı öğrenin. Sorunsuz entegrasyon için adım adım eğitimimizi izleyin.
type: docs
weight: 11
url: /tr/java/project-file-operations/render-data-format-24bppRgb/
---
## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak MS Project formatı 24bppRgb ile veri oluşturma sürecinde size rehberlik edeceğiz. Proje verilerinin görüntü formatına dönüştürülmesi, proje ilerlemesinin görsel olarak paylaşılması veya rapor oluşturulması gibi çeşitli amaçlar için faydalı olabilir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java'yı şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).
3. Temel Java programlama bilgisi: Java programlama diline aşina olmak, kod örneklerini anlamak ve uygulamak için faydalı olacaktır.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize aktarmanız gerekir:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Sağlanan örneği birden çok adıma ayıralım:
## 1. Adım: Veri Dizinini Tanımlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
```
Bu adımda proje verilerinizin bulunduğu dizini tanımlarsınız. Yer değiştirmek`"Your Data Directory"` veri dizininizin gerçek yolu ile.
## Adım 2: Proje Dosyasını Yükleyin
```java
Project project = new Project(dataDir + "project.mpp");
```
Burada MS Project dosyasını yüklüyoruz (`project.mpp` ) Aspose.Tasks'ı kullanın ve bunu`project` nesne.
## 3. Adım: Görüntü Kaydetme Seçeneklerini Yapılandırın
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Bu adım, proje verilerini görüntü olarak kaydetme seçeneklerini yapılandırmayı içerir. Görüntü formatını (TIFF), yatay ve dikey çözünürlükleri ve piksel formatını (24bppRgb) belirliyoruz.
## Adım 4: Proje Verilerini Görüntü Olarak Kaydetme
```java
project.save(dataDir + "resFile.tif", options);
```
Son olarak proje verilerini bir görüntü dosyası olarak kaydediyoruz (`resFile.tif`) belirtilen seçeneklerle.

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak MS Project formatı 24bppRgb ile proje verilerinin nasıl oluşturulacağını öğrendik. Verilen adımları takip ederek proje verilerinizi çeşitli amaçlar için kolaylıkla görüntü formatına dönüştürebilirsiniz.
## SSS'ler
### S: Proje verilerini diğer görüntü formatlarında oluşturabilir miyim?
C: Evet, Aspose.Tasks proje verilerinin PNG, JPEG, BMP vb. gibi çeşitli görüntü formatlarına dönüştürülmesini destekler.
### S: Aspose.Tasks, MS Project'in farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks, MS Project'in 2003, 2007, 2010, 2013 ve 2016 dahil birden çok sürümünü destekler.
### S: İşlenen görüntünün çözünürlüğünü ve piksel biçimini özelleştirebilir miyim?
C: Evet, Aspose.Tasks'ı kullanarak çözünürlüğü ve piksel formatını ihtiyaçlarınıza göre özelleştirebilirsiniz.
### S: Aspose.Tasks ticari kullanım için lisans gerektiriyor mu?
 C: Evet, Aspose.Tasks'ın ticari kullanımı için bir lisans satın almanız gerekiyor. Test amaçlı geçici bir lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks için nereden destek alabilirim?
 C: Aspose.Tasks için şu adresten destek alabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).