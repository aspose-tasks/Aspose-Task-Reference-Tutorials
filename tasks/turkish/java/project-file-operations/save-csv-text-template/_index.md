---
title: Aspose.Tasks'ta CSV, Metin ve Şablon Olarak Kaydet
linktitle: Aspose.Tasks'ta CSV, Metin ve Şablon Olarak Kaydet
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak Microsoft Project dosyalarını CSV, Metin ve Şablon formatlarında nasıl kaydedeceğinizi öğrenin.
weight: 16
url: /tr/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta CSV, Metin ve Şablon Olarak Kaydet

## giriiş
Bu eğitimde Aspose.Tasks for Java'yı kullanarak proje dosyalarını CSV, Metin ve Şablon gibi çeşitli formatlarda nasıl kaydedeceğimizi keşfedeceğiz. Aspose.Tasks, geliştiricilerin Microsoft Project'in kurulmasına gerek kalmadan Microsoft Project dosyalarıyla çalışmasına olanak tanıyan güçlü bir Java kütüphanesidir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Tasks for Java kütüphanesi Java projenize indirildi ve yapılandırıldı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/java/).
3. Java programlama dili hakkında temel bilgiler.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java dosyanıza aktarmanız gerekir:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Projeyi CSV Olarak Kaydet
Bir projeyi CSV olarak kaydetme adımlarını inceleyelim:
### Adım 1: Projeyi Yükleyin
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2. Adım: CSV olarak kaydedin
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Projeyi Metin Olarak Kaydet
Bir projeyi Metin olarak şu şekilde kaydedebilirsiniz:
### Adım 1: Projeyi Yükleyin
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2. Adım: Metin Olarak Kaydet
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Projeyi Şablon Olarak Kaydet
Bir projeyi şablon olarak kaydetmek aşağıdaki adımları içerir:
### Adım 1: Projeyi Yükleyin
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 2. Adım: Şablon Seçeneklerini Ayarlayın
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### 3. Adım: Şablon Olarak Kaydet
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak Microsoft Project dosyalarını CSV, Metin ve Şablon olarak nasıl kaydedeceğimizi öğrendik. Bu basit adımlarla proje dosyalarınızı çeşitli formatlarda verimli bir şekilde yönetebilir ve bir Java geliştiricisi olarak üretkenliğinizi artırabilirsiniz.
## SSS'ler
### S: Aspose.Tasks for Java karmaşık proje dosyalarını yönetebilir mi?
C: Kesinlikle! Aspose.Tasks for Java, Microsoft Project dosya formatları için kapsamlı destek sağlayarak, değişen karmaşıklıktaki projeleri kolaylıkla yönetebilir.
### S: Aspose.Tasks for Java'nın deneme sürümü mevcut mu?
 C: Evet, Aspose.Tasks for Java'nın ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for Java desteğini nerede bulabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Aspose.Tasks for Java ile ilgili her türlü yardım veya sorularınız için.
### S: Aspose.Tasks for Java için geçici bir lisans satın alabilir miyim?
 C: Evet, adresinden geçici bir lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/)kütüphanenin tüm potansiyelini değerlendirmenize olanak tanır.
### S: Aspose.Tasks for Java farklı işletim sistemleriyle uyumlu mudur?
C: Evet, Aspose.Tasks for Java; Windows, macOS ve Linux dahil çeşitli işletim sistemleriyle uyumludur.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
