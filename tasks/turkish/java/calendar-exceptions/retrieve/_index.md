---
title: Aspose.Tasks ile Takvim İstisnalarını Alın
linktitle: Aspose.Tasks ile Takvim İstisnalarını Alın
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project'ten takvim istisnalarını nasıl alacağınızı öğrenin. Kusursuz entegrasyon için adım adım eğitim.
weight: 13
url: /tr/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Takvim İstisnalarını Alın

## giriiş
Bu eğitimde, Java için Aspose.Tasks kütüphanesini kullanarak MS Project'ten takvim istisnalarının nasıl alınacağını inceleyeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmelerine olanak tanıyan güçlü bir araçtır. Kolay anlaşılması için her örneği birden fazla adıma ayırarak süreç boyunca size adım adım rehberlik edeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java'yı şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi istediğiniz herhangi bir IDE'yi kullanabilirsiniz.

## Paketleri İçe Aktar
Aspose.Tasks ile çalışmak için öncelikle gerekli paketleri içe aktarmanız gerekir:
```java
import com.aspose.tasks.*;
```
## 1. Adım: Veri Dizininizi Kurun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
```
 Değiştirildiğinden emin olun`"Your Data Directory"` MS Project dosyasını içeren dizininizin yolu ile birlikte.
## Adım 2: MS Proje Dosyasını Yükleyin
```java
Project project = new Project(dataDir + "project.mpp");
```
 Bu satır yeni bir başlangıç başlatır`Project` Yolun belirttiği MS Project dosyasını yükleyerek nesneyi oluşturun.
## 3. Adım: Takvim İstisnalarını Alın
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Burada, projedeki her takvimi ve ardından o takvim içindeki her takvim istisnasını yineliyoruz. Her istisnanın başlangıç ve bitiş tarihlerini yazdırırız.

## Çözüm
Bu eğitimde Aspose.Tasks for Java kullanarak MS Project'ten takvim istisnalarının nasıl alınacağını öğrendik. Bu basit adımları izleyerek bu işlevselliği Java uygulamalarınıza sorunsuz bir şekilde entegre edebilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.Tasks, MS Project dosyalarının farklı sürümlerini işleyebilir mi?
Evet, Aspose.Tasks, MPP, MPT ve XML formatları da dahil olmak üzere MS Project dosyalarının çeşitli sürümlerini destekler.
### Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Tasks'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Tasks for Java belgelerini nerede bulabilirim?
 Belgelere başvurabilirsiniz[Burada](https://reference.aspose.com/tasks/java/).
### Aspose.Tasks için nasıl destek alabilirim?
 Topluluk forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks için geçici lisans seçeneği var mı?
 Evet, geçici lisansları şuradan alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
