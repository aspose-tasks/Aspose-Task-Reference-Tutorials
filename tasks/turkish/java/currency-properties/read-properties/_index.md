---
title: Aspose.Tasks Projelerinde Para Birimi Özelliklerini Okuyun
linktitle: Aspose.Tasks Projelerinde Para Birimi Özelliklerini Okuyun
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project dosyalarından para birimi bilgilerini nasıl çıkaracağınızı öğrenin. Adım adım kılavuz sağlanmıştır.
weight: 10
url: /tr/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Projelerinde Para Birimi Özelliklerini Okuyun

## giriiş
Bu eğitimde, Microsoft Project dosyalarından para birimi özelliklerini okumak için Aspose.Tasks for Java'yı nasıl kullanacağımızı öğreneceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project'in kurulmasına gerek kalmadan Microsoft Project belgelerini değiştirmesine olanak tanıyan güçlü bir Java API'sidir. Aşağıda özetlenen adımları izleyerek para birimiyle ilgili bilgileri zahmetsizce çıkarabileceksiniz.
## Önkoşullar
Bu eğitime devam etmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java JAR: Aspose.Tasks for Java kütüphanesini şu adresten indirin:[Burada](https://releases.aspose.com/tasks/java/) ve Java projenize ekleyin.
## Paketleri İçe Aktar
Gerekli paketleri Java sınıfınıza aktararak başlayın:
```java
import com.aspose.tasks.*;
```
## 1. Adım: Proje Dizininizi Kurun
Öncelikle Microsoft Project dosyanızın bulunduğu proje dizininizi kurun. Bu dizin yolunu şu şekilde tanımlayabilirsiniz:
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` proje dizininizin gerçek yolu ile.
## 2. Adım: Proje Okuyucu Örneği Oluşturun
 Bir örnek oluştur`Project` Microsoft Project dosyanızın yolunu sağlayarak nesneyi:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Değiştirildiğinden emin olun`"project.mpp"` MS Project dosyanızın adıyla.
## Adım 3: Para Birimi Özelliklerini Görüntüleyin
Proje dosyasından para birimi özelliklerini alın ve görüntüleyin:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Bu kod bölümü, MS Project dosyasından para birimi kodu, rakamlar, sembol ve sembol konumu gibi bilgileri alır ve bunları konsola yazdırır.
## Adım 4: Sürecin Tamamlanması
Son olarak işlemin başarıyla tamamlandığını belirten bir mesaj yazdırın:
```java
System.out.println("Process completed Successfully");
```
## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak Microsoft Project dosyalarından para birimi özelliklerinin nasıl okunacağını araştırdık. Belirtilen adımları izleyerek, proje dosyalarınızdan para birimiyle ilgili bilgileri program aracılığıyla zahmetsizce çıkarabilir ve Java uygulamalarınızla sorunsuz entegrasyona olanak tanıyabilirsiniz.
## SSS'ler
### S: Aspose.Tasks Microsoft Project'in tüm sürümleriyle uyumlu mu?
C: Aspose.Tasks, MS Project 2003-2021 tarafından oluşturulan MPP dosyaları da dahil olmak üzere Microsoft Project'in çeşitli sürümlerini destekler.
### S: Aspose.Tasks'ı kullanarak para birimi özelliklerini değiştirebilir miyim?
C: Evet, Aspose.Tasks, MS Project dosyalarındaki para birimi özelliklerini programlı olarak okumanıza ve değiştirmenize olanak tanır.
### S: Aspose.Tasks ticari kullanıma uygun mudur?
 C: Evet, Aspose.Tasks profesyonel kullanım için tasarlanmış ticari bir kütüphanedir. Lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### S: Aspose.Tasks ücretsiz deneme sunuyor mu?
 C: Evet, Aspose.Tasks'ın ücretsiz deneme sürümünden yararlanabilirsiniz.[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks için nereden yardım veya destek alabilirim?
 C: Aspose.Tasks forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15) herhangi bir yardım veya sorularınız için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
