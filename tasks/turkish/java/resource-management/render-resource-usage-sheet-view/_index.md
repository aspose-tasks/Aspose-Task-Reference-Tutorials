---
title: Aspose.Tasks'ta Render Kaynak Kullanımı ve Sayfa Görünümü
linktitle: Aspose.Tasks'ta Render Kaynak Kullanımı ve Sayfa Görünümü
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'da MS Project Kaynak Kullanımı ve Sayfa görünümlerini nasıl oluşturacağınızı öğrenin. Ayrıntılı PDF raporlarını zahmetsizce oluşturmak için adım adım kılavuzumuzu izleyin.
weight: 16
url: /tr/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Render Kaynak Kullanımı ve Sayfa Görünümü

## giriiş
Bu eğitimde, MS Project Kaynak Kullanımı ve Sayfa görünümlerini oluşturmak için Aspose.Tasks for Java'nın nasıl kullanılacağını öğreneceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project'in kurulmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmasına olanak tanıyan güçlü bir Java kütüphanesidir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların yüklendiğinden ve ayarlandığından emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde Java Geliştirme Kitinin kurulu olduğundan emin olun. JDK'nın en son sürümünü Oracle web sitesinden indirip yükleyebilirsiniz.
2.  Aspose.Tasks for Java: Aspose.Tasks for Java kütüphanesini aşağıdaki adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/tasks/java/).

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize aktarmanız gerekir:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## 1. Adım: Kaynak Projeyi Okuyun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
// Kaynak Projeyi okuyun
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
Bu adımda kaynak Proje dosyasının yolunu belirtiyoruz (`ResourceUsageView.mpp` ) ve kullanın`Project` Bunu okumak için sınıf.
## Adım 2: Gerekli TimeScale Ayarlarıyla SaveOptions'ı Tanımlayın
```java
// SaveOptions'ı gerekli TimeScale ayarlarıyla Gün olarak tanımlayın
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Burada şunu tanımlıyoruz:`SaveOptions` gerekli olanlarla`TimeScale` ayarlar. Bu örnekte,`TimeScale` Günlere.
## 3. Adım: Sunum Formatını Kaynak Kullanımı olarak ayarlayın
```java
// Sunum biçimini Kaynak Kullanımı olarak ayarlayın
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Sunum formatını şu şekilde ayarladık:`ResourceUsage`Kaynak Kullanımı görünümünü oluşturmak istediğimizi belirtir.
## Adım 4: Projeyi Kaydet
```java
// Projeyi Kaydet
project.save(dataDir + days, options);
```
Son olarak projeyi belirtilen seçeneklerle kaydediyoruz. Bu örnekte çıktı dosyası şu şekilde kaydedilecektir:`result_days.pdf`.
## Adım 5: Diğer Zaman Ölçeği Ayarları için Görünümleri Oluşturma
Görünümleri farklı TimeScale ayarlarıyla (ThirdsOfMonths ve Months) oluşturmak için 2'den 4'e kadar olan adımları tekrarlayın.
```java
// Zaman Ölçeği ayarlarını ThirdsOfMonths olarak ayarlayın
options.setTimescale(Timescale.ThirdsOfMonths);
// Projeyi Kaydet
project.save(thirds, options);
// Zaman Ölçeği ayarlarını Ay olarak ayarlayın
options.setTimescale(Timescale.Months);
// Projeyi kaydet
project.save(dataDir + months, options);
```
 Değiştirdiğinizden emin olun`Timescale` ayarları her görünüm için uygun şekilde ayarlayın.

## Çözüm
Bu eğitimde, MS Project Kaynak Kullanımı ve Sayfa görünümlerini oluşturmak için Aspose.Tasks for Java'nın nasıl kullanılacağını araştırdık. Yukarıda özetlenen adımları izleyerek bu görünümleri PDF formatında verimli bir şekilde oluşturabilir, proje verilerinizin daha iyi görselleştirilmesini ve analizini kolaylaştırabilirsiniz.
## SSS'ler
### Aspose.Tasks, Kaynak Kullanımı ve Sayfa dışında başka görünümler de oluşturabilir mi?
Aspose.Tasks, diğerlerinin yanı sıra Gantt Grafiği, Görev Kullanımı ve Takvim görünümleri gibi çeşitli görünümlerin oluşturulmasını destekler.
### Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?
Evet, Aspose.Tasks, MPP, MPT ve XML formatları da dahil olmak üzere çok çeşitli Microsoft Project dosya formatlarını destekler.
### Aspose.Tasks'ı kullanarak işlenmiş görünümlerin görünümünü özelleştirebilir miyim?
Kesinlikle! Aspose.Tasks, işlenmiş görünümlerin görünümünü ve düzenini özel gereksinimlerinize uyacak şekilde özelleştirmek için kapsamlı seçenekler sunar.
### Aspose.Tasks'ın sistemde yüklü olması için Microsoft Project gerekiyor mu?
Hayır, Aspose.Tasks bağımsız bir kütüphanedir ve çalışması için Microsoft Project'in kurulmasını gerektirmez.
### Aspose.Tasks kullanıcıları için teknik destek mevcut mu?
 Evet, Aspose.Tasks kullanıcıları teknik destekten şu adresten yararlanabilirler:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
