---
title: Aspose.Tasks'a Güncellenmiş Kaynak Verilerini Yazma
linktitle: Aspose.Tasks'a Güncellenmiş Kaynak Verilerini Yazma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project dosyalarındaki kaynak verilerini zahmetsizce nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 21
url: /tr/java/resource-management/write-updated-resource-data/
---
## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak Microsoft Project kaynak verilerini güncelleme konusunda size rehberlik edeceğiz. Aspose.Tasks, sisteminizde Microsoft Project'in kurulmasına gerek kalmadan Microsoft Project dosyalarını değiştirmenize olanak tanıyan güçlü bir Java API'sidir.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Tasks Java kütüphanesi için. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Java programlamanın temel bilgisi.

## Paketleri İçe Aktar

Öncelikle Java kodunuzdaki Aspose.Tasks ile çalışmak için gerekli paketleri içe aktarmanız gerekir. Aşağıdaki içe aktarma ifadelerini Java dosyanıza ekleyin:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 1. Adım: Veri Dizininizi Kurun

Veri dosyalarınızın bulunduğu dizini tanımlayın:

```java
String dataDir = "Your Data Directory";
```

## Adım 2: Giriş ve Çıkış Dosyalarını Belirleyin

Giriş MS Project dosyasının ve sonuçta ortaya çıkan güncellenmiş dosyanın yollarını tanımlayın:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Güncellemek için dosyayı bir rsc ile test edin
String resultFile = dataDir + "OutputMPP.mpp"; // Test projesi yazmak için dosya
```

## Adım 3: Projeyi Yükleyin

 MS Project dosyasını bir`Project` nesne:

```java
Project project = new Project(file);
```

## 4. Adım: Kaynak Ekleme ve Nitelikleri Ayarlama

Projeye yeni bir kaynak ekleyin ve standart ücret, fazla mesai ücreti ve grup gibi özelliklerini ayarlayın:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Adım 5: Projeyi Kaydet

Güncellenen projeyi değiştirilmiş kaynak verileriyle kaydedin:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Çözüm

Bu eğitimde MS Project kaynak verilerinin Aspose.Tasks for Java kullanılarak nasıl güncelleneceğini gösterdik. Bu adımları izleyerek, MS Project dosyalarınızdaki kaynak bilgilerini programlı bir şekilde verimli bir şekilde değiştirebilirsiniz.

## SSS'ler

### S1: Aspose.Tasks for Java'yı kullanarak aynı projede birden fazla kaynağı güncelleyebilir miyim?

C1: Evet, birden fazla kaynağı yineleyerek ve niteliklerini buna göre ayarlayarak güncelleyebilirsiniz.

### S2: Aspose.Tasks, MS Project'in yanı sıra diğer dosya formatlarını da destekliyor mu?

Cevap2: Evet, Aspose.Tasks XML, MPP ve daha fazlasını içeren çeşitli dosya formatlarını destekler.

### S3: Aspose.Tasks Java'nın farklı sürümleriyle uyumlu mu?

Cevap3: Aspose.Tasks, Java sürüm 6 ve üzeri ile uyumludur.

### S4: Aspose.Tasks ile MS Project dosyaları üzerinde diğer işlemleri gerçekleştirebilir miyim?

C4: Evet, okuma, yazma ve görevleri, kaynakları ve takvimleri değiştirme gibi çok çeşitli işlemleri gerçekleştirebilirsiniz.

### S5: Aspose.Tasks için nereden ek yardım veya destek bulabilirim?

 A5: ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) herhangi bir yardım veya sorularınız için.
