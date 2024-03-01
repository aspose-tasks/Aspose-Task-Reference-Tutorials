---
title: Aspose.Tasks'ta MS Project Efsanelerini Yapılandırma
linktitle: Aspose.Tasks'ta Sayfa Göstergesini Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Etkin proje yönetimi için Aspose.Tasks'ı kullanarak .NET'te MS Project sayfa göstergelerini nasıl yapılandıracağınızı öğrenin. Adım adım kılavuz sağlanmıştır.
type: docs
weight: 18
url: /tr/net/outline-code-page-settings/page-legend/
---
## giriiş
.NET geliştirme alanında, özellikle proje yönetimiyle uğraşırken görevleri verimli bir şekilde yönetmek çok önemlidir. Aspose.Tasks for .NET, görev yönetimi süreçlerini kolaylaştırmak için çok sayıda işlevsellik sunan güçlü bir araç olarak ortaya çıkıyor. Bu özelliklerden biri, kullanıcılara proje verileri sunumuna ilişkin değerli bilgiler sağlayan MS Project sayfa göstergelerini yapılandırma yeteneğidir.
## Önkoşullar
Aspose.Tasks for .NET kullanarak MS Project sayfa açıklamalarını yapılandırmaya başlamadan önce aşağıdaki önkoşulların karşılandığından emin olun:
1. Kurulum: Geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olmasını sağlayın. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
2. Temel .NET Bilgisi: Proje oluşturma ve ad alanlarıyla çalışma da dahil olmak üzere .NET geliştirmenin temellerine aşina olun.
3. Geliştirme Ortamı: Sorunsuz kodlama deneyimi için Visual Studio gibi entegre bir geliştirme ortamı (IDE) kullanın.
4. Proje Dosyası: Denemeye hazır bir Microsoft Project dosyası (MPP) bulundurun.

## Ad Alanlarını İçe Aktar
Aspose.Tasks for .NET tarafından sağlanan işlevlere erişmek için .NET projenize gerekli ad alanlarını içe aktarın.
1. Projenizi Açın: .NET projenizi tercih ettiğiniz IDE'de başlatın.
2. Ad Alanlarını İçe Aktar: Kod dosyanızın başında gerekli ad alanlarını içe aktarın:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Aspose.Tasks for .NET kullanarak MS Project sayfa göstergelerini yapılandırmayı kapsamlı bir şekilde anlamak için sağlanan örneği adım adım kılavuz formatına ayıralım.

## 1. Adım: Belge Dizinini Belirleyin
Microsoft Project dosyanızın bulunduğu belge dizininizin yolunu ayarlayın.

```csharp
String DataDir = "Your Document Directory";
```
## Adım 2: Projeyi Yükle
 Yeni bir örneğini başlat`Project` Microsoft Project dosyanızı yükleyerek sınıfa gidin.

```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
## 3. Adım: Sayfa Açıklaması Bilgilerini Okuyun
Sayfa açıklaması bilgilerine projenin varsayılan görünümünden erişin.

```csharp
var legend = project.DefaultView.PageInfo.Legend;
```
## Adım 4: Açıklama Bilgilerini Görüntüleyin
Sol metin, sol resim, ortalanmış metin, ortalanmış resim, sağ metin, sağ resim, açıklama durumu ve genişlik gibi açıklama ayrıntılarının çıktısını alın.

```csharp
Console.WriteLine("Legend left text: {0} ", legend.LeftText);
Console.WriteLine("Legend left image: {0} ", legend.LeftImage);
Console.WriteLine("Legend center text: {0} ", legend.CenteredText);
Console.WriteLine("Legend center image: {0} ", legend.CenteredImage);
Console.WriteLine("Legend right text: {0} ", legend.RightText);
Console.WriteLine("Legend right image: {0} ", legend.RightImage);
Console.WriteLine("Legend On: {0} ", legend.LegendOn);
Console.WriteLine("Legend Width: {0} ", legend.Width);
```
## Adım 5: Açıklamayı Değiştirin
İsteğe bağlı olarak, açıklamayı gerektiği gibi değiştirin. Bu örnekte soldaki metni değiştiriyoruz.

```csharp
legend.LeftText = "New Left Text";
```
## Adım 6: Değişiklikleri Kaydet
Proje dosyasına yapılan değişiklikleri kaydedin.

```csharp
project.Save(DataDir + "WorkWithPageLegend_out.mpp", SaveFileFormat.Mpp);
```

## Çözüm
Sonuç olarak, Aspose.Tasks for .NET kullanarak MS Project sayfa açıklamalarının konfigürasyonunda uzmanlaşmak, .NET ekosistemindeki proje yönetimi yeteneklerini önemli ölçüde geliştirebilir. Geliştiriciler, belirtilen adımları ve ön koşulları takip ederek bu işlevselliği projelerine sorunsuz bir şekilde entegre edebilir ve proje verilerinin daha iyi görselleştirilmesini ve yorumlanmasını sağlayabilir.
## SSS'ler
### S: Aspose.Tasks for .NET'i diğer .NET çerçeveleriyle birlikte kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET, çeşitli .NET çerçeveleriyle uyumludur ve farklı proje gereksinimlerine göre esneklik ve uyarlanabilirlik sağlar.
### S: Aspose.Tasks for .NET'in deneme sürümü mevcut mu?
 C: Evet, şu adresten ücretsiz deneme sürümüne erişebilirsiniz:[Burada](https://releases.aspose.com/)Bir satın alma işlemi yapmadan önce özelliklerini keşfetmenize olanak tanır.
### S: Aspose.Tasks for .NET için geçici lisansların kullanımında herhangi bir sınırlama var mı?
C: Geçici lisanslar Aspose.Tasks for .NET işlevlerine tam erişim sağlar ancak zamanla sınırlıdır. Kısa vadeli projeler veya değerlendirme amaçları için uygundurlar.
### S: Sayfa göstergelerini sağlanan örneğin ötesinde özelleştirebilir miyim?
C: Kesinlikle, Aspose.Tasks for .NET, sayfa göstergelerini özel proje gereksinimlerinize göre uyarlamanıza olanak tanıyan kapsamlı kişiselleştirme seçenekleri sunar.
### S: Aspose.Tasks for .NET için desteği veya topluluk forumlarını nerede bulabilirim?
 C: Destek arayabilir ve toplulukla etkileşime geçebilirsiniz.[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15)Sorularınıza yanıt bulabileceğiniz ve diğer geliştiricilerle etkileşimde bulunabileceğiniz yer.