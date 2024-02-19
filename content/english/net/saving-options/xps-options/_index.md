---
title: XPS Options for Aspose.Tasks
linktitle: XPS Options for Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 21
url: /net/saving-options/xps-options/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp.SavingOptions
{
    using NUnit.Framework;
    using Saving;

    [TestFixture]
    public class ExXpsOptions : ApiExampleBase
    {
        [Test]
        public void WorkWithXpsOptions()
        {
            // ExStart:WorkWithXpsOptions
            // ExFor: XpsOptions
            // ExFor: XpsOptions.#ctor
            // ExFor: XpsOptions.RenderMetafileAsBitmap
            // ExSummary: Shows how to save project as XPS file.
            var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

            // create XPS save options and tune the parameters
            var options = new XpsOptions
            {
                RenderMetafileAsBitmap = true
            };

            project.Save(OutDir + "UseSvgOptions_out.xps", options);

            // ExEnd:WorkWithXpsOptions
        }
    }
}
```
