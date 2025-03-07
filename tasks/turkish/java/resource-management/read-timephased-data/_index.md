---
title: Aspose.Tasks'taki Kaynaklar için Zaman Aşamalı Verileri Okuyun
linktitle: Aspose.Tasks'taki Kaynaklar için Zaman Aşamalı Verileri Okuyun
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project kaynaklarından zaman aşamalı verileri nasıl çıkaracağınızı öğrenin. Adım adım öğretici.
weight: 15
url: /tr/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'taki Kaynaklar için Zaman Aşamalı Verileri Okuyun

## giriiş
Bu eğitimde, Aspose.Tasks for Java'yı kullanarak MS Project kaynakları için zaman aşamalı verileri okuma sürecinde size rehberlik edeceğiz. Bu kitaplık, Microsoft Project dosyalarını programlı olarak yönetmek için güçlü işlevler sağlar.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ve kurulum talimatlarını takip edin.
2.  Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini şu adresten indirin:[indirme sayfası](https://releases.aspose.com/tasks/java/) ve belgelerde verilen kurulum talimatlarını izleyin.

## Paketleri İçe Aktar
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## 1. Adım: Veri Dizinini Ayarlayın
Öncelikle MS Project dosyanızın bulunduğu dizini tanımlayın.
```java
String dataDir = "Your Data Directory";
```
## Adım 2: MS Project Şablon Dosyasını Okuyun
MS Project şablon dosyanızın adını belirtin.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Adım 3: Giriş Dosyasını Proje Olarak Okuyun
Aspose.Tasks'ı kullanarak giriş dosyasını okuyun ve onu bir Project nesnesi olarak yükleyin.
```java
Project project = new Project(dataDir + fileName);
```
## 4. Adım: Kaynağı kimliğe göre alın
İstenilen kaynağı projeden benzersiz tanımlayıcısına (ID) göre alın.
```java
Resource resource = project.getResources().getByUid(1);
```
## Adım 5: Kaynak Çalışması için Zaman Aşamalı Verileri Yazdırma
Kaynak çalışması için zaman aşamalı verileri yazdırın.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Adım 6: Kaynak Maliyeti için Zaman Aşamalı Verileri Yazdırma
Kaynak maliyeti için zaman aşamalı verileri yazdırın.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak MS Project kaynakları için zaman aşamalı verileri nasıl okuyacağımızı öğrendik. Bu adımları izleyerek proje dosyalarınızdan değerli bilgileri programlı bir şekilde verimli bir şekilde çıkarabilirsiniz.
## SSS'ler
### Aspose.Tasks, Microsoft Project dışında diğer proje dosyalarını da işleyebilir mi?
Evet, Aspose.Tasks MPP, XML ve CSV dahil olmak üzere çeşitli dosya formatlarını destekler.
### Aspose.Tasks farklı Java geliştirme ortamlarıyla uyumlu mu?
Evet, Aspose.Tasks tüm önemli Java IDE'leri ve çerçeveleriyle uyumludur.
### Aspose.Tasks'ı kullanarak proje verilerini değiştirebilir miyim?
Kesinlikle Aspose.Tasks, proje verilerini oluşturmak, değiştirmek ve analiz etmek için kapsamlı API'ler sağlar.
### Aspose.Tasks kurumsal düzeydeki projeler için uygun mu?
Evet, Aspose.Tasks, güvenilirliği ve ölçeklenebilirliği nedeniyle kurumsal ortamlarda yaygın olarak kullanılmaktadır.
### Aspose.Tasks'ı kullanırken sorunlarla karşılaşırsam nereden destek bulabilirim?
 Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluktan ve destek ekibinden yardım için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
