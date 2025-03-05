---
title: Aspose.Tasks'ta Kritik MS Proje Yolunu Hesaplayın
linktitle: Aspose.Tasks Projelerinde Kritik Yolu Hesaplayın
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project'te kritik yolu nasıl hesaplayacağınızı öğrenin. Bu, verimli proje yönetimi için adım adım rehberlik sağlar.
type: docs
weight: 10
url: /tr/java/project-management/critical-path/
---
## giriiş
Bu eğitimde, MS Project'te Aspose.Tasks for Java'yı kullanarak kritik yolu hesaplama sürecinde size rehberlik edeceğiz. Kritik yol, projenin genel programının gecikmemesini sağlamak için zamanında tamamlanması gereken görev sırasının belirlenmesine yardımcı olduğundan proje yönetimi için çok önemlidir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Tasks for Java kütüphanesi indirildi ve projenize eklendi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java sınıfınıza aktarın:
```java
import com.aspose.tasks.*;
```
## 1. Adım: Veri Dizinini Ayarlayın
MS Project dosyanızın bulunduğu veri dizininizin yolunu tanımlayın.
```java
String dataDir = "Your Data Directory";
```
## Adım 2: MS Proje Dosyasını Yükleyin
Aspose.Tasks kütüphanesini kullanarak MS Project dosyasını yükleyin.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 3. Adım: Hesaplama Modunu Ayarlayın
Kritik yolun hesaplanmasını etkinleştirmek için hesaplama modunu otomatik olarak ayarlayın.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## 4. Adım: Görev Ekle
Projenize görevler ekleyin. Bu örnekte üç alt görev ekliyoruz.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## 5. Adım: Görev Bağlantıları Oluşturun
Görevler arasındaki bağımlılıkları tanımlamak için görev bağlantıları oluşturun.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## Adım 6: Kritik Yolu Görüntüleyin
Projenin kritik yolunu alın ve görüntüleyin.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## Adım 7: Sonucu Görüntüle
İşlemin başarıyla tamamlandığını belirten bir mesaj görüntüleyin.
```java
System.out.println("Process completed Successfully");
```

## Çözüm
Aspose.Tasks for Java kullanarak MS Project'te kritik yolun hesaplanması, etkili proje yönetimi için çok önemlidir. Bu öğreticide özetlenen adımları izleyerek projenizin zaman çizelgesi için kritik olan görev sırasını doğru bir şekilde tanımlayabilirsiniz.
## SSS'ler
### S: Aspose.Tasks for Java'yı MS Project dosyalarının herhangi bir sürümüyle kullanabilir miyim?
C: Evet, Aspose.Tasks for Java, MS Project 2003'ten MS Project 2019'a kadar .mpp dosyaları da dahil olmak üzere MS Project dosyalarının çeşitli sürümlerini destekler.
### S: Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java desteğini nerede bulabilirim?
 C: Şu adreste destek bulabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
 C: Evet, adresinden geçici bir lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks for Java'yı nasıl satın alabilirim?
 C: Aspose.Tasks for Java'yı web sitesinden satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).