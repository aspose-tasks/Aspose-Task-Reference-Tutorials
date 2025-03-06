---
title: Aspose.Tasks'ta MPP Dosyasını Güncelleyin
linktitle: Aspose.Tasks'ta MPP Dosyasını Güncelleyin
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MPP dosyalarını sorunsuz bir şekilde nasıl güncelleyeceğinizi öğrenin. Verimli proje dosyası manipülasyonu için adım adım kılavuzumuzu izleyin.
weight: 19
url: /tr/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta MPP Dosyasını Güncelleyin

## giriiş
Proje yönetimi alanında proje dosyalarının işlenmesi ve güncellenmesi çok önemli bir görevdir. Aspose.Tasks for Java, Java geliştiricilerinin Microsoft Project dosyalarını sorunsuz bir şekilde yönetmeleri için güçlü bir çözüm sunar. Bu eğitimde Aspose.Tasks for Java'yı kullanarak MPP dosyalarını güncellemeyi ele alacağız.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Ortamı: Sisteminizde Java'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java'yı şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/tasks/java/).
3. Temel Java Bilgisi: Örnekleri takip etmek için Java programlama diline aşinalık gereklidir.

## Paketleri İçe Aktar
Aspose.Tasks fonksiyonlarını etkili bir şekilde kullanabilmek için öncelikle gerekli paketleri Java projenize aktarmanız gerekir.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Bu kod satırı, Aspose.Tasks kütüphanesinden tüm önemli sınıfları ve yöntemleri içe aktararak Microsoft Project dosyalarıyla zahmetsizce çalışmanıza olanak tanır.

Şimdi Aspose.Tasks for Java kullanarak bir MPP dosyasını güncelleme sürecini yönetilebilir adımlara ayıralım.
## Adım 2: Veri Dizinini Tanımlayın
```java
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` MPP dosyanızın bulunduğu gerçek yolla.
## Adım 3: Mevcut Projeyi Okuyun
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Bu kod, adlı mevcut bir MPP proje dosyasını okur.`SampleMSP2010.mpp` belirtilen veri dizininden.
## 4. Adım: Yeni Bir Görev Oluşturun
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Burada projenin kök görevine "Task1" adında yeni bir görev ekliyoruz.
## Adım 5: Başlangıç ve Bitiş Tarihlerini Ayarlayın
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Bu kod satırları, yeni oluşturulan görevin başlangıç ve bitiş tarihini belirler.
## Adım 6: Projeyi Kaydet
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Son olarak, bu adım, güncellenen projeyi yeni eklenen görevle birlikte adlı yeni bir MPP dosyasına kaydeder.`AfterLinking.mpp`.

## Çözüm
Bu eğitimde MPP dosyalarını Aspose.Tasks for Java kullanarak nasıl güncelleyeceğimizi araştırdık. Adım adım kılavuzu izleyerek, Microsoft Project dosyalarını Java uygulamalarınızda verimli bir şekilde değiştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks for Java karmaşık proje yapılarını yönetebilir mi?
C: Evet, Aspose.Tasks for Java, karmaşık proje yapılarını verimli bir şekilde yönetmek için güçlü özellikler sağlar.
### S: Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[İnternet sitesi](https://releases.aspose.com/).
### S: Aspose.Tasks for Java, Microsoft Project dosyalarının farklı sürümlerini destekliyor mu?
C: Aspose.Tasks for Java kesinlikle MPP, MPT ve XML formatları da dahil olmak üzere Microsoft Project dosyalarının çeşitli sürümlerini destekler.
### S: Aspose.Tasks for Java için geçici lisans alabilir miyim?
 C: Evet, test amaçlı geçici lisanslar mevcuttur. Bunları şuradan temin edebilirsiniz:[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks for Java ile ilgili nereden yardım veya destek alabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) herhangi bir yardım veya sorularınız için.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
