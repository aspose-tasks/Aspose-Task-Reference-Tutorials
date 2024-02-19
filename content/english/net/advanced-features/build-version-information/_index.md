---
title: Retrieving Build Version Information in Aspose.Tasks
linktitle: Retrieving Build Version Information in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 23
url: /net/advanced-features/build-version-information/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using System;
    using NUnit.Framework;

    [TestFixture]
    public class ExBuildVersionInfo : ApiExampleBase
    {
        [Test]
        public void WorkWithBuildVersionInfo()
        {
            // ExStart
            // ExFor: BuildVersionInfo
            // ExFor: BuildVersionInfo.AssemblyInformationalVersion
            // ExFor: BuildVersionInfo.AssemblyVersion
            // ExFor: BuildVersionInfo.FileVersion
            // ExFor: BuildVersionInfo.Product
            // ExSummary: Shows how to read build version info of Aspose.Tasks.
            // read common info about the current Aspose.Tasks version
            Console.WriteLine("Product: " + BuildVersionInfo.Product);
            Console.WriteLine("File Version: " + BuildVersionInfo.FileVersion);
            Console.WriteLine("Assembly Version: " + BuildVersionInfo.AssemblyVersion);
            Console.WriteLine("Assembly Informational Version: " + BuildVersionInfo.AssemblyInformationalVersion);

            // ExEnd
        }
    }
}
```
