---
title: Aspose.Tasks ile MS Project Versiyonunu Belirleyin
linktitle: Aspose.Tasks ile Proje Sürümünü Belirleyin
second_title: Aspose.Tasks Java API'si
description: Aspose.Tasks for Java'yı kullanarak MS Project dosyalarının sürümünü programlı olarak nasıl belirleyeceğinizi öğrenin. Kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 12
url: /tr/java/project-management/determine-version/
---
## giriiş
Bu eğitim, bir MS Project dosyasının sürümünü adım adım belirlemek için Aspose.Tasks for Java'yı kullanma konusunda size rehberlik edecektir. Aspose.Tasks, geliştiricilerin Microsoft Project'in kurulmasına gerek kalmadan Microsoft Project dosyalarını değiştirmesine olanak tanıyan güçlü bir Java API'sidir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Tasks for Java JAR dosyası: Aspose.Tasks for Java kütüphanesini şu adresten indirin:[İnternet sitesi](https://releases.aspose.com/tasks/java/) ve bunu Java projenize ekleyin.
3. MS Project Dosyası: Test için bir MS Project dosyası (XML formatında) hazırlayın.

## Paketleri İçe Aktar
Koda dalmadan önce gerekli paketleri içe aktaralım:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Adım 1: Projeyi Kurun
```java
// Belgeler dizininin yolu.
String dataDir = "Your Data Directory";
```
 Yer değiştirmek`"Your Data Directory"` MS Project dosyanızı içeren dizinin yolu ile birlikte.
## Adım 2: Projeyi Yükleyin
```java
Project project = new Project(dataDir + "input.xml");
```
 Yer değiştirmek`"input.xml"` MS Project dosyanızın adıyla.
## 3. Adım: Proje Sürümünü Belirleyin
```java
//Proje sürümü özelliğini görüntüle
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Bu kod parçacığı, MS Project dosyasının sürümünü ve son kaydedilme tarihini alır ve yazdırır.
## Adım 4: Sonucu Görüntüle
```java
//Dönüşümün sonucunu görüntüleyin.
System.out.println("Process completed Successfully");
```
Bu satır işlemin tamamlandığını gösterir.

## Çözüm
Bu eğitimde Aspose.Tasks for Java'yı kullanarak bir MS Project dosyasının sürümünü nasıl belirleyeceğinizi öğrendiniz. Adım adım kılavuzu takip ederek, Java uygulamalarınızda MS Project dosyalarıyla sorunsuz bir şekilde verimli bir şekilde çalışabilirsiniz.

## SSS'ler
### S: Aspose.Tasks'ı diğer programlama dilleriyle kullanabilir miyim?
C: Evet, Aspose.Tasks .NET, Java ve C dahil birden fazla programlama dilini destekler++.
### S: Aspose.Tasks büyük ölçekli projeler için uygun mudur?
C: Kesinlikle, Aspose.Tasks her boyuttaki projenin kolaylıkla üstesinden gelebilecek şekilde tasarlanmıştır.
### S: Aspose.Tasks'ı kullanarak proje verilerini özelleştirebilir miyim?
C: Evet, Aspose.Tasks'ı kullanarak proje verilerini değiştirebilir, görevleri, kaynakları değiştirebilir ve çok daha fazlasını yapabilirsiniz.
### S: Aspose.Tasks Microsoft Project kurulumu gerektiriyor mu?
C: Hayır, Aspose.Tasks bağımsız olarak çalışır ve Microsoft Project'in kurulmasını gerektirmez.
### S: Aspose.Tasks için teknik destek mevcut mu?
 C: Evet, Aspose.Tasks forumundan teknik destek alabilirsiniz:[Burada](https://forum.aspose.com/c/tasks/15).