---
title: Aspose.Tasks'ta MS Project Verilerini Excel'e Kaydetme
linktitle: Aspose.Tasks'ta Verileri Excel'e Kaydetme
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak Microsoft Project verilerini Excel dosyalarına nasıl kaydedeceğinizi öğrenin. Java geliştiricileri için kolay entegrasyon.
weight: 19
url: /tr/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta MS Project Verilerini Excel'e Kaydetme

## giriiş
Aspose.Tasks for Java, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. Bu eğitimde, verileri bir Proje dosyasından bir Excel dosyasına adım adım kaydetme sürecinde size rehberlik edeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun. JDK'nın en son sürümünü Oracle web sitesinden indirip yükleyebilirsiniz.
2.  Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini şu adresten indirin:[İndirme: {link](https://releases.aspose.com/tasks/java/) ve Java projenize ekleyin.

## Paketleri İçe Aktar
Aspose.Tasks ile çalışmak için öncelikle Java kodunuza gerekli paketleri içe aktarmanız gerekir.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Sağlanan örneği birden çok adıma ayıralım:
## 1. Adım: Veri Dizini Yolunu Tanımlayın
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"`Proje dosyasının bulunduğu veri dizininizin yolu ile birlikte.
## Adım 2: Proje Dosyasını Yükleyin
```java
Project project = new Project(dataDir + "project5.mpp");
```
Bu kod satırı, belirtilen veri dizininden "project5.mpp" adlı Proje dosyasını yükler.
## Adım 3: Projeyi XLSX olarak kaydedin
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Burada,`save` yöntemi, yüklenen Proje dosyasını aynı veri dizinine "project1.xlsx" adıyla Excel dosyası olarak kaydetmek için kullanılır. Biz şunu belirtiyoruz`SaveFileFormat.Xlsx` XLSX formatında kaydetmek için parametre.

## Çözüm
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak bir Microsoft Project dosyasındaki verileri bir Excel dosyasına nasıl kaydedeceğimizi öğrendik. Verilen adımları takip ederek bu işlevselliği Java uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## SSS'ler
### Proje verilerini programlı olarak değiştirmek için Aspose.Tasks for Java'yı kullanabilir miyim?
Evet, Aspose.Tasks for Java, proje dosyalarını okumak, yazmak ve değiştirmek de dahil olmak üzere proje verilerini işlemek için kapsamlı özellikler sağlar.
### Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Tasks for Java'nın ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Tasks for Java belgelerini nerede bulabilirim?
Aspose.Tasks for Java belgelerini bulabilirsiniz[Burada](https://reference.aspose.com/tasks/java/).
### Aspose.Tasks for Java ile ilgili herhangi bir sorun veya soru için nasıl destek alabilirim?
 Aspose.Tasks forumunu ziyaret ederek destek alabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
 Evet, adresinden geçici bir lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
