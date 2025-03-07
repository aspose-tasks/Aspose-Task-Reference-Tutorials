---
title: Aspose.Tasks Projelerinde Para Birimi Özelliklerini Ayarlama
linktitle: Aspose.Tasks Projelerinde Para Birimi Özelliklerini Ayarlama
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks projelerinde Java kullanarak para birimi özelliklerini nasıl ayarlayacağınızı öğrenin. Microsoft Project dosyalarını zahmetsizce yönetin.
weight: 11
url: /tr/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Projelerinde Para Birimi Özelliklerini Ayarlama

## giriiş
Bu eğitimde Aspose.Tasks projelerinde Java kullanarak para birimi özelliklerinin nasıl ayarlanacağını inceleyeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmelerine olanak tanıyan güçlü bir Java kitaplığıdır.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java Library: Aspose.Tasks for Java kütüphanesini aşağıdaki adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): Eclipse veya IntelliJ IDEA gibi tercih ettiğiniz IDE'yi seçin.
## Paketleri İçe Aktar
Öncelikle Java'da Aspose.Tasks ile çalışmak için gerekli paketleri içe aktaralım.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## 1. Adım: Veri Dizinini Ayarlayın
Proje dosyalarınızın bulunduğu veri dizinini ayarlayın.
```java
String dataDir = "Your Data Directory";
```
## 2. Adım: Proje Örneği Oluşturun
Aspose.Tasks'ı kullanarak yeni bir proje örneği oluşturun.
```java
Project project = new Project();
```
## 3. Adım: Para Birimi Özelliklerini Ayarlayın
Şimdi projenin para birimi özelliklerini ayarlayalım.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## Adım 4: Projeyi Kaydet
Projeyi güncellenen para birimi özellikleriyle kaydedin.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## Adım 5: Tamamlama Mesajını Görüntüleyin
İşlemin başarıyla tamamlandığını belirten bir mesaj görüntüleyin.
```java
System.out.println("Process completed Successfully");
```
Tebrikler! Aspose.Tasks projesinde para birimi özelliklerini Java kullanarak başarıyla ayarladınız.
## Çözüm
Bu eğitimde, proje dosyalarındaki para birimi özelliklerini ayarlamak için Aspose.Tasks for Java'nın nasıl kullanılacağını öğrendik. Aspose.Tasks ile geliştiriciler proje verilerini verimli bir şekilde işleyebilir, bu da onu proje yönetimi uygulamaları için değerli bir araç haline getirir.
## SSS'ler
### Aspose.Tasks'ı kullanarak tek bir projede birden fazla para birimi ayarlayabilir miyim?
Evet, Aspose.Tasks tek bir proje dosyasında birden fazla para birimini yönetmenize olanak tanır.
### Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?
Evet, Aspose.Tasks, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### Aspose.Tasks özel para birimi formatları için destek sağlıyor mu?
Kesinlikle Aspose.Tasks, belirli proje gereksinimlerini karşılamak için özel para birimi formatlarını tanımlama konusunda esneklik sunar.
### Aspose.Tasks'i diğer Java kütüphaneleri veya çerçeveleriyle entegre edebilir miyim?
Evet, Aspose.Tasks diğer Java kütüphaneleri ve çerçeveleriyle sorunsuz bir şekilde entegre edilebilir, böylece işlevselliği ve çok yönlülüğü arttırılabilir.
### Aspose.Tasks için nereden ek destek veya yardım bulabilirim?
 Ek destek için şu adresi ziyaret edebilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15), yararlı kaynaklar bulabileceğiniz ve toplulukla etkileşim kurabileceğiniz yer.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
