---
title: Aspose.Tasks ile MS Project Kaynak Yüzdesi Hesaplaması
linktitle: Aspose.Tasks'ta Kaynaklar için Yüzde Hesaplamaları Yapın
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project kaynak yüzdelerini nasıl hesaplayacağınızı öğrenin. Kod örneklerinin yer aldığı adım adım kılavuz.
type: docs
weight: 14
url: /tr/java/resource-management/percentage-calculations/
---
## giriiş
Aspose.Tasks for Java kullanarak MS Project kaynakları için yüzde hesaplamaları gerçekleştirmeye yönelik adım adım kılavuzumuza hoş geldiniz. Bu eğitimde, Microsoft Project dosyalarından kaynak verilerini verimli bir şekilde işlemek ve çıkarmak için Aspose.Tasks'tan yararlanma sürecini derinlemesine inceleyeceğiz. Aspose.Tasks, Microsoft Project belgeleriyle çalışmak için kapsamlı özellikler sağlayan, geliştiricilerin proje yönetimi işlevlerini Java uygulamalarına sorunsuz bir şekilde entegre etmelerine olanak tanıyan güçlü bir Java API'sidir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### Java Geliştirme Ortamı
 Sisteminizde Java Development Kit'in (JDK) kurulu olduğundan emin olun. JDK'yı şu adresten indirip yükleyebilirsiniz:[Burada](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks Kitaplığı
Aspose.Tasks kütüphanesinin Java projenize entegre olması gerekir. Henüz yapmadıysanız kütüphaneyi şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/tasks/java/) ve belgelerde verilen kurulum talimatlarını izleyin[Burada](https://reference.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Kodlamaya başlamadan önce bu eğitim için gerekli olan paketleri içe aktaralım:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## 1. Adım: Proje Dosya Yolunu Ayarlayın
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` Microsoft Project dosyanızın yolu ile.
## Adım 2: Projeyi Yükleyin
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Bu kod, belirtilen veri dizininde bulunan "Software Development.mpp" adlı Microsoft Project dosyasını yükler.
## Adım 3: Kaynakları Yineleyin
```java
for (Resource res : prj.getResources()) {
```
Projedeki her kaynağın üzerinden geçiyoruz.
## 4. Adım: Kaynak Adını ve Tamamlanan İşin Yüzdesini Kontrol Edin
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Kaynak adının boş olup olmadığını kontrol ediyoruz ve ardından her kaynak için tamamlanan işin yüzdesini yazdırıyoruz.

## Çözüm
Bu eğitimde, MS Project kaynaklarına yönelik yüzde hesaplamalarını verimli bir şekilde gerçekleştirmek için Aspose.Tasks for Java'yı nasıl kullanacağımızı öğrendik. Bu adımları izleyerek proje yönetimi işlevlerini Java uygulamalarınıza sorunsuz bir şekilde entegre edebilir, proje kaynak kullanımına ilişkin gelişmiş kontrol ve öngörüler sağlayabilirsiniz.
## SSS'ler
### Aspose.Tasks for Java'yı diğer Java çerçeveleriyle kullanabilir miyim?
Evet, Aspose.Tasks for Java, Spring, Hibernate ve daha fazlası gibi çeşitli Java çerçeveleriyle uyumludur.
### Aspose.Tasks, Microsoft Project dosyalarının tüm sürümlerini destekliyor mu?
Aspose.Tasks, MPP, MPT, XML ve daha fazlası dahil olmak üzere Microsoft Project dosyalarının tüm sürümleri için destek sağlar.
### Aspose.Tasks'ı kullanarak proje programlarını değiştirebilir miyim?
Aspose.Tasks kesinlikle proje programlarını değiştirmek için görevler, kaynaklar, takvimler ve daha fazlasını içeren kapsamlı özellikler sunar.
### Aspose.Tasks desteği için bir topluluk forumu var mı?
 Evet, Aspose.Tasks topluluk forumunda yardım bulabilir ve diğer kullanıcılarla iletişim kurabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks değerlendirme amacıyla geçici lisanslar sunuyor mu?
 Evet, değerlendirme için geçici bir lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).