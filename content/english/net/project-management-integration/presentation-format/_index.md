---
title: Formatting Project Presentation in Aspose.Tasks
linktitle: Formatting Project Presentation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: 
type: docs
weight: 10
url: /net/project-management-integration/presentation-format/
---

## Complete Source Code
```csharp
namespace Aspose.Tasks.Examples.CSharp
{
    using NUnit.Framework;
    using Saving;
    using Visualization;

    [TestFixture]
    public class ExPresentationFormat : ApiExampleBase
    {
        [Test]
        public void RenderResourceSheetView()
        {
            // ExStart:RenderResourceSheetView
            // ExFor: PresentationFormat
            // ExSummary: Shows how to render resource sheet view.
            var project = new Project(DataDir + "ResourceSheetView.mpp");

            SaveOptions options = new PdfSaveOptions();

            // Set the Presentation Format to Resource Sheet
            options.PresentationFormat = PresentationFormat.ResourceSheet;
            project.Save(OutDir + "ResourceSheetView_out.pdf", options);

            // ExEnd:RenderResourceSheetView
        }
    }
}
```
