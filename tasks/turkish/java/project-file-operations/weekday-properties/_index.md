---
title: Aspose.Tasks'ta Hafta İçi Özellikleri
linktitle: Aspose.Tasks'ta Hafta İçi Özellikleri
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'da hafta içi özelliklerini verimli bir şekilde yönetmeyi öğrenin. Haftanın başlangıç tarihlerini, aylık günleri ve daha fazlasını kolaylıkla özelleştirin.
weight: 25
url: /tr/java/project-file-operations/weekday-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Hafta İçi Özellikleri

## giriiş
Aspose.Tasks for Java, Java geliştiricilerinin makinede Microsoft Project yüklü olmadan Microsoft Project dosyalarıyla çalışmasını sağlayan güçlü bir API'dir. Temel işlevlerinden biri, kullanıcıların haftanın başlangıç tarihlerini, aylık günleri, günlük dakikaları ve haftalık dakikaları özelleştirmesine olanak tanıyarak hafta içi özelliklerini yönetmektir. Bu eğitimde, bu özelliklerin etkili bir şekilde nasıl kullanılacağına dair ayrıntılı bir kılavuz sağlanacaktır.
## Önkoşullar
Aspose.Tasks for Java'ya dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
### Java Geliştirme Kiti (JDK)
Sisteminizde JDK'nın kurulu olduğundan emin olun. En son JDK'yı Oracle web sitesinden indirip yükleyebilirsiniz.
### Aspose.Tasks for Java Library
 Aspose.Tasks for Java kütüphanesini web sitesinden indirip yükleyin. İndirme linkine ulaşabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
### Entegre Geliştirme Ortamı (IDE)
Java geliştirme için tercih ettiğiniz IDE'yi seçin. Popüler seçenekler arasında IntelliJ IDEA, Eclipse veya NetBeans bulunur.
## Paketleri İçe Aktar
Başlamak için gerekli Aspose.Tasks paketlerini Java projenize aktarın. İşte nasıl:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Şimdi daha iyi anlamak için verilen örneği birden fazla adıma ayıralım.
## Adım 1: Proje Dosyasını Yükleyin
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Bu adım, belirtilen veri dizininden "project.mpp" adlı bir Proje dosyasının yüklenmesini içerir.
## Adım 2: Hafta İçi Özelliklerini Görüntüleyin
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Burada yüklenen projenin hafta başlangıç tarihi, ay başına gün, gün başına dakika ve hafta başına dakika özelliklerini alıp yazdırıyoruz.
## 3. Adım: Hafta İçi Özelliklerini Ayarlama
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Bu adım, yeni bir proje örneği oluşturmayı ve haftanın başlangıç günü, aylık günler, günlük dakikalar ve haftalık dakikalar gibi özel hafta içi özellikleri ayarlamayı içerir.
## Adım 4: Projeyi Kaydet
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Son olarak değiştirilen projeyi güncellenmiş hafta içi özellikleriyle birlikte XML dosyası olarak kaydediyoruz.
## Adım 5: Sonucu Görüntüleyin
```java
System.out.println("Process completed Successfully");
```
Bu adım, sürecin başarıyla tamamlandığını teyit eder.
## Çözüm
Aspose.Tasks for Java'da hafta içi özelliklerine hakim olmak, etkili proje yönetimi için çok önemlidir. Bu öğreticiyi takip ederek hafta içi özelliklerini zahmetsizce nasıl değiştireceğinizi ve özelleştireceğinizi öğrendiniz. Proje yönetimi yeteneklerinizi geliştirmek için daha fazla belge ve örnekleri keşfedin.
## SSS'ler
### S: Aspose.Tasks for Java karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks for Java, karmaşık proje yapılarının kolaylıkla yönetilmesi için kapsamlı destek sağlar.
### S: Aspose.Tasks for Java, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Kesinlikle, Aspose.Tasks for Java, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek platformlar arasında uyumluluk sağlar.
### S: Aspose.Tasks for Java'yı mevcut Java uygulamalarıma entegre edebilir miyim?
C: Evet, Aspose.Tasks for Java, Java uygulamalarınızı güçlü proje yönetimi özellikleriyle geliştirmenize olanak tanıyan kusursuz entegrasyon yetenekleri sunar.
### S: Aspose.Tasks for Java dokümantasyon ve destek sağlıyor mu?
 C: Evet, Aspose.Tasks for Java ile ilgili kapsamlı belgelere ve topluluk desteğine kendi sitelerinden erişebilirsiniz.[İnternet sitesi](https://releases.aspose.com/).
### S: Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
C: Evet, Aspose.Tasks for Java'nın ücretsiz deneme sürümünü şuradan indirebilirsiniz:[İnternet sitesi](https://reference.aspose.com/tasks/java/) Bir satın alma işlemi yapmadan önce özelliklerini keşfetmek için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
