---
title: Aspose.Tasks'taki Dosyadan Tablo Verilerini Oku
linktitle: Aspose.Tasks'taki Dosyadan Tablo Verilerini Oku
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'nın gücünün kilidini açın. Bu kapsamlı eğitimde dosyalardan tablo verilerini çıkarmayı öğrenin.
weight: 17
url: /tr/java/project-data-reading/read-table-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'taki Dosyadan Tablo Verilerini Oku

## giriiş
Bu eğitimde Aspose.Tasks for Java kullanarak tablo verilerinin bir dosyadan nasıl okunacağını keşfedeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project belgeleriyle programlı olarak çalışmasına olanak tanıyan güçlü bir Java kitaplığıdır.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. Oracle web sitesinden indirip kurabilirsiniz.
2.  Aspose.Tasks for Java JAR Dosyası: Aspose.Tasks for Java kütüphanesini şu adresten indirin:[İndirme: {link](https://releases.aspose.com/tasks/java/) ve Java projenize ekleyin.

## Paketleri İçe Aktar
Aspose.Tasks ile çalışmak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## 1. Adım: Veri Dizinini Ayarlayın
Proje dosyanızın bulunduğu dizinin yolunu tanımlayın:
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` veri dizininizin gerçek yolu ile.
## Adım 2: Proje Dosyasını Yükleyin
Aspose.Tasks'ı kullanarak Proje dosyasını yükleyin:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 Değiştirdiğinizden emin olun`"Project2003.mpp"` Proje dosyanızın adıyla.
## 3. Adım: Tablo Bilgilerini Alın
Tabloyu projeden alın ve alanları arasında yineleyin:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
Bu kod parçacığı, tablo alanlarıyla ilgili genişlik, başlık ve hizalama gibi bilgileri alır.

## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak tablo verilerinin bir dosyadan nasıl okunacağını öğrendik. Bu adımları izleyerek, Java uygulamalarınızdaki Microsoft Project belgelerinden verileri verimli bir şekilde çıkarabilir ve işleyebilirsiniz.
## SSS'ler
### S: Aspose.Tasks Microsoft Project'in tüm sürümleriyle uyumlu mu?
C: Aspose.Tasks, Project 2003, 2007, 2010, 2013 ve 2016 dahil olmak üzere Microsoft Project'in çeşitli sürümlerini destekler.
### S: Tablo verilerini değiştirip Proje dosyasına geri kaydedebilir miyim?
C: Evet, tablo verilerini programlı olarak değiştirmek ve değişiklikleri orijinal Proje dosyasına kaydetmek için Aspose.Tasks'ı kullanabilirsiniz.
### S: Aspose.Tasks'ın ticari kullanımı ayrı bir lisans gerektiriyor mu?
 C: Evet, Aspose.Tasks'ı ticari bir ortamda kullanmayı düşünüyorsanız lisans satın almanız gerekir. adresinden lisans alabilirsiniz.[satın alma sayfası](https://purchase.aspose.com/buy).
### S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[sürümler sayfası](https://releases.aspose.com/).
### S: Aspose.Tasks için nereden yardım ve destek bulabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15)Topluluktan ve Aspose ekibinden yardım ve destek için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
