---
title: MS Project'i Java'da SVG'ye dönüştürün
linktitle: Aspose.Tasks'ta SVG Olarak Kaydet
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks kütüphanesini kullanarak Microsoft Project dosyalarını Java'da SVG olarak nasıl kaydedeceğinizi öğrenin. Kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 18
url: /tr/java/project-file-operations/save-as-svg/
---
## giriiş
Aspose.Tasks for Java, proje yönetimi dosyalarıyla çalışmak için güçlü bir kütüphanedir; geliştiricilerin proje verilerini yönetmesine, çeşitli işlemleri gerçekleştirmesine ve verimli bir şekilde rapor oluşturmasına olanak tanır. Bu eğitimde Aspose.Tasks for Java kullanarak bir projenin SVG olarak nasıl kaydedileceğini inceleyeceğiz. SVG (Ölçeklenebilir Vektör Grafikleri), web üzerinde vektör grafiklerini görüntülemek için yaygın olarak kullanılan, ölçeklenebilirlik ve yüksek kaliteli görüntü oluşturma sağlayan bir formattır.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
### Java Geliştirme Ortamı
Sisteminizde Java Development Kit'in (JDK) kurulu olduğundan emin olun. JDK'yı Oracle web sitesinden indirip yükleyebilirsiniz.
### Aspose.Tasks for Java Library
 Aspose.Tasks for Java kütüphanesini web sitesinden indirip yükleyin. İndirme bağlantısını sağlanan belgelerde bulabilirsiniz.[Burada](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Aspose.Tasks işlevleriyle çalışmak için öncelikle Java programınıza gerekli paketleri içe aktarmanız gerekir.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Şimdi verilen örneği birden çok adıma ayıralım:
## Adım 2: Veri Dizinini Tanımlayın
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"`proje dosyanızın bulunduğu dizinin yolu ile birlikte.
## Adım 3: Proje Dosyasını Yükleyin
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Bu adım, belirtilen veri dizininden "HomeMovePlan.mpp" adlı proje dosyasını yükler.
## 4. Adım: SVG olarak kaydedin
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Bu adım, yüklenen projeyi belirtilen veri dizinine "project5.svg" adıyla SVG formatında kaydeder.

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak bir projeyi SVG olarak nasıl kaydedeceğimizi öğrendik. Verilen adımları izleyerek proje dosyalarını etkili bir şekilde SVG formatına dönüştürebilir, web tabanlı uygulamalarla veya görselleştirme araçlarıyla kusursuz entegrasyona olanak tanıyabilirsiniz.
## SSS'ler
### Aspose.Tasks for Java, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mu?
Evet, Aspose.Tasks for Java, MPP, MPT ve XML formatları da dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### SVG çıktısının görünümünü özelleştirebilir miyim?
Evet, yazı tipleri, renkler ve düzen yapılandırmaları gibi parametreleri ayarlayarak SVG çıktısının görünümünü özelleştirebilirsiniz.
### Aspose.Tasks for Java ticari kullanım için lisans gerektirir mi?
 Evet, Aspose.Tasks for Java'nın ticari kullanımı için geçerli bir lisans gereklidir. Web sitesinden lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Satın almadan önce Aspose.Tasks for Java'yı deneyebilir miyim?
 Evet, web sitesinden Aspose.Tasks for Java'nın ücretsiz deneme sürümünü talep edebilirsiniz.[Burada](https://purchase.aspose.com/buy) özelliklerini ve yeteneklerini değerlendirmek.
### Aspose.Tasks for Java için nereden destek alabilirim?
 Forumu ziyaret ederek Aspose.Tasks for Java konusunda destek alabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15), soru sorabileceğiniz ve toplulukla etkileşimde bulunabileceğiniz yer.