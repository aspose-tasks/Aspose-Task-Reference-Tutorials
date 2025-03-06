---
title: Aspose.Tasks'taki Görevlerin Tamamlanma Yüzdesi Hesaplamaları
linktitle: Aspose.Tasks'taki Görevlerin Tamamlanma Yüzdesi Hesaplamaları
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı keşfedin ve proje ilerleme takibini kolaylaştırın. Verimli proje yönetimi için görev yüzdelerini zahmetsizce hesaplayın.
weight: 25
url: /tr/java/task-properties/percentage-complete-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'taki Görevlerin Tamamlanma Yüzdesi Hesaplamaları

## giriiş
Aspose.Tasks for Java'yı kullanarak görev yüzdesi hesaplamalarında uzmanlaşmaya yönelik ayrıntılı kılavuzumuza hoş geldiniz. Aspose.Tasks, Microsoft Project dosyalarıyla çalışmak üzere tasarlanmış, proje yönetimi için güçlü özellikler sunan güçlü bir Java kütüphanesidir. Bu eğitimde, proje ilerlemesini etkili bir şekilde izlemeniz ve analiz etmeniz için size bilgi sağlayacak Tamamlanma Yüzdesi hesaplamalarına odaklanacağız.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- Java Geliştirme Ortamı: Sisteminizde Java'nın kurulu olduğundan emin olun.
-  Aspose.Tasks Kitaplığı: Java için Aspose.Tasks kitaplığını şu adresten indirin:[bu bağlantı](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Aspose.Tasks for Java projeniz için gerekli paketleri içe aktararak başlayalım. Projenize aşağıdaki kod parçacığını ekleyin:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```
Şimdi her adımı ayrıntılı açıklamalarla parçalara ayıralım.
## 1. Adım: Paketleri İçe Aktarma
İlk adımda Aspose.Tasks projemizi kurmak için gerekli paketleri import ediyoruz.
## Adım 2: Belge Dizinini Ayarlama
 kullanarak belge dizininizin yolunu tanımlayın.`dataDir`değişken. "Software Development.mpp" gibi Microsoft Project dosyanızın bu dizinde olduğundan emin olun.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
```
## Adım 3: Projeyi Yükleme
 Yeni bir başlangıç başlat`Project` nesnesini oluşturun ve Microsoft Project dosyanızı proje örneğine yükleyin.
```java
Project project = new Project(dataDir + "Software Development.mpp");
```
## Adım 4: Görev Koleksiyonunu Alma
 Projenin kök görevini alın ve alt öğelerini kullanarak koleksiyon olarak alın`getRootTask().getChildren()`.
```java
TaskCollection alTasks = project.getRootTask().getChildren();
```
## Adım 5: Yazdırma Yüzdesi Tamamlandı
Koleksiyondaki her görevi gözden geçirin ve Tamamlanma Yüzdesi, Tamamlanan Çalışma Yüzdesi ve Tamamlanan Fiziksel Yüzdeyi yazdırın.
```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```
Her birinin ilerleyişi hakkında bilgi edinmek için projenizdeki her görev için bu adımları tekrarlayın.
## Çözüm
Tebrikler! Aspose.Tasks for Java'yı kullanarak görev yüzdesi hesaplamalarında başarıyla uzmanlaştınız. Bu güçlü kitaplık, geliştiricilerin proje ilerlemesini verimli bir şekilde yönetmesine ve analiz etmesine olanak tanır.
## SSS
### S: Aspose.Tasks belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/tasks/java/).
### S: Java için Aspose.Tasks kütüphanesini nasıl indirebilirim?
 İndirebilirsin[Burada](https://releases.aspose.com/tasks/java/).
### S: Ücretsiz deneme mevcut mu?
Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks için nereden destek alabilirim?
 Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tasks/15).
### S: Geçici lisansı nasıl alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
