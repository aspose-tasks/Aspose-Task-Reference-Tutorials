---
title: Aspose.Tasks for Java ile MS Proje Manipülasyonunda Uzmanlaşmak
linktitle: Aspose.Tasks'ta Kaynak Atamaları'na Genişletilmiş Nitelikler Ekleme
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project bilgilerini verimli bir şekilde yazmayı öğrenin. Java geliştiricileri için adım adım kılavuz.
weight: 10
url: /tr/java/resource-assignments/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile MS Proje Manipülasyonunda Uzmanlaşmak

## giriiş
Bu eğitimde, Microsoft Project dosyalarını programlı olarak yönetmek için güçlü bir kütüphane olan Aspose.Tasks for Java'nın kullanımını inceleyeceğiz. Temel bir göreve odaklanacağız: Aspose.Tasks'ı kullanarak MS Project bilgilerini yazmak. İster deneyimli bir geliştirici olun ister Java programlama yolculuğunuza yeni başlıyor olun, bu kılavuz süreç boyunca size adım adım yol gösterecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java Library: Aspose.Tasks for Java kütüphanesini indirip yükleyin. adresinden alabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Entegre Geliştirme Ortamı (IDE): Tercihinize göre bir IDE seçin. IntelliJ IDEA veya Eclipse'i öneriyoruz.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize aktarın:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```
#Verilen örneği birden fazla adıma ayıralım:
## 1. Adım: Veri Dizinini Ayarlayın
Proje verilerinizin saklanacağı dizini tanımlayın.
```java
String dataDir = "Your Data Directory";
```
## 2. Adım: Proje Örneği Oluşturun
Yeni bir proje örneğini başlatın.
```java
Project project = new Project();
```
## Adım 3: Proje Bilgisi Özelliklerini Ayarlayın
Projenin başlangıç tarihi, başlangıçtan itibaren zamanlaması ve durum tarihi gibi özelliklerini ayarlayın.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## Adım 4: Projeyi XML olarak kaydedin
Projeyi güncellenen bilgilerle birlikte XML dosyası olarak kaydedin.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Çözüm
Tebrikler! Aspose.Tasks for Java'yı kullanarak MS Project bilgilerini nasıl yazacağınızı başarıyla öğrendiniz. Bu yeni keşfedilen bilgiyle, Microsoft Project dosyalarıyla ilgili çeşitli görevleri otomatikleştirerek bir Java geliştiricisi olarak üretkenliğinizi artırabilirsiniz.
## SSS'ler
### S: Aspose.Tasks for Java'yı MS Project dosyalarını okumak için kullanabilir miyim?
C: Evet, Aspose.Tasks for Java, MS Project dosyalarının hem okunması hem de yazılması için güçlü işlevler sağlar.
### S: Aspose.Tasks for Java, MS Project'in farklı sürümleriyle uyumlu mudur?
C: Kesinlikle, Aspose.Tasks for Java, MS Project'in çeşitli sürümlerini destekleyerek farklı dosya formatları arasında uyumluluk sağlar.
### S: Aspose.Tasks for Java'nın deneme sürümünde herhangi bir sınırlama var mı?
C: Deneme sürümü kitaplığın yeteneklerini keşfetmenize olanak tanırken, çıktı dosyalarındaki filigranlar gibi belirli sınırlamalara sahiptir.
### S: Aspose.Tasks for Java için nasıl destek alabilirim?
 C: Aspose.Tasks topluluk forumundan yardım isteyebilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
 C: Evet, kısa süreli kullanım için geçici lisanslar mevcuttur. Şuradan bir tane alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
