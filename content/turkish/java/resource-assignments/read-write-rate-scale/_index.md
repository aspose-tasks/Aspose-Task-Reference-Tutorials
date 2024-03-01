---
title: Aspose.Tasks'ta Kaynak Atamaları için Okuma ve Yazma Hızı Ölçeği
linktitle: Aspose.Tasks'ta Kaynak Atamaları için Okuma ve Yazma Hızı Ölçeği
second_title: Aspose.Tasks Java API'si
description: Bu kapsamlı eğitimle Aspose.Tasks for Java'da kaynak atamalarının oran ölçeğini etkili bir şekilde nasıl yöneteceğinizi öğrenin.
type: docs
weight: 20
url: /tr/java/resource-assignments/read-write-rate-scale/
---
## giriiş
Bu eğitimde, Microsoft Project dosyalarıyla programlı olarak çalışmak için güçlü bir kütüphane olan Aspose.Tasks for Java'yı kullanarak kaynak atamaları oran ölçeğini yönetmeyi derinlemesine inceleyeceğiz. Bu adımları izleyerek Java uygulamalarınızdaki kaynak atamalarına ilişkin oran ölçeği ayarlarını etkili bir şekilde değiştirebileceksiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Ortamı: Sisteminizde Java Geliştirme Kitinin (JDK) kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java Library: Aspose.Tasks for Java kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Aspose.Tasks işlevleriyle çalışmak için öncelikle gerekli paketleri içe aktarmanız gerekir. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## 1. Adım: Projenizi ayarlayın
Java projenizi kurarak başlayın ve Aspose.Tasks kütüphanesini bağımlılıklarınıza ekleyin.
## Adım 2: Proje Dosyasını Yükleyin
Çalışmak istediğiniz Proje dosyasını Java uygulamanıza yükleyin.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 3. Adım: Görev Ekle
Projenize yeni bir görev ekleyin.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Adım 4: Kaynakları Tanımlayın
Maddi ve maddi olmayan kaynakları tanımlayın ve türlerini belirtin.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Adım 5: Kaynakları Göreve Atayın
Önceden tanımlanan kaynakları, oran ölçeği türleriyle birlikte göreve atayın.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Adım 6: Projeyi Kaydet
Projeyi değiştirilmiş kaynak atamalarıyla kaydedin.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Adım 7: Kaynak Atamalarını Alın
Oran ölçeği ayarlarını doğrulamak için kaydedilen projeyi yeniden yükleyin ve kaynak atamalarını alın.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Çözüm
Aspose.Tasks for Java'da kaynak atamaları oran ölçeğini yönetmek, etkili proje yönetimi için çok önemlidir. Bu adım adım kılavuzu izleyerek, Java uygulamalarınızdaki kaynak atamalarına ilişkin oran ölçeği ayarlarını sorunsuz bir şekilde değiştirebilirsiniz.
## SSS'ler
### S1: Aspose.Tasks for Java'yı herhangi bir Java IDE ile kullanabilir miyim?
C: Evet, Aspose.Tasks for Java; IntelliJ IDEA, Eclipse ve NetBeans dahil tüm önemli Java IDE'leriyle uyumludur.
### S2: Aspose.Tasks, MPP'nin yanı sıra diğer dosya formatlarını da destekliyor mu?
C: Evet, Aspose.Tasks MPP, XML ve HTML dahil olmak üzere çeşitli dosya formatlarını destekler.
### S3: Aspose.Tasks kurumsal düzeyde proje yönetimine uygun mu?
C: Kesinlikle Aspose.Tasks, her ölçekteki projeyi yönetmek için kapsamlı özellikler sunarak onu kurumsal düzeyde proje yönetimine uygun hale getiriyor.
### S4: Kaynak atamalarını oran ölçeğinin ötesinde özelleştirebilir miyim?
C: Evet, Aspose.Tasks maliyet, iş ve süre ayarlamaları da dahil olmak üzere kaynak atamalarını özelleştirmek için kapsamlı yetenekler sağlar.
### S5: Aspose.Tasks desteği için bir topluluk forumu var mı?
 C: Evet, Aspose.Tasks forumunda destek bulabilir ve diğer kullanıcılarla etkileşime geçebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).