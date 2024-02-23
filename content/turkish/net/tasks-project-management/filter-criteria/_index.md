---
title: Aspose.Tasks ile MS Project Filtre Kriterlerinde Uzmanlaşma
linktitle: Aspose.Tasks'ta Filtre Kriterleri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project'te filtre kriterlerini nasıl uygulayacağınızı öğrenin. Hedeflenen veri analiziyle proje yönetimi verimliliğini artırın.
type: docs
weight: 18
url: /tr/net/tasks-project-management/filter-criteria/
---
## giriiş
Proje yönetimi alanında Microsoft Project, proje planlayıcılarına ve yöneticilerine yardımcı olacak çok sayıda özellik sunan güçlü bir araç olarak duruyor. Pek çok işlevselliği arasında proje verilerini filtreleme yeteneği de yer alıyor ve bu sayede kullanıcılar proje görevlerinin belirli yönlerine odaklanabiliyor. Ancak bu filtreleme yeteneklerine hakim olmak, doğru rehberlik olmadan göz korkutucu bir görev olabilir. Bu eğitim, Aspose.Tasks for .NET kullanarak MS Project'te filtrea kriterlerini uygulamaya yönelik adım adım bir kılavuz sağlayarak sürecin gizemini aydınlatmayı amaçlamaktadır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Temel C# Anlayışı: Bu eğitimde ele alınan kavramları kavramak için C# programlama diline aşinalık gereklidir.
2.  Aspose.Tasks for .NET Kurulumu: Geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/tasks/net/).
3. Microsoft Project Dosyası: Filtre kriterlerini uygulamak için kullanacağınız bir Microsoft Project dosyasını (örn. Project2003.mpp) hazır bulundurun.

## Ad Alanlarını İçe Aktar
Öncelikle Aspose.Tasks for .NET ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekir. Bu adımları takip et:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Adım 1: Proje Dosyasını Yükleyin
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Açıklama: Bu kod satırı, yeni bir örneğini başlatır.`Project` sınıfına girer ve yolu tarafından belirtilen Microsoft Project dosyasını yükler.
## 2. Adım: Görev Filtresini Alın
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Açıklama: Burada projeden bir görev filtresi alıyoruz. Endeksi ayarlayın (`[1]`) istediğiniz filtreyi seçmek için ihtiyacınıza göre.
## 3. Adım: Ölçüt Satırlarını Görüntüleme
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Açıklama: Bu bölüm, filtrenin her kriter satırında yinelenir ve alanını, çalışmasını, testini ve (varsa) değerlerini görüntüler.
## Adım 4: Filtre Kriterlerini Yazdır
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Açıklama: Filtre kriterlerinin çalışmasını yazdırır.
## Adım 5: Ölçüt Ayrıntılarını Görüntüleme
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Açıklama: Bu bölüm, her ölçüt satırı hakkında ayrıntılı bilgi alır ve görüntüler, böylece filtrenin yapılandırmasına ilişkin öngörüler sağlar.

## Çözüm
Aspose.Tasks for .NET'i kullanarak MS Project'te filtre kriterlerinde uzmanlaşmak, proje yönetimi verimliliğini önemli ölçüde artırabilecek değerli bir beceridir. Bu öğreticiyi izleyerek, filtre kriterlerini programlı bir şekilde nasıl değiştireceğinizi öğrendiniz ve proje görünümlerini özel ihtiyaçlarınıza göre uyarlamanıza olanak tanıdınız.
## SSS'ler
### S: MS Project'te aynı anda birden fazla filtre uygulayabilir miyim?
C: Evet, proje verilerinizi daha da hassaslaştırmak için birden fazla filtreyi birleştirebilirsiniz.
### S: Aspose.Tasks, Microsoft Project dosyalarının eski sürümlerini destekliyor mu?
C: Evet, Aspose.Tasks geriye dönük uyumluluk sağlayarak Microsoft Project dosyalarının çeşitli sürümleriyle çalışmanıza olanak tanır.
### S: Aspose.Tasks diğer .NET çerçeveleriyle uyumlu mu?
C: Aspose.Tasks, .NET Framework, .NET Core ve .NET Standard'ı destekleyerek farklı geliştirme ortamlarında esneklik sağlar.
### S: Filtre kriterlerini dinamik koşullara göre özelleştirebilir miyim?
C: Kesinlikle, filtre kriterlerini dinamik parametrelere dayalı olarak programlı bir şekilde ayarlayarak uyarlanabilir proje veri analizine olanak sağlayabilirsiniz.
### S: Aspose.Tasks'ta sorunlarla karşılaşırsam nereden yardım alabilirim?
 C: Ziyaret edebilirsiniz[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) topluluktan destek istemek veya kişiselleştirilmiş yardım için doğrudan Aspose.Tasks desteğine ulaşmak için.