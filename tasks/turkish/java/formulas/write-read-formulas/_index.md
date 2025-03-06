---
title: Aspose.Tasks'ta MS Project Formüllerini Yazma ve Okuma
linktitle: Aspose.Tasks'ta Formül Yazma ve Okuma
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java ile MS Project formüllerini verimli bir şekilde yazmayı ve okumayı öğrenin. Proje yönetimi becerilerinizi geliştirin.
weight: 12
url: /tr/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta MS Project Formüllerini Yazma ve Okuma

## giriiş
Proje yönetimi alanında verilerin etkili bir şekilde kullanılması çok önemlidir. Aspose.Tasks for Java, Microsoft Project dosyalarından verilerin işlenmesini ve çıkarılmasını kolaylaştıran güçlü bir çözümdür. Sunduğu güçlü özelliklerden biri, MS Project formüllerini yazma ve okuma yeteneğidir. Bu eğitim, proje yönetimi görevlerinizi geliştirmek için bu işlevsellikten yararlanma sürecinde size rehberlik edecektir.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java'yı şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): Java geliştirme için tercih ettiğiniz IDE'yi seçin.

## Paketleri İçe Aktarma
Başlamak için gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## 1. Adım: Veri Dizinini Ayarlayın
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
```
Bu adımda MS Project dosyalarınızın bulunduğu dizini tanımlayın.
## Adım 2: Proje Dosyasını Yükleyin
```java
Project project = new Project(dataDir + "project.mpp");
```
Burada, MS Project dosyasını bir`Project` manipülasyon için nesne.
## 3. Adım: Özel Formülü Tanımlayın
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
Bu adım, görev maliyetini iki katına çıkaran bir formüle sahip özel bir alan oluşturmayı içerir.
## 4. Adım: Görev Ekleme ve Maliyeti Ayarlama
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Burada yeni bir görev ekleniyor ve maliyeti 100 olarak ayarlanıyor.
## Adım 5: Proje Dosyasını Kaydet
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Son olarak değiştirilen proje dosyasını kaydedin.

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak MS Project formüllerinin nasıl yazılacağını ve okunacağını araştırdık. Bu adımları izleyerek proje verilerini özel gereksinimlerinizi karşılayacak şekilde verimli bir şekilde değiştirebilirsiniz.
## SSS'ler
### Aspose.Tasks MS Project'in tüm sürümleriyle uyumlu mu?
Aspose.Tasks, MS Project'in çeşitli sürümleriyle uyumluluk sunarak kullanıcılara esneklik sağlar.
### Aspose.Tasks'ı mevcut Java projeme entegre edebilir miyim?
Kesinlikle! Aspose.Tasks, basit API kullanımı sayesinde Java projeleriyle kusursuz entegrasyon sağlar.
### Oluşturabileceğim formül türlerinde herhangi bir sınırlama var mı?
Aspose.Tasks ile proje ihtiyaçlarınıza uygun özel formüller oluşturma konusunda geniş bir esnekliğe sahip olursunuz.
### Aspose.Tasks çoklu platform dağıtımını destekliyor mu?
Evet, Aspose.Tasks birden fazla platformda dağıtımı destekleyerek çok yönlülüğünü artırır.
### Aspose.Tasks için nasıl teknik destek alabilirim?
 Teknik yardım ve topluluk desteği için şu adresi ziyaret edin:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
