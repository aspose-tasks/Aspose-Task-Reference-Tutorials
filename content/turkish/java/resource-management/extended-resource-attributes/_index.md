---
title: Aspose.Tasks ile MS Project Niteliklerini Verimli Bir Şekilde Yönetin
linktitle: Aspose.Tasks'ta Genişletilmiş Kaynak Niteliklerini Yönetme
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak genişletilmiş Microsoft Project kaynak niteliklerini verimli bir şekilde nasıl kullanacağınızı öğrenin. Kolay adımlar ve kapsamlı kılavuz.
type: docs
weight: 11
url: /tr/java/resource-management/extended-resource-attributes/
---
## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak genişletilmiş Microsoft Project kaynak niteliklerini etkili bir şekilde nasıl kullanacağımızı inceleyeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak yönetmelerine olanak tanıyan, görev ve kaynak yönetimi için kapsamlı işlevler sunan güçlü bir kitaplıktır.
## Önkoşullar
Devam etmeden önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1. Java Geliştirme Ortamı: Sisteminizde Java Geliştirme Kitini (JDK) kurun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): Java geliştirme için Eclipse veya IntelliJ IDEA gibi bir IDE'nin kurulu olmasını sağlayın.

## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın. 
```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```
## 1. Adım: Veri Dizinini Tanımlayın
Proje verilerinizin bulunduğu dizinin yolunu ayarlayın.
```java
String dataDir = "Your Data Directory";
```
## Adım 2: Proje Dosyasını Yükleyin
 Bir örnek oluştur`Project` Microsoft Project dosyanızı yükleyerek nesneyi oluşturun.
```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```
## Adım 3: Genişletilmiş Özniteliği Tanımlayın
Kaynağın genişletilmiş özniteliğini tanımlayın.
```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```
## Adım 4: Genişletilmiş Öznitelik Oluşturun ve Değeri Ayarlayın
Genişletilmiş özniteliği oluşturun ve ona sayısal bir değer atayın.
```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```
## Adım 5: Kaynak ve Genişletilmiş Özellik Ekleme
Genişletilmiş özniteliğiyle birlikte projeye yeni bir kaynak ekleyin.
```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```
## Adım 6: Projeyi Kaydet
Değiştirilen projeyi yeni bir dosyaya kaydedin.
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
## Adım 7: Sonucu Görüntüle
İşlemin tamamlandığını onaylayan bir mesaj yazdırın.
```java
System.out.println("Process completed Successfully");
```
Bu adımları titizlikle takip ederek, Aspose.Tasks for Java'yı kullanarak genişletilmiş MS Project kaynak niteliklerini sorunsuz bir şekilde yönetebilirsiniz.

## Çözüm
Sonuç olarak Aspose.Tasks for Java, genişletilmiş kaynak niteliklerinin yönetimi de dahil olmak üzere Microsoft Project dosyalarının yönetimi için güçlü yetenekler sağlar. Geliştiriciler, Aspose.Tasks'ın sunduğu işlevlerden yararlanarak çeşitli gereksinimleri karşılamak için proje verilerini verimli bir şekilde işleyebilir.
## SSS'ler
### Aspose.Tasks karmaşık proje yapılarını yönetebilir mi?
Evet, Aspose.Tasks karmaşık proje yapıları için kapsamlı destek sunarak kullanıcıların görevleri, kaynakları ve nitelikleri sorunsuz bir şekilde yönetmesine olanak tanır.
### Aspose.Tasks, Microsoft Project'in en son sürümleriyle uyumlu mu?
Aspose.Tasks, Microsoft Project'in en son sürümleriyle uyumluluğu sağlamak için düzenli olarak güncellenerek kullanıcılara proje yönetimi için güvenilir bir çözüm sunar.
### Aspose.Tasks platformlar arası geliştirmeyi destekliyor mu?
Evet, geliştiriciler Aspose.Tasks for Java'yı farklı platformlarda kullanabilir, bu da onu proje yönetimi uygulamaları için çok yönlü bir seçim haline getirir.
### Aspose.Tasks'i diğer Java kütüphaneleriyle entegre edebilir miyim?
Kesinlikle Aspose.Tasks, işlevselliği geliştirmek ve geliştirme süreçlerini kolaylaştırmak için diğer Java kitaplıklarıyla sorunsuz bir şekilde entegre edilebilir.
### Aspose.Tasks kullanıcıları için teknik destek mevcut mu?
Evet, kullanıcılar Aspose.Tasks forumu aracılığıyla teknik desteğe erişebilir ve burada yardım arayabilirler ve toplulukla etkileşime geçebilirler.