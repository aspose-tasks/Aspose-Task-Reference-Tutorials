---
title: Aspose.Tasks'ta Görev Maliyetlerini Yönetin
linktitle: Aspose.Tasks'ta Görev Maliyetlerini Yönetin
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks'ı kullanarak Java uygulamalarında görev maliyetlerini nasıl yöneteceğinizi öğrenin. Etkin proje maliyet yönetimi için adım adım kılavuzumuzu izleyin.
weight: 21
url: /tr/java/task-properties/manage-task-cost/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Görev Maliyetlerini Yönetin

## giriiş
Java uygulamalarınızda görev maliyetlerini sorunsuz bir şekilde yönetmenize olanak tanıyan güçlü bir kütüphane olan Aspose.Tasks for Java dünyasına hoş geldiniz. Bu adım adım kılavuzda, görev maliyetlerini yönetmek ve verimli proje yönetimi sağlamak için Aspose.Tasks'ı nasıl etkili bir şekilde kullanabileceğimizi keşfedeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1. Java Ortamı: Sisteminizde bir Java geliştirme ortamının kurulu olduğundan emin olun.
2. Aspose.Tasks Kütüphanesi: Aspose.Tasks for Java kütüphanesini indirip yükleyin. Kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
## Paketleri İçe Aktar
Ortamınızı ayarlayıp Aspose.Tasks kütüphanesini yükledikten sonra gerekli paketleri Java projenize aktarmanız gerekir. Kodunuza aşağıdaki satırları ekleyin:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Aspose.Tasks sınıflarını içe aktar
```
Şimdi görev maliyetlerini etkili bir şekilde yönetmek için örneği birden fazla adıma ayıralım.
## 1. Adım: Projenizi Kurun
```java
// Belge dizininizin yolunu ayarlayın
String dataDir = "Your Document Directory";
// Yeni bir proje oluştur
Project project = new Project();
```
## 2. Adım: Yeni Bir Görev Ekleme
```java
// Kök göreve yeni bir görev ekleme
Task task = project.getRootTask().getChildren().add("Task");
```
## 3. Adım: Görev Maliyetini Ayarlayın
```java
// Görev maliyetini 800 olarak ayarlayın
task.set(Tsk.COST, BigDecimal.valueOf(800));
```
## Adım 4: Görev Bilgilerini Alın
```java
// Görev bilgilerini alma ve yazdırma
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Proje düzeyinde maliyet bilgilerini alın ve yazdırın
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```
Aspose.Tasks for Java uygulamanızdaki görev maliyetlerini etkili bir şekilde yönetmek için bu adımları tekrarlayın.
## Çözüm
Sonuç olarak, görev maliyet yönetimine hakim olmak, projenin başarılı bir şekilde yürütülmesi için çok önemlidir. Aspose.Tasks for Java, geliştiricilerin maliyetleri hassasiyetle karşılamalarına olanak tanıyan sağlam bir çözüm sunar.
## SSS
### S: Aspose.Tasks for Java belgelerini nerede bulabilirim?
 C: Dokümantasyona erişebilirsiniz[Burada](https://reference.aspose.com/tasks/java/).
### S: Aspose.Tasks for Java kütüphanesini nasıl indirebilirim?
 C: Kütüphaneyi indirin[Burada](https://releases.aspose.com/tasks/java/).
### S: Aspose.Tasks for Java'yı nereden satın alabilirim?
 C: Satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
### S: Aspose.Tasks for Java'nın ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java için nereden destek alabilirim?
 C: Destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
