---
title: Aspose.Tasks Projelerinde Genişletilmiş Nitelikleri Yönetme
linktitle: Aspose.Tasks Projelerinde Genişletilmiş Nitelikleri Yönetme
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks projelerinde Java'yı verimli bir şekilde kullanarak genişletilmiş özelliklerin nasıl ele alınacağını öğrenin. Etkili proje yönetimi için adım adım kılavuz.
type: docs
weight: 13
url: /tr/java/project-management/extended-attributes/
---
## giriiş
Proje yönetiminde genişletilmiş özelliklerin yönetilmesi, proje verilerinin özelleştirilmesi ve geliştirilmesi açısından çok önemlidir. Aspose.Tasks for Java, MS Project dosyalarındaki genişletilmiş nitelikleri verimli bir şekilde yönetmek için güçlü araçlar sağlar. Bu eğitim, süreç boyunca size adım adım rehberlik edecek ve her kavramı iyice kavramanızı sağlayacaktır.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java programlamanın temel bilgisi.
2. JDK (Java Development Kit) sisteminizde kuruludur.
3. Aspose.Tasks for Java kütüphanesini indirip Java projenize kurun.
## Paketleri İçe Aktar
Öncelikle başlamak için gerekli paketleri içe aktaralım:
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## 1. Adım: Veri Dizinini Tanımlayın
```java
String dataDir = "Your Data Directory";
```
 Değiştirildiğinden emin olun`"Your Data Directory"` projenizin veri dizininin yolu ile.
## Adım 2: Proje Dosyasını Yükleyin
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 Bu satır, adlı proje dosyasını yükler.`"project5.mpp"`.
## 3. Adım: Genişletilmiş Öznitelik Tanımlarına Erişim
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
Burada projeden genişletilmiş öznitelik tanımları koleksiyonunu alıyoruz.
## Adım 4: Genişletilmiş Öznitelik Tanımı Oluşturun
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 Bu kod bölümü, özel alan türünü şu şekilde belirterek, görevler için genişletilmiş bir öznitelik tanımı oluşturur:`Start` ve özellik adı olarak`"Start 7"`.
## Adım 5: Projeye Tanım Ekleme
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
Yeni oluşturulan genişletilmiş öznitelik tanımını hem projeye hem de öznitelik tanımları koleksiyonuna ekliyoruz.
## Adım 6: Göreve ve Genişletilmiş Niteliklere Erişim
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
Burada projeden bir görevi ve onun ilişkili genişletilmiş niteliklerini alıyoruz.
## Adım 7: Genişletilmiş Öznitelik Örneği Oluşturun
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
Bu adım, önceden tanımlanmış öznitelik tanımına dayalı olarak genişletilmiş özniteliğin bir örneğini oluşturur.
## Adım 8: Özellik Değerini Ayarlayın
```java
Date date = new Date();
ea.setDateValue(date);
```
Genişletilmiş özelliğin değerini bu durumda bir tarih değeri olarak belirledik.
## Adım 9: Göreve Özellik Ekleme
```java
eas.add(ea);
```
Son olarak Extended niteliğini göreve ekliyoruz.
## Adım 10: Projeyi Kaydet
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
Bu satır, değiştirilmiş projeyi genişletilmiş öznitelik eklenmiş olarak bir XML dosyasına kaydeder.
## Çözüm
Bu eğitimde Aspose.Tasks projelerinde Java kullanarak genişletilmiş niteliklerin nasıl işleneceğini öğrendiniz. Bu adımları izleyerek özel proje verilerini verimli bir şekilde yönetebilir ve proje yönetimi becerilerinizi geliştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks'ı diğer programlama dilleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks Java, .NET ve C dahil birden fazla programlama dilini destekler++.
### S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?
C: Evet, Aspose.Tasks web sitesinden ücretsiz deneme sürümünü indirebilirsiniz.
### S: Genişletilmiş özellik türlerini özelleştirebilir miyim?
C: Kesinlikle Aspose.Tasks, proje ihtiyaçlarınıza göre uyarlanmış özel genişletilmiş özellik türleri tanımlamanıza olanak tanır.
### S: Aspose.Tasks belgelerine nasıl erişebilirim?
 C: Aspose.Tasks web sitesinde kapsamlı belgeler bulabilirsiniz.[dokümantasyon](https://reference.aspose.com/tasks/java/).
### S: Aspose.Tasks kullanıcıları için teknik destek mevcut mu?
 C: Evet, Aspose.Tasks forumu aracılığıyla teknik desteğe ulaşabilirsiniz.[İnternet sitesi](https://forum.aspose.com/c/tasks/15).