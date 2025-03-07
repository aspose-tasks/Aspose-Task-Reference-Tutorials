---
title: Aspose.Tasks'ta MS Project'i JPEG olarak dönüştürün
linktitle: Aspose.Tasks'ta Projeyi JPEG Olarak Kaydet
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak Microsoft Project dosyalarını kolayca JPEG görüntülerine nasıl dönüştürebileceğinizi öğrenin. Verimliliğinizi artırın.
weight: 20
url: /tr/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta MS Project'i JPEG olarak dönüştürün

## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak Microsoft Project dosyasını JPEG görüntüsü olarak nasıl kaydedeceğimizi inceleyeceğiz. Bu, özellikle proje görselleştirmelerini paylaşmak veya proje verilerini raporlara veya sunumlara entegre etmek için yararlı olabilir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun. En son sürümü şuradan indirip yükleyebilirsiniz:[Java web sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java: Aspose.Tasks for Java'yı indirin ve kurun.[dokümantasyon](https://reference.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java dosyanıza aktarın:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## 1. Adım: Veri Dizinini Tanımlayın
MS Project dosyanızın bulunduğu veri dizininizin yolunu ayarlayın.
```java
String dataDir = "Your Data Directory";
```
## Adım 2: MS Proje Dosyasını Yükleyin
Aspose.Tasks'ı kullanarak MS Project dosyasını yükleyin.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## 3. Adım: JPEG Kalitesini Yapılandırın (İsteğe bağlı)
 JPEG kalitesini ayarlamak istiyorsanız, bunu kullanarak ayarlayabilirsiniz.`ImageSaveOptions` sınıf. Kalite 0 ila 100 arasında değişir.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // JPEG kalitesini 50'ye ayarlayın
```
## Adım 4: Projeyi JPEG olarak kaydedin
MS Project dosyasını JPEG görüntüsü olarak kaydedin.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Çözüm
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak bir Microsoft Project dosyasını JPEG görüntüsü olarak nasıl kaydedeceğimizi öğrendik. Bu özellik, proje verilerinin çeşitli belge ve sunumlara kolayca paylaşılmasına ve entegre edilmesine olanak tanır.
## SSS'ler
### S: JPEG görüntüsünün kalitesini ayarlayabilir miyim?
 C: Evet, kaliteyi aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`setJpegQuality()` 0 ile 100 arasında değişen bir yöntem.
### S: JPEG kalitesini belirtmezsem ne olur?
C: Kaliteyi belirtmezseniz varsayılan kalite kullanılacaktır.
### S: Aspose.Tasks for Java'nın kullanımı ücretsiz mi?
 C: Aspose.Tasks for Java ticari bir kütüphanedir ancak özelliklerini ücretsiz deneme sürümüyle keşfedebilirsiniz. Ziyaret edin[ücretsiz deneme sayfası](https://releases.aspose.com/) daha fazla bilgi için.
### S: Aspose.Tasks for Java için nereden destek alabilirim?
C: Aspose.Tasks topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks için geçici lisans satın alabilir miyim?
 C: Evet, adresinden geçici bir lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
