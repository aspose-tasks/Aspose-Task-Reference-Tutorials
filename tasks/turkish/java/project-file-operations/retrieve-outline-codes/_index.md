---
title: Aspose.Tasks'ta MS Project Anahat Kodlarını Alma
linktitle: Aspose.Tasks'ta Anahat Kodlarını Alma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak Microsoft Project anahat kodlarını programlı olarak nasıl alacağınızı öğrenin. Proje yönetimi yeteneklerinizi geliştirin.
weight: 15
url: /tr/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta MS Project Anahat Kodlarını Alma

## giriiş
Bu eğitimde Aspose.Tasks for Java'yı kullanarak Microsoft Project anahat kodlarını nasıl alacağımızı öğreneceğiz. MS Project'teki anahat kodları, proje görevlerini, kaynaklarını ve atamalarını kategorize etmek ve düzenlemek için yapılandırılmış bir yol sağlar. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmesine ve yönetmesine olanak tanıyan güçlü bir Java kitaplığıdır.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
### 1. Java Geliştirme Ortamı
Sisteminizde Java Development Kit'in (JDK) kurulu olduğundan emin olun. JDK'yı Oracle web sitesinden indirip yükleyebilirsiniz.
### 2. Aspose.Tasks Kitaplığı
 Aspose.Tasks kütüphanesini indirin ve Java projenize ekleyin. Kütüphaneyi adresinden indirebilirsiniz.[Aspose.Tasks for Java İndirme Sayfası](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Öncelikle Java kodunuzdaki Aspose.Tasks'tan gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Şimdi sağlanan örnek kodu birden çok adıma ayıralım:
## Adım 1: Projeyi Yükleyin
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 Bu adımda Microsoft Project dosyasını bir klasöre yüklüyoruz.`Project` Sağlanan dosya adını kullanarak nesne.
## 2. Adım: Anahat Kodlarını Alın
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Projedeki her anahat kod tanımını yineliyoruz.
## 3. Adım: Anahat Kodu Özelliklerine Erişim
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Anahat kodu tanımının Takma Ad, Alan Kimliği ve Alan Adı gibi çeşitli özelliklerini alıp yazdırıyoruz.
## 4. Adım: Kurumsal Özel Kodu Kontrol Edin
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Anahat kodunun kurumsal özel bir kod olup olmadığını kontrol ediyoruz ve sonucu buna göre yazdırıyoruz.
## Adım 5: Anahat Kodu Maskelerini Görüntüleyin
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Anahat koduyla ilişkili her maskeyi yineliyoruz ve düzeyini ve maske değerini yazdırıyoruz.
## Adım 6: Anahat Kodu Değerlerini Görüntüleyin
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Her anahat kod değerini yineliyoruz ve açıklamasını, değer kimliğini, değerini ve türünü yazdırıyoruz.
## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak MS Project taslak kodlarını nasıl alacağımızı öğrendik. Sağlanan adımları izleyerek Java uygulamalarınızdaki anahat kodlarına etkili bir şekilde erişebilir ve bunları yönetebilir, böylece gelişmiş proje yönetimi yeteneklerini etkinleştirebilirsiniz.
## SSS'ler
### S1: Bir Proje dosyasındaki anahat kodlarını değiştirmek için Aspose.Tasks for Java'yı kullanabilir miyim?
C: Evet, Aspose.Tasks for Java, MS Project dosyalarındaki anahat kodlarını programlı olarak değiştirmek için API'ler sağlar.
### S2: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks for Java'nın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Aspose.Tasks web sitesi](https://releases.aspose.com/).
### S3: Aspose.Tasks for Java için nasıl teknik destek alabilirim?
 C: adresini ziyaret ederek teknik destek alabilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) ve sorularınızı oraya gönderiyorsunuz.
### S4: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
 C: Evet, Aspose.Tasks for Java için geçici lisansı şu adresten satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/temporary-license/).
### S5: Aspose.Tasks for Java'nın tüm belgelerini nerede bulabilirim?
 C: Şuraya başvurabilirsiniz:[dokümantasyon](https://reference.aspose.com/tasks/java/) Aspose.Tasks for Java kullanımına ilişkin ayrıntılı bilgi için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
