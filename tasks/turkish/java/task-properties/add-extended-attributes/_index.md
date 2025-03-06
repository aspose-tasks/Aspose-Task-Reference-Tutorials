---
title: Aspose.Tasks'taki Görevlere Genişletilmiş Nitelikler Ekleme
linktitle: Aspose.Tasks'taki Görevlere Genişletilmiş Nitelikler Ekleme
second_title: Aspose.Tasks Java API'si
description: Microsoft Project dosyalarını genişletilmiş niteliklerle özelleştirme konusunda Aspose.Tasks Java'nın gücünü keşfedin. Proje yönetimi yeteneklerinizi zahmetsizce geliştirin.
weight: 11
url: /tr/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'taki Görevlere Genişletilmiş Nitelikler Ekleme

## giriiş
Proje yönetimi yeteneklerinizi geliştirmek, verimli görev takibi ve kaynak yönetimi için çok önemlidir. Aspose.Tasks for Java, Java geliştiricilerinin Microsoft Project dosyalarını sorunsuz bir şekilde yönetmeleri için güçlü bir çözüm sunar. Bu eğitimde, Aspose.Tasks for Java kullanarak görevlere genişletilmiş niteliklerin nasıl ekleneceğini keşfedeceğiz, böylece proje verilerinizi özel gereksinimlerinize göre özelleştirip organize edebilirsiniz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
-  Aspose.Tasks for Java kütüphanesi kuruldu. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/tasks/java/).
- Sisteminizde yüklü bir Java Tümleşik Geliştirme Ortamı (IDE).
## Paketleri İçe Aktar
Aspose.Tasks işlevlerine erişmek için Java projenizde gerekli paketleri içe aktarın:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Şimdi her örneği birden fazla adıma ayıralım:
## 1. Düz Metin Özelliği Ekleme
1. Belge dizini yolunu ayarlayın:
```java
String dataDir = "Your Document Directory";
```
2. Yeni bir proje oluşturun:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Text1 türünün Genişletilmiş Öznitelik Tanımını oluşturun:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Tanımı projenin Genişletilmiş Öznitelikler koleksiyonuna ekleyin:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Projeye bir görev ekleyin:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Öznitelik Tanımından Genişletilmiş Bir Öznitelik Oluşturun:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Oluşturulan Genişletilmiş Özniteliğe bir değer atayın:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Genişletilmiş Özelliği göreve ekleyin:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Projeyi kaydedin:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Arama Seçeneğiyle Metin Özelliği Ekleme
Metin1'i Metin2 ile değiştirerek ve arama değerlerini özelleştirerek yukarıdaki adımların aynısını izleyin.
## 3. Arama Seçeneğiyle Süre Özelliği Ekleme
Metin1'i Süre2 ile değiştirerek ve arama değerlerini özelleştirerek yukarıdaki adımların aynısını izleyin.
## Çözüm
Bu adım adım kılavuzu takip ederek, Microsoft Project dosyalarınızdaki görevlere genişletilmiş nitelikler eklemek için Aspose.Tasks for Java'dan nasıl yararlanacağınızı öğrendiniz. Bu özelleştirme, proje yönetimi yaklaşımınızı uyarlamanıza olanak tanıyarak esnekliği ve verimliliği artırır.
## Sıkça Sorulan Sorular
### S: Aspose.Tasks for Java'yı diğer Java kütüphaneleriyle birlikte kullanabilir miyim?
C: Evet, Aspose.Tasks for Java, Java projelerinize sorunsuz bir şekilde entegre edilebilir ve diğer Java kütüphaneleriyle iyi çalışır.
### S: Aspose.Tasks for Java, büyük ölçekli proje yönetimi uygulamalarına uygun mudur?
C: Kesinlikle, Aspose.Tasks for Java, büyük ölçekli uygulamalar da dahil olmak üzere çeşitli boyutlardaki projeleri yönetmek için tasarlanmıştır.
### S: Aspose.Tasks for Java'yı ticari bir projede kullanmak için herhangi bir lisanslama hususu var mı?
 C: Evet, web sitesinde sağlanan lisans bilgilerini incelediğinizden emin olun.[Aspose.Tasks web sitesi](https://purchase.aspose.com/buy).
### S: Aspose.Tasks for Java ile ilgili nasıl destek veya yardım alabilirim?
 C: Ziyaret edin[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluk desteği ve tartışmalar için.
### S: Satın almadan önce Aspose.Tasks for Java'yı deneyebilir miyim?
 C: Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
